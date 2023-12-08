**Name:** Rahul Raj
**Roll No:** CB.EN.P2CYS22011

## THICK CLIENT

  -  A thick client, also known as a fat client or rich client, is a type of application architecture that involves a significant amount of processing on the client side. Unlike thin clients, which rely heavily on server-side processing, thick clients perform a substantial portion of the application logic and data processing on the user's device.

### A)  Identify the Application architecture, languages, and frameworks used. ? 

  -  Common Architectures of Thick Client applications are **Two-Tier** and **Three-Tier**,
  -  **Two-Tier architecture**:   In two-tier architecture, the thick client application implements client-to-server communication. The application is installed on the client computer and, in order to work, will need to communicate with a database server. For example, imagine an HR application that was installed on the client computer and, in order to retrieve the employees’ information, communicates directly with the HR database server.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/2ed99b3e-5fda-4df4-8b6a-def664527a49)
  
  -  **Three-Tier architecture**:  In three-tier architecture, the client communicates with an application server, which in turn talks to the database in a manner similar to a regular web application. The most common communication method in these applications may be carried out using HTTP/HTTPS. Three-tier architecture has a security advantage over two-tier architecture, because it prevents the end-user from communicating directly with the database server.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/80fd4a9e-671a-4f24-8b5d-ee5295cc6785)

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/cc4f56e0-ed5b-40f3-9418-936293b88596)

### B)	Decompile and try to retrieve the source code of the application. Also, check if any hardcoded sensitive information is found.? 

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/728a7695-f7db-44a7-b094-d5c19eac1596)

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/bb386ecd-d74f-4037-8709-49d4a11fc44d)

  -  Now go to the Admin.cs file. We will see the code that the application is using to upload the data through FTP.

  ![2023-11-23_14-22](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/c0be36a1-357b-4e6f-bc83-e21a0bcba4b2)
  -  It contains the IP address of the FTP server as well as the credentials.

### C)	 Sniff the traffic between client and server. Identify which protocol is being used for communication.?

  - We used the Wireshark tool to sniff the network between the client and server in the DVTA application

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/8edb2d1f-980f-4ffe-9954-f9facbbd13e0)

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/312a8e4c-9c3a-4b4b-b1a3-01191a570b7e)

### D)	Identify if unencrypted communication is happening between client and server.?

  -  I got unencrypted  communication which contain the username and password of the client in application using wireshark at the transport layer.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/c653d113-1517-4052-a6fc-5b20e18591ab)

### E)  Capture and analyse the communication using proxy tools (eg: Burpsuite, Echo mirage). 

  -  Captured client and server communication in proxy tool Echo mirage, which contains sensitive informations such as username, password and email-id.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/21e9893a-0c34-4863-a83d-f82c9bf06bd4)

### F) Analyse the application workflow and observe which all files/folders are being used by the application using Process Monitor.

  -  By analysing the application workflow, we found that these files and folders were used.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/c5401bcd-7ee8-4c76-bae5-23edbd997253)

### G)  Exploit DLL Hijacking vulnerability (You can use a simple legitimate “Hello World” printing dll –

  - We first opened DVTA application in process monitor
  - Then checked for the dll file which the application called but did not get it. So we took a calculator application dll and renamed it with the file name the application wanted.

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/c77c70a7-561c-4a4b-9db9-0eeb199610a3)

  ![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/41655ed0-c610-4604-9c4b-cf9911be68ec)

### H)  Check for sensitive information in the configuration files of the thick client application? 

![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/72f0ba09-8441-4e11-867d-2821ee67a9dc)

###  I)  Identify sensitive information found in memory? 

![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/a62f7fd1-50f7-4f99-8b1a-e5b4eaf6a62c)

![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/a84589db-06b1-40b4-b49f-367cb97376e9)

![image](https://github.com/rahulr98/Secure-Systems-Engineering/assets/116432525/8be8f9eb-f847-4394-a224-1027e77dada5)
