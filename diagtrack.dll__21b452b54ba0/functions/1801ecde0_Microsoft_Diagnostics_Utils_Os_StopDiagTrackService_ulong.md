# Microsoft::Diagnostics::Utils::Os::StopDiagTrackService(ulong)

- ea: `0x1801ecde0`
- end: `0x1801ecf5a`
- name: `?StopDiagTrackService@Os@Utils@Diagnostics@Microsoft@@SAJK@Z`
- size: `378`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180240be0`

## callees

- `0x180064e6c`
- `0x18008abf4`
- `0x1801ecde0`
- `0x1801ecf60`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801ecea9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801ecea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ece90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ece90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecefd`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801ece86`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801ece86`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801ece53`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801eceb6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801ece53`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801eceb6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801ece2b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801ece2b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801ece08`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801ece08`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::StopDiagTrackService()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  const char *v4; // r9
  __int64 v5; // rdx
  signed int v6; // eax
  bool v7; // zf
  unsigned int i; // edi
  unsigned int LastError; // ebx
  SC_HANDLE v11; // [rsp+20h] [rbp-40h] BYREF
  SC_HANDLE v12; // [rsp+28h] [rbp-38h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v0 = OpenSCManagerW(0, 0, 1u);
  v11 = v0;
  if ( !v0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x69F,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v1);
    goto LABEL_25;
  }
  v2 = OpenServiceW(v0, L"diagtrack", 0x24u);
  v12 = v2;
  v3 = v2;
  if ( v2 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v2, &ServiceStatus) )
    {
      v5 = 1708;
LABEL_5:
      v6 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
             v4);
      goto LABEL_16;
    }
    if ( ServiceStatus.dwCurrentState == 1 )
    {
LABEL_18:
      LastError = 0;
      goto LABEL_17;
    }
    if ( ControlService(v3, 1u, &ServiceStatus) )
    {
      for ( i = 0; i < 5; ++i )
      {
        Sleep(0x3E8u);
        if ( !QueryServiceStatus(v3, &ServiceStatus) )
        {
          v5 = 1727;
          goto LABEL_5;
        }
        if ( ServiceStatus.dwCurrentState == 1 )
          goto LABEL_18;
      }
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6C8,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
             (const char *)0x5B4,
             (unsigned int)v11);
      goto LABEL_16;
    }
    v6 = GetLastError();
    v7 = v6 == 1062;
  }
  else
  {
    v6 = GetLastError();
    v7 = v6 == 1060;
  }
  if ( v7 )
  {
    v6 = 0;
  }
  else if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
  }
LABEL_16:
  LastError = v6;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x1801ecde0  mov     [rsp-8+arg_0], rbx
