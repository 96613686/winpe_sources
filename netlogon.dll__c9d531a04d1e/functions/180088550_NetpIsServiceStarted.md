# NetpIsServiceStarted

- ea: `0x180088550`
- end: `0x18008861a`
- name: `NetpIsServiceStarted`
- size: `202`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18006f490`
- `0x1800700b0`

## callees

- `0x18000e270`
- `0x180088550`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180088581`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180088581`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008859f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008859f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885b0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885d8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885b0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885d8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800885e1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800885c0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800885c0`

## pseudocode

```c
_BOOL8 __fastcall NetpIsServiceStarted(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
    return 0;
  v5 = OpenServiceW(v2, lpServiceName, 4u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = v3;
LABEL_5:
    CloseServiceHandle(v7);
    return 0;
  }
  if ( !QueryServiceStatus(v5, &ServiceStatus) )
  {
    CloseServiceHandle(v3);
    v7 = v6;
    goto LABEL_5;
  }
  CloseServiceHandle(v3);
  CloseServiceHandle(v6);
  return ServiceStatus.dwCurrentState - 4 <= 2 || ServiceStatus.dwCurrentState == 7;
}

```

## disassembly

```asm
0x180088550  mov     [rsp+arg_8], rbx
0x180088555  push    rdi
0x180088556  sub     rsp, 50h
0x18008855a  mov     rax, cs:__security_cookie
0x180088561  xor     rax, rsp
0x180088564  mov     [rsp+58h+var_18], rax
0x180088569  xorps   xmm0, xmm0
0x18008856c  xor     edx, edx; lpDatabaseName
0x18008856e  mov     rdi, rcx
0x180088571  xor     ecx, ecx; lpMachineName
0x180088573  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180088578  lea     r8d, [rdx+1]; dwDesiredAccess
0x18008857c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180088581  call    cs:__imp_OpenSCManagerW
0x180088587  mov     rbx, rax
0x18008858a  test    rax, rax
0x18008858d  jnz     short loc_180088593
0x18008858f  xor     eax, eax
0x180088591  jmp     short loc_180088602
0x180088593  mov     r8d, 4; dwDesiredAccess
0x180088599  mov     rdx, rdi; lpServiceName
0x18008859c  mov     rcx, rbx; hSCManager
0x18008859f  call    cs:__imp_OpenServiceW
0x1800885a5  mov     rdi, rax
0x1800885a8  test    rax, rax
0x1800885ab  jnz     short loc_1800885B8
0x1800885ad  mov     rcx, rbx; hSCObject
0x1800885b0  call    cs:__imp_CloseServiceHandle
0x1800885b6  jmp     short loc_18008858F
0x1800885b8  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800885bd  mov     rcx, rdi; hService
0x1800885c0  call    cs:__imp_QueryServiceStatus
0x1800885c6  mov     rcx, rbx; hSCObject
0x1800885c9  test    eax, eax
0x1800885cb  jnz     short loc_1800885D8
0x1800885cd  call    cs:__imp_CloseServiceHandle
0x1800885d3  mov     rcx, rdi
0x1800885d6  jmp     short loc_1800885B0
0x1800885d8  call    cs:__imp_CloseServiceHandle
0x1800885de  mov     rcx, rdi; hSCObject
0x1800885e1  call    cs:__imp_CloseServiceHandle
0x1800885e7  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x1800885eb  lea     eax, [rcx-4]
0x1800885ee  cmp     eax, 2
0x1800885f1  jbe     short loc_1800885FD
0x1800885f3  xor     eax, eax
0x1800885f5  cmp     ecx, 7
0x1800885f8  setz    al
0x1800885fb  jmp     short loc_180088602
0x1800885fd  mov     eax, 1
0x180088602  mov     rcx, [rsp+58h+var_18]
0x180088607  xor     rcx, rsp; StackCookie
0x18008860a  call    __security_check_cookie
0x18008860f  mov     rbx, [rsp+58h+arg_8]
0x180088614  add     rsp, 50h
0x180088618  pop     rdi
0x180088619  retn
```
