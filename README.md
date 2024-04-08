# EaglerCraftX Server Info & Setup

ATTENTION MOJANG/MICROSOFT EMPLOYEES: THIS REPOSITORY DOES NOT CONTAIN YOUR INTELLECTUAL PROPERTY FILING A FALSE DMCA IS ILLEGAL AND IMMORAL
<br>
<br>
Eaglercraft uses the decompiled source of the official version of Minecraft 1.8 and 1.12 from Mojang decompiled by MCP http://www.modcoderpack.com/ and compiled to Javascript using TeaVM https://teavm.org/. Therefore it can join any Minecraft 1.12 or 1.8 server, as it is really running (a modified version of) Minecraft 1.12 in the browser. However, due to CORS restrictions it must use a modified version of Bungeecord which proxies the browser's Websocket connection to the pure TCP connection used by Minecraft. For graphics, a custom compatibility layer created by me allows the fixed function OpenGL 1.3 based rendering engine mojang uses to operate through an HTML5 WebGL canvas with minimal changes to the source.

## Introduction
Eaglercraft is an open-source web-based minecraft copy. Today I will teach you how to setup a public server with plugins for free! Please note that the project is an old one, and is not being actively maintained anymore. Because of this, you should consider hosting the server on a system outside of your network. Some examples include OCI and Github Codespaces. Now, lets begin! 

## System Setup (Linux)
For this tutorial, we will be using Ubuntu 22.04 LTS. First of all, java is required to run bungeecord and the server file. To do this, we will need to run the following commands:
<br>
<br>
`sudo apt install default-jdk && sudo apt install default-jre -y`
<br>
<br>
## Installing The Server
Now, we need to clone the server repo using `git`. Please run the following command:
<br>
<br>
`git clone https://github.com/CaenJones/EaglercraftX-Server`
<br>
<br>
Now, open 2 terminal tabs in the new server directory and paste in the following snipits (updated for logj4):
<br>
<br>
first tab: `cd server && java -Dlog4j2.formatMsgNoLookups=true -Xms4G -Xmx4G -jar server.jar`
<br>
<br>
You may need to edit the EULA.txt and change a value to `true` before running the next command:
<br>
<br>
second tab: `cd bungee && java -Dlog4j2.formatMsgNoLookups=true -Xms4G -Xmx4G -jar bungee.jar`
<br>
<br>
## Making Server Public
Great! Now, you need to forward ports  `8081` and `25565` and navigate to your servers public ip [server-ip:8081]. The server welcome page should be displayed. Congrats on running your own server!

## Installing Plugins
In order to install plugins, navigate to `server > plugins`. You will need to clone the initial [plugin-name.jar] file as well as creating a separate directory in the plugins folder in order to store the additional data. Then just restart the server and the plugin should be running!
