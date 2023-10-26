# Location Tracking Application


1. **Tracker**: The hardware component responsible for tracking the location.
2. **Tracker-API**: The Node.js server for receiving, storing, and serving location data.

## Tracker

### Project Structure
```
Tracker/
│
├── client.h          # Header file for handling Wi-Fi client connection
├── gps.h             # Header file for GPS module interfacing
├── Tracker.ino       # Main Arduino sketch for location tracking
└── wifi.h            # Header file for Wi-Fi setup
```

### Instructions
1. Load the `Tracker.ino` sketch onto your ESP8266 microcontroller using the Arduino IDE or any suitable programming environment.

2. Ensure that you have the necessary libraries for the ESP8266 and the uBlox NeoV6 GPS module installed.

3. Update the Wi-Fi credentials in `wifi.h` and other configuration parameters as needed.

4. Flash the ESP8266 with the sketch, and the tracker will start sending location data to the API.

## Tracker-API

### Project Structure
```
Tracker-API/
│
├── app.js            # Main Node.js application file
├── auth.json         # JSON file for authentication secrets (e.g., API keys)
├── config.json       # JSON file for configuration settings
├── firebase.json     # Firebase configuration (if applicable)
├── package.json      # Node.js package dependencies
├── package-lock.json # Dependency lock file
├── public/           # Directory for the frontend web application
```

### Instructions
1. Navigate to the `Tracker-API` directory.

2. Install the Node.js dependencies by running the following command:
   ```
   npm install
   ```

3. Configure the application by modifying the `config.json` and `auth.json` files to specify your API settings, including database connection and any secret keys required for secure communication.

4. If you plan to display the data on a webpage using the Google Maps SDK, you can create a frontend in the `public` directory.

5. Start the Node.js server by running:
   ```
   node app.js
   ```

The API is now up and running, ready to receive location data from the tracker and serve it to the frontend.

## Notes
- Make sure that your ESP8266 is properly connected to the uBlox NeoV6 GPS module and that you have a Wi-Fi connection available for the tracker.

- You can extend the frontend in the `public` directory to display location data on a webpage using the Google Maps SDK or any other visualization method of your choice.

- For security, it's important to protect the API with proper authentication and secure communication methods, especially if the location data is sensitive.

- This is a basic setup, and you can expand the functionality by adding features such as real-time tracking, geofencing, and more.
