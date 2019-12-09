# Netgear Firmware Recovery via TFTP

Steps outlined here are required to recover bricked AC120 E6120
Wifi-extender by Netgear.
The firmware upgrade procedure didn't go too well on mine.
It ended up blinking the power LED over and over, without any
network activity.

## Recovery steps

```
git clone git@github.com:wkoszek/netgear_recovery.git
cd netgear_recovery
unzip EX6120-V1.0.0.46_1.0.29.zip
```


1. Follow steps above
1. Disconnect from Wifi
1. On a PC/Laptop, connect an Ethernet cable between the device and your laptop.
1. On Macbook, get a dongle to get a Ethernet connectivity and connect the cable to the device
1. Open Terminal
1. Set your IP address as `192.168.1.10`
1. Start `tftp 192.168.1.1 69`
1. Set mode to binary: `mode binary`
1. Upload the file: `put EX6120-V1.0.0.46_1.0.29.chk`

The most critical step is the configuration of the binary mode.
Without it, the device won't start receiving the firmware.

