# HvHostSetStatus(ulong,ulong)

- ea: `0x1800049e0`
- end: `0x180004a57`
- name: `?HvHostSetStatus@@YAXKK@Z`
- size: `119`
- prototype: `void __fastcall(DWORD, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004a60`
- `0x180006340`

## callees

- `0x180002100`
- `0x1800049e0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004a3f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004a3f`

## pseudocode

```c
void __fastcall HvHostSetStatus(DWORD a1, DWORD a2)
{
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwControlsAccepted = 0;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwWin32ExitCode = a2;
  if ( a1 == 2 )
  {
    ServiceStatus.dwWaitHint = 120000;
  }
  else if ( a1 == 4 )
  {
    ServiceStatus.dwControlsAccepted = 5;
  }
  if ( hServiceStatus )
    SetServiceStatus(hServiceStatus, &ServiceStatus);
}

```

## disassembly

```asm
0x1800049e0  sub     rsp, 58h
0x1800049e4  mov     rax, cs:__security_cookie
0x1800049eb  xor     rax, rsp
0x1800049ee  mov     [rsp+58h+var_18], rax
0x1800049f3  xor     eax, eax
0x1800049f5  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x1800049fd  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x180004a01  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x180004a06  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x180004a0a  mov     [rsp+58h+ServiceStatus.dwCurrentState], ecx
0x180004a0e  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], edx
0x180004a12  cmp     ecx, 2
0x180004a15  jz      short loc_180004A26
0x180004a17  cmp     ecx, 4
0x180004a1a  jnz     short loc_180004A2E
0x180004a1c  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 5
0x180004a24  jmp     short loc_180004A2E
0x180004a26  mov     [rsp+58h+ServiceStatus.dwWaitHint], 1D4C0h
0x180004a2e  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004a35  test    rcx, rcx
0x180004a38  jz      short loc_180004A45
0x180004a3a  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180004a3f  call    cs:__imp_SetServiceStatus
0x180004a45  mov     rcx, [rsp+58h+var_18]
0x180004a4a  xor     rcx, rsp; StackCookie
0x180004a4d  call    __security_check_cookie
0x180004a52  add     rsp, 58h
0x180004a56  retn
```
