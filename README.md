AI-Based Face Recognition Attendance System
Github link-https://github.com/varshah10/AI-based-Attendence-System.git

Automating attendance with computer vision and real-time face recognition.

A webcam-based system that identifies registered students using the LBPH algorithm and records their attendance (name, roll number, date and time) in a CSV file. It is controlled through a simple Flask web interface.

Status: Prototype for controlled environments such as classrooms and offices.

Table of Contents
Problem
Features
How It Works
Tech Stack
Project Structure
Installation
Usage
Testing
Limitations
Future Improvements
Author
Problem

Manual attendance (roll calls and paper registers) takes class time and depends on human effort. It can lead to missing entries, incorrect records, duplicate entries and proxy attendance. This project replaces that process with an automated, contactless one.

Features
Student registration: enter a name and roll number, then capture multiple face images from the webcam
Organized dataset: images are stored in folders named by roll number
Model training: trains an LBPH face recognition model and saves it for reuse (no retraining on every start)
Live recognition: detects and identifies faces from the webcam feed in real time
Attendance logging: saves name, roll number, date and time to a CSV file
Duplicate prevention: a student is marked only once per session
Unknown face handling: unregistered faces are ignored and no attendance is recorded
Web dashboard: capture images, train the model and mark attendance from the browser
How It Works
Webcam
Face Detection
Dataset / Trained Model
Face Recognition
Student Identified
Attendance Validation
CSV Record
Register: the admin enters student details and the webcam captures face images.
Train: the dataset is used to train the LBPH model, which is saved to a file.
Recognize: the trained model is loaded and compares faces from the live feed with registered students.
Record: on a match, the attendance manager checks for duplicates and writes a new row to the CSV file.
Tech Stack
Technology	Purpose
Python	Backend logic and face recognition workflow
OpenCV	Face detection and image processing
LBPH	Face recognition algorithm
NumPy	Numerical operations and image data handling
Flask	Web interface and frontend-backend communication
CSV	Attendance record storage
Project Structure

Edit this section to match your actual folders and file names.

face-recognition-attendance/
├── app.py                 # Flask application
├── dataset/               # Captured images, one folder per roll number
├── trainer/               # Saved trained model file
├── attendance/            # Attendance CSV files
├── templates/             # HTML pages for the web interface
├── static/                # CSS and JavaScript
├── requirements.txt
└── README.md
Installation

Requirements: Python 3.8+ and a working webcam.

bash
# 1. Clone the repository
git clone https://github.com/varshah10/AI-based-Attendence-System.git
cd AI-based-Attendence-System

# 2. (Optional) Create a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux

# 3. Install dependencies
pip install opencv-contrib-python numpy flask

LBPH is part of the opencv-contrib-python package, so install that one instead of plain opencv-python.

Usage

Replace app.py with your actual entry file if it is different.

bash
python app.py

Then open http://127.0.0.1:5000 in your browser and follow these steps:

Register a student: enter the name and roll number, then capture images.
Train the model: click the train button after adding students (retrain whenever you add new ones).
Mark attendance: start attendance. Registered students are recognized and saved to the CSV file.
Testing
Level	What was checked
Unit	Dataset creation, model training, attendance module
Integration	Captured data flows into training; the trained model works for attendance
System	Full real-time workflow with a webcam

Test cases covered dataset creation, model-file generation, recognition of registered students, attendance with date and time, duplicate prevention and unknown-face handling. All documented test cases passed under controlled conditions.

Limitations
Recognition can be affected by lighting conditions
Results depend on dataset quality and camera quality
Tested only in a controlled prototype setting
Future Improvements
Store records in a database instead of CSV files
Test with a larger and more varied dataset
Add liveness detection to prevent photo-based spoofing
Add attendance reports and export options
Author
Varsha Yadav | LinkedIn- https://www.linkedin.com/in/varshah-yadav | Github- varshah10

Varsha Yadav | LinkedIn- https://www.linkedin.com/in/varshah-yadav | Github- varshah10

