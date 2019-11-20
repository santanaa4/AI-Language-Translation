# AI-Language-Translation
This Program uses Node-Red flow and a chatbot 





Got Translate Will Travel
Translation Bots
Translation bots are similar to AI virtual assistants that specialize in language translation. They can interact with a user textually or verbally. They are usually comparable to messenger services, that is, you have to communicate with them through voice or text chat to have certain phrases or words translated to the language you want. It’s like exchanging messages with someone through chat or by talking to them to ask for a translation.
The “bot” in this phrase merely infers automation. It means that you no longer have to interact with a human attendant to use a certain translation service. They employ customer support bots to dispose of minor inquiries and concerns quickly and efficiently. Instead of inundating a human customer service representative with all of the incoming questions and complaints from customers, bots are deployed to handle simple questions and issues.
Translation bots are like messenger services. They appear as chat windows with which you can interact through voice or send a text/chat message and wait for a response. Usually, the bot is the first to “talk.” You get a greeting followed by a question on what you need.
Since translation bots are powered by artificial intelligence, the experience of using them is comparable to conversing with a real person. It’s unlike what you get when you contact (by phone) the automated system of phone companies, wherein you are asked to press certain numbers to be directed to the channel that can provide the answer you are looking for.
With AI-powered translation bots, the conversation does not have to follow a certain format or sequence. For example, if you want to have a phrase translated to French, the process will not be something like this: (1) the bot greets you, (2) asks you a question, (3) directs you to choose a keyword for the language you need, and (4) asks you to enter the word, phrase, or sentence you want to be translated. Instead, you can naturally chat with the bot to request for the translation you want. For example, after the bot greets you, you can just say “Please translate ‘hello’ to French.”
Translation bots are not complete translation services or platforms themselves. They are more of an interactive interface for a translation service. In this lab you will use the AI powered Translation Service from IBM Cloud to power up your bot.







Section 1.	Use Node-RED and Telegram to create a chatbot translator
This lab is originally written by Meshaal Mohammad Alzohrah, an IBM Developer Advocate working from Riyad, Saudi Arabia. This workshop is also modified by Armen Pischdotchian to accommodate a number of language translation beyond the original document.
________________________________________
Tarkman is the name of the bot that you create. It is a Multilanguage translation service integrated with the Telegram application that you can use to make chatbot translations easier. The IBM Language Translator service can connect to other IBM services, and these services can be linked to the Telegram application using a Node-RED app. When you link the services, users can easily use the translation app by sending text or voice to your bot. In this tutorial, I walk you through the steps to create a Node-RED boilerplate that’s available on IBM Cloud and link Tarkman to a Telegram app as the user interface using Node-RED flows.
Learning objectives
After completing this project, you will understand how to:
•	Create a Node-RED flow
•	Create a Telegram bot
•	Create a translator dialog using Language Translator, Speech to Text, Text to Speech IBM services
•	Integrate Node-RED with Telegram as an interface for Tarkman
Prerequisites
To complete the project, you need the following artifacts:
•	Obtain an IBM Cloud account.
•	Provision the Language Translator service
•	Provision the Language Identification service
•	Provision the Speech to Text service
•	Provision the Text to Speech service
•	Provision the Node-RED starter app
•	Install Telegram app on your laptop; plus, optionally, on your mobile device from this link https://telegram.org/







Steps
1.1.1.	Creating a Telegram bot
After installing Telegram on a mobile device, search for “BotFather.”
 
After you find it, send a /newbot command and follow these instructions:
1.	Set a name.
2.	Set a username.
3.	Save the access token for future use.
 
Note: Make sure to create instances of all of the required services for this project before moving to the next steps.
1.1.2.	Create a Node-RED flow
To create and configure a Node-RED app:
1.	Go to your IBM Cloud account and click Catalog.
2.	Choose Starter Kits from the left menu.
3.	Select Node-RED Starter, as shown in the following figure.
4.	Complete the fields to create the app:
o	App name: Must be unique in the IBM Cloud domain.
o	Host name: Is filled out automatically based on the App name.
5.	Click Create.
 
6.	Wait for a few seconds until the application shows Running, then click Visit App URL.
 
7.	Enter a username and password, selecting the option to secure your profile so that only authorized users can access it.
 
8.	Click Go to your Node-RED flow editor.
 
1.1.3.	Configure the Telegram bot
This is a Node-RED editor and you need to add Telegram nodes. To do this:
1.	Select Manage palette from the upper right menu.
 
2.	From the Manage palette menu, click the Install tab then search for telegram.
3.	Install node-red-contrib-telegrambot and close the palette menu.
 
4.	Search for telegram nodes from the upper left filter section, then drag the Telegram receiver and Telegram sender nodes to the Flow.
 
5.	Double-click the Telegram receiver node and click the pencil icon for configuring your bot credentials.
 
6.	Complete the Bot-Name and Token fields according to the bot credentials that you created earlier.
 
7.	Click Update.
8.	Double-click the Telegram sender node, select the bot credentials that you created in the Telegram receiver node (example_bot in my case), and click Done.
 
Now you have configured the Telegram part on Node-RED. You can test it by connecting the Telegram receiver node to the Telegram sender node.
 
You can send a message to your bot on Telegram and it echoes the message you wrote. That’s because you forwarded the message payload directly to the Telegram sender.
 
1.1.4.	Connecting IBM services
Now that the bot interface is connected to Node-RED and ready to use, let’s start integrating all of the services with the Node-RED application.
1.	Go to the Node-RED application in IBM Cloud and click the Connections tab in the left menu. Click Create connection.
 
2.	Connect all of the required services.
 
3.	Restage the app to configure the new changes.
 
1.1.5.	Create the flow
1.	Copy the code from the Tarkman flow file and import it into the Node-RED clipboard.
2.	Configure all of these nodes: Speech to Text, Text to Speech, Language Translator, and Telegram.
3.	Your flow should look like the following figure. Click Deploy.
 
1.1.6.	Testing your application on Telegram
 

Congratulation, enjoy your translation bot.

