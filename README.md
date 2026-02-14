# NConvert-Gradio-Batch
Status: Working - QTWeb, no longer uses external browser for GUI.

### Description:
Its a Python QTWeb Gradio interface for converting ANY image format to ANY imgage format, even rare ones like .pspimage, all made possible through NConvert binary command line tool. The program provides a user-friendly menu to set the source folder, input file format, and desired output format. The scripts ensures efficient and seamless conversion and management of image files, making it a practical tool for users needing to process multiple common format such as `.jpg`, `.bmp`, `.png`, etc, and also less common formats such as`.pspimage`, and vice versa, and another thing, it does this recursively through subfolders, so you can just aim it at windows pictures folder, and everything will be where it was, just in the new format too.

### Features:
- **Multiple Formats**: The Gradio interface limited to 10, but they can be edited in the `.py` script. 
- **Interactive Menu**: Utilizing your standard text-based menu for effective configuration.
- **Batch Conversion**: All specified format files in, specified folder and its subfolders, to desired format.
- **Automatic Report**: Provides a summary of the total number of successfully converted files.
- **Deletion Option**: Offers the option to delete original files.
- **Persistent Settings**: Remembers format from/to and target folder.
- **Error Handling**: Displays errors for any files that fail to convert.
- **Bleep On Complete**: Incase for some reasoning it is going to take a while.

