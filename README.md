# Janus WebRTC Gateway SDK
Janus WebRTC Gateway SDK is a development suite that facilitiates plugins development. The SDK does not require to compile entire Janus WebRTC Gateway and all its dependencies from scratch.

### Janus WebRTC Gateway plugins develpement on Windows

Install relevant version of the precompiled Janus WebRTC Gateway from:

    https://github.com/marcin-sielski/janus-gateway/releases
    
To setup development environment please follow the guide under following link:

    https://msys2.github.io/
    
Once it is installed open mingw32 or mingw64 shell and install additional MSYS2 tools:

    pacman -S --noconfirm make libtool autoconf automake wget

Download relevant version of Janus WebRTC Gateway SDK:

    wget https://github.com/marcin-sielski/janus-gateway-sdk/archive/v0.2.0.W.tar.gz
    tar -xzvf v0.2.0.W.tar.gz
    cd janus-gateway-sdk

For x86 open Windows console as an Administrator and execute:

    mklink /J c:\msys64\mingw32 "c:\Program Files (x86)\Janus WebRTC Gateway\mingw32"

For x64 open Windows console as an Administrator and execute:

    mklink /J c:\msys64\mingw64 "c:\Program Files\Janus WebRTC Gateway\mingw64"
    
To compile plugins from the SDK open mingw32 or mingw64 shell and execute:

    ./autogen.sh
    ./configure --prefix=$MINGW_PREFIX/usr
    make
    make install
