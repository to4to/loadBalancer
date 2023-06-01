# Go Load Balancer

Go Load Balancer is a simple load balancer implementation in Go that distributes incoming HTTP requests among multiple servers. It helps to evenly distribute the workload across multiple servers, improving performance and availability of the system.

## Features

- Round-robin Load Balancing: The load balancer evenly distributes incoming requests among the available servers in a round-robin fashion.
- Reverse Proxy: It utilizes the `net/http/httputil` package to implement reverse proxy functionality, forwarding incoming requests to the selected server.
- Server Monitoring: The load balancer keeps track of server availability and skips any servers that are not alive, ensuring only active servers are selected for requests.

## Usage

1. Clone the repository:

   ```shell
   git clone <repository-url>
   
   
Navigate to the project directory:
  cd go-load-balancer
  
Build and run the load balancer:
   go run main.go

This will start the load balancer and listen for incoming requests on the specified port (default is 8000).


C onfigure Servers:

The load balancer is pre-configured with a list of servers. To add or modify servers, you can update the servers slice in the main function of main.go. Each server is represented by an instance of the simpleServer struct. You can specify the address of each server as a parameter to the newSimpleServer function.

servers := []Server{
    newSimpleServer("https://www.facebook.com"),
    newSimpleServer("https://www.bing.com"),
    newSimpleServer("https://www.duckduckgo.com"),
}




Test the Load Balancer:

Once the load balancer is running, you can test it by sending HTTP requests to the load balancer's address. For example, if the load balancer is running on localhost:8000, you can open a web browser and visit http://localhost:8000 to see the load balancer in action. Each request will be forwarded to one of the configured servers.


Customization:

Port: By default, the load balancer listens on port 8000. You can change the port by modifying the port parameter when creating a new instance of the load balancer in the main function of main.go.

Load Balancing Algorithm: The load balancer uses a simple round-robin algorithm to distribute requests among the available servers. If you want to implement a different load balancing algorithm, you can modify the getNextAvailableServer() method in the LoadBalancer struct.

Error Handling: The load balancer includes basic error handling for URL parsing and server availability. You can customize the error handling logic by modifying the handleErr() function.


Customization:

Port: By default, the load balancer listens on port 8000. You can change the port by modifying the port parameter when creating a new instance of the load balancer in the main function of main.go.

Load Balancing Algorithm: The load balancer uses a simple round-robin algorithm to distribute requests among the available servers. If you want to implement a different load balancing algorithm, you can modify the getNextAvailableServer() method in the LoadBalancer struct.

Error Handling: The load balancer includes basic error handling for URL parsing and server availability. You can customize the error handling logic by modifying the handleErr() function.
