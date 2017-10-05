# Twilio Connector

A simple connector to the [TWILIO API](https://www.twilio.com/messaging "TWILIO API"). 

The twilio connector allows developers to send an sms to a mobile number from their scripts.

## Using the connector


### Configuring the connector
The /config file that ships with the connector contains default configuration. You can update it to match your own settings.

Create a config file with the below information for your twilio account and save it as config

```javascript
var twilio = {
    "accountSID": "<TWILIO_ACCOUNT_SID>",
    "authToken": "<TWILIO_ACCCOUNT_TOKEN>",
    "from": "<MOBILE_REGISTERED_IN_TWILIO_ACCOUNT>"
}

```
### Sending an sms
Require the necessary classes
```javascript
 var smsmodule = require("modules/twilio/smsclient");
 var config = require("config").twilio //previousely created config
```

Instantiate the module & send an sms
```javascript
 try {
          var smsClient = new smsmodule.TwilioSMS(config);
          return smsClient.send({"number":  "<TO_MOBILE_NUMBER>", "message": "<MESSAGE_CONTENT"});
} catch(exception){
          return exception;
}
```
