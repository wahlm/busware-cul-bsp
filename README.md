# busware-cul-bsp

This repository contains the source files and a package for the Arduino
Board Manager to support the [BusWare CUL](http://www.busware.de/tiki-index.php?page=CUL).

The main purpose of this package is to build [SIGNALDuino](https://wiki.fhem.de/wiki/SIGNALduino)
for the "real" CUL.

To use it just add the following URL to the Board Manager:
<https://raw.githubusercontent.com/wahlm/busware-cul-bsp/master/package_busware-cul-bsp_index.json>

As the BusWare CUL uses the atmega factory bootloader instead of the Arduino
bootloader, uploading the sketch and programming the bootloader does not
work (yet). Just build the software in the Arduino IDE, set the CUL into
bootloader (power-on with pressed button) and then upload with

```
avrdude -c flip1 -p atmega32u4 -U flash:w:/tmp/arduino_build_xxxxxx/WhatEver.ino.hex
```
