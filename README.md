Commodore 64 I2C breakout/adapter -board for cassette port.
* 5V side and 3.3V side. Ground is common on both.
* External passthrough for powering 5V devices
* Board has a place for a fuse. It is up to you to decide what kind of fuse you end up using  (100mA, for example).
  It is probably a good idea to do some current calculations before adding too many devices.

Note 1: v0.1 requires that JP1 solder jumper is soldered (adds pull-up for SCLK on 5V side of the board).

![image](https://github.com/voutti/board_tape_i2c/blob/master/images/board_v0.1.jpg)

Note 2: Board assumes that in the SW driver - cassette port SENSE line is SDA and WRITE is SCL.
        It might be better if it was the other way around since SENSE line in Commodore 64 has a
        pretty strong 3.3kOhm pull-up and any I2C slave device needs to be able to sink enough current
        to pull it low enough to be seen as logic 0. If SENSE line would be used for SCL then the strong
        pull-up would not be a problem since SCL is (usually) only controlled by I2C master. For SDA
        we could decide our own pull-up resistor value - like 4.7kOhm or 10kOhm (4.7kOhm in v0.1 board).

![image](https://github.com/voutti/board_tape_i2c/blob/master/images/reading_i2c_slave.png)


 
