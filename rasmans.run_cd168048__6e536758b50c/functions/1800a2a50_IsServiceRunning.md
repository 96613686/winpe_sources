# IsServiceRunning

- ea: `0x1800a2a50`
- end: `0x1800a2b31`
- name: `IsServiceRunning`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003de8c`
- `0x1800a2844`

## callees

- `0x1800a2a50`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2ac7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800a2add`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800a2add`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800a2ab3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800a2ab3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2af8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2b0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2af8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2b0c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a2a81`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a2a81`

## pseudocode

```c
_BOOL8 IsServiceRunning()
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v0 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
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
0x1800a2a50  push    rbx
0x1800a2a52  push    rbp
0x1800a2a53  push    rsi
0x1800a2a54  push    rdi
0x1800a2a55  sub     rsp, 58h
0x1800a2a59  mov     rax, cs:__security_cookie
0x1800a2a60  xor     rax, rsp
0x1800a2a63  mov     [rsp+78h+var_38], rax
0x1800a2a68  xorps   xmm0, xmm0
0x1800a2a6b  xor     ebx, ebx
0x1800a2a6d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800a2a72  xor     edx, edx; lpDatabaseName
0x1800a2a74  xor     ecx, ecx; lpMachineName
0x1800a2a76  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800a2a7b  lea     ebp, [rbx+1]
0x1800a2a7e  mov     r8d, ebp; dwDesiredAccess
0x1800a2a81  call    cs:__imp_OpenSCManagerW
0x1800a2a88  nop     dword ptr [rax+rax+00h]
0x1800a2a8d  mov     rsi, rax
0x1800a2a90  test    rax, rax
0x1800a2a93  jnz     short loc_1800A2AA3
0x1800a2a95  call    cs:__imp_GetLastError
0x1800a2a9c  nop     dword ptr [rax+rax+00h]
0x1800a2aa1  jmp     short loc_1800A2B18
0x1800a2aa3  mov     r8d, 4; dwDesiredAccess
0x1800a2aa9  lea     rdx, aIkeext; "ikeext"
0x1800a2ab0  mov     rcx, rsi; hSCManager
0x1800a2ab3  call    cs:__imp_OpenServiceA
0x1800a2aba  nop     dword ptr [rax+rax+00h]
0x1800a2abf  mov     rdi, rax
0x1800a2ac2  test    rax, rax
0x1800a2ac5  jnz     short loc_1800A2AD5
0x1800a2ac7  call    cs:__imp_GetLastError
0x1800a2ace  nop     dword ptr [rax+rax+00h]
0x1800a2ad3  jmp     short loc_1800A2AF5
0x1800a2ad5  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800a2ada  mov     rcx, rdi; hService
0x1800a2add  call    cs:__imp_QueryServiceStatus
0x1800a2ae4  nop     dword ptr [rax+rax+00h]
0x1800a2ae9  test    eax, eax
0x1800a2aeb  jz      short loc_1800A2AC7
0x1800a2aed  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800a2af2  cmovz   ebx, ebp
0x1800a2af5  mov     rcx, rsi; hSCObject
0x1800a2af8  call    cs:__imp_CloseServiceHandle
0x1800a2aff  nop     dword ptr [rax+rax+00h]
0x1800a2b04  test    rdi, rdi
0x1800a2b07  jz      short loc_1800A2B18
0x1800a2b09  mov     rcx, rdi; hSCObject
0x1800a2b0c  call    cs:__imp_CloseServiceHandle
0x1800a2b13  nop     dword ptr [rax+rax+00h]
0x1800a2b18  mov     eax, ebx
0x1800a2b1a  mov     rcx, [rsp+78h+var_38]
0x1800a2b1f  xor     rcx, rsp; StackCookie
0x1800a2b22  call    __security_check_cookie
0x1800a2b27  add     rsp, 58h
0x1800a2b2b  pop     rdi
0x1800a2b2c  pop     rsi
0x1800a2b2d  pop     rbp
0x1800a2b2e  pop     rbx
0x1800a2b2f  retn
```
