# meatberry

Sour-vide cooker with Raspberry Pi.

## How to use

```
git clone https://github.com/tmdojo/meatberry.git
cd meatberry
sudo /home/pi/miniconda/bin/jupyter notebook --ip=0.0.0.0 &
```

Make sure to adjust path to jupyter.
Note that jupyter must be started with sudo so that the process can access GPIO.

Open web browser on PC/Mac and navigate to http://raspberry.local:8888
You should see Jupyter Notebook.

Open runPID.ipynb and adjust GPIO pin number for the relay and DS18B20's ID.

Adjust target temperature, cooking time as well as PID coefficients and run.

## Hardware parts

* Raspberry Pi 2: Any Pi would do but default GPIO pin is set to use ones in extended area.
* DS18B20 temperature sensor: https://www.adafruit.com/product/381
* Relay SSR-40DA: https://www.ebay.com/sch/i.html&_nkw=SSR-40DA
* Kettle: Simple switch-on-to-boil kettle. Large size is good. Something like this. https://www.amazon.com/T-FAL-electric-kettle-Justin-KO340176/dp/B00LGM4UDO/ref=sr_1_4?s=kitchen&ie=UTF8&qid=1500555722&sr=1-4&keywords=kettle&refinements=p_89%3AT-fal

## Hardware wiring

To be updated

Enable DS18B20 temperature sensor by loading 1 wire module

```
sudo echo w1-gpio >> /etc/modules
sudo echo w1-therm >> /etc/modules
sudo echo 'dtoverlay=w1-gpio-pullup,gpiopin=20' >> /boot/config.txt
sudo reboot
```

## Software requirement

You would fist need to setup:

* Python2.7
* numpy
* matplotlib
* jupyter notebook

The new version of Raspbian has the RPi.GPIO library pre-installed.

## Acknowledgement

PID.py is from Ivmech PID Controller
https://github.com/ivmech/ivPID

Majority of the project idea is from
http://www.cuspy.org/diary/raspberrypi-roastbeef/
https://github.com/hamano/python-niku
