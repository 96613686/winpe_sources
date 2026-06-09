# ReportStatusToSCMgr

- ea: `0x18000b324`
- end: `0x18000b3d0`
- name: `ReportStatusToSCMgr`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009bf0`
- `0x18000f3e4`
- `0x18000f6c4`

## callees

- `0x18000b324`
- `0x18000f51c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b37c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b37c`

## pseudocode

```c
__int64 __fastcall ReportStatusToSCMgr(DWORD a1, DWORD a2, DWORD a3)
{
  unsigned int v3; // ebx

  if ( a1 == 2 )
  {
    ServiceStatus.dwControlsAccepted = 0;
  }
  else
  {
    ServiceStatus.dwControlsAccepted = 5;
    if ( a1 == 4 )
      ServiceStatus.dwControlsAccepted = 133;
  }
  ServiceStatus.dwCurrentState = a1;
  if ( a2 )
  {
    ServiceStatus.dwServiceSpecificExitCode = a2;
    ServiceStatus.dwWin32ExitCode = 1066;
  }
  else
  {
    ServiceStatus.dwWin32ExitCode = 0;
  }
  ServiceStatus.dwWaitHint = a3;
  if ( a1 == 4 || a1 == 1 )
    ServiceStatus.dwCheckPoint = 0;
  else
    ServiceStatus.dwCheckPoint = dword_1800200F4++;
  v3 = SetServiceStatus(sshStatusHandle, &ServiceStatus);
  if ( !v3 )
    AddToMessageLog();
  return v3;
}

```

## disassembly

```asm
0x18000b324  push    rbx
0x18000b326  sub     rsp, 20h
0x18000b32a  cmp     ecx, 2
0x18000b32d  jz      short loc_18000B390
0x18000b32f  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x18000b339  cmp     ecx, 4
0x18000b33c  jnz     short loc_18000B348
0x18000b33e  mov     cs:ServiceStatus.dwControlsAccepted, 85h
0x18000b348  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18000b34e  test    edx, edx
0x18000b350  jnz     short loc_18000B39C
0x18000b352  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x18000b358  mov     cs:ServiceStatus.dwWaitHint, r8d
0x18000b35f  cmp     ecx, 4
0x18000b362  jnz     short loc_18000B3AE
0x18000b364  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18000b36e  mov     rcx, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000b375  lea     rdx, ServiceStatus; lpServiceStatus
0x18000b37c  call    cs:__imp_SetServiceStatus
0x18000b382  mov     ebx, eax
0x18000b384  test    eax, eax
0x18000b386  jz      short loc_18000B3C9
0x18000b388  mov     eax, ebx
0x18000b38a  add     rsp, 20h
0x18000b38e  pop     rbx
0x18000b38f  retn
0x18000b390  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18000b39a  jmp     short loc_18000B348
0x18000b39c  mov     cs:ServiceStatus.dwServiceSpecificExitCode, edx
0x18000b3a2  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000b3ac  jmp     short loc_18000B358
0x18000b3ae  cmp     ecx, 1
0x18000b3b1  jz      short loc_18000B364
0x18000b3b3  mov     eax, cs:dword_1800200F4
0x18000b3b9  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000b3bf  inc     eax
0x18000b3c1  mov     cs:dword_1800200F4, eax
0x18000b3c7  jmp     short loc_18000B36E
0x18000b3c9  call    AddToMessageLog
0x18000b3ce  jmp     short loc_18000B388
```
