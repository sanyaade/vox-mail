#Web Site
http://voxmail.org
http://rocketsource.org

#How to Use Voxmail

Step 1: Verify everything is working correctly by making a test call
1a. Open the SIP phone by clicking on Start > All Programs > Voxeo > SIP Phone.
1b. Dial the number sip:voxmail@127.0.0.1
1c. When prompted to enter a Work Phone and PIN enter 8135551111 and 1234
1d. Follow the prompts to set up your account

Step 2: Checking Voice Mail Via the Web
2a. Open a web browser and go to the following URL: http://127.0.0.1:9991/vox-mail/
2b. Enter 8135551111 for the phone and 1234 for pin.
2c. You should now see all the messages for "Jamie Foxx". Clicking on the "Voicemail Message" link will play the message.
2d. Clicking on any of the "Move to" links will move the message to the specified folder

To change the pin or configure IMAP username and password, select the "change pin" link from the web interface.


#Config info:

The default context for the project is /vox-mail.  If you deploy this in the Prophecy server, it is configured for a deployment in the location: C:\Program Files\Voxeo\webapps\vox-mail.  If you have installed Prohpecy in a different location, see the config information below on settings to change.

1. Path to hsql db is in WEB-INF/classes/voxmail.properties

2. smtp host and imap host is also in the voxmail.properties file.  
Modify this based on your configuration.  You can use either the local filesystem for messages or imap.  To use imap, set the property useImap=true and enter the imap host.

3. if you receive errors on startup regarding hsql locks, verify another process isn't already running and accessing this db. You can delete the .lck file if you are having problems.

4. This application uses an hsql db located in the WEB-INF/db directory.  New accounts can be provisioned using the /voxmail/provision.do action with parameters: contactId, firstName, lastName, phoneNumber, and email.  The default login is phoneNumber and the default pin is 8135551111 and 1234.


#Voicemail Guest Access

1. The easiest way to leave a message is to call into the Vox-Attendant application and for a 
contact who has voicemail enabled, select the Voicemail option.  This will automatically link to the Vox-mail application as a guest.

2. To login as a user, press * at the leave message and enter the 4 digit pin.  
The default pin at provisioning time is 1234 for all accounts.

#Issues
Voxmail only supports 10 digit office phone numbers coming from the autoattendant right now (for login purposes).  If you are using a sip address for the work phone, then the voicemail account will not provision correctly nor will you be able to leave a message or login on voicemail.






