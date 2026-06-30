# PLDR-KiCad
---
## NUCLEO64-G474RE - No Connection Pins:

PB8-BOOT0 - Boot Select + GPIO:
Using PB8 as PWM output from TIM8 -> NC for no IO on PB8-BOOT0

PA13 and PA14 - Serial Wire Debug:
Used by ST-LINK for SWD + flashing user code through USB -> NC so no IO towards SWD functions outside of USB

PA15 - Shared pin with PC0/PA15:
PC0/PA15 uses PC0 for TIM1 PWM output -> NC for no IO from PA15

PC14, PC15, PF0, and PF1 - Low/High Speed Clock Input/Output:
Used by Nucleo board circuit to route onboard crystal signals -> NC to prevent IO to and from the crystals to the rest of the board

NRST - Internal Reset:
Will program resets within code and default faults -> NC to prevent signals from accidentaly reseting MCU

PC4, PC4/PA2, and PC5/PA3 - Shared with PA2 and PA3:
"Communication between the target STM32G4 and the STLINK-V3E MCU is enabled on LPUART1 to support the Virtual COM port" - Nucleo-G474RE user manual describing how LPUART already locked PA2 and PA3 pins -> NC to prevent IO to and from VCOM
