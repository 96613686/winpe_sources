# QueryService(ushort const *,bool &)

- ea: `0x180041e38`
- end: `0x180041f28`
- name: `?QueryService@@YAJPEBGAEA_N@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180041610`

## callees

- `0x180041e38`
- `0x180044420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041efa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041e5c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041e5c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041ed2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041ef2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041ed2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041ef2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041e7e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041e7e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180041ea1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180041ea1`

## pseudocode

```c
__int64 __fastcall QueryService(const unsigned __int16 *a1, bool *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  signed int v10; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"WinMgmt", 4u);
    v6 = v5;
    if ( v5 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v5, &ServiceStatus) )
      {
        v8 = 0;
        *a2 = ServiceStatus.dwCurrentState == 4;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      v9 = GetLastError();
      v8 = v9;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x180041e38  push    rbx
0x180041e3a  push    rsi
0x180041e3b  push    rdi
0x180041e3c  push    r14
0x180041e3e  sub     rsp, 58h
0x180041e42  mov     rax, cs:__security_cookie
0x180041e49  xor     rax, rsp
0x180041e4c  mov     [rsp+78h+var_38], rax
0x180041e51  mov     r14, rdx
0x180041e54  xor     ecx, ecx; lpMachineName
0x180041e56  xor     edx, edx; lpDatabaseName
0x180041e58  lea     r8d, [rdx+1]; dwDesiredAccess
0x180041e5c  call    cs:__imp_OpenSCManagerW
0x180041e62  mov     rsi, rax
0x180041e65  test    rax, rax
0x180041e68  jz      loc_180041EFA
0x180041e6e  mov     r8d, 4; dwDesiredAccess
0x180041e74  lea     rdx, ServiceName; "WinMgmt"
0x180041e7b  mov     rcx, rax; hSCManager
0x180041e7e  call    cs:__imp_OpenServiceW
0x180041e84  mov     rdi, rax
0x180041e87  test    rax, rax
0x180041e8a  jz      short loc_180041EDA
0x180041e8c  xorps   xmm0, xmm0
0x180041e8f  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180041e94  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180041e99  mov     rcx, rax; hService
0x180041e9c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180041ea1  call    cs:__imp_QueryServiceStatus
0x180041ea7  test    eax, eax
0x180041ea9  jnz     short loc_180041EC2
0x180041eab  call    cs:__imp_GetLastError
0x180041eb1  mov     ebx, eax
0x180041eb3  test    eax, eax
0x180041eb5  jle     short loc_180041ECF
0x180041eb7  movzx   ebx, ax
0x180041eba  or      ebx, 80070000h
0x180041ec0  jmp     short loc_180041ECF
0x180041ec2  xor     ebx, ebx
0x180041ec4  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180041ec9  setz    al
0x180041ecc  mov     [r14], al
0x180041ecf  mov     rcx, rdi; hSCObject
0x180041ed2  call    cs:__imp_CloseServiceHandle
0x180041ed8  jmp     short loc_180041EEF
0x180041eda  call    cs:__imp_GetLastError
0x180041ee0  mov     ebx, eax
0x180041ee2  test    eax, eax
0x180041ee4  jle     short loc_180041EEF
0x180041ee6  movzx   ebx, ax
0x180041ee9  or      ebx, 80070000h
0x180041eef  mov     rcx, rsi; hSCObject
0x180041ef2  call    cs:__imp_CloseServiceHandle
0x180041ef8  jmp     short loc_180041F0F
0x180041efa  call    cs:__imp_GetLastError
0x180041f00  mov     ebx, eax
0x180041f02  test    eax, eax
0x180041f04  jle     short loc_180041F0F
0x180041f06  movzx   ebx, ax
0x180041f09  or      ebx, 80070000h
0x180041f0f  mov     eax, ebx
0x180041f11  mov     rcx, [rsp+78h+var_38]
0x180041f16  xor     rcx, rsp; StackCookie
0x180041f19  call    __security_check_cookie
0x180041f1e  add     rsp, 58h
0x180041f22  pop     r14
0x180041f24  pop     rdi
0x180041f25  pop     rsi
0x180041f26  pop     rbx
0x180041f27  retn
```
