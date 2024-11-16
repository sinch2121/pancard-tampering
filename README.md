PAN Card Tampering Detection Using Computer Vision

Overview

The PAN Card Tampering Detection project is a computer vision-based solution designed to help organizations verify the authenticity of PAN cards provided by their employees. This project enables organizations to check if the PAN card provided by an employee matches an original reference image, offering instant results without the need for external verification systems.

Objective

Organizations typically verify PAN card details through online systems, often linked with Aadhaar card databases. This project simplifies the process by providing a direct, automated way to identify tampered PAN cards using image comparison techniques.

Key Features

1. Accepts user-provided PAN card images for comparison.
2. Resizes and formats images to match standard requirements.
3. Applies computer vision techniques to analyze and compare images.
4. Provides a similarity score to indicate tampering.
5. How It Works
6. The project processes two images: a reference (original) PAN card image and the PAN card image provided by the employee. By performing a series of image processing steps, the application checks the similarity between the images and determines if any tampering has occurred.

Project Workflow

1. Get Images from User
The system prompts the user to upload an image of the original PAN card and the PAN card provided for verification.
The input images are read using Python image-processing libraries such as OpenCV.
2. Check for Image Size and Format
The uploaded images are checked for valid file formats (e.g., .jpg, .png).
The images must meet the required size and resolution criteria for further processing.
3. Resize and Shape Adjustment
The uploaded images are resized and adjusted to a standard shape and size to match the dimensions of the reference PAN card.
This step ensures uniformity and proper alignment for accurate comparison.
4. Convert Image to Grayscale
The images are converted to grayscale to simplify processing and enhance the effectiveness of comparison.
Grayscale conversion reduces computational complexity by handling only the intensity information of the pixels.
5. Calculate the Similarity Index
The similarity index between the two images is calculated using methods like Structural Similarity Index (SSIM).
SSIM helps quantify how similar the two images are on a scale from 0 to 1, where 1 indicates identical images.
6. Apply Thresholding
Thresholding is applied to identify significant differences between the images.
This process highlights areas of potential tampering by making the differences more visible.
7. Contour Detection Using IMUTILS
Contours are detected in the thresholded image using imutils, a Python library for image processing.
These contours represent areas in the image that may differ from the original and need further inspection.
8. Draw Bounding Rectangles
A bounding rectangle is drawn around detected contours to indicate areas that may have been altered.
This visualization helps identify specific regions where tampering may have occurred.
9. Display Results

The project plots and displays the following:
Original image
Tampered image (uploaded by the user)
Thresholded image showing differences
Image with contours and bounding rectangles
The differences are visually represented to help users see where potential tampering has occurred.
11. Compare and Output Similarity Score
The images are compared, and a similarity score is generated to indicate the level of tampering.
A high similarity score close to 1 suggests minimal or no tampering, while lower scores indicate discrepancies.

Libraries and Technologies Used

Python: The primary programming language used for the project.
OpenCV: Used for image processing and analysis.
imutils: Simplifies basic image processing functions.
PIL import Image - for downloading images
import requests - for pulling necessary requests from URLs

How to Run the Project

Prerequisites
Ensure you have Anaconda installed to create and manage your environment.

Installation Steps

Clone the Repository

bash
Copy code
git clone https://github.com/yourusername/pan-card-tampering.git
cd pan-card-tampering
Create a New Conda Environment

bash
Copy code
conda create --name pan_tampering python=3.x
Activate the Environment

bash
Copy code
conda activate pan_tampering
Install Required Dependencies

bash
Copy code
python -m pip install -r requirements.txt
Run the Application

bash
Copy code
python app.py
Access the Web Application

Copy the URL displayed in the terminal (e.g., http://127.0.0.1:5000/) and paste it into your web browser.
Sample Data
A sample_data folder is included in the repository with images for testing. Use these images to try out the application and see how it detects tampering.

License
This project is open source and available. 

