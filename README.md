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

- Setup Resources in Azure
- Ensure Connectivity
- Install Active Directory
- Create an Admin and User Account in AD
- Join Client-1 to your domain
- Setup Remote Desktop for non-administrative users

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/82Xe6VD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create two virtual machines inside of Azure, one as the Domain Controller and the other as Client. Set Domain Controller's NIC Private IP Address to be static. After this is done ensure that both VM's are in the same Vnet.
</p>
<br />

<p>
<img src=https://i.imgur.com/jm5fe3B.png"" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To ensure connectivity login to Client-1 with remote desktop and ping DC-1's private IP address. Login to the Domain Controller and enable ICMPv4 in on the local windows Firewall, then check back at Client-1 to see the ping succeed.
</p>
<br />

<p>
<img src="https://i.imgur.com/qMfSTyN.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 and instll Active Directory Domain Services.
</p>
<br />


<p>
<img src="https://i.imgur.com/a1BYsXm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Active Directory Users and Computers (ADUC). create new Organizational Units called Employees and Admins. After that is done create a new employee and log back in.
</p>
<br />



<p>
<img src="https://i.imgur.com/7OIQe7u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Azure Portal, set Client-1's DNS settings to the DC's Private IP address.
</p>
<br />



<p>
<img src="https://i.imgur.com/dNWXBfV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Allow all "domain users" to access remote desktop.
</p>
<br />
