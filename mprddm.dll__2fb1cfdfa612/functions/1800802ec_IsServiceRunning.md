# IsServiceRunning

- ea: `0x1800802ec`
- end: `0x1800803a2`
- name: `IsServiceRunning`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800441d8`
- `0x180080100`

## callees

- `0x1800802ec`
- `0x18008c630`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008032b`
- `KERNEL32!GetLastError` at `0x180080351`
- `KERNEL32!GetLastError` at `0x18008032b`
- `KERNEL32!GetLastError` at `0x180080351`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180080361`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180080361`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180080343`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180080343`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008031d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008031d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080376`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080384`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080376`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080384`

## pseudocode

```c
_BOOL8 IsServiceRunning()
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

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
0x1800802ec  push    rbx
0x1800802ee  push    rbp
0x1800802ef  push    rsi
0x1800802f0  push    rdi
0x1800802f1  sub     rsp, 58h
0x1800802f5  mov     rax, cs:__security_cookie
0x1800802fc  xor     rax, rsp
0x1800802ff  mov     [rsp+78h+var_38], rax
0x180080304  xorps   xmm0, xmm0
0x180080307  xor     ebx, ebx
0x180080309  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18008030e  xor     edx, edx; lpDatabaseName
0x180080310  xor     ecx, ecx; lpMachineName
0x180080312  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180080317  lea     ebp, [rbx+1]
0x18008031a  mov     r8d, ebp; dwDesiredAccess
0x18008031d  call    cs:__imp_OpenSCManagerW
0x180080323  mov     rsi, rax
0x180080326  test    rax, rax
0x180080329  jnz     short loc_180080333
0x18008032b  call    cs:__imp_GetLastError
0x180080331  jmp     short loc_18008038A
0x180080333  mov     r8d, 4; dwDesiredAccess
0x180080339  lea     rdx, ServiceName; "ikeext"
0x180080340  mov     rcx, rsi; hSCManager
0x180080343  call    cs:__imp_OpenServiceA
0x180080349  mov     rdi, rax
0x18008034c  test    rax, rax
0x18008034f  jnz     short loc_180080359
0x180080351  call    cs:__imp_GetLastError
0x180080357  jmp     short loc_180080373
0x180080359  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18008035e  mov     rcx, rdi; hService
0x180080361  call    cs:__imp_QueryServiceStatus
0x180080367  test    eax, eax
0x180080369  jz      short loc_180080351
0x18008036b  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180080370  cmovz   ebx, ebp
0x180080373  mov     rcx, rsi; hSCObject
0x180080376  call    cs:__imp_CloseServiceHandle
0x18008037c  test    rdi, rdi
0x18008037f  jz      short loc_18008038A
0x180080381  mov     rcx, rdi; hSCObject
0x180080384  call    cs:__imp_CloseServiceHandle
0x18008038a  mov     eax, ebx
0x18008038c  mov     rcx, [rsp+78h+var_38]
0x180080391  xor     rcx, rsp; StackCookie
0x180080394  call    __security_check_cookie
0x180080399  add     rsp, 58h
0x18008039d  pop     rdi
0x18008039e  pop     rsi
0x18008039f  pop     rbp
0x1800803a0  pop     rbx
0x1800803a1  retn
```
