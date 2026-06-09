# CServiceMonitor::AttachToService(void)

- ea: `0x180008e14`
- end: `0x180008f1d`
- name: `?AttachToService@CServiceMonitor@@IEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011c38`

## callees

- `0x180002270`
- `0x180008e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008ea0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008ea0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008e44`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008e44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008e76`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008e76`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008ecd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008ecd`

## string_xrefs

- `0x180008e35`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::AttachToService(const WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  signed int v4; // eax
  signed int v5; // ebx
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  SC_HANDLE v8; // rcx
  signed int v9; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = 0;
    v6 = OpenServiceW(v2, this + 4, 4u);
    *((_QWORD *)this + 67) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( v5 >= 0 )
  {
    v8 = (SC_HANDLE)*((_QWORD *)this + 67);
    v5 = -2147467259;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v8 )
    {
      if ( QueryServiceStatus(v8, &ServiceStatus) )
      {
        v5 = 0;
LABEL_15:
        *((_DWORD *)this + 131) = ServiceStatus.dwCurrentState;
        return (unsigned int)v5;
      }
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v5 >= 0 )
      goto LABEL_15;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008e14  mov     [rsp+arg_8], rbx
0x180008e19  mov     [rsp+arg_10], rbp
0x180008e1e  push    rsi
0x180008e1f  sub     rsp, 50h
0x180008e23  mov     rax, cs:__security_cookie
0x180008e2a  xor     rax, rsp
0x180008e2d  mov     [rsp+58h+var_18], rax
0x180008e32  mov     rsi, rcx
0x180008e35  lea     rdx, DatabaseName; "ServicesActive"
0x180008e3c  xor     ecx, ecx; lpMachineName
0x180008e3e  mov     r8d, 1; dwDesiredAccess
0x180008e44  call    cs:__imp_OpenSCManagerW
0x180008e4a  mov     rbp, rax
0x180008e4d  test    rax, rax
0x180008e50  jnz     short loc_180008E69
0x180008e52  call    cs:__imp_GetLastError
0x180008e58  mov     ebx, eax
0x180008e5a  test    eax, eax
0x180008e5c  jle     short loc_180008EA6
0x180008e5e  movzx   ebx, ax
0x180008e61  or      ebx, 80070000h
0x180008e67  jmp     short loc_180008EA6
0x180008e69  xor     ebx, ebx
0x180008e6b  lea     rdx, [rsi+8]; lpServiceName
0x180008e6f  mov     rcx, rbp; hSCManager
0x180008e72  lea     r8d, [rbx+4]; dwDesiredAccess
0x180008e76  call    cs:__imp_OpenServiceW
0x180008e7c  mov     [rsi+218h], rax
0x180008e83  test    rax, rax
0x180008e86  jnz     short loc_180008E9D
0x180008e88  call    cs:__imp_GetLastError
0x180008e8e  mov     ebx, eax
0x180008e90  test    eax, eax
0x180008e92  jle     short loc_180008E9D
0x180008e94  movzx   ebx, ax
0x180008e97  or      ebx, 80070000h
0x180008e9d  mov     rcx, rbp; hSCObject
0x180008ea0  call    cs:__imp_CloseServiceHandle
0x180008ea6  test    ebx, ebx
0x180008ea8  js      short loc_180008EFE
0x180008eaa  mov     rcx, [rsi+218h]; hService
0x180008eb1  xorps   xmm0, xmm0
0x180008eb4  mov     ebx, 80004005h
0x180008eb9  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180008ebe  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008ec3  test    rcx, rcx
0x180008ec6  jz      short loc_180008EF0
0x180008ec8  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180008ecd  call    cs:__imp_QueryServiceStatus
0x180008ed3  test    eax, eax
0x180008ed5  jz      short loc_180008EDB
0x180008ed7  xor     ebx, ebx
0x180008ed9  jmp     short loc_180008EF4
0x180008edb  call    cs:__imp_GetLastError
0x180008ee1  mov     ebx, eax
0x180008ee3  test    eax, eax
0x180008ee5  jle     short loc_180008EF0
0x180008ee7  movzx   ebx, ax
0x180008eea  or      ebx, 80070000h
0x180008ef0  test    ebx, ebx
0x180008ef2  js      short loc_180008EFE
0x180008ef4  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x180008ef8  mov     [rsi+20Ch], eax
0x180008efe  mov     eax, ebx
0x180008f00  mov     rcx, [rsp+58h+var_18]
0x180008f05  xor     rcx, rsp; StackCookie
0x180008f08  call    __security_check_cookie
0x180008f0d  mov     rbx, [rsp+58h+arg_8]
0x180008f12  mov     rbp, [rsp+58h+arg_10]
0x180008f17  add     rsp, 50h
0x180008f1b  pop     rsi
0x180008f1c  retn
```
