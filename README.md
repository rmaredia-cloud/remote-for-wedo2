WeDo 2.0 Web Remote Control
===========================

A modern, responsive, and configurable web-based remote control for the LEGO® Education WeDo 2.0 Smart Hub. This application allows users to control two independent motors with customizable speed and direction, all from a browser or a mobile app.

🚀 Live Access & Usage
----------------------

### 🌐 Desktop (Chrome / Edge / Bluefy)

This application uses the **Web Bluetooth API** to communicate directly with your hardware.

1.  Open the `wedo_remote.html` file in a supported browser:

    -   **Google Chrome** (Desktop)

    -   **Microsoft Edge** (Desktop)

    -   **Bluefy / WebBLE** (iOS/iPadOS)

2.  Ensure Bluetooth is enabled on your device.

3.  Click **"Connect WeDo Hub"**.

4.  Select your hub (usually named `LPF2` or `WeDo Hub`) from the browser's device picker.

### 📱 Mobile (Capacitor / Android / iOS)

The code is designed to be easily packaged into a native app.

1.  Wrap the HTML code in a [Capacitor](https://capacitorjs.com/ "null") project.

2.  Ensure you have the necessary Bluetooth permissions in your `AndroidManifest.xml` or `Info.plist`.

3.  Build and deploy to your Android or iOS device to use it as a standalone remote.

✨ Features
----------

-   **Dual Motor Control:** Independent controls for Port 1 (Motor A) and Port 2 (Motor B).

-   **Momentary Action:** "Hold-to-run" buttons mimic a real physical remote control.

-   **Speed Precision:** Adjust the power level (0-100%) for each motor individually using sliders.

-   **Port Detection:** Integrated visual status dots that turn green when the Hub detects a motor is physically plugged into a port.

-   **Real-time Logging:** A built-in debug console to monitor Bluetooth traffic (TX/RX) and system events.

-   **LEGO® Inspired Design:** Clean, dark-mode UI built with Tailwind CSS for high visibility.

🛠 Technical Details
--------------------

### Bluetooth UUIDs

The app communicates using the following LEGO® Power Functions 2.0 specifications:

-   **Service:** `00001523-1212-efde-1523-785feabcd123`

-   **Motor I/O Characteristic:** `00001524-1212-efde-1523-785feabcd123`

-   **Device Info Characteristic:** `00001527-1212-efde-1523-785feabcd123`

### Command Protocol

Motor commands are sent as 4-byte arrays: `[0x01, Port, 0x01, PowerByte]`

-   **Port:** `0x01` (Port 1) or `0x02` (Port 2).

-   **PowerByte:** `0` (Stop), `1-100` (Forward), `156-255` (Backward).

🔧 Troubleshooting
------------------

-   **No Bluetooth Found:** Ensure you are using **HTTPS** (or `localhost`). Web Bluetooth is disabled on insecure connections.

-   **Permissions:** Check the browser's site settings to ensure Bluetooth access isn't blocked.

-   **Connection Busy:** The WeDo 2.0 Hub only supports one active connection. Ensure no other apps (like the official LEGO app) are connected to the hub.

-   **Chrome Flags:** If the device picker doesn't appear on Linux/Windows, try enabling `chrome://flags/#enable-experimental-web-platform-features`.

📄 License
----------

This project is open-source. LEGO® is a trademark of the LEGO Group of companies which does not sponsor, authorize, or endorse this software.
