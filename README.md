<h1>GLPI LDAP Authentication</h1>

<h2>Overview</h2>
In this part of the project, I configured LDAP for centralized user authentication and management, ensuring a secure and streamlined approach to handling user access. This integration provided secure access control by centralizing authentication processes, allowing for efficient onboarding and offboarding of employees, and reducing the risk of unauthorized access.
<br />


<h2>Application Used</h2>

- <b>VMware Workstation 17 Pro</b>
- <b>Windows Server 2019</b>
- <b>Wampserver</b>
- <b>GLPI</b>


<h2>Lab walk-through:</h2>

<p align="left">
These are the users we currently have in Active Directory.<br/>
<img src="https://i.imgur.com/0srt5tI.png" height="60%" width="60%"/>
<img src="https://i.imgur.com/m4jxYgF.png" height="60%" width="60%"/>
<img src="https://i.imgur.com/HUbE7tm.png" height="60%" width="60%"/>
<br />
<br />
Create a user in the Users folder for authentication.<br/>
<img src="https://i.imgur.com/mSA0kcu.png" height="60%" width="60%"/>
<br />
<br />
Open Windows Defender Firewall and select Advanced Security.<br/>
Right click on Inbound Rules and select New Rule.<br/>
<img src="https://i.imgur.com/6070DHT.png" height="60%" width="60%"/>
<br />
<br />
Select Port as the Rule Type and click next, then enter 389, 636 in the “Specific local ports:” text box.<br/>
<img src="https://i.imgur.com/RPBCC4K.png" height="60%" width="60%"/>
<br />
<br />
Select “Allow the connection” on the Action page then click next.<br/>
Check all options in the profile page then click next.<br/>
Enter a name then click finish.<br/>
<img src="https://i.imgur.com/oJihcq5.png" height="60%" width="60%"/>
<br />
<br />
Open GLPI, select the Setup option, click on Authentication then select LDAP Directories.<br/>
<img src="https://i.imgur.com/LN4unZZ.png" height="60%" width="60%"/>
<br />
<br />
Click Add at the top, fill in the information then select Add at the bottom right.<br/>
<img src="https://i.imgur.com/9GcV40D.png" height="60%" width="60%"/>
<br />
<br />
Click on the newly created LDAP Directory, click the Test option then select Test.<br/>
<img src="https://i.imgur.com/QtvxUAJ.png" height="60%" width="60%"/>
<br />
<br />
Select the Administration option, click on Users then select LDAP Directories Link.<br/>
<img src="https://i.imgur.com/Nasprh4.png" height="60%" width="60%"/>
<br />
<br />
Select Import New Users, then click Search. This will display all the Active Directory users.<br/>
Click on the “Synchronization Field” check box to select all the users.<br/>
Click the Actions button, select Import and click submit.<br/>
<img src="https://i.imgur.com/3c3pfsp.png" height="60%" width="60%"/>
<br />
<br />
A notification will appear stating all the users have been added.<br/>
Click on the Administration option and select Users to see all users.<br/> 
<img src="https://i.imgur.com/2fsDdR2.png" height="60%" width="60%"/>
<br />
<br />
To synchronize changes made in Active Directory with GLPI.<br/>
Click on LDAP Directory Link then select “Synchronizing already imported users”.<br/>
<img src="https://i.imgur.com/yksmovz.png" height="60%" width="60%"/>
<br />
<br />
Click on the Search button. This will display all the users imported into GLPI.<br/>
Click on the “Synchronization Field” check box to select all the imported users.<br/>
Click the Actions button, select Synchronize and click submit.<br/>
<img src="https://i.imgur.com/s5i4XE1.png" height="60%" width="60%"/>
<br />
<br />
To display the users first name, click on the wrench icon, select First Name from the options then click Add.<br/>
<img src="https://i.imgur.com/OZbVdOJ.png" height="60%" width="60%"/>
<br />
<br />
To change the administrative permission of a user. We select the user first, then click on the Actions button and select Associate to a Profile.<br/>
<img src="https://i.imgur.com/E9CuS9K.png" height="60%" width="60%"/>
<br />
<br />
Choose the appropriate profile then click Add.<br/>
<img src="https://i.imgur.com/JfDp8Zh.png" height="60%" width="60%"/>
<br />
<br />
Open an incognito tab and log in as one of the users.<br/>
<img src="https://i.imgur.com/sbTDDTO.png" height="60%" width="60%"/>
<br />
<br />
Jane Brooks has a Self-Service profile. A Self-Service profile can only create tickets and check the statues of their tickets.<br/>
<img src="https://i.imgur.com/PjSVTzO.png" height="60%" width="60%"/>
<img src="https://i.imgur.com/e4GTqmI.png" height="60%" width="60%"/>
<img src="https://i.imgur.com/fLaZSzP.png" height="60%" width="60%"/>
<br />
<br />
Let's login in as John Smith because he has an Administrator profile. An Admin profile has a lot more access to GLPI.<br/>
<img src="https://i.imgur.com/wYr8wDb.png" height="60%" width="60%"/>
<br />
<br />
List of all the profiles.<br/>
<img src="https://i.imgur.com/cmrSA5U.png" height="60%" width="60%"/>
<br />
<br />
</p>