### Preview:
- The Video Demonstration on YouTube (for v1.00-Final)...
<br>[![NConvert-Batch on YouTube](./media/wisetime_youtube.jpg)](https://www.youtube.com/watch?v=ECydHjJ04U4)

- The NConvert-Batch Gradio WebUi...
![Alternative text](https://github.com/wiseman-timelord/NConvertBatch/blob/main/media/gradio_interface.jpg)

- The installation processes, showing a Clean Install...
<details> 

    ===============================================================================
        NConvert-Gradio-Batch — Clean Install
    ===============================================================================
    
    ✓ Python 3.12 detected
    
    -------------------------------------------------------------------------------
        Phase 1: Purge
    -------------------------------------------------------------------------------
    
    Purging data directory: C:\Media_Files\NConvert-Gradio-Batch\NConvert-Gradio-Batch\data
    ✓ Data directory removed
    Purging workspace directory: C:\Media_Files\NConvert-Gradio-Batch\NConvert-Gradio-Batch\temp
    ✓ Workspace directory removed
    
    Uninstalling existing application packages...
    ✓ Application packages uninstalled
    -------------------------------------------------------------------------------
        Phase 2: Fresh Install
    -------------------------------------------------------------------------------
    
    ✓ Workspace directory ready: C:\Media_Files\NConvert-Gradio-Batch\NConvert-Gradio-Batch\temp
    NConvert not found, attempting download...
    Detected architecture: 64-bit (x64) [machine=amd64, platform.architecture=64bit]
    Downloading NConvert 64-bit from: https://download.xnview.com/NConvert-win64.zip
    Found partial download (0.0 MB) → will attempt to resume
    
    Download attempt 1/4 - Starting download...
    Progress:  74%  (   7.7/10.4 MB)
    
    Incomplete download detected (8087904 / 10885373 bytes)
    
    Download failed: Download incomplete
    Retrying in 4 seconds... (attempt 2/4)
    
    Download attempt 2/4 - Resuming download...
    Progress: 100%  (  10.4/10.4 MB)
    Download completed successfully ✓
    Extracting: nconvert-q12wkfhp.zip
    ✓ Extraction completed
    Moved: Formats.txt
    Moved: license.txt
    Moved: nconvert.exe
    Moved: plugins
    Moved: Plugins.txt
    Moved: ReadMe.txt
    Moved: Usage.txt
    Moved: vcomp120.dll
    Moved: WhatsNew.txt
    ✓ Moved 9 items to .\data\NConvert\
    ✓ NConvert installation completed
    
    Upgrading build tools (pip, setuptools) to latest...
    → Upgrading pip to latest version...
    ✓ pip upgraded successfully
    → Upgrading setuptools to latest version...
    ✓ setuptools upgraded successfully
    
    Installing pinned application packages...
    (This includes PyQt6-WebEngine for the built-in browser)
    ✓ All application packages installed successfully
    ✓ Default persistent config created: data/persistent.json
    
    Verifying critical components...
    ✓ nconvert.exe found at .\data\NConvert\
    ✓ gradio available
    ✓ pandas available
    ✓ numpy available
    ✓ psutil available
    ✓ PyQt6-WebEngine available
    ✓ All critical components verified successfully
    
    ===============================================================================
    ✓ Clean installation completed successfully!
    
    You can now run NConvert-Gradio-Batch.bat
   
</details>

## Requirements:
- Windows 10-11 - The Batch uses a 80x30 text display, the new QTWeb code needs to be assessed for case operation/install, so for now its 10-11, however v1.2 versions have cases of operation/install for 7-11 compatibility. Likely I will drop Windows 7-8.1 going forwards.
- [NConvert](https://www.xnview.com/en/nconvert) - ~500 image formats supported (installed by installer).
- Python 3.9+ - Tested on 3.11/3.12, but ensure python.exe is on system PATH.
- Powershell ? - Needs to be assessed, but its for the text buffer. 
- Internet - Installer requires internet for install of Python libraries etc.

### Instructions:
Here are my current instructions...
```
1. Downlaod latest release, and unpack to a suitable location.
2. Run `NConvert-Gradio-Batch.Bat` by right click `Run as Administrator`, as we are doing, complex recursive file operations under the interface and downloading/unpacking NConvert in the installer. 
- It is optional to manually download/unpack NConvert to ".\data\NConvert\*", and the installer will detect it, but otherwise the installer would handle the download/install if there is no NConvert unpacked there. This may help if there are for some reason network issues.
3. Install Requirements from menu through option `2` on the batch menu, it will run `.\installer.py`, which will install everything you require via web/pip. 
4. After requirements are installed, then run `NConvert-Batch` from `1.` on the batch menu, and if the gradio interface does not pop-up in its own built-in browser window.
5. Configure the settings in the browser interface, if your file format preference is not in the list, then edit relevant lists in python script by replace appropriate extension text.
6. When all setting are correct, then 1st ensure you noticed the `Delete Original Files?` tickbox, and if you did, then click `Start Conversion`, and it will convert the files, as  you have specified, over-writing as it goes.
7. Check the image folders, I saved you potentially hours of work, but I did say I was a TimeLord ha.
```

### NOTATION:
- If you want to display, for example "AVIF" format, in the Windows Explorer thumbnails, then you should install [Icaros](https://github.com/Xanashi/Icaros/releases), then in the configuration add, in the case of the example ".avif", to the file extension list, and activate it.
- De-Confustion... Meaning 1: "Batch" - a `*.bat` Windows Batch file. Meaning 2: "Batch" - Repetitive actions done together in sequence.
- If you want others among the ~500 possible formats, then you will need to manually edit the top of ".\launcher.py".
- Thanks to, DeepSeek v2.5-v3 and GPT-4o and Claudev4 and Grok and Qwen3-Max, for assistance in programming. 
- Thanks to [XnView Software](https://www.xnview.com/en/) for, creating and hosting, [NConvert](https://www.xnview.com/en/nconvert/), the binary behind my frontend.
- NConvert-Batch is the Windows version of [NConvert-Bash](https://github.com/wiseman-timelord/NConvert-Bash).
- A slideshow window for after conversion was attempted in, Qwen3-Max and Grok, but both failed, 50/50 on the idea anyhow.

### Development:
- Merge, "NConvert-Batch" and "NConvert-Bash", into "NConvert-GUI", with Dual-mode scripts. Includine introduction of ".\scripts\configure.py" for, globals and load/save config. Requiring the deletion of project "NConvert-Bash". This will not be able to be done until I have a Ubuntu setup again.
- Rename "program.py" to "launcher.py", in order for the python scripts to sit next to each other neatly in the folder.

## DISCLAIMER:
This software is subject to the terms in License.Txt, covering usage, distribution, and modifications. For full details on your rights and obligations, refer to License.Txt.
NConvert is not made by Wiseman-Timelord, only the, Gradio Interface and Batch Launcher/Installer, is; Terms and Conditions, for NConvert still apply.
