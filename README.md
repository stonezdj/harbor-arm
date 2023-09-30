# harbor-arm
Build Harbor for arm architecture.


## Build
<hr>

**System Requirements:**

**On a Linux host**: docker 19+  and support docker buildx

Before you build the harbor arm image, you need to check if your local environment supports docker buildx

By running the command `docker buildx ls`，If the result shows `linux/arm64`, it proves that the arm image can be built

## Get Started

1. Install git, make, docker, docker-compose

2. Clone Harbor ARM code
```
git clone https://github.com/goharbor/harbor-arm.git
```

3. Build online package

```
cd harbor-arm 
make all
```

4. Copy the online installer package to the installation directory

```
mkdir -p ~/harbor_latest
cp harbor-online-installer-dev-arm.tgz ~/harbor_latest
```

5. Extract the install package and install Harbor
```
cd ~/harbor_latest
tar xvf harbor-online-installer-dev-arm.tgz
cd harbor
# Generate cert and create the harbor.yml file
./install.sh --with-trivy
```

After installation, then visit the Harbor via URL: https://<Harbor_fqdn>





