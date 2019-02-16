# VLC_Mingw64_Compiling_Tips
<pre>
$ git clone http://git.videolan.org/git/vlc.git vlc2
$ cd ~/vlc2/extras/tools/
$ ./bootstrap  
$ make

$ cd ../..
$ mkdir -p contrib/win32
$ cd contrib/win32
$ ../bootstrap --host=x86_64-w64-mingw32 --disable-bluray
$ make fetch
$ make
$ ln -sf 'x86_64-w64-mingw32' ../i686-w64-mingw32

$ cd -
$ ./bootstrap
$ mkdir win32 && cd win32
$ export PKG_CONFIG_LIBDIR=$HOME/vlc2/contrib/x86_64-w64-mingw32/lib/pkgconfig
$ ../extras/package/win32/configure.sh --host=x86_64-w64-mingw32 --build=x86_64-pc-linux-gnu --disable-faad
$ make PROTOC=~/vlc2/extras/tools/build/bin/protoc

# Creates a subdirectory named vlc-x.x.x with all the binaries. You can run VLC directly from this directory.
$ make package-win-common
</pre>
