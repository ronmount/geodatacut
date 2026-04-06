git clone https://github.com/yichya/xray-geodata-cut.git
cd xray-geodata-cut && go mod tidy && go build -o xray-geodata-cut.exe main.go && mv xray-geodata-cut.exe ../. && cd ..
wget https://github.com/v2fly/geoip/releases/latest/download/geoip.dat
wget https://github.com/itdoginfo/allow-domains/releases/latest/download/geosite.dat
.\xray-geodata-cut.exe -in geoip.dat -keep "ru,private" -out geoip-cut.dat -trimipv6 -type geoip
