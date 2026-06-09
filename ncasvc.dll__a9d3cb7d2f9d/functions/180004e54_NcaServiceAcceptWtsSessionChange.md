# NcaServiceAcceptWtsSessionChange

- ea: `0x180004e54`
- end: `0x180004efd`
- name: `NcaServiceAcceptWtsSessionChange`
- size: `169`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ebf0`

## callees

- `0x180004e54`
- `0x180004f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ee8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ee8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e63`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004e8a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ea2`

## pseudocode

```c
__int64 NcaServiceAcceptWtsSessionChange()
{
  DWORD LastError; // ebx
  BOOL v1; // eax

  LastError = 0;
  EnterCriticalSection(&stru_180028AF0);
  if ( hServiceStatus )
  {
    ServiceStatus.dwControlsAccepted |= 0x80u;
    v1 = SetServiceStatus(hServiceStatus, &ServiceStatus);
    ServiceStatus.dwControlsAccepted &= ~0x80u;
    if ( !v1 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids, LastError);
    }
  }
  LeaveCriticalSection(&stru_180028AF0);
  return LastError;
}

```

## disassembly

```asm
0x180004e54  push    rbx
0x180004e56  sub     rsp, 20h
0x180004e5a  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004e61  xor     ebx, ebx
0x180004e63  call    cs:__imp_EnterCriticalSection
0x180004e6a  nop     dword ptr [rax+rax+00h]
0x180004e6f  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004e76  test    rcx, rcx
0x180004e79  jz      short loc_180004EE1
0x180004e7b  bts     cs:ServiceStatus.dwControlsAccepted, 7
0x180004e83  lea     rdx, ServiceStatus; lpServiceStatus
0x180004e8a  call    cs:__imp_SetServiceStatus
0x180004e91  nop     dword ptr [rax+rax+00h]
0x180004e96  btr     cs:ServiceStatus.dwControlsAccepted, 7
0x180004e9e  test    eax, eax
0x180004ea0  jnz     short loc_180004EE1
0x180004ea2  call    cs:__imp_GetLastError
0x180004ea9  nop     dword ptr [rax+rax+00h]
0x180004eae  mov     ebx, eax
0x180004eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eb7  lea     rax, WPP_GLOBAL_Control
0x180004ebe  cmp     rcx, rax
0x180004ec1  jz      short loc_180004EE1
0x180004ec3  test    byte ptr [rcx+1Ch], 1
0x180004ec7  jz      short loc_180004EE1
0x180004ec9  mov     rcx, [rcx+10h]
0x180004ecd  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004ed4  mov     edx, 26h ; '&'
0x180004ed9  mov     r9d, ebx
0x180004edc  call    WPP_SF_d
0x180004ee1  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004ee8  call    cs:__imp_LeaveCriticalSection
0x180004eef  nop     dword ptr [rax+rax+00h]
0x180004ef4  mov     eax, ebx
0x180004ef6  add     rsp, 20h
0x180004efa  pop     rbx
0x180004efb  retn
```
