/*
This code works on 2-button-step 1 axis travelling motion controller, 
positive parabolic direction.
*/

#include <math.h>

const int in_1 = 7;
const int in_2 = 6;
const int buttonMove = 2;
const int buttonPlusCounter = 3;
const int buttonMinusCounter = 4;
int buttonStateMove = 0;
int buttonStateCounterPlus = 0;
int buttonStateCounterMinus = 0;
double Counter = 1;
double v = 1; //Variable
double m = 0.1; //Modifier

void setup() {
  Serial.begin(9600);
  pinMode(buttonMove, INPUT);
  pinMode(buttonPlusCounter, INPUT);
  pinMode(buttonMinusCounter, INPUT);
  pinMode(in_1, OUTPUT);
  pinMode(in_2, OUTPUT);
}

void loop() {
  buttonStateMove = digitalRead(buttonMove);
  buttonStateCounterPlus = digitalRead(buttonPlusCounter);
  buttonStateCounterMinus = digitalRead(buttonMinusCounter);
  if (buttonStateCounterPlus == HIGH) {
    v = v + 1;
    Counter = m*(v*v);
    Serial.print ("Mudança de progressão de movimento para ");
    Serial.println (Counter);
    Serial.print ("ms");
    delay (500);
  }
  if (buttonStateCounterMinus == HIGH) {
    v = v - 1;
    Counter = m*(v*v);
    Serial.print ("Mudanca para ");
    Serial.println (Counter);
    delay (500);
  }
  if (buttonStateMove == HIGH){
    //delay (500);
     //MOTOR DIRECTION 01 V01
    digitalWrite(in_1, HIGH);
    digitalWrite(in_2, LOW);
    delay (Counter);
    //stop
    digitalWrite(in_1, LOW);
    digitalWrite(in_2, LOW);
    delay (1000);
    Serial.print ("Movimento a ");
    Serial.println (Counter);
    Serial.print ("ms");
  }
}
