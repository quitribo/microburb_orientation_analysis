# Microburbs Property Orientation Analysis

## Overview
This project analyzes property orientation by matching property addresses to cadastral parcels and determining the direction each property faces. The analysis includes spatial operations, data visualization, and output generation for unmatched properties.

## Objectives
- Determine the orientation of each property (e.g., North-facing).
- Match property addresses to cadastral parcels.
- Visualize unmatched properties and analyze potential data gaps.
- Generate a final output file with property addresses and orientations.

## Features
- **Data Loading**: Reads property, cadastral, and road datasets.
- **Spatial Analysis**: Matches properties to cadastral parcels using spatial joins.
- **Orientation Calculation**: Determines property orientation based on the longest edge of cadastral polygons.
- **Visualization**: Plots unmatched properties for further analysis.
- **Output Generation**: Produces a CSV file with property addresses and orientations.

## File Structure
```
project/
├── data/                     # Contains input datasets (GNAF, cadastre, roads)
├── script/                   # Contains analysis scripts and notebooks
│   └── ango_task2_orientation.ipynb  # Main analysis notebook
├── property_orientations.csv # Output file with property orientations
└── README.md                 # Project documentation
```

## Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd microburbs
   ```
3. Install required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Open the Jupyter Notebook `ango_task2_orientation.ipynb`.
2. Follow the steps in the notebook to:
   - Load datasets.
   - Perform spatial analysis.
   - Visualize unmatched properties.
   - Generate the output file.
3. The final output file `property_orientations.csv` will be saved in the project directory.

## Data Sources
- **GNAF**: Contains property address data with latitude and longitude coordinates.
- **Cadastre**: Provides property boundary polygons.
- **Roads**: Represents the road network (not used in this analysis).

## Key Functions
- `calculate_orientation`: Computes the orientation of cadastral parcels based on the longest edge.
- `bearing_to_orientation`: Converts numerical bearings into compass directions.
- `gpd.sjoin`: Matches property points to cadastral polygons.

## Output
- **property_orientations.csv**: Contains the following columns:
  - `gnaf_pid`: Unique property identifier.
  - `address`: Property address.
  - `orientation`: Compass direction (e.g., North, East).
  - `bearing_degrees`: Bearing in degrees (rounded to 1 decimal place).

## Visualization
The notebook includes visualizations to:
- Compare unmatched properties with cadastral parcels.
- Analyze the distribution of property orientations.

## Conclusion
This project successfully determines property orientations for most properties. Unmatched properties are visualized for further investigation to address data gaps or coordinate mismatches.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
- Geopandas for spatial data analysis.
- Matplotlib for data visualization.
- GNAF and cadastral datasets for providing essential data.

---

Feel free to contribute to this project by submitting issues or pull requests!
