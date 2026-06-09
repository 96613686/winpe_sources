# ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)

- ea: `0x140007374`
- end: `0x140007452`
- name: `?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z`
- size: `222`
- prototype: `__int64 __fastcall(ServiceStatus *this, DWORD, DWORD, DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140006490`
- `0x140007780`
- `0x140007820`
- `0x1400078f0`

## callees

- `0x140005014`
- `0x140007110`
- `0x140007374`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x140007418`
- `ADVAPI32!SetServiceStatus` at `0x140007418`
- `KERNEL32!EnterCriticalSection` at `0x14000738c`
- `KERNEL32!EnterCriticalSection` at `0x14000738c`
- `KERNEL32!LeaveCriticalSection` at `0x140007441`
- `KERNEL32!LeaveCriticalSection` at `0x140007441`
- `KERNEL32!GetLastError` at `0x140007424`
- `KERNEL32!GetLastError` at `0x140007424`

## string_xrefs

- `0x14000742c`: `SetServiceStatus failed.`

## pseudocode

```c
__int64 __fastcall ServiceStatus::ReportStatusToSCMgr(ServiceStatus *this, DWORD a2, DWORD a3, DWORD a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  BOOL v9; // edi
  DWORD LastError; // eax

  EnterCriticalSection(&g_cServiceStatus);
  v7 = 0;
  if ( ServiceStatus.dwCurrentState != 1 )
  {
    ServiceStatus.dwControlsAccepted = 0;
    if ( a2 != 2 )
    {
      if ( g_cInstances > 0 || (v8 = FCanStopService(), ServiceStatus.dwControlsAccepted = 5, !v8) )
        ServiceStatus.dwControlsAccepted = 4;
    }
    ServiceStatus.dwCurrentState = a2;
    ServiceStatus.dwWin32ExitCode = a3;
    ServiceStatus.dwWaitHint = a4;
    if ( a2 == 4 || a2 == 1 )
      ServiceStatus.dwCheckPoint = 0;
    else
      ServiceStatus.dwCheckPoint = dword_140010190++;
    v9 = SetServiceStatus(hServiceStatus, &ServiceStatus);
    if ( !v9 )
    {
      LastError = GetLastError();
      ReportErrorToDebugOutput((const WCHAR *)L"SetServiceStatus failed.", LastError);
    }
    v7 = v9;
  }
  LeaveCriticalSection(&g_cServiceStatus);
  return v7;
}

```

## disassembly

```asm
0x140007374  push    rbx
0x140007376  push    rbp
0x140007377  push    rsi
0x140007378  push    rdi
0x140007379  sub     rsp, 28h
0x14000737d  lea     rcx, ?g_cServiceStatus@@3VServiceStatus@@A; lpCriticalSection
0x140007384  mov     esi, r9d
0x140007387  mov     ebp, r8d
0x14000738a  mov     edi, edx
0x14000738c  call    cs:__imp_EnterCriticalSection
0x140007392  xor     ebx, ebx
0x140007394  cmp     cs:ServiceStatus.dwCurrentState, 1
0x14000739b  jz      loc_14000743A
0x1400073a1  mov     cs:ServiceStatus.dwControlsAccepted, ebx
0x1400073a7  cmp     edi, 2
0x1400073aa  jz      short loc_1400073D1
0x1400073ac  cmp     cs:?g_cInstances@@3JA, ebx; long g_cInstances
0x1400073b2  jg      short loc_1400073C7
0x1400073b4  call    ?FCanStopService@@YAHXZ; FCanStopService(void)
0x1400073b9  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x1400073c3  test    eax, eax
0x1400073c5  jnz     short loc_1400073D1
0x1400073c7  mov     cs:ServiceStatus.dwControlsAccepted, 4
0x1400073d1  mov     cs:ServiceStatus.dwCurrentState, edi
0x1400073d7  mov     cs:ServiceStatus.dwWin32ExitCode, ebp
0x1400073dd  mov     cs:ServiceStatus.dwWaitHint, esi
0x1400073e3  cmp     edi, 4
0x1400073e6  jz      short loc_140007404
0x1400073e8  cmp     edi, 1
0x1400073eb  jz      short loc_140007404
0x1400073ed  mov     ecx, cs:dword_140010190
0x1400073f3  mov     cs:ServiceStatus.dwCheckPoint, ecx
0x1400073f9  lea     eax, [rcx+1]
0x1400073fc  mov     cs:dword_140010190, eax
0x140007402  jmp     short loc_14000740A
0x140007404  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x14000740a  mov     rcx, cs:hServiceStatus; hServiceStatus
0x140007411  lea     rdx, ServiceStatus; lpServiceStatus
0x140007418  call    cs:__imp_SetServiceStatus
0x14000741e  mov     edi, eax
0x140007420  test    eax, eax
0x140007422  jnz     short loc_140007438
0x140007424  call    cs:__imp_GetLastError
0x14000742a  mov     edx, eax; unsigned int
0x14000742c  lea     rcx, aSetservicestat; "SetServiceStatus failed."
0x140007433  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x140007438  mov     ebx, edi
0x14000743a  lea     rcx, ?g_cServiceStatus@@3VServiceStatus@@A; lpCriticalSection
0x140007441  call    cs:__imp_LeaveCriticalSection
0x140007447  mov     eax, ebx
0x140007449  add     rsp, 28h
0x14000744d  pop     rdi
0x14000744e  pop     rsi
0x14000744f  pop     rbp
0x140007450  pop     rbx
0x140007451  retn
```
