# I did not make this code from scratch I have just updated this to work with a current Raspberry Pi OS

# Pi Connect Cam

Add an extra camera to Prusa Connect using a Pi + Cam.

## How it works

It installs a systemd service that just captures an image from a connected camera (using libcamera-jpeg) and sends it to Prusa Connect for viewing in the web UI.

It just pipes the output of rpicam-jpeg to a curl command. The curl sends the image to Prusa's Connect API.

## Prerequisites

* Pi device (Tested on Pi 4b)
* Camera (Tested with Pi Cam V2)
* Prusa Connect token - login, "Add new web camera", copy token
* UUID for camera fingerprint (I used https://www.uuidgenerator.net)


## Installation

1. Connect the camera to the Pi
2. Flash Pi OS to your SD card - it's useful to configure WiFi and SSH at this point using Pi Imager.
3. Insert SD card and ensure the device connects to your network
4. Connect to the device via SSH
5. Download the code using curl. `curl -OL https://api.github.com/repos/thecoderanger5280/pi-connect-cam/tarball/main`
6. Extract main. `tar -xzf main`
7. CD into the folder that was just created.
8. Make the install file executable. `chmod u+x install.sh`
9. Run the install.sh file. `sudo ./install.sh [USERNAME] [TOKEN] [UUID]`
    - Where: [USERNAME] is your Pi OS Username, [TOKEN] is the token from Prusa Connect, [UUID] is the UUID you generated

### Resources

https://github.com/johntron/pi-connect-cam
