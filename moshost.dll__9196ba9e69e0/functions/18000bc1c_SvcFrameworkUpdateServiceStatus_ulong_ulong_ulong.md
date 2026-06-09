# SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18000bc1c`
- end: `0x18000bc9e`
- name: `?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z`
- size: `130`
- prototype: `__int64 __fastcall(DWORD, DWORD, DWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000b6e0`
- `0x18000b7e0`
- `0x18000b8e0`
- `0x18000bac0`

## callees

- `0x18000bc1c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bc91`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bc91`

## pseudocode

```c
__int64 __fastcall SvcFrameworkUpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  DWORD v3; // eax
  DWORD v4; // eax

  if ( a1 == 4 )
  {
    v3 = ServiceStatus.dwControlsAccepted | 0x400;
  }
  else
  {
    v3 = ServiceStatus.dwControlsAccepted & 0xFFFFFBFF;
    if ( a1 == 2 )
    {
      v4 = ServiceStatus.dwControlsAccepted & 0xFFFFFBFE;
      goto LABEL_4;
    }
  }
  v4 = v3 | 1;
LABEL_4:
  ServiceStatus.dwControlsAccepted = v4;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwWin32ExitCode = a2;
  ServiceStatus.dwWaitHint = a3;
  if ( a1 == 4 || a1 == 1 )
    ServiceStatus.dwCheckPoint = 0;
  else
    ServiceStatus.dwCheckPoint = dword_1800182BC++;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  return 0;
}

```

## disassembly

```asm
0x18000bc1c  sub     rsp, 28h
0x18000bc20  mov     eax, cs:ServiceStatus.dwControlsAccepted
0x18000bc26  cmp     ecx, 4
0x18000bc29  jnz     short loc_18000BC6B
0x18000bc2b  bts     eax, 0Ah
0x18000bc2f  or      eax, 1
0x18000bc32  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x18000bc38  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18000bc3e  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x18000bc44  mov     cs:ServiceStatus.dwWaitHint, r8d
0x18000bc4b  cmp     ecx, 4
0x18000bc4e  jz      short loc_18000BC79
0x18000bc50  cmp     ecx, 1
0x18000bc53  jz      short loc_18000BC79
0x18000bc55  mov     eax, cs:dword_1800182BC
0x18000bc5b  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000bc61  inc     eax
0x18000bc63  mov     cs:dword_1800182BC, eax
0x18000bc69  jmp     short loc_18000BC83
0x18000bc6b  btr     eax, 0Ah
0x18000bc6f  cmp     ecx, 2
0x18000bc72  jnz     short loc_18000BC2F
0x18000bc74  and     eax, 0FFFFFFFEh
0x18000bc77  jmp     short loc_18000BC32
0x18000bc79  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18000bc83  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000bc8a  lea     rdx, ServiceStatus; lpServiceStatus
0x18000bc91  call    cs:__imp_SetServiceStatus
0x18000bc97  xor     eax, eax
0x18000bc99  add     rsp, 28h
0x18000bc9d  retn
```
