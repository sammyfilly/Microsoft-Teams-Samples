---
page_type: sample
description: This is a sample application which demonstrates how to use CART link to send live captions in the meeting tabs.
products:
- office-teams
- office
- office-365
languages:
- nodejs
- javascript
extensions:
 contentType: samples
 createdDate: "06/24/2022 12:00:00 AM"
urlFragment: officedev-microsoft-teams-samples-meetings-live-caption-nodejs
---

# Meeting side panel application uses CART link to send caption in live meeting.

This is a sample meeting side panel application which demonstrates how to enable live caption in the meeting and using the CART link how to send caption in live meeting. Meeting side panel application uses CART link to send caption in live meeting.

## Enable CART Captions
Once the meeting is scheduled. Follow this doc to enable [CART Captions](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47).
Copy the CART link it will used while configuring tab for meeting.

## Included Features
* Meeting Chat 
* Meeting Details
* Meeting SidePanel
* Cart API

## Key features

![Key Features](Images/MeetingCaption.gif)

## Prerequisites

- Microsoft Teams is installed and you have an account (not a guest account)
-  [NodeJS](https://nodejs.org/en/)
-  [dev tunnel](https://learn.microsoft.com/en-us/azure/developer/dev-tunnels/get-started?tabs=windows) or [ngrok](https://ngrok.com/download) latest version or equivalent tunneling solution
-  [M365 developer account](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant) or access to a Teams account with the appropriate permissions to install an app.
- [Teams Toolkit for VS Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension) or [TeamsFx CLI](https://learn.microsoft.com/microsoftteams/platform/toolkit/teamsfx-cli?pivots=version-one)

## Run the app (Using Teams Toolkit for Visual Studio Code)

The simplest way to run this sample in Teams is to use Teams Toolkit for Visual Studio Code.

1. Ensure you have downloaded and installed [Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
1. Install the [Teams Toolkit extension](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
1. Select **File > Open Folder** in VS Code and choose this samples directory from the repo
1. Using the extension, sign in with your Microsoft 365 account where you have permissions to upload custom apps
1. Select **Debug > Start Debugging** or **F5** to run the app in a Teams web client.
1. In the browser that launches, select the **Add** button to install the app to Teams.

## To try this sample

> Note these instructions are for running the sample on your local machine, the tunnelling solution is required because
> the Teams service needs to call the tab.

### 1. Clone and start your sample sample
1) Clone the repository

    ```bash
    git clone https://github.com/OfficeDev/Microsoft-Teams-Samples.git
    ```

2) In a terminal, navigate to `samples/meetings-live-caption/nodejs`

3) Install modules

    ```bash
    npm install
    ```
4) Run ngrok - point to port 3978

   ```bash
   ngrok http 3978 --host-header="localhost:3978"
   ```  

   Alternatively, you can also use the `dev tunnels`. Please follow [Create and host a dev tunnel](https://learn.microsoft.com/en-us/azure/developer/dev-tunnels/get-started?tabs=windows) and host the tunnel with anonymous user access command as shown below:

   ```bash
   devtunnel host -p 3978 --allow-anonymous
   ```

5) Run your app

    ```bash
    npm start
    ```
### 2. Manually update the manifest.json
1. Manually update the manifest.json
    - Edit the `manifest.json` contained in the  `appPackage/` folder to replace the `<<AppId>>` with any guid value and `<<APP-DOMAIN>>` with with base Url domain. E.g. if you are using ngrok it would be `1234.ngrok.com` and if you are using dev tunnels then your domain will be `12345.devtunnels.ms`.
    - Zip up the contents of the `appPackage/` folder to create a `manifest.zip`
    - Upload the `manifest.zip` to Teams (in the left-bottom *Apps* view, click "Manage your apps -> Upload an app -> Upload a custom app")

**NOTE: If you are unable to send caption, try configuring tab again.**

### Features of the sample.
1. Schedule the meeting and add Meeting Caption Tab in that particular scheduled meeting.
![Add Tab](Images/AddMeetingCaption.png)
2. Once meeting started, turn on live caption.
![Start live caption](Images/TurnOnLiveCaption.png)
3. Once the live caption has started, you can use the app to send live caption.
![Send live caption](Images/MeetingCaptionSidePanel.png)
4. After clicking on `Submit` button, you will see the caption in the meeting.
![Caption in meeting](Images/LiveCaption.png)



<img src="https://pnptelemetry.azurewebsites.net/microsoft-teams-samples/samples/meetings-live-caption-nodejs" />