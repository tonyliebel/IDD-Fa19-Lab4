# Paper Puppets

A lab report by Tony Liebel

## In this Report

To submit your lab, clone [this repository](https://github.com/FAR-Lab/IDD-Fa18-Lab4). You'll need to describe your design, include a video of your paper display in operation, and upload any code you wrote to make it move.

## Part A. Actuating DC motors

**Link to a video of your vibratio motor**

https://youtu.be/HC76HJxEgAk

In my video - the motor vibrated itself off of the breadboard - but it worked!

## Part B. Actuating Servo motors

### Part 1. Connect the Servo to your breadboard

**a. Which color wires correspond to power, ground and signal?**
Orange is Data, Red is Power, Brown is Ground

### Part 2. Connect the Servo to your Arduino

**a. Which Arduino pin should the signal line of the servo be attached to?**
     A PWM Pin. In this case, I am using pin 9
     
**b. What aspects of the Servo code control angle or speed?**
     (pos = 180; pos >= 0; pos -= 1) The first two pos's control the start and stop of the sweep. The third POS is the number of steps that the servo runs through. By changing the third POS value, you can increase the speed. However, if you increase the speed too much, the servo is unable to keep up with the instruction, and will not run through it's full 180 degree sweep.
     
## Part C. Integrating input and output

Video! https://youtu.be/54Hau18SbMs

I used this code to get the servo motor mapped to the potentiometer: 

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}


**Include a photo/movie of your raw circuit in action.**

## Part D. Paper puppet

**a. Make a video of your proto puppet.**

https://www.youtube.com/watch?v=FokZo2rjamY&feature=youtu.be
My Puppet's joints for the arms had too much tape, so it wiggled more than it raised and lowered it's arms.

This also used the code that I used above, so that I could raise and lower "Gimpy's" arms via potentiometer.

## Part E. Make it your own

Scary eyes & even more twitching speed! Gimpy is coming for you!
https://github.com/tonyliebel/IDD-Fa19-Lab4/blob/master/00024.MTS
 
