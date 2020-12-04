# Twilio_SMS_Forwarding

## Features

* Public-facing contact number

* Messages can be forwarded to private numbers without exposing their contact info

* Forwarding can be changed depending on the need

* Photos can be sent and brought onto a local machine

## Components

Twilio
* Account + Number
* Studio Flow script

Google Scripts
* Phonebook
* Email handler

.NET executable

## Initial Setup

1. Decide on a passcode for Twilio to communicate with Google (NOT your Twilio or Google password, SID, or Auth Token... Something unique and alphanumeric)
1. Create a Google account (if you don't have one already)
   1. Create two scripts in [Google Scripts](https://script.google.com/home/my)
       1. [GoogleScriptEMAIL](https://github.com/td0g/Twilio_SMS_Forwarding/blob/main/googleScriptEMAIL)
       1. [GoogleScriptPHONEBOOK](https://github.com/td0g/Twilio_SMS_Forwarding/blob/main/googleScriptPHONEBOOK)
       1. Edit the passcode in each script to match your Twilio/Google passcode (default is 'abcd')
   1. Publish the scripts (Anyone can use, even anonymous)
   1. Copy the script URLs for the Twilio HTTP Requests
1. Create a [Twilio account](https://www.twilio.com/) (PAID, not trial), purchase a number
   1. Create a new [Twilio Studio](https://www.twilio.com/console/studio) script (name it whatever you like), select 'Import from JSON', and paste the text from the [StudioFlowJSON file](https://github.com/td0g/Twilio_SMS_Forwarding/raw/main/StudioFlowJSON)
   1.  Go to the script, select Contact Info, and change the passcode variable to match your Twilio/Google passcode (default is 'abcd')
   1. Go to you [phone numbers](https://www.twilio.com/console/phone-numbers/incoming), set 'A Message Comes In' to the Twilio Flow script you created
1. Download the TwilioLocal.exe file (setup... TODO)
   1. The [source code](https://github.com/td0g/Twilio_SMS_Forwarding/blob/main/TwilioLocalSOURCE) can be compiled in Visual Studio (.NET Framework C# Console App)

## Use

1. Change the forwarding phone number and email address in the [Twilio Flow](https://www.twilio.com/console/studio/dashboard) script. Click on the script name, click **Contact_Info** and edit the **emailAddress** and **phNumber** variables (the bottom field).  Click Save on the right, then Publish at the top.
1.  To collect messages and photos locally, simply run the TwilioLocal.exe file.  It will create two .html files, one containing images and the other containing the text messages.

## ToDo

* TwilioLocal.exe store SID and Auth Token somewhere sensible
* Find easier way to change the forwarding email address and phone number
* TwilioLocal.exe general improvements... The .html files are unfortunate and clunky

## Changelog

2020-12-03 1.0 Initial Commit
