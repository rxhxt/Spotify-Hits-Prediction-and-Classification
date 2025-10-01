
# Spotify-Hits-Prediction-and-Classification

This project explores a dataset of Spotify songs from the 1960s to the 2010s to predict song popularity and characteristics through machine learning. By analyzing various audio features, we aim to build models for regression, classification, and clustering tasks.

## The Dataset

The dataset is a compilation of CSV files, each representing a decade of music from the 1960s to the 2010s. It contains 41,106 tracks with 19 features, including:

- **Audio Features**: `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, and `tempo`.
- **Track Information**: `track`, `artist`, `duration_ms`, `key`, `mode`.
- **Target Variables**:
    - `target`: A binary variable indicating if a song is a "hit" (1) or a "flop" (0).
    - `danceability`: A continuous variable used for the regression task.

## Project Objectives & Methodology

The project is structured around three primary machine learning tasks, as detailed in the `final_project.ipynb` notebook.

### 1. Exploratory Data Analysis (EDA)
Before modeling, a thorough EDA was conducted to understand the data's distribution and relationships. Key insights include:
- Most tracks are moderately danceable and energetic (0.4-0.8 range).
- The dataset is dominated by non-acoustic, vocal-heavy studio recordings with low speechiness.
- The tempo is concentrated around 120 BPM, which is common for popular music.

### 2. Regression: Predicting Danceability

*   **Objective**: To predict a song's danceability score based on its other audio features.
*   **Model**: A `LinearRegression` model was trained.
*   **Preprocessing**: Features were scaled using `StandardScaler`.
*   **Evaluation**: The model's performance was evaluated using R² score and Mean Squared Error (MSE), achieving an R² of approximately 0.69.

### 3. Classification: Predicting a "Hit" or "Flop"

*   **Objective**: To classify whether a song will be a "hit" (1) or a "flop" (0) using the `target` variable.
*   **Models**: Several classification algorithms were trained and evaluated:
    - `LogisticRegression`
    - `DecisionTreeClassifier`
    - `RandomForestClassifier`
    - `SVC` (Support Vector Classifier)
    - `KNeighborsClassifier`
*   **Preprocessing**: The dataset was balanced by down-sampling the majority class to handle the 50/50 class distribution. Features were also scaled.
*   **Evaluation**: Models were compared based on accuracy, precision, recall, and F1-score. The `RandomForestClassifier` demonstrated the best overall performance.

### 4. Clustering: Grouping Similar Tracks

*   **Objective**: To group similar songs together based on their audio features, which can be useful for playlist curation and genre analysis.
*   **Methodology**:
    - **Dimensionality Reduction**: `PCA` was used to reduce the feature space to 2 components for visualization.
    - **Optimal Cluster Selection**: The Elbow Method was applied to determine the optimal number of clusters, which was found to be 5.
    - **Clustering**: A `KMeans` model with 5 clusters was trained.
*   **Evaluation**: The clustering performance was assessed using the Silhouette Score and Davies-Bouldin Score. The results indicate a reasonable grouping of songs.

## How to Use

1.  Clone the repository:
    ```bash
    git clone https://github.com/Rohit-Nagotkar/Spotify-Hits-Prediction-and-Classification.git
    ```
2.  Navigate to the project directory and open `final_project.ipynb` in a Jupyter environment.
3.  Ensure the `raw_data/` directory is present with the decade-based CSV files.
4.  Run the notebook cells to see the analysis and model results.
