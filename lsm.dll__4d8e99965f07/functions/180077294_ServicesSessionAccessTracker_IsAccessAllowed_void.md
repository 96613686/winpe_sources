# ServicesSessionAccessTracker::IsAccessAllowed(void)

- ea: `0x180077294`
- end: `0x180077423`
- name: `?IsAccessAllowed@ServicesSessionAccessTracker@@QEBAHXZ`
- size: `399`
- prototype: `__int64 __fastcall(ServicesSessionAccessTracker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800627a0`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x180077294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800772e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800773a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800772e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800773a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007732e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007732e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800772cd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800772cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800773e8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800773f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800773e8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800773f7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180077394`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180077394`

## string_xrefs

- `0x18007730b`: `OpenSCManager failed: 0x%x in %s`
- `0x18007736c`: `OpenService failed: 0x%x in %s`
- `0x180077301`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x180077362`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x1800773c0`: `ServicesSessionAccessTracker::IsAccessAllowed`
- `0x1800773ca`: `QueryServiceStatus failed: 0x%x in %s`

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
0x180077294  mov     [rsp+arg_0], rbx
0x180077299  mov     [rsp+arg_8], rsi
0x18007729e  push    rdi
0x18007729f  sub     rsp, 50h
0x1800772a3  mov     rax, cs:__security_cookie
0x1800772aa  xor     rax, rsp
0x1800772ad  mov     [rsp+58h+var_18], rax
0x1800772b2  xorps   xmm0, xmm0
0x1800772b5  mov     edi, 80000000h
0x1800772ba  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800772bf  mov     r8d, edi; dwDesiredAccess
0x1800772c2  xor     edx, edx; lpDatabaseName
0x1800772c4  xor     ecx, ecx; lpMachineName
0x1800772c6  xor     ebx, ebx
0x1800772c8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800772cd  call    cs:__imp_OpenSCManagerW
0x1800772d4  nop     dword ptr [rax+rax+00h]
0x1800772d9  mov     rsi, rax
0x1800772dc  test    rax, rax
0x1800772df  jnz     short loc_180077321
0x1800772e1  call    cs:__imp_GetLastError
0x1800772e8  nop     dword ptr [rax+rax+00h]
0x1800772ed  test    eax, eax
0x1800772ef  jle     short loc_1800772FB
0x1800772f1  movzx   eax, ax
0x1800772f4  or      eax, 80070000h
0x1800772f9  test    eax, eax
0x1800772fb  jns     loc_180077403
0x180077301  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x180077308  mov     r8d, eax
0x18007730b  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x in %s"
0x180077312  mov     ecx, 8; int
0x180077317  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007731c  jmp     loc_180077403
0x180077321  mov     r8d, edi; dwDesiredAccess
0x180077324  lea     rdx, ServiceName; "ui0detect"
0x18007732b  mov     rcx, rsi; hSCManager
0x18007732e  call    cs:__imp_OpenServiceW
0x180077335  nop     dword ptr [rax+rax+00h]
0x18007733a  mov     rdi, rax
0x18007733d  test    rax, rax
0x180077340  jnz     short loc_18007737F
0x180077342  call    cs:__imp_GetLastError
0x180077349  nop     dword ptr [rax+rax+00h]
0x18007734e  test    eax, eax
0x180077350  jle     short loc_18007735C
0x180077352  movzx   eax, ax
0x180077355  or      eax, 80070000h
0x18007735a  test    eax, eax
0x18007735c  jns     loc_1800773F4
0x180077362  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x180077369  mov     r8d, eax
0x18007736c  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x in %s"
0x180077373  mov     ecx, 8; int
0x180077378  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007737d  jmp     short loc_1800773F4
0x18007737f  xorps   xmm0, xmm0
0x180077382  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180077387  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18007738c  mov     rcx, rdi; hService
0x18007738f  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180077394  call    cs:__imp_QueryServiceStatus
0x18007739b  nop     dword ptr [rax+rax+00h]
0x1800773a0  test    eax, eax
0x1800773a2  jnz     short loc_1800773DD
0x1800773a4  call    cs:__imp_GetLastError
0x1800773ab  nop     dword ptr [rax+rax+00h]
0x1800773b0  test    eax, eax
0x1800773b2  jle     short loc_1800773BE
0x1800773b4  movzx   eax, ax
0x1800773b7  or      eax, 80070000h
0x1800773bc  test    eax, eax
0x1800773be  jns     short loc_1800773E5
0x1800773c0  lea     r9, aServicessessio; "ServicesSessionAccessTracker::IsAccessA"...
0x1800773c7  mov     r8d, eax
0x1800773ca  lea     rdx, aQueryservicest_1; "QueryServiceStatus failed: 0x%x in %s"
0x1800773d1  mov     ecx, 8; int
0x1800773d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800773db  jmp     short loc_1800773E5
0x1800773dd  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800773e2  setz    bl
0x1800773e5  mov     rcx, rdi; hSCObject
0x1800773e8  call    cs:__imp_CloseServiceHandle
0x1800773ef  nop     dword ptr [rax+rax+00h]
0x1800773f4  mov     rcx, rsi; hSCObject
0x1800773f7  call    cs:__imp_CloseServiceHandle
0x1800773fe  nop     dword ptr [rax+rax+00h]
0x180077403  mov     eax, ebx
0x180077405  mov     rcx, [rsp+58h+var_18]
0x18007740a  xor     rcx, rsp; StackCookie
0x18007740d  call    __security_check_cookie
0x180077412  mov     rbx, [rsp+58h+arg_0]
0x180077417  mov     rsi, [rsp+58h+arg_8]
0x18007741c  add     rsp, 50h
0x180077420  pop     rdi
0x180077421  retn
```
