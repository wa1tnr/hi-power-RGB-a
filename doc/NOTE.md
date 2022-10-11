Tue 11 Oct 10:49:58 UTC 2022

High power RGB LED work

  Solid discussion of real power requirements, 1440 RGB's:

  https://learn.adafruit.com/1500-neopixel-led-curtain-with-raspberry-pi-fadecandy/power-topology

  Modest 144 RGB's in a Sousaphone (somewhat or fully portable):

  https://youtu.be/T9dLTKwh5WY


  * Yes, they really do draw 60 mA at full brightness

  * Reference project (1440 RGB's) took a 60 Ampere 5 Volt Meanwell RSP-320-5 (USD $67, Mouser, October 2022)

  * Ref project used all three outputs of that power supply, sharing load 1/3 total per main output bus

  * Ref project chose 12 AWG wiring '12 gauge wire'

  * Ref project uses 1440 RGB's, 60 mA (max) per RGB
```
    1440 x 0.06 Ampere = 86.40 Amperes

      $ dc -e '5 k 1440 0.06 * p q'  86.40

    5 Volts x 86.40 Amperes = 432 Watts  @5VDC

      $ dc -e '5 k 5 86.4 * p q'   432.0
```

  * Ref project power supply capable of 300 Watts output @5VDC
```
      $ dc -e '5 k 5 60 * p q'   300
```
  * Ref project author refers to this as '70%' capable (the PSU can
    deliver 70% of the required current @5VDC)

  * Ref project uses 24 RGB strips in three groups of eight strips
```
      $ dc -e '0 k 1440 24 / p q'   60
```

Additional citations

  Giant Power Supplies

    ('Powering NeoPixels' from 'Adafruit NeoPixel Überguide' By Phillip Burgess)

  https://learn.adafruit.com/adafruit-neopixel-uberguide/powering-neopixels#giant-power-supplies-2894491

  Low-Power Portable work

    ('Sipping Power With NeoPixels' (on learn.adafruit.com) By Phillip Burgess)

  https://learn.adafruit.com/sipping-power-with-neopixels


Random (hah) selection of related factoids follows.

  * Railroad signals - use DC current at rather low voltages, on the tracks, to detect the presence of a train - only between two traffic signals.

    They do this by shorting the two railroad tracks together, through the body of the train.  Which closes a switch (by completing a circuit).

    This is a pretty good sized distance to work with such a low DC voltage; they've already worked out those details.  One may assume the low voltage aspect makes the idea and its implementation especially safe (for both human and animal 'visitors' to the railroad track).

END.
