# BdeSvcApiStartService(void)

- ea: `0x180012f48`
- end: `0x1800130a2`
- name: `?BdeSvcApiStartService@@YAJXZ`
- size: `346`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006570`
- `0x180010cb0`

## callees

- `0x180012f48`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013063`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001302d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001302d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180013007`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180013007`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001307b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013084`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001307b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013084`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012fb8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012fb8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012f7c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012f7c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012fec`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001303b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012fec`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001303b`

## string_xrefs

- `0x180012f63`: `ServicesActive`

## pseudocode

```c
__int64 BdeSvcApiStartService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  signed int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  signed int LastError; // eax
  signed int v7; // eax
  int v8; // edi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"BDESVC", 0x14u);
    v5 = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_23;
    }
    if ( QueryServiceStatus(v4, &ServiceStatus) )
    {
      v3 = 0;
      if ( ServiceStatus.dwCurrentState == 4 )
        goto LABEL_22;
      if ( !StartServiceW(v5, 0, 0) )
      {
        v7 = GetLastError();
        if ( v7 != 1056 )
        {
          if ( v7 <= 0 )
          {
            v3 = v7;
            goto LABEL_22;
          }
LABEL_21:
          v3 = (unsigned __int16)v7 | 0x80070000;
        }
LABEL_22:
        CloseServiceHandle(v5);
LABEL_23:
        CloseServiceHandle(v1);
        return v3;
      }
      v8 = 0;
      while ( 1 )
      {
        Sleep(0xC8u);
        if ( !QueryServiceStatus(v5, &ServiceStatus) )
          break;
        if ( ServiceStatus.dwCurrentState != 2 )
        {
          if ( ServiceStatus.dwCurrentState == 4 )
            goto LABEL_22;
LABEL_19:
          v3 = -2147023843;
          goto LABEL_22;
        }
        if ( ++v8 >= 25 )
          goto LABEL_19;
      }
    }
    v7 = GetLastError();
    v3 = v7;
    if ( v7 <= 0 )
      goto LABEL_22;
    goto LABEL_21;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x180012f48  push    rbx
0x180012f4a  push    rbp
0x180012f4b  push    rsi
0x180012f4c  push    rdi
0x180012f4d  sub     rsp, 58h
0x180012f51  mov     rax, cs:__security_cookie
0x180012f58  xor     rax, rsp
0x180012f5b  mov     [rsp+78h+var_38], rax
0x180012f60  xorps   xmm0, xmm0
0x180012f63  lea     rdx, DatabaseName; "ServicesActive"
0x180012f6a  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180012f6f  mov     r8d, 1; dwDesiredAccess
0x180012f75  xor     ecx, ecx; lpMachineName
0x180012f77  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180012f7c  call    cs:__imp_OpenSCManagerW
0x180012f82  mov     rbp, rax
0x180012f85  test    rax, rax
0x180012f88  jnz     short loc_180012FA8
0x180012f8a  call    cs:__imp_GetLastError
0x180012f90  mov     ebx, eax
0x180012f92  test    eax, eax
0x180012f94  jle     loc_18001308A
0x180012f9a  movzx   ebx, ax
0x180012f9d  or      ebx, 80070000h
0x180012fa3  jmp     loc_18001308A
0x180012fa8  mov     r8d, 14h; dwDesiredAccess
0x180012fae  lea     rdx, ServiceName; "BDESVC"
0x180012fb5  mov     rcx, rbp; hSCManager
0x180012fb8  call    cs:__imp_OpenServiceW
0x180012fbe  mov     rsi, rax
0x180012fc1  test    rax, rax
0x180012fc4  jnz     short loc_180012FE4
0x180012fc6  call    cs:__imp_GetLastError
0x180012fcc  mov     ebx, eax
0x180012fce  test    eax, eax
0x180012fd0  jle     loc_180013081
0x180012fd6  movzx   ebx, ax
0x180012fd9  or      ebx, 80070000h
0x180012fdf  jmp     loc_180013081
0x180012fe4  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180012fe9  mov     rcx, rsi; hService
0x180012fec  call    cs:__imp_QueryServiceStatus
0x180012ff2  test    eax, eax
0x180012ff4  jz      short loc_180013063
0x180012ff6  xor     ebx, ebx
0x180012ff8  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180012ffd  jz      short loc_180013078
0x180012fff  xor     r8d, r8d; lpServiceArgVectors
0x180013002  xor     edx, edx; dwNumServiceArgs
0x180013004  mov     rcx, rsi; hService
0x180013007  call    cs:__imp_StartServiceW
0x18001300d  test    eax, eax
0x18001300f  jnz     short loc_180013026
0x180013011  call    cs:__imp_GetLastError
0x180013017  cmp     eax, 420h
0x18001301c  jz      short loc_180013078
0x18001301e  test    eax, eax
0x180013020  jg      short loc_18001306F
0x180013022  mov     ebx, eax
0x180013024  jmp     short loc_180013078
0x180013026  xor     edi, edi
0x180013028  mov     ecx, 0C8h; dwMilliseconds
0x18001302d  call    cs:__imp_Sleep
0x180013033  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180013038  mov     rcx, rsi; hService
0x18001303b  call    cs:__imp_QueryServiceStatus
0x180013041  test    eax, eax
0x180013043  jz      short loc_180013063
0x180013045  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 2
0x18001304a  jnz     short loc_180013055
0x18001304c  inc     edi
0x18001304e  cmp     edi, 19h
0x180013051  jl      short loc_180013028
0x180013053  jmp     short loc_18001305C
0x180013055  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18001305a  jz      short loc_180013078
0x18001305c  mov     ebx, 8007041Dh
0x180013061  jmp     short loc_180013078
0x180013063  call    cs:__imp_GetLastError
0x180013069  mov     ebx, eax
0x18001306b  test    eax, eax
0x18001306d  jle     short loc_180013078
0x18001306f  movzx   ebx, ax
0x180013072  or      ebx, 80070000h
0x180013078  mov     rcx, rsi; hSCObject
0x18001307b  call    cs:__imp_CloseServiceHandle
0x180013081  mov     rcx, rbp; hSCObject
0x180013084  call    cs:__imp_CloseServiceHandle
0x18001308a  mov     eax, ebx
0x18001308c  mov     rcx, [rsp+78h+var_38]
0x180013091  xor     rcx, rsp; StackCookie
0x180013094  call    __security_check_cookie
0x180013099  add     rsp, 58h
0x18001309d  pop     rdi
0x18001309e  pop     rsi
0x18001309f  pop     rbp
0x1800130a0  pop     rbx
0x1800130a1  retn
```
