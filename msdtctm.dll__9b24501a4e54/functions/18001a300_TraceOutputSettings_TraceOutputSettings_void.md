# TraceOutputSettings::~TraceOutputSettings(void)

- ea: `0x18001a300`
- end: `0x18001a4d2`
- name: `??1TraceOutputSettings@@QEAA@XZ`
- size: `466`
- prototype: `void __fastcall(TraceOutputSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bc860`

## callees

- `0x1800063b0`
- `0x18001a300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a346`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a346`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a30d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a3c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a30d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a32e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a32e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a499`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a47c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a47c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a4b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a4b1`
- `KERNEL32!UnregisterWaitEx` at `0x18001a3ee`
- `KERNEL32!UnregisterWaitEx` at `0x18001a3ee`

## string_xrefs

- `0x18001a368`: `Failed receiving the RegistryChangeListenerFinished event`
- `0x18001a3af`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18001a41d`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18001a452`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18001a384`: `Successfully received the RegistryChangeListenerFinished event`
- `0x18001a432`: `Successfully unregistered for registry change notifications`

## pseudocode

```c
void __fastcall TraceOutputSettings::~TraceOutputSettings(TraceOutputSettings *this)
{
  __int64 v1; // r9
  __int64 v2; // rdx
  DWORD LastError; // [rsp+28h] [rbp-20h]
  const wchar_t *v4; // [rsp+30h] [rbp-18h]
  DWORD v5; // [rsp+38h] [rbp-10h]

  EnterCriticalSection(&stru_1801535E0);
  if ( TraceOutputSettings::fWatchingRegistry )
  {
    TraceOutputSettings::fWatchingRegistry = 0;
    RegCloseKey(TraceOutputSettings::hkConfiguration);
    TraceOutputSettings::hkConfiguration = 0;
    LeaveCriticalSection(&stru_1801535E0);
    if ( WaitForSingleObject(TraceOutputSettings::RegistryChangeListenerFinished, 0x3E8u) )
    {
      v4 = L"Failed receiving the RegistryChangeListenerFinished event";
      LastError = GetLastError();
      v1 = 101;
      v2 = 1;
    }
    else
    {
      v4 = L"Successfully received the RegistryChangeListenerFinished event";
      LastError = 0;
      v1 = 108;
      v2 = 3;
    }
    TraceStringInline(
      2,
      v2,
      L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      v1,
      L"TraceOutputSettings::~TraceOutputSettings",
      LastError,
      v4);
    EnterCriticalSection(&stru_1801535E0);
    CloseHandle(TraceOutputSettings::RegistryChangeListenerFinished);
    TraceOutputSettings::RegistryChangeListenerFinished = 0;
    if ( UnregisterWaitEx(TraceOutputSettings::RegistryWaitObject, 0) )
    {
      TraceStringInline(
        2,
        3,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        127,
        L"TraceOutputSettings::~TraceOutputSettings",
        0,
        L"Successfully unregistered for registry change notifications");
    }
    else
    {
      v5 = GetLastError();
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        121,
        L"TraceOutputSettings::~TraceOutputSettings",
        v5,
        L"UnregisterWait returned the 0x%x error code.",
        v5);
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
  LeaveCriticalSection(&stru_1801535E0);
}

```

## disassembly

