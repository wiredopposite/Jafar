
# Jafar
![Jafar PCB](https://github.com/wiredopposite/Jafar/blob/main/images/Jafar.jpg?raw=true)

This is a custom board reimagination of the Aladdin chip for the Original Xbox. gerbers are available [here](Gerber_PCB_jafar_2022-12-09.zip)

This VHDL was written by PsychoChewbacca and released with his AladdinXBlast repository

# Licensing

Jafar is free and open source. Please respect the licenses available in their respective folders.

-   Hardware is shared under the  [CERN OHL version 1.2.](https://ohwr.org/cernohl).
-   Firmware is shared under  [GPLv3](https://www.gnu.org/licenses/quick-guide-gplv3.en.html).

# Instructions

1.  Connect a JTAG programmer to the JTAG pins shown below.
    
2.  Make sure to apply 3.3V power to the Jafar board. This can be done by plugging it into the LPC port on the Xbox, an external power supply, or a JTAG programmer that can supply power.  A modified Lattice USB programmer or FlashCat are two examples of programmers that can supply power.
    
3.  Program the CPLD with the  `SVF` or `JED`  file in this repository . It can be programmed with  [UrJTAG](http://urjtag.org/)  using a  [compatible programming cable](http://urjtag.org/book/_system_requirements.html#_supported_jtag_adapters_cables) for the `SVF` or ispVM for the `JED` files. The general programming sequence in UrJTAG is something like: (Commands written in  **bold**).
    
    **cable usbblaster**  _Type  `help cable`  for other supported cables._  
    **detect**  _To confirm that the cpld is detected._  
    **svf FILENAME.SVF progress**  _To program the CPLD._
        
4.  Remove the JTAG programming points.
    
5.  The flash chip needs to either be programmed ahead of time, or can be hot-swapped with an existing chip to program it.
        
6.  Install onto the LPC header in your Xbox. You can either ground the D0 points or attach D0 to the pad on the Jafar chip to drive it correctly.
    
# BOM
| Qty | Value/Model | Description | Marking | URL (Passive components provided as sample only) |
| --- | --- | --- | --- | --- |
| 1 | LC4032V-75TN44CTQFP44 | Mach 4000 series CPLD 32MC | U1 | https://www.digikey.com/short/47m5hh |
| 1 | SST49LF080A-33-4C-NHEPLCC32_NH_SST_MCH- | PLCC32 LPC flash | U2 | https://www.digikey.com/short/47m54w |
| 1 | PLCC-32-AT-SMT (Optional) | PLCC SOCKET 32P SMT | CN1 | https://www.digikey.com/short/vrhtcrp7 |
| 1 | 0805 Resistor ~100ohm | around 100ohm 1/8W 0805 resistor | R1| https://www.digikey.com/short/47m59f |
| 1 | 0805 LED| any color 0805 LED| LED1 |https://www.digikey.com/short/47m5b2 |
| 1 | 2x6 female pinheader| 2x6 header| SV1 | https://www.digikey.com/short/47m550 |
