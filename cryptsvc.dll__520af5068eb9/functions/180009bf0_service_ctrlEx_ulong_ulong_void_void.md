# service_ctrlEx(ulong,ulong,void *,void *)

- ea: `0x180009bf0`
- end: `0x180009db3`
- name: `?service_ctrlEx@@YAKKKPEAX0@Z`
- size: `451`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, __int64 lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180009bf0`
- `0x180009e50`
- `0x18000b324`
- `0x18000f51c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009d9c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009d9c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009c51`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009c51`

## pseudocode

```c
__int64 __fastcall service_ctrlEx(DWORD dwControl, DWORD dwEventType, __int64 lpEventData, LPVOID lpContext)
{
  int v7; // ebx
  DWORD v8; // ecx
  DWORD v9; // ecx
  DWORD v10; // ecx
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  void (__fastcall *v13)(__int64, _QWORD, _QWORD, __int64); // rax

  if ( dwControl == 4 )
  {
    ServiceStatus.dwWaitHint = 0;
    if ( ServiceStatus.dwCurrentState == 2 )
    {
      *(_QWORD *)&ServiceStatus.dwControlsAccepted = 0;
    }
    else
    {
      ServiceStatus.dwControlsAccepted = 5;
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        *(_QWORD *)&ServiceStatus.dwControlsAccepted = 133;
LABEL_5:
        ServiceStatus.dwCheckPoint = 0;
LABEL_6:
        if ( SetServiceStatus(sshStatusHandle, &ServiceStatus) )
          return 0;
        AddToMessageLog();
        return 0;
      }
      ServiceStatus.dwWin32ExitCode = 0;
      if ( ServiceStatus.dwCurrentState == 1 )
        goto LABEL_5;
    }
    ServiceStatus.dwCheckPoint = dword_1800200F4++;
    goto LABEL_6;
  }
  v7 = 0;
  v8 = dwControl - 1;
  if ( !v8 )
  {
LABEL_27:
    ServiceStatus.dwCurrentState = 3;
    ReportStatusToSCMgr(3, 0, 0);
    if ( hServerStopEvent )
    {
      if ( v7 )
        dword_180020248 = 1;
      SetEvent(hServerStopEvent);
    }
    return 0;
  }
  v9 = v8 - 4;
  if ( !v9 )
  {
    v7 = 1;
    goto LABEL_27;
  }
  v10 = v9 - 6;
  if ( v10 )
  {
    if ( v10 == 3 )
    {
      v11 = dword_180020234;
      v12 = 0;
      if ( (unsigned int)dword_180020234 >= 5 )
      {
        v11 = 5;
      }
      else if ( !dword_180020234 )
      {
        return 0;
      }
      do
      {
        v13 = (void (__fastcall *)(__int64, _QWORD, _QWORD, __int64))qword_180020378[2 * v12];
        if ( v13 )
          v13(3, 0, dwEventType, lpEventData);
        ++v12;
      }
      while ( v12 < v11 );
      return 0;
    }
    else
    {
      return 120;
    }
  }
  else
  {
    CryptsvcCtrl(4u, 0, dwEventType, lpEventData);
    return 0;
  }
}

```

## disassembly