```asm
0x18001a300  push    rdi
0x18001a302  sub     rsp, 40h
0x18001a306  lea     rcx, stru_1801535E0; lpCriticalSection
0x18001a30d  call    cs:__imp_EnterCriticalSection
0x18001a313  cmp     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x18001a31a  jz      loc_18001A48D
0x18001a320  mov     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x18001a327  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x18001a32e  call    cs:__imp_RegCloseKey
0x18001a334  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x18001a33f  lea     rcx, stru_1801535E0; lpCriticalSection
0x18001a346  call    cs:__imp_LeaveCriticalSection
0x18001a34c  mov     edx, 3E8h; dwMilliseconds
0x18001a351  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hHandle
0x18001a358  call    cs:__imp_WaitForSingleObject
0x18001a35e  test    eax, eax
0x18001a360  jz      short loc_18001A384
0x18001a362  call    cs:__imp_GetLastError
0x18001a368  lea     rcx, aFailedReceivin; "Failed receiving the RegistryChangeList"...
0x18001a36f  mov     [rsp+48h+var_18], rcx
0x18001a374  mov     dword ptr [rsp+48h+var_20], eax
0x18001a378  mov     r9d, 65h ; 'e'
0x18001a37e  lea     edx, [r9-64h]
0x18001a382  jmp     short loc_18001A3A3
0x18001a384  lea     rax, aSuccessfullyRe; "Successfully received the RegistryChang"...
0x18001a38b  mov     [rsp+48h+var_18], rax
0x18001a390  mov     [rsp+48h+var_20], 0
0x18001a399  mov     r9d, 6Ch ; 'l'
0x18001a39f  lea     edx, [r9-69h]
0x18001a3a3  lea     rdi, aTraceoutputset_0; "TraceOutputSettings::~TraceOutputSettin"...
0x18001a3aa  mov     [rsp+48h+var_28], rdi
0x18001a3af  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18001a3b6  mov     ecx, 2
0x18001a3bb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a3c0  lea     rcx, stru_1801535E0; lpCriticalSection
0x18001a3c7  call    cs:__imp_EnterCriticalSection
0x18001a3cd  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hObject
0x18001a3d4  call    cs:__imp_CloseHandle
0x18001a3da  mov     cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangeListenerFinished
0x18001a3e5  xor     edx, edx; CompletionEvent
0x18001a3e7  mov     rcx, cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA; WaitHandle
0x18001a3ee  call    cs:__imp_UnregisterWaitEx
0x18001a3f4  test    eax, eax
0x18001a3f6  jnz     short loc_18001A432
0x18001a3f8  call    cs:__imp_GetLastError
0x18001a3fe  mov     [rsp+48h+var_10], eax
0x18001a402  lea     rcx, aUnregisterwait; "UnregisterWait returned the 0x%x error "...
0x18001a409  mov     [rsp+48h+var_18], rcx
0x18001a40e  mov     dword ptr [rsp+48h+var_20], eax
0x18001a412  mov     [rsp+48h+var_28], rdi
0x18001a417  mov     r9d, 79h ; 'y'
0x18001a41d  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18001a424  lea     edx, [r9-78h]
0x18001a428  lea     ecx, [rdx+1]
0x18001a42b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a430  jmp     short loc_18001A465
0x18001a432  lea     rax, aSuccessfullyUn; "Successfully unregistered for registry "...
0x18001a439  mov     [rsp+48h+var_18], rax
0x18001a43e  mov     [rsp+48h+var_20], 0
0x18001a447  mov     [rsp+48h+var_28], rdi
0x18001a44c  mov     r9d, 7Fh
0x18001a452  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18001a459  lea     edx, [r9-7Ch]
0x18001a45d  lea     ecx, [rdx-1]
0x18001a460  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a465  mov     cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryWaitObject
0x18001a470  mov     rcx, cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA; hObject
0x18001a477  test    rcx, rcx
0x18001a47a  jz      short loc_18001A48D
0x18001a47c  call    cs:__imp_CloseHandle
0x18001a482  mov     cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangedEvent
0x18001a48d  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x18001a494  test    rcx, rcx
0x18001a497  jz      short loc_18001A4AA
0x18001a499  call    cs:__imp_RegCloseKey
0x18001a49f  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x18001a4aa  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x18001a4b1  call    cs:__imp_LocalFree
0x18001a4b7  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x18001a4be  lea     rcx, stru_1801535E0; lpCriticalSection
0x18001a4c5  call    cs:__imp_LeaveCriticalSection
0x18001a4cb  nop
0x18001a4cc  add     rsp, 40h
0x18001a4d0  pop     rdi
0x18001a4d1  retn
```
