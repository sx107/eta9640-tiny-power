# eta9640-tiny-power
Tiny ETA9640 Li-Ion USB-C battery charger and 5V booster / 5V UPS board

This is a tiny board that provides single-cell Li-Ion charging through USB-C (no QC or PD, just 5V 1A max) or external power and 5V boost output.

This is not a powerbank board: it only receives and does not output any power through the USB-C connector.

![Board photo](photo.jpg?raw=true "Board photo")
![Board image](board.png?raw=true "Board image")

## Features
- Small size: 0.6x1 inch (around 16x26 mm)
- Two power inputs with USB-C priotity charging: the board won't consume almost any power from external power input if USB-C is connected
- Backwards voltage propagation protection with LM73100 IC: if, for example, USB-C is connected, external power input will still be floating and vice versa
- Reverse polarity/overvoltage protection with LM73100 IC
- Selectable charge current (0.2A, 0.5A, 1A or Adjustable via 0603 resistor)
- Output enable pin
- Low-power support: ETA9640 always outputs 5V unless the EN pin is pulled low, no minimum load required
- Gas gauge LED, that blinks and shows the remaining battery charge when the board is charging or when it is outputting any power. This 0603 LED may be desoldered for low-power applications
- Output power not interrupted when charging starts: this board works almost as an uninterraptable power supply (UPS)

## Main characteristics
- Board size: 600 x 1025 thou (1/1000s of an inch)
- 5V output, 1A max
- 5V nominal input, 1A max
- Input voltage protected range: 4.2V-5.7V
- Absolute maximum input voltage: -15V for negative voltages, 27V for positive
- Boost efficiency up to 96% at 0.2-0.3A output current
- Charge current: 0.1-1A
- Quiescent current (5V boost on / EN pin high, no load): around 100-200uA with LED desoldered
- Shutdown current (5V boost off / EN pin low): 10uA max

## Shared files

This repo provides the schematic and all files (gerber/BOM/PNP) for ordering.
Unfortunately, I can't share the project files since they were made in a proprietary ECAD.

- [Schematic.pdf](schematic.pdf "Schematic.pdf"): board schematic
- [Board folder](board "Board folder"): all files required for ordering on [JLCPCB](http://jlcpcb.com "JLCPCB")
- [Board/eta9640-tiny-power PCB.ZIP](board/eta9640-tine-power-PCB.ZIP "Board/eta9640-tiny-power PCB.ZIP"): Gerber files ZIP
- [Board/eta9640-tiny-power-BOM.xls](board/eta9640-tiny-power-BOM.xls "Board/eta9640-tiny-power-BOM.xls"): Bill of materials file
- [Board/eta9640-tiny-power-PNP.csv](board/eta9640-tiny-power-PNP.csv "Board/eta9640-tiny-power-PNP.csv"): Pick and place file
- [Board/eta9640-tiny-power-COMMENT.txt](board/eta9640-tiny-power-COMMENT.txt "Board/eta9640-tiny-power-COMMENT.txt"): JLCPCB ordering notes (do not send to JLCPCB)
- Example order screenshots are also provided as images in the *board/ * folder.

## Parts datasheets
- ETA9640: [ETA9640 datasheet](http://www.eta-semi.com/wp-content/uploads/2022/03/ETA9640_V1.5.pdf "ETA9640 datasheet")
- LM73100: [LM73100 datasheet](https://www.ti.com/lit/ds/symlink/lm7310.pdf "LM73100 datasheet")

## License

Shared under the [CERN Open Hardware Licence Version 2 Permissive](LICENSE "License file") license.

