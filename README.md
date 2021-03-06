# pedump
An simplest PE parser, which list all import and export entries.

The first line is look like linux tool named `file`, detials is a simple list.

- Support 32bits dll/exe
- Support 64bits dll/exe

Usage:
```
Version: 2016.11.01
Build  : Jan  1 2017 20:10:50
Usage  : pedump [option] files
  -v, --verbose              show import and export details
  --ni                       do not show import
  --ne                       do not show export
  --no                       do not show export
  --vi                       show import
  --ve                       show export
  --vo                       show export
```

Example
```
7z.dll: PE32+ executable (DLL) (GUI) x86_64 (Sat May 21 16:34:19 2016)
  Sections
    RVA        OFFSET    
    ---------- ----------
    0x00001000 0x00000400
    0x0010f000 0x0010e400
    0x0015c000 0x0015b000
    0x00166000 0x0015c000
    0x00178000 0x0016d800
    0x00190000 0x00185400

  Import OLEAUT32.dll
    Hint     Name
    -------- --------
    0x0007   (NONAME)
    0x0009   (NONAME)
    0x000a   (NONAME)
    0x0002   (NONAME)
    0x0096   (NONAME)
    0x0006   (NONAME)
    0x0004   (NONAME)

  Import USER32.dll
    Hint     Name
    -------- --------
    0x0037   CharUpperW
    0x002e   CharPrevExA

  Import msvcrt.dll
    Hint     Name
    -------- --------
    0x02a1   memset
    0x02b1   realloc
    0x0264   free
    0x0299   malloc
    0x0039   __CxxFrameHandler
    0x02cc   strlen
    0x02c8   strcpy
    0x0030   _CxxThrowException
    0x02f0   wcscmp
    0x02c6   strcmp
    0x02a0   memmove
    0x029f   memcpy
    0x029e   memcmp
    0x0178   _purecall
    0x02c5   strchr
    0x0037   __C_specific_handler
    0x007e   _beginthreadex
    0x0011   ??1type_info@@UEAA@XZ
    0x002d   ?terminate@@YAXXZ
    0x004e   __dllonexit
    0x016e   _onexit
    0x00f4   _initterm
    0x02d3   strstr

  Import KERNEL32.dll
    Hint     Name
    -------- --------
    0x01a2   GetProcAddress
    0x035c   Sleep
    0x0225   InitializeCriticalSection
    0x02bf   ReleaseSemaphore
    0x006f   CreateSemaphoreW
    0x02cb   ResetEvent
    0x031d   SetEvent
    0x0053   CreateEventW
    0x0396   WaitForSingleObject
    0x0389   VirtualFree
    0x0387   VirtualAlloc
    0x029f   QueryPerformanceCounter
    0x00c7   FileTimeToLocalFileTime
    0x0084   DeleteCriticalSection
    0x0256   LocalFileTimeToFileTime
    0x0394   WaitForMultipleObjects
    0x024d   LeaveCriticalSection
    0x009b   EnterCriticalSection
    0x01cc   GetSystemTimeAsFileTime
    0x00c6   FileTimeToDosDateTime
    0x0092   DosDateTimeToFileTime
    0x01c7   GetSystemInfo
    0x003b   CompareFileTime
    0x03aa   WriteFile
    0x02b1   ReadFile
    0x0164   GetFileAttributesW
    0x0181   GetModuleHandleA
    0x00d8   FindFirstFileW
    0x00d1   FindClose
    0x0173   GetLastError
    0x0271   MultiByteToWideChar
    0x039a   WideCharToMultiByte
    0x0036   CloseHandle
    0x0059   CreateFileW
    0x0321   SetFileAttributesW
    0x0184   GetModuleHandleW
    0x0051   CreateDirectoryW
    0x0087   DeleteFileW
    0x01d8   GetTempPathW
    0x032e   SetLastError
    0x0146   GetCurrentProcessId
    0x01e1   GetTickCount
    0x0149   GetCurrentThreadId

  Export 7z.dll
    Ordinal  Hint     Entry      Name
    -------- -------- ---------- --------
    0x0001   0x0000   0x000eb450 CreateDecoder
    0x0002   0x0001   0x000eb4d0 CreateEncoder
    0x0003   0x0002   0x0005b528 CreateObject
    0x0004   0x0003   0x0005b4c4 GetHandlerProperty
    0x0005   0x0004   0x0005b244 GetHandlerProperty2
    0x0006   0x0005   0x000ebb80 GetHashers
    0x0007   0x0006   0x0005b4e0 GetIsArc
    0x0008   0x0007   0x000eb710 GetMethodProperty
    0x0009   0x0008   0x0005b4d4 GetNumberOfFormats
    0x000a   0x0009   0x000eb880 GetNumberOfMethods
    0x000b   0x000a   0x0005b5e0 SetCaseSensitive
    0x000c   0x000b   0x0005b818 SetCodecs
    0x000d   0x000c   0x0005b5d0 SetLargePageMode
```
