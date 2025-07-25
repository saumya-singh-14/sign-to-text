# SignSpeak
A real-time, browser-based translator that uses TensorFlow.js and KNN classifier to convert webcam-based hand gestures into text and speech.

## **Project Overview**
This project bridges the communication gap between hearing-impaired individuals who use sign language and those who don't understand it.  
By leveraging machine learning directly in the browser, it translates static hand gestures captured via webcam into text (and optionally, speech) - without requiring a backend server.

## **Features**
- Live training and classification of gestures using KNN
- Runs entirely in the browser (client-side)
- Works in varying lighting conditions
- Copy translated text to clipboard
- Text-to-speech output for recognized gestures
- Extendable to multiple gestures or words
- Video call feature (prototype): communicate using gestures converted to speech

## **Technologies & Libraries Used**
  **TensorFlow.js (deeplearn.js)** : Runs ML models directly in browser; no backend needed                         
  **deeplearn-knn-image-classifier** : Simple and lightweight; perfect for few-shot gesture training                 
  **JavaScript, HTML, CSS** : Enables real-time browser UI and interaction without installation             
  **Webcam API / WebRTC** : Access real-time video stream in browser                                      
  **SpeechSynthesis API** : Converts recognized text into speech                                          

## **Project Workflow**

1. **Webcam Initialization:**  
   Capture real-time video frames in browser.

2. **Feature Extraction:**  
   Each frame is processed through MobileNet (pre-trained CNN) to extract feature vectors.

3. **User-Driven Training:**  
   - Users add labeled examples by clicking “Train” while holding each gesture.
   - These feature vectors + labels are stored in KNN classifier.

4. **Real-time Prediction:**  
   - New frames are passed through MobileNet to extract features.
   - KNN compares them to stored vectors and predicts label based on closest matches.

5. **Display & Speech:**  
   - If prediction confidence > 98%, display the label as text.
   - Optionally use SpeechSynthesis to read it out.

## **Installation & Running**
Clone and run locally in browser:
git clone https://github.com/saumya-singh-14/signspeak.git
cd sign-language-translator/Sign-Language-Translator-newclassifier
npm install
npm start
