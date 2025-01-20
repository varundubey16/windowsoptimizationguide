NOTE:- REMOVED THE .VBS FILE BECASUE IT WAS CAUSING ISSUES ON WIN 11, WILL LOOK INTO IT AND GIVE AN UPDATE IN FUTURE


# Windows Optimization Guide for Gaming and Performance

## 1. Basic Optimization Checklist
- **Keep Windows Updated**: Check for Updates and use something like DriverBooster by Iobit or Device Manager manual right click drivers and update them.
- **Driver Updates**: Intel Support Assistant or AMD for CPUS's & NVIDIA GeForce Experience for GPU to keep drivers updated. These are actually useful.
- **Debloat Windows**: Run a Windows debloater to remove unnecessary bloatware. The best one is at - https://github.com/Sycnex/Windows10Debloater
- **Antivirus**: Run a full antivirus scan to keep your system safe. like MRT, Defender or any 3rd part like Mcafee if u use.
- **Troubleshoot**: Use built-in Windows troubleshooters for any ongoing issues.
- **Memory and Disk Diagnostics**:
  - Press `Windows + R`, type `mdsched` for memory diagnostics.
  - Run `mrt` for malware removal.

## 2. Privacy and Background Services
- **Game Mode**: Turn on Game Mode for optimized gaming performance. It actually speeds up CPU significantly.
- **Privacy Settings**: Turn off data sharing for diagnostics, inking & typing, and feedback inside settings.
- **Permissions**: Disable location, camera, microphone, and notifications permissions unless needed in settings.
- **Default Apps and Background Apps**:
  - Set essential apps as defaults.
  - Delete offline maps, disable not required startup apps, and turn off not necessary background apps.
- **Network Settings**: Disable unused network adapters (like Ethernet if on Wi-Fi) and configure IPv4 DNS to Google (8.8.8.8) or Cloudflare (1.1.1.1).

## 3. System Maintenance
- **Temporary Files**:
  - Use `Windows + R` to delete temporary files:
    - Type `temp`, `%temp%`, and `prefetch` to open directories and delete files.
  - Run `WSReset.exe` to clear the Windows Store cache.
- **Optimize Disk**:
  - For HDDs, run Disk Defrag (DO NOT DEFRAG SSD! Only Optimize).
- **Disk Cleanup**:
  - Use - Disk Cleanup on the C: drive; select check “Clean up system files.”
- **Software Distribution**: Delete contents in `Windows/Software Distribution/Downloads` to clear old update files. They are upto 6GB sometimes.

## 4. Performance Enhancements
- **Power Plan**: Create New Power Plan - High Performance or Ultimate Performance (if available).
- **Advanced System Settings**:
  - Go to "This PC" > Properties > Advanced System Settings > Performance Settings and set it to “Adjust for best performance.”
  - Disable remote access and delete old restore points.
- **Gaming Settings**:
  - Add games to the Windows Graphics Settings for dedicated GPU access.
- **Desktop Customization**:
  - Set a solid color background to reduce system load.
- **Startup Programs**:
  - Use Task Manager to disable unnecessary startup apps.
  - Use `msconfig` to enable all processors on boot and hide non-Microsoft services.

## 5. Services and Registry Tweaks
- **Service Optimization**:
  - Disable unnecessary services like Xbox Services, SysMain, Windows Search, and Connected User Experiences.
- **Command Line Health Check**:
  - Open Command Prompt as Administrator and run the following:
    ```bash
    Dism /Online /Cleanup-Image /CheckHealth
    Dism /Online /Cleanup-Image /ScanHealth
    Dism /Online /Cleanup-Image /RestoreHealth
    sfc /SCANNOW
    ```
- **Registry Tweaks**:
  - **Disable NDU**:
    - Navigate to `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Ndu` and change “Start” to 4.
  - **Clear Page File at Shutdown**:
    - Go to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management` and set “ClearPageFileAtShutdown” to 1.
  - **Optimize Game DVR**:
    - In `Computer\HKEY_CURRENT_USER\System\GameConfigStore`, set “GameDVR_Enabled” to 0.
    - In `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\default\ApplicationManagement\AllowGameDVR`, set it to 0.

## 6. Memory and CPU Management
- **Virtual Memory**:
  - Go to "System Properties" > Advanced > Performance > Virtual Memory and set a custom size based on RAM (1.5x your installed RAM).
- **Core Parking**:
  - Use QuickCPU or ParkControl to disable core parking and maximize CPU usage.
- **Task Manager & MSConfig**:
  - Set all processors to be used during boot-up and configure to boot without GUI for faster startup.
- **Sound Enhancements**:
  - Disable sound effects in the playback properties of your default audio device.

## 7. Network and Browser Optimization
- **DNS Settings**:
  - Run Command Prompt as Administrator and enter:
    ```bash
    ipconfig /flushdns
    ipconfig /registerdns
    ipconfig /release
    ipconfig /renew
    netsh winsock reset
    ```
- **Network Throttling**:
  - In `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games`, set GPU priority to 8 and CPU priority to 6.
- **Browser Optimization**:
  - Disable hardware acceleration in Chrome, Edge, and other apps.
  - Enable parallel downloading in Chrome flags.

## 8. Additional Tools and Tips
- **CCleaner or Advanced SystemCare**:
  - Run once to clean up your system, then uninstall and use after next 4-5 months.
- **Driver Updates**:
  - Manually update NVIDIA/AMD drivers from the official website.
- **TimeResolution**:
  - Use TimeResolution to reduce system latency while gaming.
- **Disable Unnecessary Services**:
  - Disable services like compnay bloatware from services, example  - Dell SupportAssist, TechHub, DataCollector, DataVault if on a Dell system.
 
  - THESE SETTINGS WILL GIVE DIFFERENT RESULTS ON DIFFERENT DEVICES. 
