nrf24l01
========

nrf24l01+ Raspberry arduino
**********************************************************************************************
                     Enabling Raspberry Pi GPIO
sudo apt-get install python-dev
 
#make sure to COMMENT the lines with spi-bcm2708 and i2c-bcm2708 modules
sudo vim /etc/modprobe.d/raspi-blacklist.conf
 
#be sure to have i2c-dev module in the /etc/module
sudo vim /etc/modules
 
sudo adduser pi i2c
sudo apt-get update
 
#reboot:
sudo shutdown -r now
 
#get the GPIO software
wget https://pypi.python.org/packages/source/R/RPi.GPIO/RPi.GPIO-0.5.3a.tar.gz
 
#untar it and install it
tar -xzvf RPi.GPIO-0.5.3a.tar.gz
cd RPi.GPIO-0.5.3a/
sudo python setup.py install
sudo apt-get install i2c-tools
-------------------------------------------------------------------------
                         Method 2 (not tested, but should work):

#Pretty similar except for the python-dev package taken from the repos.
#source: Adafruit.com
 
sudo apt-get update
 
sudo apt-get install python-dev
 
sudo apt-get install python-rpi.gpio
 
#add this two modules: i2c-bcm2708 i2c-dev
sudo nano /etc/modules 
 
sudo apt-get install python-smbus
sudo apt-get install i2c-tools
 
# do COMMENT the lines with spi and i2c modules
sudo nano /etc/modprobe.d/raspi-blacklist.conf
