## STM 32 Flight Computer
This is a project to make a flight computer PCB that can be used to control mechanisms on a rocket. It uses a STM32F405 as the MCU, with an altimeter (BMP388), an IMU (BMI088), and a magnetometer (LIS3MDLTR). It also has 2 servo outport pins, and supports both USB-C and SWD debugging. 

#### Why I made this project
I had previously made a basic flight computer that utilized an ESP32, but here in college, pretty much all the rocketry teams are using STM32s to control their flight computers, and so I wanted to get some more experience designing with STM32s, and also programming with them too. 

Note: JLCPCB doesn't support 3 of the sensors I'm using in economic assembly, and so I'm going to purchase them from their parts store and then reflow solder them manually.

3D View of the full PCB:
![3D View](./Pictures/3D%20View.png)

PCB Layout:
![PCB View](./Pictures/PCB%20Layout.png)

PCB Schematic:
![Schematic View](./Pictures/PCB%20Schematic.png)

BOM:
|ID |Name                |Designator                                       |Footprint                              |Quantity|Manufacturer Part|Manufacturer        |Supplier|Supplier Part|Price|
|---|--------------------|-------------------------------------------------|---------------------------------------|--------|-----------------|--------------------|--------|-------------|-----|
|1  |100nF               |C1,C2,C3,C7,C8,C9,C21,C23,C16,C20,C22,C24,C25,C26|C0402                                  |14      |CL05B104KO5NNNC  |SAMSUNG(三星)         |LCSC    |C1525        |0.001|
|2  |10pF                |C4,C5                                            |C0402                                  |2       |CL05C100JB5NNNC  |SAMSUNG(三星)         |LCSC    |C32949       |0.004|
|3  |1uF                 |C6                                               |C0402                                  |1       |CL05A105KA5NQNC  |SAMSUNG(三星)         |LCSC    |C52923       |0.003|
|4  |10uF                |C10,C11,C12                                      |C0603                                  |3       |CL10A106KP8NNNC  |SAMSUNG(三星)         |LCSC    |C19702       |0.006|
|5  |TF PUSH             |CARD1                                            |TF-SMD_TF-PUSH                         |1       |TF PUSH          |SHOU HAN(首韩)        |LCSC    |C393941      |0.059|
|6  |USBLC6-2SC6_C2687116|D2                                               |SOT-23-6_L2.9-W1.6-P0.95-LS2.8-BL      |1       |USBLC6-2SC6      |UMW(友台半导体)          |LCSC    |C2687116     |0.038|
|7  |SS54_C22452         |D4,D1                                            |SMA_L4.4-W2.8-LS5.4-R-RD               |2       |SS54             |MDD(辰达半导体)          |LCSC    |C22452       |0.043|
|8  |White               |LED1                                             |LED0603-R-RD_WHITE                     |1       |KT-0603白灯        |KENTO               |LCSC    |C2290        |0.011|
|9  |Red                 |LED2                                             |LED0603-RD                             |1       |KT-0603R         |KENTO               |LCSC    |C2286        |0.006|
|10 |HL3401A             |Q1                                               |SOT-23-3_L2.9-W1.3-P1.90-LS2.4-BR      |1       |HL3401A          |R+O(宏嘉诚)            |LCSC    |C7420349     |0.034|
|11 |10kΩ                |R1                                               |R0402                                  |1       |0402WGF1002TCE   |UNI-ROYAL(厚声)       |LCSC    |C25744       |0.001|
|12 |5.1kΩ               |R4,R5,R6,R7                                      |R0402                                  |4       |0402WGF5101TCE   |UNI-ROYAL(厚声)       |LCSC    |C25905       |0.001|
|13 |100kΩ               |R3                                               |R0603                                  |1       |0603WAF1003T5E   |UNI-ROYAL(厚声)       |LCSC    |C25803       |0.001|
|14 |TS-1187A-B-A-B      |SW1,SW2                                          |SW-SMD_4P-L5.1-W5.1-P3.70-LS6.5-TL_H1.5|2       |TS-1187A-B-A-B   |XKB Connection(中国星坤)|LCSC    |C318884      |0.019|
|15 |BMP388              |U2                                               |SENSORM-SMD_BMP388                     |1       |BMP388           |Bosch(博世)           |LCSC    |C779278      |1.253|
|16 |BMI088              |U4                                               |LGA-16_L4.5-W3.0-P0.50-BL              |1       |BMI088           |Bosch(博世)           |LCSC    |C194919      |3.499|
|17 |AMS1117-3.3         |U6                                               |SOT-223-3_L6.5-W3.4-P2.30-LS7.0-BR     |1       |AMS1117-3.3      |AMS                 |LCSC    |C6186        |0.164|
|18 |LIS3MDLTR           |U8                                               |LGA-12_L2.0-W2.0-P0.50-BL              |1       |LIS3MDLTR        |ST(意法半导体)           |LCSC    |C478483      |3.639|
|19 |TYPEC-304-ACP16     |USB3                                             |USB-C-SMD_TYPE-C-16P-1                 |1       |TYPEC-304-ACP16  |XUNPU(讯普)           |LCSC    |C2982555     |0.13 |
|20 |16MHz               |X1                                               |OSC-SMD_4P-L3.2-W2.5-BL                |1       |X322516MLB4SI    |YXC(扬兴晶振)           |LCSC    |C13738       |0.066|
|21 |STM32F405RGT6       |U1                                               |LQFP-64_L10.0-W10.0-P0.50-LS12.0-BL    |1       |STM32F405RGT6    |ST(意法半导体)           |LCSC    |C15742       |3.091|
|22 |2.2uF               |C17,C18                                          |C0402                                  |2       |CL05A225MQ5NSNC  |SAMSUNG(三星)         |LCSC    |C12530       |0.003|
|23 |4.7uF               |C19                                              |C0402                                  |1       |CL05A475MP5NRNC  |SAMSUNG(三星)         |LCSC    |C23733       |0.005|
|24 |W25Q128JVSIQTR      |U3                                               |SOIC-8_L5.3-W5.3-P1.27-LS8.0-BL        |1       |W25Q128JVSIQ     |Winbond(华邦)         |LCSC    |C97521       |1.599|

