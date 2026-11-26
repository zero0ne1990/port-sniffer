# Port Sniffer

A small Windows tool for checking the ports on a used laptop or desktop before you buy it.

## Download
Get **PortSniffer.exe** from the [Releases page](../../releases/latest), or from the `bin` folder of this repository.

You don't need to install anything. Copy the exe to a USB stick and run it on the computer you're checking. It works on any Windows 10 or 11 PC. Windows will ask for administrator rights (UAC), and the tool needs them to read the USB hubs, battery and drive health.

> Windows SmartScreen may warn that the app is from an unknown publisher, because it isn't code-signed. Click **More info → Run anyway**.

## How to use it
1. Plug things into the ports you want to test: a USB stick (move it from port to port), headphones, a network cable, a monitor or TV, and the charger.
2. Tick the port types to test, or click **Select all**.
3. Under **USB ports to test**, choose **Only this computer's own ports** or **Computer ports + ports on USB hubs**.
4. Click **SNIFF**.
5. Read the results. A red **PROBLEM** row means a fault was detected. A grey **NOT TESTED** row means the port exists but nothing was plugged in. Click **Save report...** to keep a .txt or .csv copy.

If **Play left / right speaker test beep** is ticked, you'll hear a beep from the left speaker, then the right. If one is missing or crackly, that speaker is faulty.

## What each test does
| Port | How it is tested |
|---|---|
| USB (A and C) | Asks each USB port what is connected, whether it responded properly and what speed it runs at. It flags **over-current** (a shorted port), **failed connection**, **not enough power**, and **USB 3 devices running only at USB 2 speed**, which points to damaged contacts. Only the computer's own sockets are counted. |
| HDMI / DP / VGA / DVI | A port passes when the connected monitor reports its identity back. It also checks the graphics chips for errors. |
| Ethernet | Checks the cable link and speed, then pings the router. A gigabit port that only links at 100 Mbps is flagged, because that usually means damaged wires or pins. |
| Wi-Fi | Scans for nearby networks, then checks signal strength and router replies. |
| Audio | Detects whether anything is plugged into the headphone and microphone jacks, and can play a left/right speaker test. |
| Charging / battery | Checks the charger is detected and the battery is charging, and reports battery health and charge cycles. |
| Serial (COM) | Opens each port and sends test data. With a loopback plug (pins 2 and 3 bridged) it checks the data comes back. |
| Storage, webcam, card reader, Bluetooth, Thunderbolt, LPT, coax/TV tuner | Driver and health status reported by the device. |
| Device Manager | Lists every device that reports an error. |

**Limitation:** a port with nothing plugged in can be found, but it can't be tested, because an empty port doesn't respond. Test each port with something plugged in.

## License
Free to download and use. Modifying, decompiling or redistributing modified versions is not allowed. See [LICENSE](LICENSE).
