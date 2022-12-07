<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Create Two VMs 
- Step 2: Make sure both VMs are online
- Step 3: Allow permissions on DC-1's Firewall
- Step 4: Test communication between VMs
- Step 5: Set up Domain
- Step 6: Created Organzational Units (OU) Active Directory 
- Step 7: Joined Client-1 to created domain
- Step 8: Setup Remote Desktop for non-admin users on Client-1
- Step 9: Created additional users via Powershell ISE on Client-1
- Step 10: Logged into a new user account on Client-1 VM

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/EVJ3emt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step:1 Created Virtual Machine #1 as the Domain Controller setting it up as a Windows Server 2022 titled "DC-1". Secondly, created a users' VM titled "Client-1" regualar Windows 10.
</p>
<br />

<p>
<img src="https://i.imgur.com/yFq1CCq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step:2 Set Domain Controller's NIC private IP Address to static & ensured both VMs are in the same Vnet. This will ensure that both VMs can communicate and connect with eachother later in the lab.
</p>
<br />

<p>
<img src="https://i.imgur.com/PhAxO44.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3: Remote Desktop into VM#1 DC-1 to allow IPV4 permissions on DC-1's Firewall. This will open the firewall for connectivity after this VM is converted into a domain. 
</p>
<br />

<p>
<img src="https://i.imgur.com/haofkT5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 4: Ensure communication between both VMs via perpetual ping using cmd:ping -t (Ip Address).
</p>
<br />

<p>
<img src="https://i.imgur.com/xgMuhJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 5: Installed Active Directory on DC-1. Set up DC-1 as a new domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/SVRL4NQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 6: Remote Desktop into DC-1 to create two Organzational Units (OU) titled "Admins" and another titled "Employees" within Active Directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/ShU8C26.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Urmjpmq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 7: Changed Client-1's DNS settings in Azure to match the same private IP Address as DC-1. Next, I added client one to the same domain as DC-1. Lastly, I created a new OU named "_clients".
</p>
<br />

<p>
<img src="https://i.imgur.com/ekCSO1N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 8: Went into Remote Desktop in the system settings to allow "domain users" access for all non-admin users on Client-1 VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/XnDeUOB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Uploaded a script with 100 additional users via Powershell ISE to Client-1. This created 100 new users with random names. This was done to simulate employees in the company.
</p>
<br />

<p>
<img src="https://i.imgur.com/4wPUapk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Logged into a new user account (one generated from the script) on Client-1 VM. The login attempt with the user's name & generic password created was successful. This is the conclusion of the lab, thank you for viewing!
</p>
<br />
