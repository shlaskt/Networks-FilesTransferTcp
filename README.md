# filesTransferTcp

**Implementation of a simple file sharing network**   
To do this, we implemented two parts- Server and Client, using TCP only.  
The actual file transfer is directly between clients.  

**Server Api:**  
Client that want to connect the server, send message in the format: "1 [Port] [Files]" . 
When the port is the client's port, and the files are a list of files that the client want to share.  

Client that want to search for a file, send message in the format: "2 [Search]" . 
When the Serach is a string or a sub-string of the file's name.  
The server send back to the client a list with all the files and the relevant clients data, in this format: "[Name] [IP] [Port],...,[Name] [IP] [Port]\n" . 

**Notice** - the server handle only one client every time (no multy-threading) . 

**Client:**  
Client can search files (client behaviour) or share files (server behaviour) .  
If you run the client with first arg "0" - the client will act like server .  
In that case, the client share all the files in the current directory.  
 
If you run the client with first arg "1" - the client will act like client .   
In that case, client need to input the text he is searching. then he will get a sorted list of the matching files.     
Then the user need to choose the file, and it will sent to he's directory (from the relavent client).   

**What to run?** .   
Server: "python3 server.py [server port]" .   
Client mode 0: "python3 client.py 0 [server ip] [server port] [client port]" .   
Client mode 1: "python3 client.py 1 [server ip] [server port]" .   

