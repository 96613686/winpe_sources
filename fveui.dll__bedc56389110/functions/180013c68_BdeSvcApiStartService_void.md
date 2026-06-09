# BdeSvcApiStartService(void)

- ea: `0x180013c68`
- end: `0x180013dc7`
- name: `?BdeSvcApiStartService@@YAJXZ`
- size: `351`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007360`

## callees

- `0x180001bb0`
- `0x180013c68`

## import_xrefs

- `KERNEL32!Sleep` at `0x180013d6d`
- `KERNEL32!Sleep` at `0x180013d6d`
- `KERNEL32!GetLastError` at `0x180013caa`
- `KERNEL32!GetLastError` at `0x180013ce6`
- `KERNEL32!GetLastError` at `0x180013d16`
- `KERNEL32!GetLastError` at `0x180013d48`
- `KERNEL32!GetLastError` at `0x180013caa`
- `KERNEL32!GetLastError` at `0x180013ce6`
- `KERNEL32!GetLastError` at `0x180013d16`
- `KERNEL32!GetLastError` at `0x180013d48`
- `ADVAPI32!QueryServiceStatus` at `0x180013d0c`
- `ADVAPI32!QueryServiceStatus` at `0x180013d7b`
- `ADVAPI32!QueryServiceStatus` at `0x180013d0c`
- `ADVAPI32!QueryServiceStatus` at `0x180013d7b`
- `ADVAPI32!CloseServiceHandle` at `0x180013da0`
- `ADVAPI32!CloseServiceHandle` at `0x180013da9`
- `ADVAPI32!CloseServiceHandle` at `0x180013da0`
- `ADVAPI32!CloseServiceHandle` at `0x180013da9`
- `ADVAPI32!OpenSCManagerW` at `0x180013c9c`
- `ADVAPI32!OpenSCManagerW` at `0x180013c9c`
- `ADVAPI32!StartServiceW` at `0x180013d3e`
- `ADVAPI32!StartServiceW` at `0x180013d3e`
- `ADVAPI32!OpenServiceW` at `0x180013cd8`
- `ADVAPI32!OpenServiceW` at `0x180013cd8`

## string_xrefs

- `0x180013c83`: `ServicesActive`

## pseudocode

```c
__int64 BdeSvcApiStartService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  signed int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  DWORD dwCurrentState; // eax
  int i; // esi
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
      if ( ServiceStatus.dwCurrentState != 4 )
      {
        if ( StartServiceW(v5, 0, 0) )
        {
          dwCurrentState = ServiceStatus.dwCurrentState;
          for ( i = 0; i < 25; ++i )
          {
            Sleep(0xC8u);
            if ( !QueryServiceStatus(v5, &ServiceStatus) )
              goto LABEL_8;
            dwCurrentState = ServiceStatus.dwCurrentState;
            if ( ServiceStatus.dwCurrentState != 2 )
              break;
          }
          if ( dwCurrentState != 4 )
            v3 = -2147023843;
          goto LABEL_22;
        }
        v7 = GetLastError();
        if ( v7 != 1056 )
        {
          if ( v7 <= 0 )
          {
            v3 = v7;
            goto LABEL_22;
          }
          goto LABEL_9;
        }
      }
    }
    else
    {
LABEL_8:
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
LABEL_9:
        v3 = (unsigned __int16)v7 | 0x80070000;
    }
LABEL_22:
    CloseServiceHandle(v5);
