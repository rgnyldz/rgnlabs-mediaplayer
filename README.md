Build process: https://youtu.be/qrFpkbAZsBY

Convert any existing speaker you have to a fully local, home assistant compatible media player with just two parts. 

Parts used;
- ESP32-S3
- PCM5102A Dac

<img width="1618" height="1065" alt="image" src="https://github.com/user-attachments/assets/c5ebd069-831b-4c5f-ad44-b46ec15c6c17" />


The PCM5102A module has five Jumpers/Solder Bridges that need to be set correctly for the board to work with an ESP32. They switch the following functions below, depending if connected to High or Low. The settings you want are marked in bold:

SCK = Master Clock: Low if not external master clock signal is provided
H1L / FLT = Filter select : Normal latency (Low) / Low latency (High)
H2L / DEMP = De-emphasis control for 44.1kHz sampling rate: Off (Low) / On (High)
H3L / XSMT = Soft mute control: Soft mute (Low) / soft un-mute (High)
H4L / FMT = Audio format selection I2S : Right justified (Low) / Left justified (High)

https://www.makerguides.com/playing-audio-with-esp32-and-pcm5102/#Function_Jumpers

Solder these pads -
SCK - Front of the board
H1L - LOW
H2L - LOW
H3L - HIGH
H4L - LOW

<img width="326" height="347" alt="image" src="https://github.com/user-attachments/assets/9328d10e-24b5-4f46-b62b-71bfbd7bfe7d" />
<img width="273" height="310" alt="image" src="https://github.com/user-attachments/assets/370298e3-2750-408a-9877-ec8f408a1c54" />
