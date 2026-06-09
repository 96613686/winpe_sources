# IsServiceRunning

- ea: `0x180085bb0`
- end: `0x180085cad`
- name: `IsServiceRunning`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800851d8`
- `0x1800859a4`

## callees

- `0x180085bb0`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180085c05`
- `KERNEL32!GetLastError` at `0x180085c37`
- `KERNEL32!GetLastError` at `0x180085c05`
- `KERNEL32!GetLastError` at `0x180085c37`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180085c4d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180085c4d`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180085c23`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180085c23`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085bf1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085bf1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085c68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085c7c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085c68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085c7c`

## pseudocode

```c
_BOOL8 IsServiceRunning()
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "ikeext", 4u);
    v4 = v3;
    if ( v3 && QueryServiceStatus(v3, &ServiceStatus) )
      v0 = ServiceStatus.dwCurrentState == 4;
    else
      GetLastError();
    CloseServiceHandle(v2);
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x180085bb0  mov     r11, rsp
0x180085bb3  mov     [r11+8], rbx
0x180085bb7  mov     [r11+10h], rbp
0x180085bbb  mov     [r11+18h], rsi
0x180085bbf  push    rdi
0x180085bc0  sub     rsp, 50h
0x180085bc4  mov     rax, cs:__security_cookie
0x180085bcb  xor     rax, rsp
0x180085bce  mov     [rsp+58h+var_18], rax
0x180085bd3  xor     eax, eax
0x180085bd5  xorps   xmm0, xmm0
0x180085bd8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180085bdd  mov     [r11-28h], rax
0x180085be1  xor     ebx, ebx
0x180085be3  xor     edx, edx; lpDatabaseName
0x180085be5  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x180085be9  xor     ecx, ecx; lpMachineName
0x180085beb  lea     ebp, [rbx+1]
0x180085bee  mov     r8d, ebp; dwDesiredAccess
0x180085bf1  call    cs:__imp_OpenSCManagerW
0x180085bf8  nop     dword ptr [rax+rax+00h]
0x180085bfd  mov     rsi, rax
0x180085c00  test    rax, rax
0x180085c03  jnz     short loc_180085C13
0x180085c05  call    cs:__imp_GetLastError
0x180085c0c  nop     dword ptr [rax+rax+00h]
0x180085c11  jmp     short loc_180085C88
0x180085c13  mov     r8d, 4; dwDesiredAccess
0x180085c19  lea     rdx, ServiceName; "ikeext"
0x180085c20  mov     rcx, rsi; hSCManager
0x180085c23  call    cs:__imp_OpenServiceA
0x180085c2a  nop     dword ptr [rax+rax+00h]
0x180085c2f  mov     rdi, rax
0x180085c32  test    rax, rax
0x180085c35  jnz     short loc_180085C45
0x180085c37  call    cs:__imp_GetLastError
0x180085c3e  nop     dword ptr [rax+rax+00h]
0x180085c43  jmp     short loc_180085C65
0x180085c45  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180085c4a  mov     rcx, rdi; hService
0x180085c4d  call    cs:__imp_QueryServiceStatus
0x180085c54  nop     dword ptr [rax+rax+00h]
0x180085c59  test    eax, eax
0x180085c5b  jz      short loc_180085C37
0x180085c5d  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180085c62  cmovz   ebx, ebp
0x180085c65  mov     rcx, rsi; hSCObject
0x180085c68  call    cs:__imp_CloseServiceHandle
0x180085c6f  nop     dword ptr [rax+rax+00h]
0x180085c74  test    rdi, rdi
0x180085c77  jz      short loc_180085C88
0x180085c79  mov     rcx, rdi; hSCObject
0x180085c7c  call    cs:__imp_CloseServiceHandle
0x180085c83  nop     dword ptr [rax+rax+00h]
0x180085c88  mov     eax, ebx
0x180085c8a  mov     rcx, [rsp+58h+var_18]
0x180085c8f  xor     rcx, rsp; StackCookie
0x180085c92  call    __security_check_cookie
0x180085c97  mov     rbx, [rsp+58h+arg_0]
0x180085c9c  mov     rbp, [rsp+58h+arg_8]
0x180085ca1  mov     rsi, [rsp+58h+arg_10]
0x180085ca6  add     rsp, 50h
0x180085caa  pop     rdi
0x180085cab  retn
```