LABEL_23:
    CloseServiceHandle(v1);
    return v3;
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
0x180013c68  push    rbx
0x180013c6a  push    rbp
0x180013c6b  push    rsi
0x180013c6c  push    rdi
0x180013c6d  sub     rsp, 58h
0x180013c71  mov     rax, cs:__security_cookie
0x180013c78  xor     rax, rsp
0x180013c7b  mov     [rsp+78h+var_38], rax
0x180013c80  xorps   xmm0, xmm0
0x180013c83  lea     rdx, DatabaseName; "ServicesActive"
0x180013c8a  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180013c8f  mov     r8d, 1; dwDesiredAccess
0x180013c95  xor     ecx, ecx; lpMachineName
0x180013c97  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180013c9c  call    cs:__imp_OpenSCManagerW
0x180013ca2  mov     rbp, rax
0x180013ca5  test    rax, rax
0x180013ca8  jnz     short loc_180013CC8
0x180013caa  call    cs:__imp_GetLastError
0x180013cb0  mov     ebx, eax
0x180013cb2  test    eax, eax
0x180013cb4  jle     loc_180013DAF
0x180013cba  movzx   ebx, ax
0x180013cbd  or      ebx, 80070000h
0x180013cc3  jmp     loc_180013DAF
0x180013cc8  mov     r8d, 14h; dwDesiredAccess
0x180013cce  lea     rdx, ServiceName; "BDESVC"
0x180013cd5  mov     rcx, rbp; hSCManager
0x180013cd8  call    cs:__imp_OpenServiceW
0x180013cde  mov     rdi, rax
0x180013ce1  test    rax, rax
0x180013ce4  jnz     short loc_180013D04
0x180013ce6  call    cs:__imp_GetLastError
0x180013cec  mov     ebx, eax
0x180013cee  test    eax, eax
0x180013cf0  jle     loc_180013DA6
0x180013cf6  movzx   ebx, ax
0x180013cf9  or      ebx, 80070000h
0x180013cff  jmp     loc_180013DA6
0x180013d04  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180013d09  mov     rcx, rdi; hService
0x180013d0c  call    cs:__imp_QueryServiceStatus
0x180013d12  test    eax, eax
0x180013d14  jnz     short loc_180013D2D
0x180013d16  call    cs:__imp_GetLastError
0x180013d1c  mov     ebx, eax
0x180013d1e  test    eax, eax
0x180013d20  jle     short loc_180013D9D
0x180013d22  movzx   ebx, ax
0x180013d25  or      ebx, 80070000h
0x180013d2b  jmp     short loc_180013D9D
0x180013d2d  xor     ebx, ebx
0x180013d2f  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180013d34  jz      short loc_180013D9D
0x180013d36  xor     r8d, r8d; lpServiceArgVectors
0x180013d39  xor     edx, edx; dwNumServiceArgs
0x180013d3b  mov     rcx, rdi; hService
0x180013d3e  call    cs:__imp_StartServiceW
0x180013d44  test    eax, eax
0x180013d46  jnz     short loc_180013D5D
0x180013d48  call    cs:__imp_GetLastError
0x180013d4e  cmp     eax, 420h
0x180013d53  jz      short loc_180013D9D
0x180013d55  test    eax, eax
0x180013d57  jg      short loc_180013D22
0x180013d59  mov     ebx, eax
0x180013d5b  jmp     short loc_180013D9D
0x180013d5d  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x180013d61  xor     esi, esi
0x180013d63  cmp     esi, 19h
0x180013d66  jge     short loc_180013D92
0x180013d68  mov     ecx, 0C8h; dwMilliseconds
0x180013d6d  call    cs:__imp_Sleep
0x180013d73  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180013d78  mov     rcx, rdi; hService
0x180013d7b  call    cs:__imp_QueryServiceStatus
0x180013d81  test    eax, eax
0x180013d83  jz      short loc_180013D16
0x180013d85  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x180013d89  cmp     eax, 2
0x180013d8c  jnz     short loc_180013D92
0x180013d8e  inc     esi
0x180013d90  jmp     short loc_180013D63
0x180013d92  cmp     eax, 4
0x180013d95  mov     ecx, 8007041Dh
0x180013d9a  cmovnz  ebx, ecx
0x180013d9d  mov     rcx, rdi; hSCObject
0x180013da0  call    cs:__imp_CloseServiceHandle
0x180013da6  mov     rcx, rbp; hSCObject
0x180013da9  call    cs:__imp_CloseServiceHandle
0x180013daf  mov     eax, ebx
0x180013db1  mov     rcx, [rsp+78h+var_38]
0x180013db6  xor     rcx, rsp; StackCookie
0x180013db9  call    __security_check_cookie
0x180013dbe  add     rsp, 58h
0x180013dc2  pop     rdi
0x180013dc3  pop     rsi
0x180013dc4  pop     rbp
0x180013dc5  pop     rbx
0x180013dc6  retn
```
