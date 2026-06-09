# BdeSvcApiStartService(void)

- ea: `0x1800ffcd4`
- end: `0x1800ffe8b`
- name: `?BdeSvcApiStartService@@YAJXZ`
- size: `439`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800ffe94`

## callees

- `0x1800ffcd4`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffd1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffd1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffde9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ffe14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ffe14`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ffd08`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ffd08`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800ffdd9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800ffdd9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ffd50`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ffd50`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ffe57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ffe66`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ffe57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ffe66`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800ffd90`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800ffe28`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800ffd90`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800ffe28`

## string_xrefs

- `0x1800ffcef`: `ServicesActive`

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
0x1800ffcd4  push    rbx
0x1800ffcd6  push    rbp
0x1800ffcd7  push    rsi
0x1800ffcd8  push    rdi
0x1800ffcd9  sub     rsp, 58h
0x1800ffcdd  mov     rax, cs:__security_cookie
0x1800ffce4  xor     rax, rsp
0x1800ffce7  mov     [rsp+78h+var_38], rax
0x1800ffcec  xorps   xmm0, xmm0
0x1800ffcef  lea     rdx, DatabaseName; "ServicesActive"
0x1800ffcf6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800ffcfb  mov     r8d, 1; dwDesiredAccess
0x1800ffd01  xor     ecx, ecx; lpMachineName
0x1800ffd03  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800ffd08  call    cs:__imp_OpenSCManagerW
0x1800ffd0f  nop     dword ptr [rax+rax+00h]
0x1800ffd14  mov     rbp, rax
0x1800ffd17  test    rax, rax
0x1800ffd1a  jnz     short loc_1800FFD40
0x1800ffd1c  call    cs:__imp_GetLastError
0x1800ffd23  nop     dword ptr [rax+rax+00h]
0x1800ffd28  mov     ebx, eax
0x1800ffd2a  test    eax, eax
0x1800ffd2c  jle     loc_1800FFE72
0x1800ffd32  movzx   ebx, ax
0x1800ffd35  or      ebx, 80070000h
0x1800ffd3b  jmp     loc_1800FFE72
0x1800ffd40  mov     r8d, 14h; dwDesiredAccess
0x1800ffd46  lea     rdx, ServiceName; "BDESVC"
0x1800ffd4d  mov     rcx, rbp; hSCManager
0x1800ffd50  call    cs:__imp_OpenServiceW
0x1800ffd57  nop     dword ptr [rax+rax+00h]
0x1800ffd5c  mov     rdi, rax
0x1800ffd5f  test    rax, rax
0x1800ffd62  jnz     short loc_1800FFD88
0x1800ffd64  call    cs:__imp_GetLastError
0x1800ffd6b  nop     dword ptr [rax+rax+00h]
0x1800ffd70  mov     ebx, eax
0x1800ffd72  test    eax, eax
0x1800ffd74  jle     loc_1800FFE63
0x1800ffd7a  movzx   ebx, ax
0x1800ffd7d  or      ebx, 80070000h
0x1800ffd83  jmp     loc_1800FFE63
0x1800ffd88  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800ffd8d  mov     rcx, rdi; hService
0x1800ffd90  call    cs:__imp_QueryServiceStatus
0x1800ffd97  nop     dword ptr [rax+rax+00h]
0x1800ffd9c  test    eax, eax
0x1800ffd9e  jnz     short loc_1800FFDC4
0x1800ffda0  call    cs:__imp_GetLastError
0x1800ffda7  nop     dword ptr [rax+rax+00h]
0x1800ffdac  mov     ebx, eax
0x1800ffdae  test    eax, eax
0x1800ffdb0  jle     loc_1800FFE54
0x1800ffdb6  movzx   ebx, ax
0x1800ffdb9  or      ebx, 80070000h
0x1800ffdbf  jmp     loc_1800FFE54
0x1800ffdc4  xor     ebx, ebx
0x1800ffdc6  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800ffdcb  jz      loc_1800FFE54
0x1800ffdd1  xor     r8d, r8d; lpServiceArgVectors
0x1800ffdd4  xor     edx, edx; dwNumServiceArgs
0x1800ffdd6  mov     rcx, rdi; hService
0x1800ffdd9  call    cs:__imp_StartServiceW
0x1800ffde0  nop     dword ptr [rax+rax+00h]
0x1800ffde5  test    eax, eax
0x1800ffde7  jnz     short loc_1800FFE04
0x1800ffde9  call    cs:__imp_GetLastError
0x1800ffdf0  nop     dword ptr [rax+rax+00h]
0x1800ffdf5  cmp     eax, 420h
0x1800ffdfa  jz      short loc_1800FFE54
0x1800ffdfc  test    eax, eax
0x1800ffdfe  jg      short loc_1800FFDB6
0x1800ffe00  mov     ebx, eax
0x1800ffe02  jmp     short loc_1800FFE54
0x1800ffe04  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800ffe08  xor     esi, esi
0x1800ffe0a  cmp     esi, 19h
0x1800ffe0d  jge     short loc_1800FFE49
0x1800ffe0f  mov     ecx, 0C8h; dwMilliseconds
0x1800ffe14  call    cs:__imp_Sleep
0x1800ffe1b  nop     dword ptr [rax+rax+00h]
0x1800ffe20  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800ffe25  mov     rcx, rdi; hService
0x1800ffe28  call    cs:__imp_QueryServiceStatus
0x1800ffe2f  nop     dword ptr [rax+rax+00h]
0x1800ffe34  test    eax, eax
0x1800ffe36  jz      loc_1800FFDA0
0x1800ffe3c  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800ffe40  cmp     eax, 2
0x1800ffe43  jnz     short loc_1800FFE49
0x1800ffe45  inc     esi
0x1800ffe47  jmp     short loc_1800FFE0A
0x1800ffe49  cmp     eax, 4
0x1800ffe4c  mov     ecx, 8007041Dh
0x1800ffe51  cmovnz  ebx, ecx
0x1800ffe54  mov     rcx, rdi; hSCObject
0x1800ffe57  call    cs:__imp_CloseServiceHandle
0x1800ffe5e  nop     dword ptr [rax+rax+00h]
0x1800ffe63  mov     rcx, rbp; hSCObject
0x1800ffe66  call    cs:__imp_CloseServiceHandle
0x1800ffe6d  nop     dword ptr [rax+rax+00h]
0x1800ffe72  mov     eax, ebx
0x1800ffe74  mov     rcx, [rsp+78h+var_38]
0x1800ffe79  xor     rcx, rsp; StackCookie
0x1800ffe7c  call    __security_check_cookie
0x1800ffe81  add     rsp, 58h
0x1800ffe85  pop     rdi
0x1800ffe86  pop     rsi
0x1800ffe87  pop     rbp
0x1800ffe88  pop     rbx
0x1800ffe89  retn
```
