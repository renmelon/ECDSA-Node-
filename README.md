# ECDSA-Node-

This project is an example of using a client and server to facilitate transfers between different addresses. Since there is just a single server on the back-end handling transfers, this is clearly very centralized. We won't worry about distributed consensus for this project.

However, something that we would like to incorporate is Public Key Cryptography. By using Elliptic Curve Digital Signatures we can make it, so the server only allows transfers that have been signed for by the person who owns the associated address.

Results

The application allows you to sign monetary transactions using the user's private key. Then, the server verifies that the signature is correct and extracts the address of the sender to modify the account balances.

Cryptography module

For this project, a typescript cryptography module was created with the following functions:

function hashMessage(message: string) : Uint8Array

async function signMessage(message: string, privateKey: Uint8Array) : Promise<[string, number]>

function getAddress(publicKey: Uint8Array): string

function recoverKey(message: string, signature: string, recoveryBit: number): Uint8Array

function authenticate(message: string, signature: string, recoveryBit: number): [boolean, string]
The objective of the module is to provide the UI and the server with the same cryptographic functions so that they can communicate securely.

Get started

Video instructions

For an overview of this project as well as getting started instructions, check out the following video:

https://www.loom.com/share/0d3c74890b8e44a5918c4cacb3f646c4

Client

The client folder contains a react app using vite. To get started, follow these steps:

Open up a terminal in the /client folder
Run npm install to install all the dependencies
Run npm run dev to start the application
Now you should be able to visit the app at http://127.0.0.1:5173/
Server

The server folder contains a node.js server using express. To run the server, follow these steps:

Open a terminal within the /server folder
Run npm install to install all the dependencies
Run node index to start the server
The application should connect to the default server port (3042) automatically!

Hint - Use nodemon instead of node to automatically restart the server on any changes.
