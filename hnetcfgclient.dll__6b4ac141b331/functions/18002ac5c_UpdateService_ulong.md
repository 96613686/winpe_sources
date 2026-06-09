# UpdateService(ulong)

- ea: `0x18002ac5c`
- end: `0x18002ad06`
- name: `?UpdateService@@YAXK@Z`
- size: `170`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180010350`
- `0x180017bf0`
- `0x18001f590`
- `0x180022a40`
- `0x180023050`
- `0x1800236c0`
- `0x180023e20`
- `0x1800240a0`
- `0x180024c20`
- `0x180024cf0`
- `0x180024e40`
- `0x1800250a0`
- `0x18002aa18`

## callees

- `0x18002ac5c`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acbf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ac93`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ac93`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002acda`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ace3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002acda`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ace3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002acb1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002acb1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002acd1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002acd1`

## string_xrefs

- `0x18002aca7`: `SharedAccess`

## pseudocode

```c
void __fastcall UpdateService(DWORD dwControl)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"SharedAccess", 0xF01FFu);
    v5 = v4;
    if ( v4 )
    {
      ControlService(v4, dwControl, &ServiceStatus);
      CloseServiceHandle(v5);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v3);
  }
}

```

## disassembly

```asm
0x18002ac5c  mov     [rsp+arg_8], rbx
0x18002ac61  mov     [rsp+arg_10], rsi
0x18002ac66  push    rdi
0x18002ac67  sub     rsp, 50h
0x18002ac6b  mov     rax, cs:__security_cookie
0x18002ac72  xor     rax, rsp
0x18002ac75  mov     [rsp+58h+var_18], rax
0x18002ac7a  xorps   xmm0, xmm0
0x18002ac7d  mov     esi, ecx
0x18002ac7f  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18002ac84  xor     edx, edx; lpDatabaseName
0x18002ac86  xor     ecx, ecx; lpMachineName
0x18002ac88  mov     r8d, 0F003Fh; dwDesiredAccess
0x18002ac8e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002ac93  call    cs:__imp_OpenSCManagerW
0x18002ac99  mov     rdi, rax
0x18002ac9c  test    rax, rax
0x18002ac9f  jz      short loc_18002ACE9
0x18002aca1  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002aca7  lea     rdx, ?c_wszSharedAccess@@3QBGB; "SharedAccess"
0x18002acae  mov     rcx, rax; hSCManager
0x18002acb1  call    cs:__imp_OpenServiceW
0x18002acb7  mov     rbx, rax
0x18002acba  test    rax, rax
0x18002acbd  jnz     short loc_18002ACC7
0x18002acbf  call    cs:__imp_GetLastError
0x18002acc5  jmp     short loc_18002ACE0
0x18002acc7  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002accc  mov     edx, esi; dwControl
0x18002acce  mov     rcx, rbx; hService
0x18002acd1  call    cs:__imp_ControlService
0x18002acd7  mov     rcx, rbx; hSCObject
0x18002acda  call    cs:__imp_CloseServiceHandle
0x18002ace0  mov     rcx, rdi; hSCObject
0x18002ace3  call    cs:__imp_CloseServiceHandle
0x18002ace9  mov     rcx, [rsp+58h+var_18]
0x18002acee  xor     rcx, rsp; StackCookie
0x18002acf1  call    __security_check_cookie
0x18002acf6  mov     rbx, [rsp+58h+arg_8]
0x18002acfb  mov     rsi, [rsp+58h+arg_10]
0x18002ad00  add     rsp, 50h
0x18002ad04  pop     rdi
0x18002ad05  retn
```
