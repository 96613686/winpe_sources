# SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18000bbb8`
- end: `0x18000bc3a`
- name: `?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180008360`
- `0x1800083c0`
- `0x18000b7a0`
- `0x18000b8a0`
- `0x18000ba60`

## callees

- `0x18000bbb8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bc2d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000bc2d`

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
    ServiceStatus.dwCheckPoint = dword_18002A2D8++;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  return 0;
}

```

## disassembly

```asm
0x18000bbb8  sub     rsp, 28h
0x18000bbbc  mov     eax, cs:ServiceStatus.dwControlsAccepted
0x18000bbc2  cmp     ecx, 4
0x18000bbc5  jnz     short loc_18000BC07
0x18000bbc7  bts     eax, 0Ah
0x18000bbcb  or      eax, 1
0x18000bbce  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x18000bbd4  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18000bbda  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x18000bbe0  mov     cs:ServiceStatus.dwWaitHint, r8d
0x18000bbe7  cmp     ecx, 4
0x18000bbea  jz      short loc_18000BC15
0x18000bbec  cmp     ecx, 1
0x18000bbef  jz      short loc_18000BC15
0x18000bbf1  mov     eax, cs:dword_18002A2D8
0x18000bbf7  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000bbfd  inc     eax
0x18000bbff  mov     cs:dword_18002A2D8, eax
0x18000bc05  jmp     short loc_18000BC1F
0x18000bc07  btr     eax, 0Ah
0x18000bc0b  cmp     ecx, 2
0x18000bc0e  jnz     short loc_18000BBCB
0x18000bc10  and     eax, 0FFFFFFFEh
0x18000bc13  jmp     short loc_18000BBCE
0x18000bc15  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18000bc1f  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000bc26  lea     rdx, ServiceStatus; lpServiceStatus
0x18000bc2d  call    cs:__imp_SetServiceStatus
0x18000bc33  xor     eax, eax
0x18000bc35  add     rsp, 28h
0x18000bc39  retn
```
