# IsServiceRunning

- ea: `0x180001160`
- end: `0x180001241`
- name: `IsServiceRunning`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800022c4`

## callees

- `0x180001160`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011d7`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800011c3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800011c3`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180001191`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180001191`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800011ed`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800011ed`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001208`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000121c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001208`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000121c`

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
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "rasman", 4u);
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
0x180001160  push    rbx
0x180001162  push    rbp
0x180001163  push    rsi
0x180001164  push    rdi
0x180001165  sub     rsp, 58h
0x180001169  mov     rax, cs:__security_cookie
0x180001170  xor     rax, rsp
0x180001173  mov     [rsp+78h+var_38], rax
0x180001178  xorps   xmm0, xmm0
0x18000117b  xor     ebx, ebx
0x18000117d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180001182  xor     edx, edx; lpDatabaseName
0x180001184  xor     ecx, ecx; lpMachineName
0x180001186  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000118b  lea     ebp, [rbx+1]
0x18000118e  mov     r8d, ebp; dwDesiredAccess
0x180001191  call    cs:__imp_OpenSCManagerA
0x180001198  nop     dword ptr [rax+rax+00h]
0x18000119d  mov     rsi, rax
0x1800011a0  test    rax, rax
0x1800011a3  jnz     short loc_1800011B3
0x1800011a5  call    cs:__imp_GetLastError
0x1800011ac  nop     dword ptr [rax+rax+00h]
0x1800011b1  jmp     short loc_180001228
0x1800011b3  mov     r8d, 4; dwDesiredAccess
0x1800011b9  lea     rdx, ServiceName; "rasman"
0x1800011c0  mov     rcx, rsi; hSCManager
0x1800011c3  call    cs:__imp_OpenServiceA
0x1800011ca  nop     dword ptr [rax+rax+00h]
0x1800011cf  mov     rdi, rax
0x1800011d2  test    rax, rax
0x1800011d5  jnz     short loc_1800011E5
0x1800011d7  call    cs:__imp_GetLastError
0x1800011de  nop     dword ptr [rax+rax+00h]
0x1800011e3  jmp     short loc_180001205
0x1800011e5  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800011ea  mov     rcx, rdi; hService
0x1800011ed  call    cs:__imp_QueryServiceStatus
0x1800011f4  nop     dword ptr [rax+rax+00h]
0x1800011f9  test    eax, eax
0x1800011fb  jz      short loc_1800011D7
0x1800011fd  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180001202  cmovz   ebx, ebp
0x180001205  mov     rcx, rsi; hSCObject
0x180001208  call    cs:__imp_CloseServiceHandle
0x18000120f  nop     dword ptr [rax+rax+00h]
0x180001214  test    rdi, rdi
0x180001217  jz      short loc_180001228
0x180001219  mov     rcx, rdi; hSCObject
0x18000121c  call    cs:__imp_CloseServiceHandle
0x180001223  nop     dword ptr [rax+rax+00h]
0x180001228  mov     eax, ebx
0x18000122a  mov     rcx, [rsp+78h+var_38]
0x18000122f  xor     rcx, rsp; StackCookie
0x180001232  call    __security_check_cookie
0x180001237  add     rsp, 58h
0x18000123b  pop     rdi
0x18000123c  pop     rsi
0x18000123d  pop     rbp
0x18000123e  pop     rbx
0x18000123f  retn
```
