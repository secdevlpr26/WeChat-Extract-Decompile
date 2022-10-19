# WeChat-Decompile

1. Use a Mini program from WeChat
2. WeChat mini program source files from the server are downloaded to the mobile in the following location:
        *data/data/com.tencent.mm/MicroMsg/a505c04df05cb788e53e736b8ffba461/appbrand/pkg/<wxapkg filename> /sdcard/apkfilesdata*
  
3. The location is read-only, hence:
       
        $ adb shell
        $ su
        # mount -o rw,remount /data
  
4. Copy the entire folder to internal storage
       
         # cp -R data/data/com.tencent.mm/MicroMsg/a505c04df05cb788e53e736b8ffba461/appbrand/pkg/ /sdcard/
  
  or, Copy one particular wxapkg file and exit the adb shell:
       
         # cp data/data/com.tencent.mm/MicroMsg/a505c04df05cb788e53e736b8ffba461/appbrand/pkg/<wxapkg filename> /sdcard/
         # exit
         $ exit

5. Pull the files to development system:
         $ adb pull /sdcard/<path in the mobile>/ <path to the computer>
  
  or, 
  
         $ adb pull /sdcard/<path in the mobile>/<wxapkg filename> <path to the computer>
  
 6. To Decompile the extracted Binary files,used the following Github repo:
        
               https://github.com/Supraja9726/decrypt-unpack-wxapkg    
    
  
 
