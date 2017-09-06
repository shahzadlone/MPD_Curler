# MPEG-DASH Curler (Check if MPDs are Up) 

------------------------
Builds:
------------------------
```sh
gcc Curler.c -Llibs/ -Ithird_party -lxml2 -lcurl -o curler -Wl,-rpath=libs/ && echo $?
```
------------------------
Usage:
------------------------
```sh
Takes one argument: [Path-To-File-With-The-URLS]
```
    WHERE:
          [Path-To-File-With-The-URLS]: path to the file that contains all the URLs to the MPDs on seperate lines.

------------------------
Examples:
------------------------
    [ ./curler URLs ]
    [ ./curler URLs 2>/dev/null ] (Try this for a cleaner output)

Note: If curling takes more than 5 seconds for any URL, program shows it's down. (Easily Configurable)

![Sample Output](/image/Example.PNG?raw=true)

------------------------
Extra:
------------------------
- Add ```2>/dev/null``` to omit the std error output and get a cleaner output.
- Use ```sort URLs | uniq --count``` to find if there are duplicates.

------------------------
FAQ:
------------------------
- Q1) While Compilation Getting Some RTMP Linker Errors.
Try ```sudo ln -s /usr/lib/x86_64-linux-gnu/librtmp.so.1 /usr/lib/x86_64-linux-gnu/librtmp.so.0```
