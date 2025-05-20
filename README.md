# IoT Doorbell Notification System

This project is a smart doorbell system that integrates an Arduino-based sensor with an AWS Lambda function to send real-time notifications using Amazon SNS.

## 📦 Components

- **Arduino/ESP device** with a button/sensor (`project.ino`)
- **AWS Lambda Function** to send notifications (`lamda.txt`)
- **Amazon SNS** Topic for broadcasting messages

---

## 🛠️ Setup

### 1. Arduino/ESP Microcontroller

- Upload the `project.ino` code to your device.
- Ensure the device connects to Wi-Fi and triggers a cloud event (e.g., via AWS IoT, HTTP request, or MQTT) on button press.

### 2. AWS SNS Topic

- Create an SNS Topic in **us-east-1**
- Add at least one subscription (e.g., email or SMS).
- Copy the **Topic ARN** and insert it into the `topic_arn` field in `lamda.txt`.

### 3. Lambda Function (Python)

1. Use the code in `lamda.txt`.
2. Make sure your Lambda function has the correct IAM permissions for `sns:Publish`.
3. Deploy the function and set a trigger (e.g., API Gateway or AWS IoT Rule).
