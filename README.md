# Automatic Barnacle

## Description
Automatic Barnacle is an **ethical hacking tool** designed for WiFi attacking, inspired by Deauther and EvilTwin. 
It allows you to discover passwords for WiFi networks using the 802.11 standard.

## Features
- Retrieve passwords of targeted WiFi networks using the 802.11 standard.
- Perform Deauthentication (Deauth) attacks to disconnect devices from the target network.
- Clone a targeted WiFi network using an Evil Twin attack.

## How to Upload the Program
1. Prepare an ESP8266 board (any version of ESP8266 is supported, but ESP32 is not).
2. Open **Arduino IDE** and follow these steps:
    - Go to `File` -> `Preferences` -> `Additional Board Manager URLs`.
    - Copy and paste the following link:
      ```
      https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json
      ```
3. Go to `Tools` -> `Board` -> `Board Manager`.
    - Search for `Deauther ESP8266 Board` and download it.
4. Copy the `Crispy-Fi.ino` file into the Arduino IDE.
5. Select the port connected to your ESP8266 board.
    - In the `Erase Flash` menu, select `All Flash Contents`.
6. Upload the sketch to your board.

## How to Use
1. Connect your device (PC, smartphone, etc.) to the AP named **"Hidden Network"** and enter the password **"deauther"**. This device called "control device".
2. Open your browser and type `192.168.4.1` in the search bar.
3. Scan for available APs (Access Points) using the tool and select **one** target AP.
4. Click the `Start Deauth` button to disconnect devices connected to the target AP.
5. Click the `Start Evil Twin` button to clone the target AP.
6. Wait until someone trying to reconnect to the target AP with correct password. If you wanna test does it works, you can follow this following step:
    - Use another device (not the control device) connected to the target AP.
    - Connect to the cloned AP (usually shown without a lock icon).
    - You will be redirected to a page prompting you to input the password for the target AP. Enter the correct password.
    - Wait a moment for the device to reconnect to the target AP normally.
    
7. Reconnect the control device to **"Hidden Network"** with the password **"deauther"**.
    - Open `192.168.4.1` in the browser.
    - You will see a message like:
      **"Successfully got password for: [AP Name] - [Password]"**.
    - Don't forget to stop deauthing by clicking `Stop Deauthing`.

## Disclaimer
Automatic Barnacle is developed strictly for **ethical purposes** such as testing the security of your own WiFi network. Unauthorized use on networks without permission is illegal and violates ethical standards. Use responsibly!
