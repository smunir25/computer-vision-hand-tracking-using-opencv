# Hand Tracking using OpenCV

A computer vision project that performs real-time hand landmark detection and tracking using **OpenCV** and **MediaPipe**. Supports both live webcam feed and pre-recorded video files, with FPS display and annotated hand landmark overlays.

## Features

- Real-time hand tracking via webcam with FPS counter
- Video file mode: processes an input `.mp4` and writes annotated output video
- Detects and visualizes all 21 hand landmarks using MediaPipe Hands
- Highlights the wrist landmark (id=0) with a filled circle
- Draws full hand skeleton connections using MediaPipe's drawing utilities

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| OpenCV | Video capture, frame processing & display |
| MediaPipe | Hand landmark detection model |

## Project Structure

```
hand-tracking-using-opencv/
├── app.py                          # Real-time webcam hand tracking
├── Hand Tracking from Media .py    # Video file hand tracking with output writer
├── requirements.txt                # Python dependencies
└── Data Sources and Artifacts/     # Sample input/output video files
```

## Getting Started

### Prerequisites

- Python 3.7+
- A webcam (for `app.py`)

### Installation

```bash
git clone https://github.com/smunir25/computer-vision-hand-tracking-using-opencv.git
cd computer-vision-hand-tracking-using-opencv
pip install -r requirements.txt
```

### Run Webcam Tracking

```bash
python app.py
```

- Shows live webcam feed with hand landmarks overlaid
- Displays FPS in the top-left corner
- Press **Q** to quit

### Run Video File Tracking

```bash
python "Hand Tracking from Media .py"
```

- Set `video_path` in the script to your input video file
- Outputs annotated video as `output_video.mp4`
- Press **Q** to stop early

## How It Works

1. Each video frame is converted from BGR to RGB
2. MediaPipe Hands processes the frame and returns landmark coordinates
3. Landmarks are mapped back to pixel coordinates and drawn on the original frame
4. The wrist landmark (index 0) is highlighted with a magenta filled circle
5. Full hand skeleton is rendered using `mpDraw.draw_landmarks`

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