```asm
0x180009bf0  mov     [rsp+arg_18], rbx
0x180009bf5  push    rbp
0x180009bf6  push    rsi
0x180009bf7  push    rdi
0x180009bf8  sub     rsp, 30h
0x180009bfc  xor     edi, edi
0x180009bfe  mov     rsi, r8
0x180009c01  mov     ebp, edx
0x180009c03  cmp     ecx, 4
0x180009c06  jnz     short loc_180009C7E
0x180009c08  mov     eax, cs:ServiceStatus.dwCurrentState
0x180009c0e  mov     cs:ServiceStatus.dwCurrentState, eax
0x180009c14  mov     cs:ServiceStatus.dwWaitHint, edi
0x180009c1a  cmp     eax, 2
0x180009c1d  jz      loc_180009D13
0x180009c23  mov     ebx, 5
0x180009c28  mov     cs:ServiceStatus.dwControlsAccepted, ebx
0x180009c2e  cmp     eax, ecx
0x180009c30  jnz     short loc_180009C6E
0x180009c32  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 85h
0x180009c3d  mov     cs:ServiceStatus.dwCheckPoint, edi
0x180009c43  mov     rcx, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180009c4a  lea     rdx, ServiceStatus; lpServiceStatus
0x180009c51  call    cs:__imp_SetServiceStatus
0x180009c57  test    eax, eax
0x180009c59  jz      loc_180009DA7
0x180009c5f  mov     eax, edi
0x180009c61  mov     rbx, [rsp+48h+arg_18]
0x180009c66  add     rsp, 30h
0x180009c6a  pop     rdi
0x180009c6b  pop     rsi
0x180009c6c  pop     rbp
0x180009c6d  retn
0x180009c6e  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x180009c74  cmp     eax, 1
0x180009c77  jz      short loc_180009C3D
0x180009c79  jmp     loc_180009D1A
0x180009c7e  xor     ebx, ebx
0x180009c80  sub     ecx, 1
0x180009c83  jz      loc_180009D65
0x180009c89  sub     ecx, 4
0x180009c8c  jz      loc_180009D60
0x180009c92  sub     ecx, 6
0x180009c95  jz      loc_180009D47
0x180009c9b  cmp     ecx, 3
0x180009c9e  jnz     loc_180009D33
0x180009ca4  mov     ebx, cs:dword_180020234
0x180009caa  mov     [rsp+48h+arg_8], r14
0x180009caf  xor     r14d, r14d
0x180009cb2  cmp     ebx, 5
0x180009cb5  jnb     loc_180009D3D
0x180009cbb  test    ebx, ebx
0x180009cbd  jz      short loc_180009CF3
0x180009cbf  mov     [rsp+48h+arg_10], r15
0x180009cc4  lea     r15, qword_180020378
0x180009ccb  mov     eax, r14d
0x180009cce  add     rax, rax
0x180009cd1  mov     rax, [r15+rax*8]
0x180009cd5  test    rax, rax
0x180009cd8  jnz     short loc_180009CFF
0x180009cda  inc     r14d
0x180009cdd  cmp     r14d, ebx
0x180009ce0  jb      short loc_180009CCB
0x180009ce2  mov     r15, [rsp+48h+arg_10]
0x180009ce7  mov     eax, edi
0x180009ce9  mov     r14, [rsp+48h+arg_8]
0x180009cee  jmp     loc_180009C61
0x180009cf3  mov     r14, [rsp+48h+arg_8]
0x180009cf8  mov     eax, edi
0x180009cfa  jmp     loc_180009C61
0x180009cff  mov     r9, rsi
0x180009d02  mov     r8d, ebp
0x180009d05  xor     edx, edx
0x180009d07  mov     ecx, 3
0x180009d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d11  jmp     short loc_180009CDA
0x180009d13  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, rdi
0x180009d1a  mov     eax, cs:dword_1800200F4
0x180009d20  mov     cs:ServiceStatus.dwCheckPoint, eax
0x180009d26  inc     eax
0x180009d28  mov     cs:dword_1800200F4, eax
0x180009d2e  jmp     loc_180009C43
0x180009d33  mov     eax, 78h ; 'x'
0x180009d38  jmp     loc_180009C61
0x180009d3d  mov     ebx, 5
0x180009d42  jmp     loc_180009CBF
0x180009d47  mov     r9, rsi
0x180009d4a  mov     r8d, ebp
0x180009d4d  xor     edx, edx
0x180009d4f  mov     ecx, 4
0x180009d54  call    CryptsvcCtrl
0x180009d59  mov     eax, edi
0x180009d5b  jmp     loc_180009C61
0x180009d60  mov     ebx, 1
0x180009d65  xor     r8d, r8d
0x180009d68  mov     cs:ServiceStatus.dwCurrentState, 3
0x180009d72  xor     edx, edx
0x180009d74  mov     ecx, 3
0x180009d79  call    ReportStatusToSCMgr
0x180009d7e  mov     rcx, cs:?hServerStopEvent@@3PEAXEA; hEvent
0x180009d85  test    rcx, rcx
0x180009d88  jz      loc_180009C5F
0x180009d8e  test    ebx, ebx
0x180009d90  jz      short loc_180009D9C
0x180009d92  mov     cs:dword_180020248, 1
0x180009d9c  call    cs:__imp_SetEvent
0x180009da2  jmp     loc_180009C5F
0x180009da7  call    AddToMessageLog
0x180009dac  mov     eax, edi
0x180009dae  jmp     loc_180009C61
```
