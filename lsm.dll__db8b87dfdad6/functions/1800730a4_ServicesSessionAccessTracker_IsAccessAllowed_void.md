# ServicesSessionAccessTracker::IsAccessAllowed(void)

- ea: `0x1800730a4`
- end: `0x180073202`
- name: `?IsAccessAllowed@ServicesSessionAccessTracker@@QEBAHXZ`
- size: `350`
- prototype: `__int64 __fastcall(ServicesSessionAccessTracker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005ecb0`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x1800730a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800730eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800730eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073196`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180073132`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180073132`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800730dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800730dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800731d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800731dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800731d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800731dd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007318c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007318c`

## string_xrefs

- `0x18007310f`: `OpenSCManager failed: 0x%x in %s`
- `0x180073164`: `OpenService failed: 0x%x in %s`
- `0x180073105`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x18007315a`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x1800731ac`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x1800731b6`: `QueryServiceStatus failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall ServicesSessionAccessTracker::IsAccessAllowed(ServicesSessionAccessTracker *this)
{
  unsigned int v1; // ebx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int v4; // eax
  bool v5; // sf
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  bool v9; // sf
  signed int LastError; // eax
  bool v11; // sf
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = 0;
  v2 = OpenSCManagerW(0, 0, 0x80000000);
  v3 = v2;
  if ( v2 )
  {
    v6 = OpenServiceW(v2, L"ui0detect", 0x80000000);
    v7 = v6;
    if ( v6 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v6, &ServiceStatus) )
      {
        LOBYTE(v1) = ServiceStatus.dwCurrentState == 4;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v11 = LastError < 0;
        }
        if ( v11 )
          _DbgPrintMessage(
            8,
            "QueryServiceStatus failed: 0x%x in %s",
            LastError,
            "ServicesSessionAccessTracker::IsAccessAllowed");
      }
      CloseServiceHandle(v7);
    }
    else
    {
      v8 = GetLastError();
      v9 = v8 < 0;
      if ( v8 > 0 )
      {
        v8 = (unsigned __int16)v8 | 0x80070000;
        v9 = v8 < 0;
      }
      if ( v9 )
        _DbgPrintMessage(8, "OpenService failed: 0x%x in %s", v8, "ServicesSessionAccessTracker::IsAccessAllowed");
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 )
      _DbgPrintMessage(8, "OpenSCManager failed: 0x%x in %s", v4, "ServicesSessionAccessTracker::IsAccessAllowed");
  }
  return v1;
}

```

## disassembly

```asm
0x1800730a4  mov     [rsp+arg_0], rbx
0x1800730a9  mov     [rsp+arg_8], rsi
0x1800730ae  push    rdi
0x1800730af  sub     rsp, 50h
0x1800730b3  mov     rax, cs:__security_cookie
0x1800730ba  xor     rax, rsp
0x1800730bd  mov     [rsp+58h+var_18], rax
0x1800730c2  xorps   xmm0, xmm0
0x1800730c5  mov     edi, 80000000h
0x1800730ca  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800730cf  mov     r8d, edi; dwDesiredAccess
0x1800730d2  xor     edx, edx; lpDatabaseName
0x1800730d4  xor     ecx, ecx; lpMachineName
0x1800730d6  xor     ebx, ebx
0x1800730d8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800730dd  call    cs:__imp_OpenSCManagerW
0x1800730e3  mov     rsi, rax
0x1800730e6  test    rax, rax
0x1800730e9  jnz     short loc_180073125
0x1800730eb  call    cs:__imp_GetLastError
0x1800730f1  test    eax, eax
0x1800730f3  jle     short loc_1800730FF
0x1800730f5  movzx   eax, ax
0x1800730f8  or      eax, 80070000h
0x1800730fd  test    eax, eax
0x1800730ff  jns     loc_1800731E3
0x180073105  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x18007310c  mov     r8d, eax
0x18007310f  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x in %s"
0x180073116  mov     ecx, 8; int
0x18007311b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180073120  jmp     loc_1800731E3
0x180073125  mov     r8d, edi; dwDesiredAccess
0x180073128  lea     rdx, ServiceName; "ui0detect"
0x18007312f  mov     rcx, rsi; hSCManager
0x180073132  call    cs:__imp_OpenServiceW
0x180073138  mov     rdi, rax
0x18007313b  test    rax, rax
0x18007313e  jnz     short loc_180073177
0x180073140  call    cs:__imp_GetLastError
0x180073146  test    eax, eax
0x180073148  jle     short loc_180073154
0x18007314a  movzx   eax, ax
0x18007314d  or      eax, 80070000h
0x180073152  test    eax, eax
0x180073154  jns     loc_1800731DA
0x18007315a  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x180073161  mov     r8d, eax
0x180073164  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x in %s"
0x18007316b  mov     ecx, 8; int
0x180073170  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180073175  jmp     short loc_1800731DA
0x180073177  xorps   xmm0, xmm0
0x18007317a  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18007317f  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180073184  mov     rcx, rdi; hService
0x180073187  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18007318c  call    cs:__imp_QueryServiceStatus
0x180073192  test    eax, eax
0x180073194  jnz     short loc_1800731C9
0x180073196  call    cs:__imp_GetLastError
0x18007319c  test    eax, eax
0x18007319e  jle     short loc_1800731AA
0x1800731a0  movzx   eax, ax
0x1800731a3  or      eax, 80070000h
0x1800731a8  test    eax, eax
0x1800731aa  jns     short loc_1800731D1
0x1800731ac  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x1800731b3  mov     r8d, eax
0x1800731b6  lea     rdx, aQueryservicest_1; "QueryServiceStatus failed: 0x%x in %s"
0x1800731bd  mov     ecx, 8; int
0x1800731c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800731c7  jmp     short loc_1800731D1
0x1800731c9  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800731ce  setz    bl
0x1800731d1  mov     rcx, rdi; hSCObject
0x1800731d4  call    cs:__imp_CloseServiceHandle
0x1800731da  mov     rcx, rsi; hSCObject
0x1800731dd  call    cs:__imp_CloseServiceHandle
0x1800731e3  mov     eax, ebx
0x1800731e5  mov     rcx, [rsp+58h+var_18]
0x1800731ea  xor     rcx, rsp; StackCookie
0x1800731ed  call    __security_check_cookie
0x1800731f2  mov     rbx, [rsp+58h+arg_0]
0x1800731f7  mov     rsi, [rsp+58h+arg_8]
0x1800731fc  add     rsp, 50h
0x180073200  pop     rdi
0x180073201  retn
```
