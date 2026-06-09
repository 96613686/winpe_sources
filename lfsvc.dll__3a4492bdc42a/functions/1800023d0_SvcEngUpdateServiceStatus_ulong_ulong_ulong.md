# SvcEngUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x1800023d0`
- end: `0x18000245f`
- name: `?SvcEngUpdateServiceStatus@@YAJKKK@Z`
- size: `143`
- prototype: `__int64 __fastcall(DWORD, DWORD, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180002b30`
- `0x1800037f0`
- `0x180008c20`

## callees

- `0x1800023d0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002447`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002447`

## pseudocode

```c
__int64 __fastcall SvcEngUpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  if ( !hServiceStatus )
    return 2147549183LL;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwWin32ExitCode = a2;
  ServiceStatus.dwWaitHint = a3;
  if ( a1 == 2 )
  {
    ServiceStatus.dwControlsAccepted = 0;
  }
  else
  {
    ServiceStatus.dwControlsAccepted = 4225;
    if ( a1 == 4 || a1 == 1 )
    {
      ServiceStatus.dwCheckPoint = 0;
      goto LABEL_8;
    }
  }
  ServiceStatus.dwCheckPoint = dword_18001223C++;
LABEL_8:
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  return 0;
}

```

## disassembly

```asm
0x1800023d0  sub     rsp, 28h
0x1800023d4  mov     eax, ecx
0x1800023d6  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800023dd  test    rcx, rcx
0x1800023e0  jnz     short loc_1800023EC
0x1800023e2  mov     eax, 8000FFFFh
0x1800023e7  add     rsp, 28h
0x1800023eb  retn
0x1800023ec  xor     r9d, r9d
0x1800023ef  mov     [rsp+28h+var_8], rbx
0x1800023f4  mov     cs:ServiceStatus.dwCurrentState, eax
0x1800023fa  mov     ebx, r9d
0x1800023fd  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x180002403  mov     cs:ServiceStatus.dwWaitHint, r8d
0x18000240a  cmp     eax, 2
0x18000240d  jnz     short loc_180002418
0x18000240f  mov     cs:ServiceStatus.dwControlsAccepted, r9d
0x180002416  jmp     short loc_18000242C
0x180002418  mov     cs:ServiceStatus.dwControlsAccepted, 1081h
0x180002422  cmp     eax, 4
0x180002425  jz      short loc_180002456
0x180002427  cmp     eax, 1
0x18000242a  jz      short loc_180002456
0x18000242c  mov     eax, cs:dword_18001223C
0x180002432  mov     cs:ServiceStatus.dwCheckPoint, eax
0x180002438  inc     eax
0x18000243a  mov     cs:dword_18001223C, eax
0x180002440  lea     rdx, ServiceStatus; lpServiceStatus
0x180002447  call    cs:__imp_SetServiceStatus
0x18000244d  mov     eax, ebx
0x18000244f  mov     rbx, [rsp+28h+var_8]
0x180002454  jmp     short loc_1800023E7
0x180002456  mov     cs:ServiceStatus.dwCheckPoint, r9d
0x18000245d  jmp     short loc_180002440
```
