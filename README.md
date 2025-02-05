# Simple WebSocket Chat Server with Go

This guide will help you set up and understand a simple WebSocket chat server using Go. You'll also learn how to test it using a web browser and Postman.

## 📁 Project Overview
- **Server**: Go program using Gin web framework and Gorilla WebSocket
- **Client**: `index.html` with basic chat interface
- **Features**:
  - Real-time message broadcasting
  - Basic inappropriate word filtering
  - WebSocket communication

## 🛠️ Prerequisites
1. [Go](https://golang.org/doc/install) installed
2. VS Code (or any text editor)
3. Web browser (Chrome/Firefox)
4. [Postman](https://www.postman.com/downloads/) (for testing)

## 🚀 Setup Instructions
### 1. Install Go
```
wget https://go.dev/dl/go1.23.6.linux-amd64.tar.gz
```
```
sudo tar -C /usr/local -xzf go1.23.6.linux-amd64.tar.gz
```
```
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
```
```
source ~/.bashrc
```

### 2. Clone or create the project directory
```
git clone https://github.com/ramymohamed10/25W_CST8916_Chat_Server_using_Go
```

### 3. Install Dependencies
In VS Code terminal:
```bash
go mod tidy
```

### 4. Run the Server
```bash
go run main.go
```
You should see: `WebSocket server running on :8080`

## 🌐 Using the Web Client
### 1. Open index.html in your browser (right-click → "Open with Live Server" in VS Code)
### 2. The chat interface will appear:
- Type messages in the input box
- Press Enter or click Send
- Messages appear in real-time
- Try banned words like "damn" to see filtering

## 🧪 Testing with Postman
### 1. Open Postman → New → WebSocket Request
### 2. Enter URL: `ws://localhost:8080/ws`
### 3. Click `Connect`
### 4. Send messages through the connection:
```
Hello everyone! 
```
```
What's the crap weather today?
```
### 5. Observe responses in both Postman and browser

## 🧠 Understanding the Code
### Server Structure (`main.go`)
1. WebSocket Configuration
   - Allows all origins (for testing)
   - Manages client connections

2. Message Handling
   - Filters banned words
   - Broadcasts messages to all clients

3. Routes
   - /ws → WebSocket endpoint

### Client Structure (`index.html`)
1. WebSocket Connection
   - Connects to `ws://localhost:8080/ws`

2. Message Handling
   - Sends messages on button click/Enter
   - Displays incoming messages with styling
   - Shows warnings for filtered messages

## 🔍 Key Concepts to Explore
- WebSocket protocol vs HTTP
- Goroutine usage for broadcasting
- Message filtering techniques
- Client-server WebSocket communication

## Exercises
1. Identify Key Components:
   - Explain the purpose of Gin in this project.
   - Describe how WebSocket connections are handled.

2. Modify the Code:
   - Add a new banned word to the filter list.
   - Modify the server to log all received messages.

3. Extend the Functionality:
   - Allow users to send their name along with messages.
   - Implement a feature to allow clients to disconnect gracefully.

4. Understanding Goroutines:
   - Explain how goroutines are used in the project.
   - Modify the broadcast function to include a delay and observe the effect.
   - Implement a new goroutine that periodically logs the number of connected clients.

5. Debugging Exercise:
   - Intentionally introduce an error in the server code and debug it.

6. Testing Variations:
   - Use Postman to send WebSocket messages and analyze the responses.
   - Observe what happens when multiple clients connect and send messages simultaneously.

7. Rewriting in a Different Language:
   - Try implementing the WebSocket server in another programming language such as Python, JavaScript (Node.js), or Java.
   - Compare the implementation differences between Go and the chosen language.
   - Discuss the advantages and disadvantages of Go for real-time WebSocket applications.