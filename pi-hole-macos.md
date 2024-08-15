# How to use Pi-Hole on MacOS

1. Install Intel or Apple Silicon versions of Docker:
- [Apple Silicon Download](https://desktop.docker.com/mac/main/arm64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-mac-arm64)
- [Intel Download](https://desktop.docker.com/mac/main/arm64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-mac-arm64)

2. Double-click the `.dmg` to install

3. Open the docker app then minimize it (you shouldn't need it after it is open)

4. Open up the macOS Terminal and enter the below commands:

    Install homebrew:<br/>
      `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
    
    Install Docker Command Line Interface:<br/>
      `brew install docker`
    
    Download and install Pi Hole using docker:<br/>
      `docker run -p 80:80 pihole/pihole`


5. In your web browser, type the following into the URL Address bar:<br/>
  `localhost/admin`

6. Login (you might only be prompted for password): <br/>
    - Username: `pi-hole`
    - Password: `pi-hole`
  
7. Select `Local DNS` in the Side Nav and enter your own records

8. Get macOS IP using the below command:

     `ifconfig | grep "inet " | grep -v 127.0.0.1 | awk '{print $2}' | head -n 1`

9. Use the resulting IP as the DNS for each device
