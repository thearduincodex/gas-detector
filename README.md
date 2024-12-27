// Define the analog pin connected to the MQ2 sensor
const int gasSensorPin = A0; // MQ2 sensor output connected to analog pin A0

// Threshold value for gas concentration
const int gasThreshold = 400; 

void setup() {
  // Start the Serial Monitor for debugging
  Serial.begin(9600);
  Serial.println("MQ2 Gas Sensor Test");
}

void loop() {
  // Read the analog value from the MQ2 sensor
  int gasValue = analogRead(gasSensorPin);
  
  // Print the gas value to the Serial Monitor
  Serial.print("Gas Value: ");
  Serial.println(gasValue);

  // Check if the gas value exceeds the threshold
  if (gasValue > gasThreshold) {
    Serial.println("Gas detected! Take action!");
    // You can add actions here, like turning on a buzzer or LED
  }

  // Wait 500ms before the next reading
  delay(500);
}
