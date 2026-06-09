# StopW32Time(void)

- ea: `0x1800177d4`
- end: `0x18001792c`
- name: `?StopW32Time@@YAJXZ`
- size: `344`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800174e4`

## callees

- `0x180014660`
- `0x1800177d4`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!ControlService` at `0x18001789b`
- `ADVAPI32!ControlService` at `0x18001789b`
- `ADVAPI32!CloseServiceHandle` at `0x1800178fe`
- `ADVAPI32!CloseServiceHandle` at `0x180017907`
- `ADVAPI32!CloseServiceHandle` at `0x1800178fe`
- `ADVAPI32!CloseServiceHandle` at `0x180017907`
- `ADVAPI32!OpenServiceW` at `0x18001785a`
- `ADVAPI32!OpenServiceW` at `0x18001785a`
- `ADVAPI32!OpenSCManagerW` at `0x180017810`
- `ADVAPI32!OpenSCManagerW` at `0x180017810`
- `KERNEL32!GetLastError` at `0x1800178a5`
- `KERNEL32!GetLastError` at `0x1800178a5`

## string_xrefs

- `0x180017822`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x18001786c`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800178ea`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800177f5`: `ServicesActive`

## pseudocode

```c
__int64 StopW32Time(void)
{
  SC_HANDLE v0; // rax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  SC_HANDLE v3; // rsi
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  SC_HANDLE v8; // rdi
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v0;
  if ( v0 )
  {
    v5 = OpenServiceW(v0, L"w32time", 0x20u);
    v8 = v5;
    if ( v5 )
    {
      if ( ControlService(v5, 1u, &ServiceStatus) )
      {
        v4 = 0;
        if ( ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0 )
          CEventLogger::LogError(
            v10,
            v9,
            L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
            0x2DBu,
            L"StopW32Time",
            0);
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        CEventLogger::LogError(
          v13,
          v12,
          L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
          0x2D3u,
          L"StopW32Time",
          0);
      }
      CloseServiceHandle(v8);
    }
    else
    {
      CEventLogger::LogError(v7, v6, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x2CEu, L"StopW32Time", 0);
      v4 = -2147467259;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    CEventLogger::LogError(v2, v1, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x2C9u, L"StopW32Time", 0);
    return (unsigned int)-2147467259;
  }
  return v4;
}

```

## disassembly

```asm
0x1800177d4  mov     [rsp+arg_0], rbx
0x1800177d9  mov     [rsp+arg_8], rsi
0x1800177de  push    rdi
0x1800177df  sub     rsp, 60h
0x1800177e3  mov     rax, cs:__security_cookie
0x1800177ea  xor     rax, rsp
0x1800177ed  mov     [rsp+68h+var_18], rax
0x1800177f2  xorps   xmm0, xmm0
0x1800177f5  lea     rdx, DatabaseName; "ServicesActive"
0x1800177fc  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180017801  mov     ebx, 1
0x180017806  xor     ecx, ecx; lpMachineName
0x180017808  mov     r8d, ebx; dwDesiredAccess
0x18001780b  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180017810  call    cs:__imp_OpenSCManagerW
0x180017816  mov     rsi, rax
0x180017819  test    rax, rax
0x18001781c  jnz     short loc_18001784A
0x18001781e  mov     [rsp+68h+var_40], eax; unsigned int
0x180017822  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017829  lea     rax, aStopw32time; "StopW32Time"
0x180017830  mov     r9d, 2C9h; unsigned int
0x180017836  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001783b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017840  mov     ebx, 80004005h
0x180017845  jmp     loc_18001790D
0x18001784a  mov     r8d, 20h ; ' '; dwDesiredAccess
0x180017850  lea     rdx, ServiceName; "w32time"
0x180017857  mov     rcx, rsi; hSCManager
0x18001785a  call    cs:__imp_OpenServiceW
0x180017860  mov     rdi, rax
0x180017863  test    rax, rax
0x180017866  jnz     short loc_180017891
0x180017868  mov     [rsp+68h+var_40], eax; unsigned int
0x18001786c  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017873  lea     rax, aStopw32time; "StopW32Time"
0x18001787a  mov     r9d, 2CEh; unsigned int
0x180017880  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180017885  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001788a  mov     ebx, 80004005h
0x18001788f  jmp     short loc_180017904
0x180017891  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180017896  mov     edx, ebx; dwControl
0x180017898  mov     rcx, rdi; hService
0x18001789b  call    cs:__imp_ControlService
0x1800178a1  test    eax, eax
0x1800178a3  jnz     short loc_1800178CA
0x1800178a5  call    cs:__imp_GetLastError
0x1800178ab  mov     ebx, eax
0x1800178ad  test    eax, eax
0x1800178af  jle     short loc_1800178BA
0x1800178b1  movzx   ebx, ax
0x1800178b4  or      ebx, 80070000h
0x1800178ba  mov     [rsp+68h+var_40], 0
0x1800178c2  mov     r9d, 2D3h
0x1800178c8  jmp     short loc_1800178E3
0x1800178ca  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x1800178ce  xor     ebx, ebx
0x1800178d0  dec     eax
0x1800178d2  test    eax, 0FFFFFFFDh
0x1800178d7  jz      short loc_1800178FB
0x1800178d9  mov     [rsp+68h+var_40], ebx; unsigned int
0x1800178dd  mov     r9d, 2DBh; unsigned int
0x1800178e3  lea     rax, aStopw32time; "StopW32Time"
0x1800178ea  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800178f1  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800178f6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800178fb  mov     rcx, rdi; hSCObject
0x1800178fe  call    cs:__imp_CloseServiceHandle
0x180017904  mov     rcx, rsi; hSCObject
0x180017907  call    cs:__imp_CloseServiceHandle
0x18001790d  mov     eax, ebx
0x18001790f  mov     rcx, [rsp+68h+var_18]
0x180017914  xor     rcx, rsp; StackCookie
0x180017917  call    __security_check_cookie
0x18001791c  mov     rbx, [rsp+68h+arg_0]
0x180017921  mov     rsi, [rsp+68h+arg_8]
0x180017926  add     rsp, 60h
0x18001792a  pop     rdi
0x18001792b  retn
```
