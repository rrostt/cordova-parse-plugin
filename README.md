cordova-parse-plugin
====================

Cordova Plugin for Parse
Requires Cordova v4.0.0 or above.

Adapted by @rrostt from https://github.com/FrostyElk/cordova-parse-plugin

My edits help with opening app from a notification. Original version did not work for me so I changed it.

# Usage

This will add the necessary code for Android and iOS to receive notifications as they arrive when sent through Parse. To set it up, you must run the following from your ionic app, after ionicPlatform ready:

      ParsePlugin.initialize(appId, clientKey, function() {
      });
      
For Android make sure you have set the ParsePluginMainApplication as the Application class in your Manifest. This is done by setting the android:name attribute of the application tag:

    android:name="se.frostyelk.cordova.parse.plugin.ParsePluginMainApplication"
    
If not, then Parse may not be initialized when a notification arrives and the app will crash. If the app repeatedly crashes on incoming notifications, this is probably why.

To subscribe to a channel, use:

    ParsePlugin.subscribe('SampleChannel', function() {});
          

