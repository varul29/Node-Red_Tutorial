# Node-Red 

The open source JS foundation and IBM contribution made a visual tool for wiring the IOT hardware with APIs and different online Services. Also with many other different features, you can connect the IoT hardware solution with the various different web based application which quickly assembles the flow of service.

## Install Node-Red 

To start with Node-Red, Node.js, should be running in your Hardware platforms like:

Windows
Raspberry Pi
BeagleBone Black

Which uses the operating system Windows, Linux, Ubuntu can download the LTS(Long Term Support) version and check the Node.JS version

    node -v

To install the Node-Red easily, we can install the global module to add Node-Red in system path using the package manager commands in your windows(or you can install with Alternative method also) 

    npm install -g --unsafe-perm node-red

#### Note: To install it in Linux or Ubuntu OS, we will  use ‘sudo’ before the mentioned above command

After the installation run the let’s start the node red:

  - Open the command prompt in the operating system
  - Write node-red and enter it 



  - As in highlight area of the snapshot, the local server IP for hardware will be displayed e.g.127.x.x.1:1880



  - Copy the mentioned above IP and paste it in the web browser, click enter.



##  MQTT Broker

The Node-RED does not include an MQTT broker which helps to create the connection with the TCP/IP protocols especially used in OS. We need to install the MQTT broker (such as mosquitto, Cloud MQTT, HiveMQTT, Paho etc) in node-red. As in this project we have used MOSCA MQTT broker and To install the MQTT broker use the follows:

  - Click on the top right option corner.
  - Select Manage Palette



  - In User Settings page click Install



  - Search node-red-contrib-mqtt-broker
  - Click on Install Button


## Node-Red Dashboard

This Node-Red provides the different set of nodes for dashboard representation to their users. To install the dashboard:

Use Node.JS command in command prompt or NodeJS command shell and then restart your node red

		npm i node-red-dashboard

If you want to install the dashboard using Manage Pallete then:

  - Click on the top right option corner.
  - Select Manage Palette



  - In User Settings page click Install
  - Search node-red-dashboard



  - Click on Install Button

After the Installation in the main screen of Node-Red on the left side option will be able to select the dashboard option. Using mentioned below image you can drag whatever node you want to use in the flow.



Note: The mentioned above Image is just the example of how to drag the nodes to flow. We will be discussing nodes in next topics


# Create Node-Red Flow
 
The Node-Red service is built on Node.JS and using version 0.14 MQTT nodes configured with TLS connections which we are using to send the Temperature sensor data to Node-Red platform.

  Drag the following Nodes

  MQTT node from Output node options. 

  - We will drag or copy and paste 3 MQTT node and will give a different unique name to their topics.
  - Double click on MQTT node
  - In, Edit MQTT in node setting, Click on the edit button mention on right side Server textbox.

     
  - In Edit MQTT-Broker-Node, give a unique name to MQTT node.
  - Write a server name which which is earlier mentioned while coding the  ESP8266 in Arduino IDE

        #define mqtt_server "iot.eclipse.org”

  - Set the time session after which the MQTT server will receive the message from the sensor hardware.
  - Click Update button in Edit MQTT-Broker-Node



  - Set the topic name which is earlier mentioned in Arduino IDE code

        #define humidity_topic "humid"
        #define temperature_C "Ctemp"
        #define temperature_F "Ftemp"
 
  - Click Done Button, Edit MQTT in node setting

	
Note: 

  - The server name must not be similar to the web browser Ip. Otherwise, you will not be able to create the MQTT connection with your device.
  - The Topics must be written correctly which will also help to receive the data from Sensor and the similar topics we will be mentioning in ESP8266 code also.
  - Both mentioned above points are most important to create the connection between the sensor device and Node-Red.

 
  Debug node from Output node options to test the payload.

  - Similar to MQTT node here also, drag or copy and paste 3 Debug node and will set the default settings. 


  Gauge node from Dashboard node option

  - Like previous, For every MQTT node will use Gauge node.
  - Double Click on gauge nodes.
  - In Edit Gauge Node, Fill up your instruction which you want to display in the Dashboard with Every Gauge.
  - Click Done.


The Final node red output will be


Connect all the node as mentioned below in snapshot and then click on the deploy button on the top right corner

On the top right   select the dashboard option.  



Below the dashboard, you will select the dashboard screen button by clicking on which the screen will appear in which Dashboard gauge will be available.



## Output

We will be able to check the output display as mentioned in a snapshot below





## Limitations

In this application, the Node red service is responding only to a local server which is greatly running on the PC hardware for the secured local connection. 

## Future Enhancement 

- The OS-based Application based system has 225,000 repos with much different input and output node available.
- Using various Nodes we can also send the data to different IoT platforms or Online servers Like Firebase, Microsoft Azure, IBM Watson
- Using different API present with in the node red like JSON, HTTPS etc will help you to connect the service Directly with your mobile applications or online servers also.
- Not only Creating the local MQTT Server connection, but you can also create the connection with the online server by using various MQTT broker which is easy to install in node red like Mosquitto, HiveMQTT, CloudMQTT, Predix, and many others which uses the online storage database.
