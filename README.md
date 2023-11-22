# DoraCMS Verification Code Reuse

## Vulnerability Description
In the DoraCMS backend, when logging in by entering the account and password, the verification code can be reused. This allows for a weak password brute-force attack using the same verification code multiple times.

## Affected Versions
DoraCMS version 2.1.8

## Source Code Download Link
https://github.com/doramart/DoraCMS
## Environment Deployment Tool
VSCode
## Reproduction Steps:

Access the backend address: http://192.168.184.142:8080/dr-admin
Enter the account 'doracms', followed by the password and verification code. Click on the login button.
![image-20231122142357987](https://github.com/woshinibaba222/.github.io-/assets/55568679/600b25db-054a-426e-8858-e63546ce3ec9)
To capture the request using Burp Suite:
![image-20231122142530751](https://github.com/woshinibaba222/.github.io-/assets/55568679/e9f7e9f3-1e7b-4ffc-b3e1-b7d83f6ce408)
To use Burp Suite Intruder for password brute-forcing:
![image-20231122142615538](https://github.com/woshinibaba222/.github.io-/assets/55568679/74cd91d7-d803-4c1c-a879-e30f588e3da0)
When incorrect passwords can still be used for brute-force attacks, it indicates that the verification code can be reused.
![image-20231122142654813](https://github.com/woshinibaba222/.github.io-/assets/55568679/fbc3fe82-0f65-4740-8634-04d79bf83d7d)
![image-20231122142825069](https://github.com/woshinibaba222/.github.io-/assets/55568679/f3223b4e-4ac7-44d1-88da-a3f2e48198ad)
![image-20231122142844694](https://github.com/woshinibaba222/.github.io-/assets/55568679/8996ca4d-a5d8-4a6f-8a78-e1d591b86903)
At the 50th attempt, the login was successful.
![image-20231122142909391](https://github.com/woshinibaba222/.github.io-/assets/55568679/13e654eb-9739-4817-b3a5-0867c19d2490)
![image-20231122142923502](https://github.com/woshinibaba222/.github.io-/assets/55568679/1b0faec1-0225-4f6d-b223-4f74beea535b)
The entered password is 123456
![image-20231122143726938](https://github.com/woshinibaba222/.github.io-/assets/55568679/e3c5dc0d-eaa6-414f-aa54-5377b545d67f)
Login successful
![image-20231122143743725](https://github.com/woshinibaba222/.github.io-/assets/55568679/d1923bf6-ca55-4ef8-ba92-60e9532a2dfa)

