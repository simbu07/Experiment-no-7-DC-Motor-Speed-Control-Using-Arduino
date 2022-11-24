## Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM :
To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board

•	L293D driver

•	12V DC motor

•	10K ohm potentiometer

•	Pushbutton

•	12V source

•	Breadboard

•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

### FIGURE-01 H BRIDGE CIRUCIT INTERFACE: 
![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)

 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
### TABLE-01 EXITATION TABLE FOR H BRIDGE:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM FOR STIMULATION: 
```c
Name: silambarasan.K
Roll  no: 212221230101

const int motorpin1 = 5;
const int motorpin2 = 6;


void setup()
{
  pinMode(motorpin1,OUTPUT);
  pinMode(motorpin2,OUTPUT);
}

void loop()
{
  
  digitalWrite(motorpin1,HIGH);
  delay(2000);
  digitalWrite(motorpin2,LOW);
  delay(200);
  
  
}
```
### PROGRAM FOR RPM:
```c
#define motorIn1 5
#define motorIn2 6

void setup()
{
  pinMode(motorIn1,OUTPUT);
  pinMode(motorIn2,OUTPUT);
}
void loop()
{
  clockwise(250);
  delay(6000);
  counterclockwise(64);
  delay(6000);
}
void counterclockwise(int speed)
{
  analogWrite(motorIn1,speed);
  analogWrite(motorIn2,0);
}

void clockwise(int speed)
{
  
  analogWrite(motorIn1,0);
  analogWrite(motorIn2,speed);
}


```
### OUTPUT:
![output1](https://user-images.githubusercontent.com/94525786/198937485-cbaed2b1-2a61-4cdd-92d3-345e1f6921c3.png)

### GRAPH AND TABULATION 
![t9](https://user-images.githubusercontent.com/94525786/198937488-e49cbe28-ce91-40de-b713-aaafcf242f2f.png)

![g10](https://user-images.githubusercontent.com/94525786/198937473-9c3165ec-5774-4664-a94e-adcccbc7d8d1.png)

![t10](https://user-images.githubusercontent.com/94525786/198937491-f86a379f-49f3-4c4f-aff7-abc22331742b.png)

![g11](https://user-images.githubusercontent.com/94525786/198937482-a0cf763c-7f9e-44f5-b39b-232ef73858ed.png)





### RESULTS :
Thus, the speed and the direction of a DC motor using L293D driver ic( H- bridge) is controlled.