0x1801ecde5  mov     [rsp-8+arg_8], rdi
0x1801ecdea  push    rbp
0x1801ecdeb  mov     rbp, rsp
0x1801ecdee  sub     rsp, 60h
0x1801ecdf2  mov     rax, cs:__security_cookie
0x1801ecdf9  xor     rax, rsp
0x1801ecdfc  mov     [rbp+var_10], rax
0x1801ece00  xor     edx, edx; lpDatabaseName
0x1801ece02  xor     ecx, ecx; lpMachineName
0x1801ece04  lea     r8d, [rdx+1]; dwDesiredAccess
0x1801ece08  call    cs:__imp_OpenSCManagerW
0x1801ece0e  mov     [rbp+var_40], rax
0x1801ece12  test    rax, rax
0x1801ece15  jz      loc_1801ECF1C
0x1801ece1b  mov     rdx, cs:lpServiceName; lpServiceName
0x1801ece22  mov     r8d, 24h ; '$'; dwDesiredAccess
0x1801ece28  mov     rcx, rax; hSCManager
0x1801ece2b  call    cs:__imp_OpenServiceW
0x1801ece31  mov     [rbp+var_38], rax
0x1801ece35  mov     rbx, rax
0x1801ece38  test    rax, rax
0x1801ece3b  jz      loc_1801ECEFD
0x1801ece41  xorps   xmm0, xmm0
0x1801ece44  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1801ece48  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1801ece4c  mov     rcx, rax; hService
0x1801ece4f  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1801ece53  call    cs:__imp_QueryServiceStatus
0x1801ece59  test    eax, eax
0x1801ece5b  jnz     short loc_1801ECE74
0x1801ece5d  mov     edx, 6ACh; void *
0x1801ece62  mov     rcx, [rbp+8]; this
0x1801ece66  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801ece6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801ece72  jmp     short loc_1801ECEEC
0x1801ece74  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x1801ece78  jz      short loc_1801ECEF9
0x1801ece7a  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x1801ece7e  mov     edx, 1; dwControl
0x1801ece83  mov     rcx, rbx; hService
0x1801ece86  call    cs:__imp_ControlService
0x1801ece8c  test    eax, eax
0x1801ece8e  jnz     short loc_1801ECE9D
0x1801ece90  call    cs:__imp_GetLastError
0x1801ece96  cmp     eax, 426h
0x1801ece9b  jmp     short loc_1801ECF08
0x1801ece9d  xor     edi, edi
0x1801ece9f  cmp     edi, 5
0x1801ecea2  jnb     short loc_1801ECED1
0x1801ecea4  mov     ecx, 3E8h; dwMilliseconds
0x1801ecea9  call    cs:__imp_Sleep
0x1801eceaf  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1801eceb3  mov     rcx, rbx; hService
0x1801eceb6  call    cs:__imp_QueryServiceStatus
0x1801ecebc  test    eax, eax
0x1801ecebe  jz      short loc_1801ECECA
0x1801ecec0  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x1801ecec4  jz      short loc_1801ECEF9
0x1801ecec6  inc     edi
0x1801ecec8  jmp     short loc_1801ECE9F
0x1801ececa  mov     edx, 6BFh
0x1801ececf  jmp     short loc_1801ECE62
0x1801eced1  mov     rcx, [rbp+8]; this
0x1801eced5  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801ecedc  mov     r9d, 5B4h; char *
0x1801ecee2  mov     edx, 6C8h; void *
0x1801ecee7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801eceec  mov     ebx, eax
0x1801eceee  lea     rcx, [rbp+var_38]
0x1801ecef2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801ecef7  jmp     short loc_1801ECF33
0x1801ecef9  xor     ebx, ebx
0x1801ecefb  jmp     short loc_1801ECEEE
0x1801ecefd  call    cs:__imp_GetLastError
0x1801ecf03  cmp     eax, 424h
0x1801ecf08  jnz     short loc_1801ECF0E
0x1801ecf0a  xor     eax, eax
0x1801ecf0c  jmp     short loc_1801ECEEC
0x1801ecf0e  test    eax, eax
0x1801ecf10  jle     short loc_1801ECEEC
0x1801ecf12  movzx   eax, ax
0x1801ecf15  or      eax, 80070000h
0x1801ecf1a  jmp     short loc_1801ECEEC
0x1801ecf1c  mov     rcx, [rbp+8]; this
0x1801ecf20  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801ecf27  mov     edx, 69Fh; void *
0x1801ecf2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801ecf31  mov     ebx, eax
0x1801ecf33  lea     rcx, [rbp+var_40]
0x1801ecf37  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801ecf3c  mov     eax, ebx
0x1801ecf3e  mov     rcx, [rbp+var_10]
0x1801ecf42  xor     rcx, rsp; StackCookie
0x1801ecf45  call    __security_check_cookie
0x1801ecf4a  mov     rbx, [rsp+60h+arg_0]
0x1801ecf4f  mov     rdi, [rsp+60h+arg_8]
0x1801ecf54  add     rsp, 60h
0x1801ecf58  pop     rbp
0x1801ecf59  retn
```
