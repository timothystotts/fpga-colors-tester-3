# fpga-colors-tester-3

FFPGA Colors Palette Tester Version 3

by Timothy Stotts

Now with support for:

- Digilent Inc. Arty S7-25 FPGA development board containing a small Xilinx Spartan-7 FPGA
- Digilent Inc. Arty A7-100 FPGA development board containing a large Xilinx Artix-7 FPGA
- Digilent Inc. Zybo Z7-20 APSoC development board containing a moderate Zyng-7000 SoC.

## Description
A small FPGA project of different implementations for testing 24-bit color palette PWM mixing of discrete RGB LEDs
versus 16-bit color mixing of a 96x64 OLEDrgb display's text.

The Xilinx MicroBlaze designs can now target either of two FPGA development boards produced by Digilent Inc; one being
lower cost.
	- Digilent Inc. Arty-S7-25 FPGA development board containing a small Xilinx Spartan-7 FPGA
	- Digilent Inc. Arty-A7-100 FPGA development board containing a large Xilinx Artix-7 FPGA

Two peripherals are used: Digilent Inc. Pmod KYPD, Digilent Inc. Pmod OLEDrgb.

Additionally, the Xilinx Zynq design targets the
Digilent Inc. Zybo-Z7-20 FPGA development board containing a Xilinx Zynq-7000 APSoC.

Two peripherals are used: Digilent Inc. Pmod KYPD, Digilent Inc. Pmod OLEDrgb.

The design is broken into three groupings.
The first group targets the Digilent Inc. Arty A7-100 development board.
The second group targets the Digilent Inc. Arty S7-25 development board.
The last group targets the Digilent Inc. Zybo Z7-20 development board.
The projects are likely portable to the smaller Arty A7-35 and Zybo-Z7-10
respectively as the designs are low resource utilization.

The folder Color-Tester-Design-MB-A7 contains a Xilinx Vivado IP Integrator plus
Xilinx Vitis design. A MicroBlaze soft CPU is instantiated to talk with board components,
a 4x4 alphanumeric keypad, and 96x64 pixel color display.
Source to be incorporated into a Xilinx Vitis project contain
a very small Standalone program in C; drivers for the peripherals; and a main loop to repeatedly
read keypad entry and then update both discrete LEDs and display.
This design targets the Arty A7-100 development board.

The folder Color-Tester-Design-MB-S7 contains a Xilinx Vivado IP Integrator plus
Xilinx Vitis design. The design is essentially the same as the Color-Tester-Design-MB-A7 mentioned
above, but instead targets the Arty S7-25 development board, including the differences in available
board components, such as count of RGB LEDs.

The folder Colors-Tester-Design-Zynq contains a Xilinx Vivado IP Integrator plus Xilinx Vitis
design. The Zynq hard ARM CPU #0 is configured to talk with board components, a 4x4 alphanumeric
keypad, and 96x64 pixel color display. Its functionality is mostly equivalent to that of the
Color-Tester-Design-MB-A7 design, but differs in the count of RGB LEDs.

### Project information document:

[FPGA Colors Palette Tester info](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Colors%20Palette%20Tester%20-%20Refreshed.pdf)

### Target device assembly: Arty A7-100 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device assembly](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-assembled-20200831_202137119.jpg)

### Target device assembly: Arty S7-25 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device assembly](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-s7-assembled-20220715.jpg)

### Target device assembly: Zybo Z7-20 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device assembly](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-zynq-assembled-20200902_130951746.jpg)

### Target device execution example: Arty A7-100 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device execution example](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-executing-a-20200831_204635464.jpg)

### Target device execution example: Arty S7-25 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device execution example](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-s7-executing-a-20220715.jpg)

### Target device execution example: Zybo Z7-20 with Pmod KYPD, Pmod OLEDrgb, on extension cables
![Target device execution example](https://github.com/timothystotts/fpga-colors-tester-3/blob/main/Color-Tester-Design-Documents/img_color-palette-tester-zynq-executing-a-20200902_130933775.jpg)
