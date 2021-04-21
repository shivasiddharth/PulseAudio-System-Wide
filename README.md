# PulseAudio-System-Wide
 Git to help you setup pulse audio as a system wide service. this has been tested and found to work on Raspberry Pi

## Run the following commands one after another. ```sudo``` should be used only where indicated.            
```
sudo apt-get update     
sudo apt-get install git    
cd /home/${USER}/       
git clone https://github.com/shivasiddharth/PulseAudio-System-Wide       
cd ./Pulseaudio-System-Wide/      
sudo cp ./pulseaudio.service /etc/systemd/system/pulseaudio.service    
systemctl --system enable pulseaudio.service       
systemctl --system start pulseaudio.service       
sudo cp ./client.conf /etc/pulse/client.conf        
sudo sed -i '/^pulse-access:/ s/$/root,pi/' /etc/group    
```     
All done. Now you should have PulseAudio as a system service.     
