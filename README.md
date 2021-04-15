# ConnectWiseControlRouterSetup
 How to setup the ConnectWise Control Router service so that each service can listen on the same port.
 
 The setup was originally described on a forum that is no longer available so this repo includes the original forum post.  
 
 I have added a quick powershell script that copies the Relay service into the Router service and renames it appropriately.
Also included is a slightly updated web.config block that must be added and customized depending upon the Control server's current configuration.

        ---------Setup Instructions---------
1.  To create the new service, copy the ScreenConnect Relay service entry (HKLM:\SYSTEM\CurrentControlSet\Services\ScreenConnect Relay) within the registry and rename it to ScreenConnect Router.
2.  Reboot the server.
3.  Add the configuration blocks for the Router service to the web.config file, just below the opening <configuration> block.
4.  Modify the forwardPayload actions to correctly match the current WebServerListenUri and RelayListenUri ports. (Example included in repo)
5.  Save the web.config file.
