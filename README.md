pyobd
=====

<pre>OBD-PiTFT: Display Car Diagnostics (OBD-II) Data On Adafruit's PiTFT Touchscreen Display For Raspberry Pi 

In this tutorial you will learn how to connect your Raspberry Pi to a Bluetooth OBD-II adapter and display realtime engine data on Adafruit's PiTFT touchscreen display.

Hardware Required:
1. Raspberry Pi
2. Adafruit PiTFT Touchscreen Display
3. Plugable USB Bluetooth 4.0 Low Energy Micro Adapter 
4. 2A Car Supply / Switch or Micro USB Car Charger
5. ELM327 Bluetooth Adapter or ELM327 USB Cable
6. Sweetbox Raspberry Pi Case (*optional)
7. Car Mount Holder (*optional)
8. Keyboard (*optional)

What is OBD-II?
OBD stands for On-Board Diagnostics, and this standard connector has been mandated in the US since 1996. Now you can think of OBD-II as an on-board computer system that is responsible for monitoring your vehicle’s engine, transmission, and emissions control components. 

Vehicles that comply with the OBD-II standards will have a data connector within about 2 feet of the steering wheel. The OBD connector is officially called a SAE J1962 Diagnostic Connector, but is also known by DLC, OBD Port, or OBD connector. It has positions for 16 pins.

pyOBD?
pyOBD (aka pyOBD-II or pyOBD2) is an open source OBD-II (SAE-J1979) compliant scantool software written entirely in Python. It is designed to interface with low-cost ELM 32x OBD-II diagnostic interfaces such as ELM-USB. It will basically allow you to talk to your car's ECU, display fault codes, display measured values, read status tests, etc.

I took a fork of pyOBD’s software from their GitHub repository, https://github.com/peterh/pyobd, and used this as the basis for my program.

The program will connect through the OBD-II interface, display the gauges available dependent on the particular vehicle and display realtime engine data on Adafruit's PiTFT touchscreen display in an interactive GUI.

Software Installation
In order to add support for the 2.8" TFT and touchscreen, we'll need to install a new Linux Kernel. Head over to Adafruit and follow their Software Installation, then come on back!

We'll be doing this from a console cable connection, but you can just as easily do it from the direct HDMI/TV console or by SSH'ing in. Whatever gets you to a shell will work!

Note: For the following command line instructions, do not type the '#', that is only to indicate that it is a command to enter. 

Before proceeding, run:
#  sudo apt-get update
#  sudo apt-get upgrade
#  sudo apt-get autoremove
#  sudo reboot

Install these components using the command:
#  sudo apt-get install python-serial
#  sudo apt-get install bluetooth bluez-utils blueman
#  sudo apt-get install python-wxgtk2.8 python-wxtools wx2.8-i18n libwxgtk2.8-dev
#  sudo apt-get install git-core
#  sudo reboot 

Next, download the OBD-Pi Software direct from GitHub.
(https://github.com/sakurusurya2000/pyobd.git)

Or using the command:
#  cd ~
#  git clone https://github.com/sakurusurya2000/pyobd.git

Vehicle Installation
The vehicle installation is quite simple.

1. Insert the USB Bluetooth dongle into the Raspberry Pi along with the SD card.

2. Connect your PiTFT display to the Raspberry Pi.

3. Insert the OBD-II Bluetooth adapter into the SAE J196216 (OBD Port) connector.

4. Install your 2A Car Supply / Switch or Micro USB Car Charger.

5. Finally, turn your key to the ON position.

6. Enter your login credentials and run:
#  startx

7. Launch BlueZ, the Bluetooth stack for Linux. Pair + Trust your ELM327 Bluetooth Adapter and Connect To: SPP Dev. You should see the Notification "Serial port connected to /dev/rfcomm0"

Note: Click the Bluetooth icon, bottom right (Desktop) to configure your device. Right click on your Bluetooth device to bring up Connect To: SPP Dev.

8. Open up Terminal and run:
#  cd pyobd
#  sudo su
#  python obd_gui.py

Note: Run, # python obd_gui_square.py to use the rounded rectangle gauge.
To exit the program just press Control and C or Alt and Esc.
Tap the display to cycle through the gauges!

9. To record the data sensed from the sensors:
#  cd pyobd
#  python obd_recorder.py

Enjoy and drive safe!</pre>
