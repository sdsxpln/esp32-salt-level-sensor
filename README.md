Note:  The HC-SR04 did not end up giving me consistent results.  I ended up switching to using the time-of-flight vl53l0x sensor.  [Here](https://github.com/kylehendricks/esp32-salt-level-sensor-vl53l0x) is the new project.

# esp32-salt-level-sensor
An ESP32 based water softener salt level sensor

Uses the [HC-SR04](http://www.elecfreaks.com/store/download/product/Sensor/HC-SR04/HC-SR04_Ultrasonic_Module_User_Guide.pdf) ultrasonic distance sensor to measure the salt level in the brine tank.

The level is published to an MQTT broker configured in the menuconfig.

To get accurate measurements of the echo signal from the HC-SR04, the ESP32's [RMT](https://esp-idf.readthedocs.io/en/latest/api-reference/peripherals/rmt.html) peripheral is used.

## Building

1. Run `make menuconfig` to configure Wifi and MQTT.
2. Run `make flash && make monitor` to flash then tail the ESP32 logs.
