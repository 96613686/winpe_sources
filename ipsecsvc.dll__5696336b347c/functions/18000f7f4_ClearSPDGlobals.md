# ClearSPDGlobals

- ea: `0x18000f7f4`
- end: `0x18000f907`
- name: `ClearSPDGlobals`
- size: `275`
- prototype: `void()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000c564`

## callees

- `0x180006f60`
- `0x18000ed88`
- `0x18000f7f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f85d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f88f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f85d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f88f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f810`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f82c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f810`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f82c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8dd`

## pseudocode

```c
void ClearSPDGlobals()
{
  DestroyInterfaceChangeEvent();
  if ( gbSPDSection )
  {
    DeleteCriticalSection(&gcSPDSection);
    gbSPDSection = 0;
  }
  if ( gbServerListenSection == 1 )
  {
    DeleteCriticalSection(&gcServerListenSection);
    gbServerListenSection = 0;
  }
  if ( ghServiceStopEvent )
  {
    CloseHandle(ghServiceStopEvent);
    ghServiceStopEvent = 0;
  }
  if ( ghNewDSPolicyEvent )
  {
    CloseHandle(ghNewDSPolicyEvent);
    ghNewDSPolicyEvent = 0;
  }
  if ( ghNewLocalPolicyEvent )
  {
    CloseHandle(ghNewLocalPolicyEvent);
    ghNewLocalPolicyEvent = 0;
  }
  if ( ghForcedPolicyReloadEvent )
  {
    CloseHandle(ghForcedPolicyReloadEvent);
    ghForcedPolicyReloadEvent = 0;
  }
  if ( ghPolicyChangeNotifyEvent )
  {
    CloseHandle(ghPolicyChangeNotifyEvent);
    ghPolicyChangeNotifyEvent = 0;
  }
  if ( ghGpupdateRefreshEvent )
  {
    CloseHandle(ghGpupdateRefreshEvent);
    ghGpupdateRefreshEvent = 0;
  }
  if ( gbSPDAuditSection )
  {
    DeleteCriticalSection(&gcSPDAuditSection);
    gbSPDAuditSection = 0;
  }
  if ( gpSPDSD )
  {
    IpsecFreeMem(gpSPDSD);
    gpSPDSD = 0;
  }
}

```

## disassembly

```asm
0x18000f7f4  push    rbx
0x18000f7f6  sub     rsp, 20h
0x18000f7fa  call    DestroyInterfaceChangeEvent
0x18000f7ff  xor     ebx, ebx
0x18000f801  cmp     cs:gbSPDSection, ebx
0x18000f807  jz      short loc_18000F81C
0x18000f809  lea     rcx, gcSPDSection; lpCriticalSection
0x18000f810  call    cs:__imp_DeleteCriticalSection
0x18000f816  mov     cs:gbSPDSection, ebx
0x18000f81c  cmp     cs:gbServerListenSection, 1
0x18000f823  jnz     short loc_18000F838
0x18000f825  lea     rcx, gcServerListenSection; lpCriticalSection
0x18000f82c  call    cs:__imp_DeleteCriticalSection
0x18000f832  mov     cs:gbServerListenSection, ebx
0x18000f838  mov     rcx, cs:ghServiceStopEvent; hObject
0x18000f83f  test    rcx, rcx
0x18000f842  jz      short loc_18000F851
0x18000f844  call    cs:__imp_CloseHandle
0x18000f84a  mov     cs:ghServiceStopEvent, rbx
0x18000f851  mov     rcx, cs:ghNewDSPolicyEvent; hObject
0x18000f858  test    rcx, rcx
0x18000f85b  jz      short loc_18000F86A
0x18000f85d  call    cs:__imp_CloseHandle
0x18000f863  mov     cs:ghNewDSPolicyEvent, rbx
0x18000f86a  mov     rcx, cs:ghNewLocalPolicyEvent; hObject
0x18000f871  test    rcx, rcx
0x18000f874  jz      short loc_18000F883
0x18000f876  call    cs:__imp_CloseHandle
0x18000f87c  mov     cs:ghNewLocalPolicyEvent, rbx
0x18000f883  mov     rcx, cs:ghForcedPolicyReloadEvent; hObject
0x18000f88a  test    rcx, rcx
0x18000f88d  jz      short loc_18000F89C
0x18000f88f  call    cs:__imp_CloseHandle
0x18000f895  mov     cs:ghForcedPolicyReloadEvent, rbx
0x18000f89c  mov     rcx, cs:ghPolicyChangeNotifyEvent; hObject
0x18000f8a3  test    rcx, rcx
0x18000f8a6  jz      short loc_18000F8B5
0x18000f8a8  call    cs:__imp_CloseHandle
0x18000f8ae  mov     cs:ghPolicyChangeNotifyEvent, rbx
0x18000f8b5  mov     rcx, cs:ghGpupdateRefreshEvent; hObject
0x18000f8bc  test    rcx, rcx
0x18000f8bf  jz      short loc_18000F8CE
0x18000f8c1  call    cs:__imp_CloseHandle
0x18000f8c7  mov     cs:ghGpupdateRefreshEvent, rbx
0x18000f8ce  cmp     cs:gbSPDAuditSection, ebx
0x18000f8d4  jz      short loc_18000F8E9
0x18000f8d6  lea     rcx, gcSPDAuditSection; lpCriticalSection
0x18000f8dd  call    cs:__imp_DeleteCriticalSection
0x18000f8e3  mov     cs:gbSPDAuditSection, ebx
0x18000f8e9  mov     rcx, cs:gpSPDSD; lpMem
0x18000f8f0  test    rcx, rcx
0x18000f8f3  jz      short loc_18000F901
0x18000f8f5  call    IpsecFreeMem
0x18000f8fa  mov     cs:gpSPDSD, rbx
0x18000f901  add     rsp, 20h
0x18000f905  pop     rbx
0x18000f906  retn
```
