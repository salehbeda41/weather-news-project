# Weather and News Data Analysis Project

## Overview

This project integrates data from two APIs — OpenWeatherMap and NewsAPI — to retrieve and visualize weather information and news headlines from different cities worldwide. The program fetches data using HTTP requests, processes and combines it, and then visualizes the results in a bar chart showing current temperatures across selected cities. It also stores the processed data in a JSON file for further analysis or archival.

## Approach

### 1. **API Setup and Configuration**
   - **Environment Variables**: We used `python-dotenv` to load sensitive API keys securely from a `.env` file. This ensures that keys are not hardcoded in the script, enhancing security and flexibility.
   - **API Integration**: Two APIs were utilized:
     - **OpenWeatherMap API**: Provides real-time weather data for different cities.
     - **NewsAPI**: Fetches the top news headlines based on the country code of the city.
   - The API requests were made using the `requests` library, and the responses were handled as JSON objects, making it easy to extract necessary information like temperature, weather descriptions, and headlines.

### 2. **Data Processing**
   - **Weather Data Extraction**: The application collects weather data such as the city name, temperature, and weather description (e.g., "clear sky").
   - **News Data Extraction**: Using the country code from the weather data, the application retrieves the top 3 headlines for each country associated with the city.
   - **Data Combination**: A function called `process_data()` combines the weather and news data into a structured dictionary format, simplifying further usage and visualization.

### 3. **Data Visualization and Storage**
   - **Visualization**: The application uses **Matplotlib** to create a bar chart of temperatures across the chosen cities. The chart provides a quick and clear visual summary of the current temperatures in each city.
   - **Data Storage**: The processed data, which includes weather and news information, is saved into a JSON file (`weather_news_data.json`). This allows for easy storage and retrieval for any subsequent analysis.

### 4. **Error Handling**
   - The application implements basic error handling for HTTP requests to manage situations like invalid responses, network issues, or incorrect API configurations. If an error occurs while fetching data for a city, the application prints an error message but continues processing the next city, ensuring robustness.

## Findings

1. **Weather Insights**:
   - The temperatures of the selected cities (e.g., New York, London, Tokyo, Sydney, and Mumbai) varied significantly, reflecting different climatic zones and current weather patterns. The bar chart clearly highlights these differences.
   
2. **News Headlines**:
   - For each city, the top news headlines provide a snapshot of the current events happening in that country. This combination of weather and news data gives a contextual overview, making the application useful for real-time monitoring or travel preparation.

## Reflections

### Achievements
   - The project successfully demonstrated how to integrate and use external APIs to collect, process, and visualize data.
   - It also reinforced important programming practices such as **environment variable management**, **error handling**, and **data visualization** using Python libraries.

### Challenges
   - API Rate Limits: During testing, the rate limits of the APIs were a constraint. Managing these efficiently would be crucial if scaling the application to include more cities or frequent updates.
   - Handling Incomplete or Missing Data: If the API returns incomplete information (e.g., a city has no news coverage), future iterations could include more advanced data validation and fallback options.

### Future Improvements
   - **Enhanced Visualization**: Additional charts (e.g., weather trends over time) and interactive features using libraries like Plotly could be added to make the visualizations more engaging.
   - **Cache Implementation**: To reduce API calls and optimize performance, a caching mechanism could be integrated, storing data for a specified period before making new requests.
   - **Scalability**: Expanding the project to cover more cities, countries, and other types of data (like air quality) would increase its usefulness as a monitoring tool.

## Conclusion

This project serves as an excellent example of how APIs can be leveraged to gather, process, and present real-time data in a meaningful way. It offers valuable insights into API handling, data manipulation, and visualization, all of which are fundamental skills in data science and software development. Further enhancements could turn this into a powerful, scalable application for tracking global weather and news data.

---

### Installation and Usage Instructions
To run the project, ensure you have the required dependencies installed:
```bash
pip install requests pandas matplotlib python-dotenv
```

Save your API keys in a `.env` file as follows:
```
OPENWEATHER_API_KEY=your_openweather_api_key
NEWS_API_KEY=your_news_api_key
```

Run the main script using:
```bash
python main.py
```

This will generate a bar chart visualizing the temperature data and save the processed information in a `weather_news_data.json` file.