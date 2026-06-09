# TraceOutputSettings::~TraceOutputSettings(void)

- ea: `0x140005dd4`
- end: `0x140005fa6`
- name: `??1TraceOutputSettings@@QEAA@XZ`
- size: `466`
- prototype: `void __fastcall(TraceOutputSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007300`

## callees

- `0x140002980`
- `0x140005dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005de1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005e9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005de1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005e9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005e1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005f99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005e1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005f99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005e2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ea8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ea8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005f85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005f85`
- `KERNEL32!UnregisterWaitEx` at `0x140005ec2`
- `KERNEL32!UnregisterWaitEx` at `0x140005ec2`

## string_xrefs

- `0x140005e83`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x140005ef1`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x140005f26`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x140005e3c`: `Failed receiving the RegistryChangeListenerFinished event`
- `0x140005e58`: `Successfully received the RegistryChangeListenerFinished event`
- `0x140005f06`: `Successfully unregistered for registry change notifications`

## pseudocode

```c
void __fastcall TraceOutputSettings::~TraceOutputSettings(TraceOutputSettings *this)
{
  __int64 v1; // rdx

  EnterCriticalSection(&stru_140010798);
  if ( TraceOutputSettings::fWatchingRegistry )
  {
    TraceOutputSettings::fWatchingRegistry = 0;
    RegCloseKey(TraceOutputSettings::hkConfiguration);
    TraceOutputSettings::hkConfiguration = 0;
    LeaveCriticalSection(&stru_140010798);
    if ( WaitForSingleObject(TraceOutputSettings::RegistryChangeListenerFinished, 0x3E8u) )
    {
      GetLastError();
      v1 = 1;
    }
    else
    {
      v1 = 3;
    }
    TraceStringInline(2, v1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
    EnterCriticalSection(&stru_140010798);
    CloseHandle(TraceOutputSettings::RegistryChangeListenerFinished);
    TraceOutputSettings::RegistryChangeListenerFinished = 0;
    if ( UnregisterWaitEx(TraceOutputSettings::RegistryWaitObject, 0) )
    {
      TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
    }
    else
    {
      GetLastError();
      TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
    }
    TraceOutputSettings::RegistryWaitObject = 0;
    if ( TraceOutputSettings::RegistryChangedEvent )
    {
      CloseHandle(TraceOutputSettings::RegistryChangedEvent);
      TraceOutputSettings::RegistryChangedEvent = 0;
    }
  }
  if ( TraceOutputSettings::hkConfiguration )
  {
    RegCloseKey(TraceOutputSettings::hkConfiguration);
    TraceOutputSettings::hkConfiguration = 0;
  }
  LocalFree(TraceOutputSettings::TraceFilePath);
  TraceOutputSettings::fInitialized = 0;
  LeaveCriticalSection(&stru_140010798);
}

```

## disassembly

```asm
0x140005dd4  push    rdi
0x140005dd6  sub     rsp, 40h
0x140005dda  lea     rcx, stru_140010798; lpCriticalSection
0x140005de1  call    cs:__imp_EnterCriticalSection
0x140005de7  cmp     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x140005dee  jz      loc_140005F61
0x140005df4  mov     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x140005dfb  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x140005e02  call    cs:__imp_RegCloseKey
0x140005e08  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x140005e13  lea     rcx, stru_140010798; lpCriticalSection
0x140005e1a  call    cs:__imp_LeaveCriticalSection
0x140005e20  mov     edx, 3E8h; dwMilliseconds
0x140005e25  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hHandle
0x140005e2c  call    cs:__imp_WaitForSingleObject
0x140005e32  test    eax, eax
0x140005e34  jz      short loc_140005E58
0x140005e36  call    cs:__imp_GetLastError
0x140005e3c  lea     rcx, aFailedReceivin; "Failed receiving the RegistryChangeList"...
0x140005e43  mov     [rsp+48h+var_18], rcx
0x140005e48  mov     dword ptr [rsp+48h+var_20], eax
0x140005e4c  mov     r9d, 65h ; 'e'
0x140005e52  lea     edx, [r9-64h]
0x140005e56  jmp     short loc_140005E77
0x140005e58  lea     rax, aSuccessfullyRe; "Successfully received the RegistryChang"...
0x140005e5f  mov     [rsp+48h+var_18], rax
0x140005e64  mov     [rsp+48h+var_20], 0
0x140005e6d  mov     r9d, 6Ch ; 'l'
0x140005e73  lea     edx, [r9-69h]
0x140005e77  lea     rdi, aTraceoutputset_0; "TraceOutputSettings::~TraceOutputSettin"...
0x140005e7e  mov     [rsp+48h+var_28], rdi
0x140005e83  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x140005e8a  mov     ecx, 2
0x140005e8f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140005e94  lea     rcx, stru_140010798; lpCriticalSection
0x140005e9b  call    cs:__imp_EnterCriticalSection
0x140005ea1  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hObject
0x140005ea8  call    cs:__imp_CloseHandle
0x140005eae  mov     cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangeListenerFinished
0x140005eb9  xor     edx, edx; CompletionEvent
0x140005ebb  mov     rcx, cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA; WaitHandle
0x140005ec2  call    cs:__imp_UnregisterWaitEx
0x140005ec8  test    eax, eax
0x140005eca  jnz     short loc_140005F06
0x140005ecc  call    cs:__imp_GetLastError
0x140005ed2  mov     [rsp+48h+var_10], eax
0x140005ed6  lea     rcx, aUnregisterwait; "UnregisterWait returned the 0x%x error "...
0x140005edd  mov     [rsp+48h+var_18], rcx
0x140005ee2  mov     dword ptr [rsp+48h+var_20], eax
0x140005ee6  mov     [rsp+48h+var_28], rdi
0x140005eeb  mov     r9d, 79h ; 'y'
0x140005ef1  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x140005ef8  lea     edx, [r9-78h]
0x140005efc  lea     ecx, [rdx+1]
0x140005eff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140005f04  jmp     short loc_140005F39
0x140005f06  lea     rax, aSuccessfullyUn; "Successfully unregistered for registry "...
0x140005f0d  mov     [rsp+48h+var_18], rax
0x140005f12  mov     [rsp+48h+var_20], 0
0x140005f1b  mov     [rsp+48h+var_28], rdi
0x140005f20  mov     r9d, 7Fh
0x140005f26  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x140005f2d  lea     edx, [r9-7Ch]
0x140005f31  lea     ecx, [rdx-1]
0x140005f34  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140005f39  mov     cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryWaitObject
0x140005f44  mov     rcx, cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA; hObject
0x140005f4b  test    rcx, rcx
0x140005f4e  jz      short loc_140005F61
0x140005f50  call    cs:__imp_CloseHandle
0x140005f56  mov     cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangedEvent
0x140005f61  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x140005f68  test    rcx, rcx
0x140005f6b  jz      short loc_140005F7E
0x140005f6d  call    cs:__imp_RegCloseKey
0x140005f73  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x140005f7e  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x140005f85  call    cs:__imp_LocalFree
0x140005f8b  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x140005f92  lea     rcx, stru_140010798; lpCriticalSection
0x140005f99  call    cs:__imp_LeaveCriticalSection
0x140005f9f  nop
0x140005fa0  add     rsp, 40h
0x140005fa4  pop     rdi
0x140005fa5  retn
```
