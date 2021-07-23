# Seed Studio [Wio Node](https://www.seeedstudio.com/Wio-Node.html)  Setup through Arduino IDE/Platformio

The Wio Node is a low cost, potable, compact ESP 8266 based devlopment board. It can be easily used with [Wio Link](https://wiki.seeedstudio.com/Wio_Link/) app to setup an IoT application in a short time. However, it severely limit's it's functionality as the Wio Link app only supports a spcific number of devices. It can neither be programmed through the Micro-USB port as it is meant only to supply power. We are going to see how we can use Arduino IDE/Platformio to program the Wio Node.


Requirements
-------------

- Platformio: add the Wio Node [board support.](https://docs.platformio.org/en/latest/boards/espressif8266/wio_node.html)
- Arduino: Add the ESP8266 Board Library from Library Manager
- TTL Programmer/ESP01 programmer: [ESP-01 (ESP8266) Programmer](https://www.xgadget.de/anleitung/esp-01-esp8266-programmer-so-funktioniert-der-flashvorgang/)


Instructions
-------------
1.	Make the connections from the UART of the Wio node ([schematic](https://wiki.seeedstudio.com/Wio_Node/#schematic-online-viewer)) to the programmer port as shown below:

                   Wio Node UART0		  		  ESP Programmer

                   |  ]---||o  U0RXD				| 1 | 2 |     _____
                   |  ]---||o  U0TXD				| 3 | 4 |          |
                   |  ]---||o  VCC				| 5 | 6 |     _____|
                   |  ]---||o  GND				| 7 | 8 |

                  Connect GND to pin 2 of ESP programmer.
                  Connect VCC to pin 7 of ESP programmer.
                  Connect U0RXD to pin 8 of ESP programmer
                  Connect U0TXD to pin 1 of ESP programmer

2.	Before plugging in the programmer to the PC with the Wio Node connected to it as above, press the *func* button on the Wio Node. Keeping the *RST* button pressed plug the programmer into the PC. Once plugged in, release the button.
  - This ensures that the wio node starts in programmable mode.
  - Please Note: In order to flash the Wio Node again, you will have to eject the programmer and plug it again following this procedure.
4.	Now flash your program code as required, however remember to keep the following commands in the setup to retain the functionality of the ports:

                  pinMode(15, OUTPUT);
                  digitalWrite(15, 1);
                  
5.	Press the RST button to run the code that you uploaded
6.	Now flash and use your Wio Node and make full use of it’s portable size.
7.	If you want to make use of both the ports, power the Node via USB or Battery pack.
 
