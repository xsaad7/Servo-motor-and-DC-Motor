# Servo-motor-and-DC-Motor
What is a Servo Motor

A type of electric motor that functions as a rotary actuator and allows for a precise control of angular velocity, position and acceleration is known as servo motor.

A servo motors consists of a sensor for position feedback on their rotor to control its position and speed at all times. Thus, the servo motors are generally characterized by their closed-loop control system design

What is a DC Motor?

DC motor is the type of electric motor that converts the electrical energy in form of direct current (DC) into mechanical energy (rotation of shaft)

The DC motors have two types of constructions namely brushed DC motor and brushless DC motor. But, when we use the keyword DC motor, it simply means that we are talking about brushed DC motor

Servo Motor

Instruction Code:

#include <Servo.h>

int posicao = 0;
Servo servo;

#define bt1 2
#define bt2 3


void setup()
{
  Serial.begin(9600);
  servo.attach(7);
  servo.write(0);//INICIA O MOTOR NA POSIÇÃO 0º
  pinMode(bt1, INPUT);
  pinMode(bt2, INPUT);
}

void loop()
{
  Serial.println(digitalRead(bt1));
  Serial.println(digitalRead(bt2));
  
  if(digitalRead(bt1) == HIGH && posicao <=180){
    
    posicao++;
    servo.write(posicao);
    delay(5);
  }
  
  if(digitalRead(bt2) == HIGH && posicao >=0){
    
    posicao--;
    servo.write(posicao);
    delay(5);
  }
}

circuit Digrams:

![image](https://github.com/xsaad7/Servo-motor-and-DC-Motor/assets/139689886/e92a3177-dcc2-434f-bf04-ed7347d3dbc9)


DC Motor

instrction code:
const int m1 = 9;
const int m2 = 10;
const int m3 = 5;
const int m4 = 6;

void setup() {
  // put your setup code here, to run once:
pinMode(9,OUTPUT);
pinMode(10,OUTPUT);
pinMode(5,OUTPUT);
pinMode(6,OUTPUT);
}

void loop() {

// motor 1, turns clockwise
digitalWrite(m1,HIGH);
digitalWrite(m2,LOW);
digitalWrite(m3,LOW);
digitalWrite(m4,LOW);

delay(1000);

// motor 1, turns anticlockwise
digitalWrite(m1,LOW);
digitalWrite(m2,HIGH);
digitalWrite(m3,LOW);
digitalWrite(m4,LOW);

delay(1000);

//motor 2, turns clockwise
digitalWrite(m1,LOW);
digitalWrite(m2,LOW);
digitalWrite(m3,HIGH);
digitalWrite(m4,LOW);

delay(1000);

//motor 2, turns anticlockwise
digitalWrite(m1,LOW);
digitalWrite(m2,LOW);
digitalWrite(m3,LOW);
digitalWrite(m4,HIGH);
  
delay(700);
}

circuit Digrams

![image](https://github.com/xsaad7/Servo-motor-and-DC-Motor/assets/139689886/6d5dd428-4b0e-4057-88b7-fa22f1e4546e)
