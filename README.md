# MATLAB Crystal Dataset Creation Tool

A MATLAB App Designer GUI created to accelerate the process of building an image dataset for machine learning. This app allows a user to load a video file, navigate through its frames, and interactively crop specific objects (e.g., crystals) to save them as individual image files.

---

### **Table of Contents**
1.  [Overview](#overview)
2.  [App Functionality](#app-functionality)
3.  [Prerequisites](#prerequisites)
4.  [How to Use](#how-to-use)
5.  [UI Elements](#ui-elements)
6.  [Git Repository Setup](#git-repository-setup)

---

## Overview

Training a computer vision model requires a large, well-labeled dataset. Manually creating this dataset by capturing, separating, and cropping images is tedious and time-consuming. This application streamlines the workflow by leveraging video recordings. A user can record a video of multiple crystals, and then use this tool to quickly extract high-quality, tightly-cropped images of each one, making dataset creation significantly faster.

![Screenshot of the app interface](assets/app-screenshot.png)

---

## App Functionality

* **Load Video**: Supports common video formats (`.mp4`, `.avi`, `.mov`).
* **Frame Navigation**: Navigate through video frames using a slider for quick seeking or next/previous buttons for precise, frame-by-frame control.
* **Interactive Cropping**: Interactively draw a rectangle on the video frame to select the exact region of interest. The app is robust against misclicks on other UI elements during the cropping process.
* **Custom Output Folder**: Choose and set any destination folder for the saved image files.
* **Session Counter**: Keep track of how many images have been cropped and saved during the current session.

---

## Prerequisites

To run this application, you will need:

1.  **MATLAB** (Recommended: R2020a or newer)
2.  **Image Processing Toolbox™** (This is essential for video reading and `imcrop` functionality)

---

## How to Use

1.  Clone or download this repository to your local machine.
2.  Open MATLAB and navigate to the project's root folder.
3.  Open the `.mlapp` file (e.g., `CrystalCropperGUI.mlapp`). This will launch the MATLAB App Designer.
4.  Click the **Run** button in the App Designer's toolbar.
5.  **Set Output Folder**: Click the "Set Output Folder" button to choose where your cropped images will be saved. It defaults to a `Cropped_Crystals` folder in the project directory.
6.  **Load Video**: Click the "Load Video" button and select your video file. The first frame will appear.
7.  **Navigate**: Use the slider or the "Next" / "Previous" buttons to find a frame with a clear view of a crystal. Use the built-in axes zoom tools if needed.
8.  **Crop Crystal**: Click the "Crop Crystal" button. Your cursor will change to a crosshair. Click and drag a box around the crystal.
9.  **Confirm Crop**: Once the rectangle is drawn, click the "Confirm Crop" button. The selected area will be saved as a `.png` file with a unique, timestamped name in your chosen output folder. The on-screen counter will update.
10. Repeat steps 7-9 to continue building your dataset.

---

## UI Elements

The application interface is composed of the following main components:

| Component                 | Functionality                                                               |
| ------------------------- | --------------------------------------------------------------------------- |
| **Set Output Folder Button** | Opens a dialog to select the destination folder for saved images.           |
| **Output Folder Field** | A read-only field that displays the current save path.                      |
| **Load Video Button** | Opens a file dialog to select a video. Resets the session counter.          |
| **Main Display (UIAxes)** | Displays the current video frame where all interactions take place.         |
| **Frame Slider** | Allows for quick seeking through the video's frames.                        |
| **Previous/Next Buttons** | Provide precise, single-frame navigation.                                   |
| **Crop Crystal Button** | Activates the drawing mode to let you select a rectangular region.          |
| **Confirm Crop Button** | Confirms the selection, performs the crop, saves the image, and updates the counter. |
| **Crystals Saved Label** | Displays the number of images saved in the current session.                 |

---

## Git Repository Setup

This repository includes a `.gitignore` file. This file is configured to intentionally ignore the default `Cropped_Crystals/` folder. This prevents the large number of generated image files from being accidentally committed to the Git repository. If you use a custom output folder, it is recommended that you add its name to the `.gitignore` file as well.
