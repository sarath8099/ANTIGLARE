# ANTIGLARE

# Real-Time Anti-Glare Image Enhancement System

This project implements a real-time anti-glare using TensorFlow and advanced image processing techniques. The system enhances visibility in glare-polluted images by dynamically removing glare and restoring image quality with high precision. It is suitable for applications in Advanced Driver Assistance Systems (ADAS) and autonomous vehicles.

---

## Features

- **Flare Removal**: Efficiently removes flare artifacts in images using gamma correction.
- **Light Source Blending**: Retains and enhances critical light sources for natural image restoration.
- **Edge Detection and Restoration**: Detects and restores edges in images using custom Sobel filters.
- **Contrast and Brightness Analysis**: Calculates contrast improvement and brightness consistency to assess performance.
- **Batch Processing**: Processes a specified number of images from an input folder in batches.
- **Visualization**: Displays input and processed images side-by-side with metrics like edge improvement and brightness consistency.

---

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your_username/real-time-anti-glare.git
    cd real-time-anti-glare
    ```
2. Install required dependencies:
    ```bash
    pip install tensorflow matplotlib numpy
    ```

3. Ensure you have the required trained model and input images:
    - Place the TensorFlow model in the `model_path`.
    - Store input images in a folder specified as `input_folder`.

---

## Usage

1. **Input Data**:
    - Prepare a folder containing input images in `.jpg`, `.png`, or `.jpeg` formats.

2. **Run the Code**:
    ```bash
    python main.py
    ```

3. **Processed Outputs**:
    - The script processes the input images and outputs enhanced images with metrics such as edge improvement, contrast improvement, and brightness consistency displayed.

---

## Key Functions

### Main Functions:

1. **`remove_flare()`**:
   - Removes flare from the image in linear space using gamma correction.

2. **`blend_light_source()`**:
   - Blends the suspected light source from the input into the processed image.

3. **`process_one_image()`**:
   - Processes a single image by removing flare and restoring clarity.

4. **`process_images()`**:
   - Processes a batch of images from the input folder.

5. **`display_images_side_by_side()`**:
   - Visualizes input and output images along with computed improvement metrics.

### Metrics Functions:

- **`detect_edges()`**: Detects edges in an image using custom Sobel filters.
- **`calculate_edge_change_percentage()`**: Calculates the percentage change in edge density between input and output images.
- **`calculate_contrast()`**: Computes RMS contrast for the input and output images.
- **`calculate_brightness_consistency()`**: Measures the percentage change in brightness consistency.

---

## Model Integration

The code loads the trained TensorFlow model using the `TFSMLayer`. Ensure the model is placed in the specified path:
```python
model = tf.keras.layers.TFSMLayer('path_to_model', call_endpoint='serving_default')
```

---

## Example Output

### Metrics Displayed:

- **Brightness Consistency Improvement**: Measures how well brightness is maintained.
- **Edge Detection Improvement**: Quantifies the clarity of edge restoration.
- **Contrast Improvement**: Highlights the enhancement in image contrast.

---

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for new features or bug fixes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

For questions or suggestions, contact [your_email@example.com].
