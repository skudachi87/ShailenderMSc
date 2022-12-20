1) A program that can create new crime case registration, and all the details of the complainant will be saved in the “public” table of the SQL database ( sqllite module being used)
2) When the same complainant comes back to check the case details/status, MFA is used through OTP ( pyotp library being used)
3)  Police staff account creation, OTP based authentication, search for existing cases, validates them, and save all of the data to file in an encrypted format, including sensitive information which are BSN and Password in the attached program. All the police user details are being saved in the “private” table of the sql database to keep the external and internal database segregated.


2) The following security ideas have been incorporated into the program during construction:


In order to restrict the length of the user name/password.
The user is REQUIRED to enter the secure password in accordance with the standards implemented.
Before the information is written to the SQL database table, sensitive fields like BSN and Passwords have had encryption turned on for them.


3) Following Modules have been used in the program:
*****Re, datetime, base64 and password_validator*****


-Module "RE" used for name validation etc.
-Module "base64" is used for encryption/decryption of sensitive user information like BSN /Password etc.
 
4) Following functions have been used during the program for different purposes.


===================================
def Crime_add_Function():
===================================
This is the starting point of the program.
This function is used to create a new user / crime. User is required to enter the required details like Name, Password, Date of Birth, BSN, address etc.for user registration.
There are validation checks being used for every element entered.




===================================
def passwordvalidate1(password):
===================================
Function is used to validate the password user inputs to ensure it is meeting the security standards defined in the program.




===================================
def birthvalidate(date_text):
===================================
Function is used to validate the format of the DOB entered vs the format defined in the program. There will be a continuous loop unless the format entered is correct.


===================================
def checkBSN(BSN):
===================================
Function is used to validate the format of the BSN entered vs the format defined in the program. There will be a continuous loop unless the format entered is correct.




===================================
def Crime_search_Function():
===================================


This function is used to fetch the case details.
As it will be used by the Police staff, the personal details like BSN etc. are shown as ENCRYPTED keeping the security practices in place.


===================================
def Crime_update_Function():
===================================


This function is being used ONLY by police personnel to update the case details.




===================================
def Police_Add_Function(): 
===================================


Function used to add the new police staff, but in a separate table called “private” of sql database called “securerepo.db”




===================================
def PoliceValidatefunction():
===================================
Function is used to validate the police staff with OTP based MFA


-----------------------------
Process to Use the program:
----------------------------
-Run the program
-If you are a new user, enter the required fields for new registration. 
-If you are a police staff member and want to update the case, you would like to see if the case already exists and this is where the SEARCH function is used.
-All of that case information can be retrieved and double-checked with the user before the registration.




---------------------------------------------------------------------------------------------------
## Difference between the initial design and the implemented system ## 
---------------------------------------------------------------------------------------------------


Improving cybersecurity was the goal of the NCSC of The Netherlands (Government of The Netherlands, n.d.) To achieve the wanted results, the Complaint System was designed to register complaints from victims and store them in a database after encryption, where the data can be later decrypted and accessed by the police to resolve the issues and to keep track of crime patterns in order to reduce crimes and make The Netherland more secure. 
 
The implementation of the system has followed the initial design with different classes for the victim, police, and complaint. However, the crime class was the same as the complaint class as complaints registered for crimes, in addition to that, implementing a class for crimes that would include the same details of the complaint class would cause redundancy.  Moreover, the initial design contained a criminal class which was not implemented due to time limitation. The criminal class should be implemented with more details which would help the police categorize crimes and criminals to be able to keep track of crimes and criminal files in order to prevent such cyber crimes from being repeated. Such a system needs more details and time to create a system that efficiently takes a different type of complaints and saves them to different types of crime cases to be easily accessed by the police. In order to prevent unauthorized access the system has two separate functions for the victim -regular user- and the police which would allow the police to have access to all the registered complaints and change the status where needed. The initial design included a department as well which was not implemented due to time limitation. Furthermore, as the data in the system are highly sensitive data the implementation followed the initial design and encrypted all data input before sorting them to the database and decrypted them when fetched after authorization. Moreover, OTP was implemented to ensure user identity and eliminate the risk of compromising data by unauthorized access which was introduced in the initial design as well. To clarify, the design decisions were all implemented in order to ensure the implemented system is secured and eliminate the risk of cyber-attacks. Moreover, the vulnerabilities discussed in the initial design were looked at as well and prevented through implementing the previously mentioned countermeasures which are implementing MFA as well as the implementation of encryption and decryption algorithms. In addition to that, input validation algorithms were applied to ensure that the received input follows the required format, which consequently, will help reduce error margin as well as increasing security. 
 
As the proposed design took into account the security standards that needed to be followed such as the GDPR, a high level of security is required for such sensitive data to be compliant with the GDPR which consequently, required another level of authentication before accessing victims data. To illustrate the point, if an attacker was able to get on hold with the credentials of a police user the OTP will only be received by the police which will prevent the attacker from accessing the system.  
 
To sum up, a lot of research, discussion and thought was put in the proposed design decisions to help improve the Netherlands cyber security. Consequently, the implementation followed about 75 percent of the initial design to ensure achieving the wanted secure environment as well as helping significantly in securing the Northlands through preventing future cyber attacks with the usage of the implemented system. 






## References ## 
Government of The Netherlands (n.d.) Fighting Cybercrim in the Netherlands. Available from: https://www.government.nl/topics/cybercrime/fighting-cybercrime-in-the-netherlands [Accessed 2 Dec 2022].