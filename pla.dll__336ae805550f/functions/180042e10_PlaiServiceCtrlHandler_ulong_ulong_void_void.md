# PlaiServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180042e10`
- end: `0x180042ebd`
- name: `?PlaiServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `173`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180042e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042eb5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042eb5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180042e69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180042ea8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180042e69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180042ea8`

## pseudocode

```c
__int64 __fastcall PlaiServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx

  v4 = 0;
  _m_prefetchw(&dword_180169B84);
  if ( (_InterlockedOr(&dword_180169B84, 2u) & 1) != 0 )
    goto LABEL_6;
  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( !v6 )
    {
      if ( hServiceStatus )
        SetServiceStatus(hServiceStatus, &ServiceStatus);
      goto LABEL_6;
    }
    if ( v6 != 1 )
    {
      v4 = 120;
      goto LABEL_6;
    }
  }
  ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwCurrentState = 3;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  if ( hServiceStatus )
    SetServiceStatus(hServiceStatus, &ServiceStatus);
  SetEvent(hObject);
LABEL_6:
  _InterlockedAnd(&dword_180169B84, 0xFFFFFFFD);
  return v4;
}

```

## disassembly

```asm
0x180042e10  push    rbx
0x180042e12  sub     rsp, 20h
0x180042e16  xor     r8d, r8d
0x180042e19  mov     ebx, r8d
0x180042e1c  prefetchw byte ptr cs:dword_180169B84
0x180042e23  mov     eax, cs:dword_180169B84
0x180042e29  mov     edx, eax
0x180042e2b  or      edx, 2
0x180042e2e  lock cmpxchg cs:dword_180169B84, edx
0x180042e36  jnz     short loc_180042E29
0x180042e38  test    al, 1
0x180042e3a  jnz     short loc_180042E52
0x180042e3c  sub     ecx, 1
0x180042e3f  jz      short loc_180042E7D
0x180042e41  sub     ecx, 3
0x180042e44  jnz     short loc_180042E71
0x180042e46  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180042e4d  test    rcx, rcx
0x180042e50  jnz     short loc_180042E62
0x180042e52  lock and cs:dword_180169B84, 0FFFFFFFDh
0x180042e5a  mov     eax, ebx
0x180042e5c  add     rsp, 20h
0x180042e60  pop     rbx
0x180042e61  retn
0x180042e62  lea     rdx, ServiceStatus; lpServiceStatus
0x180042e69  call    cs:__imp_SetServiceStatus
0x180042e6f  jmp     short loc_180042E52
0x180042e71  cmp     ecx, 1
0x180042e74  jz      short loc_180042E7D
0x180042e76  mov     ebx, 78h ; 'x'
0x180042e7b  jmp     short loc_180042E52
0x180042e7d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180042e84  mov     cs:ServiceStatus.dwWin32ExitCode, r8d
0x180042e8b  mov     cs:ServiceStatus.dwCurrentState, 3
0x180042e95  mov     qword ptr cs:ServiceStatus.dwCheckPoint, r8
0x180042e9c  test    rcx, rcx
0x180042e9f  jz      short loc_180042EAE
0x180042ea1  lea     rdx, ServiceStatus; lpServiceStatus
0x180042ea8  call    cs:__imp_SetServiceStatus
0x180042eae  mov     rcx, cs:hObject; hEvent
0x180042eb5  call    cs:__imp_SetEvent
0x180042ebb  jmp     short loc_180042E52
```
