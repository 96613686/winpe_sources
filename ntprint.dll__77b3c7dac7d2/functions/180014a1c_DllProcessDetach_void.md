# DllProcessDetach(void)

- ea: `0x180014a1c`
- end: `0x180014b26`
- name: `?DllProcessDetach@@YAXXZ`
- size: `266`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180016504`

## callees

- `0x18000d624`
- `0x18000dadc`
- `0x180014a1c`
- `0x180016680`
- `0x1800353e4`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180014afb`
- `ntdll!EtwEventUnregister` at `0x180014afb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014a3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014a3f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014a55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014a8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014ad6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014a55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014a8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014ad6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180014aa8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180014aa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ab5`

## string_xrefs

- `0x180014a20`: `DLL_PROCESS_DETACH`
- `0x180014a27`: `DllProcessDetach`

## pseudocode

```c
void DllProcessDetach(void)
{
  unsigned int v0; // eax

  ClassInstallerTelemetry::WriteDbgTraceInfo("DllProcessDetach", L"DLL_PROCESS_DETACH");
  if ( hPrintui )
    FreeLibrary(hPrintui);
  if ( gbCDMCritSectInitialized )
  {
    DeleteCriticalSection(&CDMCritSect);
    gbCDMCritSectInitialized = 0;
  }
  DestroyCodedownload(gpCodeDownLoadInfo);
  gpCodeDownLoadInfo = 0;
  if ( gbSetupapiGlobalFlagsCritSectInitialized )
  {
    DeleteCriticalSection(&SetupapiGlobalFlagsCritSect);
    gbSetupapiGlobalFlagsCritSectInitialized = 0;
  }
  if ( gpszSkipDir )
  {
    RemoveDirectoryW(gpszSkipDir);
    LocalFree((HLOCAL)gpszSkipDir);
    gpszSkipDir = 0;
  }
  if ( gbSkipCritSectInitialized )
  {
    DeleteCriticalSection(&SkipCritSect);
    gbSkipCritSectInitialized = 0;
  }
  McGenEventUnregister_EventUnregister();
  if ( g_bTracingEnabled )
  {
    v0 = EtwEventUnregister(g_splRegistrationHandle);
    if ( !v0 )
      g_bTracingEnabled = 0;
    PerfLibTelemetry::WriteDbgTraceInfo("SplEventLogUnregister", L"rc: %d", v0);
  }
}

```

## disassembly

```asm
0x180014a1c  sub     rsp, 28h
0x180014a20  lea     rdx, aDllProcessDeta; "DLL_PROCESS_DETACH"
0x180014a27  lea     rcx, aDllprocessdeta; "DllProcessDetach"
0x180014a2e  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014a33  mov     rcx, cs:?hPrintui@@3PEAUHINSTANCE__@@EA; hLibModule
0x180014a3a  test    rcx, rcx
0x180014a3d  jz      short loc_180014A45
0x180014a3f  call    cs:__imp_FreeLibrary
0x180014a45  cmp     cs:gbCDMCritSectInitialized, 0
0x180014a4c  jz      short loc_180014A65
0x180014a4e  lea     rcx, CDMCritSect; lpCriticalSection
0x180014a55  call    cs:__imp_DeleteCriticalSection
0x180014a5b  mov     cs:gbCDMCritSectInitialized, 0
0x180014a65  mov     rcx, cs:gpCodeDownLoadInfo; hMem
0x180014a6c  call    DestroyCodedownload
0x180014a71  cmp     cs:gbSetupapiGlobalFlagsCritSectInitialized, 0
0x180014a78  mov     cs:gpCodeDownLoadInfo, 0
0x180014a83  jz      short loc_180014A9C
0x180014a85  lea     rcx, SetupapiGlobalFlagsCritSect; lpCriticalSection
0x180014a8c  call    cs:__imp_DeleteCriticalSection
0x180014a92  mov     cs:gbSetupapiGlobalFlagsCritSectInitialized, 0
0x180014a9c  mov     rcx, cs:gpszSkipDir; lpPathName
0x180014aa3  test    rcx, rcx
0x180014aa6  jz      short loc_180014AC6
0x180014aa8  call    cs:__imp_RemoveDirectoryW
0x180014aae  mov     rcx, cs:gpszSkipDir; hMem
0x180014ab5  call    cs:__imp_LocalFree
0x180014abb  mov     cs:gpszSkipDir, 0
0x180014ac6  cmp     cs:gbSkipCritSectInitialized, 0
0x180014acd  jz      short loc_180014AE6
0x180014acf  lea     rcx, SkipCritSect; lpCriticalSection
0x180014ad6  call    cs:__imp_DeleteCriticalSection
0x180014adc  mov     cs:gbSkipCritSectInitialized, 0
0x180014ae6  call    McGenEventUnregister_EventUnregister
0x180014aeb  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180014af2  jz      short loc_180014B21
0x180014af4  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180014afb  call    cs:__imp_EtwEventUnregister
0x180014b01  test    eax, eax
0x180014b03  jnz     short loc_180014B0B
0x180014b05  mov     cs:?g_bTracingEnabled@@3HA, eax; int g_bTracingEnabled
0x180014b0b  mov     r8d, eax
0x180014b0e  lea     rdx, aRcD; "rc: %d"
0x180014b15  lea     rcx, aSpleventlogunr; "SplEventLogUnregister"
0x180014b1c  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014b21  add     rsp, 28h
0x180014b25  retn
```
