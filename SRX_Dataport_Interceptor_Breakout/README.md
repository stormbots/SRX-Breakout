# Talon SRX Dataport Intercepter Breakout
This board breaks out the Talon SRX pins into a more easily usable 3-wire configuration that's compatible with standard servo cabling. This variant also includes a passthrough to the Gadgeteer port, allowing mixed usage of both 3 wire and Gadgeteer plug devices from [CTRE](http://www.ctr-electronics.com/). 

For additional configuration of the Talon SRX to take advantage of this board, see the [Talon SRX User's guide](http://content.vexrobotics.com/vexpro/pdf/Talon-SRX-User-Guide-20150201.pdf)

## Wiring
 The 4 3-wire connectors simply match servo cable order. Since switches generally don't care about voltage, all 3-wire signals use 3.3V. The voltage for the Analog Input Signal pin MUST be 3.3V in order to avoid damage to the Talon SRX.
 
 Connection Name | Pin 1 | Pin 2 | Pin 3 
 ---|---|---|---
Forward Limit Switch | GND |3.3V| Signal
Reverse Limit Switch | GND |3.3V| Signal
Quadrature Index Switch | GND |3.3V| Signal
Analog Input | GND |3.3V| Signal

The 4 wire quadrature encoder has a slightly different configuration. In addition, a solder jumper on the reverse side of the board allows for a configurable voltage. This is needed since some encoder boards require 5V signals, rather than the 3.3V.

Connection Name | Pin 1 | Pin 2 | Pin 3 |Pin 4
---|---|---|---|---
 Quadrature Encoder |GND | 3.3V or 5V |Signal A | Signal B

 ### Gadgeteer Pin Usage Chart
The Gadgeteer passthrough port works exactly as the one on the SRX does, with the same pinout and shroud orientation. 
Note, that compatibility issues will arise if both the Gadgeteer device and 3 wire device try to drive the same input line. This is called [bus contention](https://google.com/search?q=bus contention) and can result in incorrect operation or damage to your devices. 

This is not guaranteed to be complete, but may help assess what pins are available in combination with various other devices

Component                   |Analog |Fwd Limit| Rev Limit |Quad A | Quad B|
----------------------------|:-----:|:-------:|:---------:|:-----:|:-----:|
[CTRE Mag Encoder](http://www.ctr-electronics.com/srx-magnetic-encoder.html) |   Used   |         |           |  Used    |   Used   


[mag]: ""

## Bill Of Materials

Quantity | Description                  | Part Number |link
--------:|-----|------------------------|-------------|---
4        |  3-pin 0.1" header | Generic | [Digikey](http://www.digikey.com/product-detail/en/61300311121/732-5316-ND/4846825)
1        |  4-pin 0.1" header | Generic | [Digikey](http://www.digikey.com/product-detail/en/M20-9990445/952-2265-ND/3728229)
1        |  14-position 0.5" header | FCI 20021321-00014T4LF | [Digikey](https://www.digikey.com/product-detail/en/20021321-00014T4LF/609-3771-ND/2209082)
2        |  10k resistor (0603 package) | Generic | [Digikey](https://www.digikey.com/product-detail/en/RC0603JR-0710KL/311-10KGRCT-ND/729647)
2        |  Jumper wires | Generic 22 gauge wire  | 
1        | 10 pin 0.05" pitch shrouded socket  CNC Tech 3220-10-0100-00| [Digikey](PTH Version http://www.digikey.com/product-detail/en/3220-10-0100-00/1175-1627-ND/3883661)


## Assembly
1. Assemble the surface mount components to the bottom of the board
2. Solder the jumper to select the voltage for the quadrature encoder. 
3. Attach the wire jumpers. These jumpers only work as spacers between the Talon SRX and the PCB. This helps stabilize the connector, and prevent shorting against the 0.1" headers.
4. Attach the 0.1" headers so they face away from the body of the Talon SRX
4. Optionally, attach the 0.05" header so they face away from the body of the Talon SRX
5. Place a piece of electrical tape over the bottom of the board, covering the 0.1" headers, resistors, and solder jumpers.

## Mounting 
1. Remove the screws on the Talon SRX
2. Gently connect the backside connector to the Talon SRX. 
3. Re-insert the screws, and tighten gently. Do not use excessive force*


*  _Using significant force on the screws can damage the Talon SRX. It can also cause the 0.1" joints to punch through the electrical tape, causing signal errors or power shorting. The jumper wires will help provide spacing to prevent these issues._


## FRC Technicalities
This is a passive wiring board, and contains no active components.
