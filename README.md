# beacon

Remote beacon for sharing your pipboy data.

```
PipBoy Electron App <--- | ---> Fallout 4
                         |
                        \/
                      Beacon  --> friend1
                              --> friend2
                              --> dev calling API
```

## Roadmap

### Client side relay

From, e.g., [the pipboy Electron app](https://github.com/rgbkrk/pipboy), send the pip boy data on to a remote server we'll call a beacon.

* Generate public and private key pairs for sending data to beacon
* Encrypt the data
* Launch a fully configured beacon server that uses the public/private key pairs appropriately to accept data
* Send data on to the beacon

### Server side beacon

The beacon itself is all about ease of running and providing data.

* Boot up with configured public/private key pairs
* Opens up a port specifically for authenticated operations
* Receieve raw TCP data on the authenticated channel
* Publish the raw data on a TCP port
* Provide JSON endpoints for others to make mashups
* Provide both Server Sent Events and a long polling JSON API
