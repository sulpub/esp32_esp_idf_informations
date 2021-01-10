# esp32_esp_idf_informations

This document list some informations concerning the ESP32 toolchain compilation.

# ESP-IDF_windows_environment

To begin a compilation for the ESP32 plateform, it is important to install these tools :
* Python 3.7 or later
* Git for supporting the update project
* ESP-IDF source depending of your version
* IDF tools directory (IDF_TOOLS_PATH): C:\Users\your_windows_account\.espressif
* CMAKE (latest version on : https://cmake.org/)

The best way is to download the latest ESP-IDF Tools Installer (example : esp-idf-tools-setup-2.3.exe)

Link : https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/windows-setup.html

To see if you have all tools installed correctly, on the Windows Powershell run this script.
Nota : if some path is not define, you can install it on the Powershell with these command : 
```
$env:path += ";C:\Program Files\cmake\bin"
```

Copy paste these line and save it as *tools_version.bat*

After save file run it on the Windows powershell
```
echo off

echo $env
echo $env:path += ";C:\Program Files\cmake\bin"
echo $env:path += ";C:\Users\your_windows_account\.espressif\tools\xtensa-esp32-elf\version_to_complete\xtensa-esp32-elf\bin"
echo $env:path += ";C:\Users\your_windows_account\Desktop\esp-idf\tools"
echo $env:path += ";C:\Users\your_windows_account\.espressif\tools\ninja\1.10.0"

echo "--------------------------------------------------------------------------"
echo "--------------TOOL VERSION FOR ESP32 COMPILATION NOVOSENSO----------------"
echo "--------------------------------------------------------------------------"
echo( 

echo "--------------------------------------------------------------------------"
echo "------------------- XTENSA ESP32 GCC VERSION -----------------------------"
xtensa-esp32-elf-gcc --version
echo "--------------------------------------------------------------------------"
echo( 

echo "--------------------------------------------------------------------------"
echo "-------------------------- IDF-ESP VERSION -------------------------------"
py idf.py --version
echo "--------------------------------------------------------------------------"
echo( 

echo "--------------------------------------------------------------------------"
echo "-------------------------- CMAKE VERSION ---------------------------------"
cmake --version
echo "--------------------------------------------------------------------------"
echo( 

echo "--------------------------------------------------------------------------"
echo "---------------------------- GIT VERSION ---------------------------------"
git --version
echo "--------------------------------------------------------------------------"
echo(

echo "--------------------------------------------------------------------------"
echo "-------------------------- PYTHON VERSION --------------------------------"
py --version
echo "--------------------------------------------------------------------------"
echo( 

echo "--------------------------------------------------------------------------"
echo "----------------------------NINJA VERSION --------------------------------" 
ninja --version
echo "--------------------------------------------------------------------------"
echo( 
```

To verify if your setup was correct, *on the esp-dif directory*, run these command :

```
install.bat
```
You must have:

```
All done! You can now run: 
    export.bat
```

If all was correct, you can run another command that add PATH on your system :

```
export.bat
```

You must have :
```
Done! You can now compile ESP-IDF projects.
Go to the project directory and run:

  idf.py build
```
