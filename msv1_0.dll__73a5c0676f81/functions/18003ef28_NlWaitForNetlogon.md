# NlWaitForNetlogon

- ea: `0x18003ef28`
- end: `0x18003f2ce`
- name: `NlWaitForNetlogon`
- size: `934`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001a470`
- `0x180024c00`
- `0x18003dcf0`

## callees

- `0x180020bb0`
- `0x18002ee7c`
- `0x18002fb50`
- `0x180030844`
- `0x18003509c`
- `0x18003c8c8`
- `0x18003ef28`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003efc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f25b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003efc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f25b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f288`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f296`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f288`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f296`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003efa1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003efa1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003f008`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003f008`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003f053`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003f0cb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003f053`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003f0cb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003f145`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003f145`

## string_xrefs

- `0x18003ef72`: `\NETLOGON_SERVICE_STARTED`
- `0x18003f1a3`: `\NETLOGON_SERVICE_STARTED`

## pseudocode

```c
__int64 NlWaitForNetlogon()
{
  __int64 result; // rax
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // r15
  DWORD LastError; // eax
  unsigned int v4; // ebx
  _QUERY_SERVICE_CONFIGW *v5; // rsi
  int v6; // edi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  DWORD v9; // eax
  __int64 v10; // rdx
  _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rax
  _QWORD *v12; // rcx
  struct _QUERY_SERVICE_CONFIGW *v13; // rax
  __int64 dwStartType; // r9
  DWORD dwWin32ExitCode; // eax
  _QWORD *v16; // rcx
  DWORD pcbBytesNeeded[4]; // [rsp+30h] [rbp-59h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+40h] [rbp-49h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-9h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  pcbBytesNeeded[0] = 0;
  result = NlWaitForEvent(L"\\NETLOGON_SERVICE_STARTED", 0);
  if ( (int)result < 0 )
  {
    if ( NlDoingSetup() )
      return 3221225874LL;
    v1 = OpenSCManagerW(0, 0, 1u);
    v2 = v1;
    if ( !v1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, LastError);
      }
      return (unsigned int)-1073741422;
    }
    v5 = 0;
    v6 = 5;
    v7 = OpenServiceW(v1, L"NETLOGON", 5u);
    v8 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_55;
      v9 = GetLastError();
      v10 = 21;
      goto LABEL_52;
    }
    if ( QueryServiceConfigW(v7, &ServiceConfig, 0x40u, pcbBytesNeeded) )
    {
      p_ServiceConfig = &ServiceConfig;
    }
    else
    {
      v9 = GetLastError();
      if ( v9 != 122 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_55;
        v10 = 22;
        goto LABEL_53;
      }
      v13 = (struct _QUERY_SERVICE_CONFIGW *)((__int64 (__fastcall *)(_QWORD))qword_180088390)(pcbBytesNeeded[0]);
      v5 = v13;
      if ( !v13 )
      {
        v4 = -1073741801;
LABEL_56:
        CloseServiceHandle(v2);
        if ( v8 )
          CloseServiceHandle(v8);
        if ( v5 )
          ((void (__fastcall *)(_QUERY_SERVICE_CONFIGW *))qword_180088398)(v5);
        return v4;
      }
      if ( !QueryServiceConfigW(v8, v13, pcbBytesNeeded[0], pcbBytesNeeded) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_55;
        v9 = GetLastError();
        v10 = 23;
LABEL_52:
        v12 = WPP_GLOBAL_Control;
LABEL_53:
        dwStartType = v9;
        goto LABEL_54;
      }
      p_ServiceConfig = v5;
    }
    dwStartType = p_ServiceConfig->dwStartType;
    if ( (_DWORD)dwStartType == 2 )
    {
      while ( QueryServiceStatus(v8, &ServiceStatus) )
      {
        dwStartType = ServiceStatus.dwCurrentState;
        switch ( ServiceStatus.dwCurrentState )
        {
          case 1u:
            dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
            if ( ServiceStatus.dwWin32ExitCode != 1077 )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
                  ServiceStatus.dwWin32ExitCode,
                  ServiceStatus.dwWin32ExitCode);
                dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
                v16 = WPP_GLOBAL_Control;
              }
              if ( dwWin32ExitCode == 1066 && v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 )
                WPP_SF_dd(
                  v16[2],
                  27,
                  WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
                  ServiceStatus.dwServiceSpecificExitCode,
                  ServiceStatus.dwServiceSpecificExitCode);
              goto LABEL_55;
            }
            break;
          case 2u:
            break;
          case 4u:
            v4 = 0;
            goto LABEL_56;
          default:
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v10 = 28;
              goto LABEL_54;
            }
            goto LABEL_55;
        }
        v4 = NlWaitForEvent(L"\\NETLOGON_SERVICE_STARTED", 0xAu);
        if ( v4 != -1073741422 )
          goto LABEL_56;
        if ( !--v6 )
          goto LABEL_55;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v9 = GetLastError();
        v10 = 25;
        goto LABEL_52;
      }
      goto LABEL_55;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_55:
      v4 = -1073741422;
      goto LABEL_56;
    }
    v10 = 24;
LABEL_54:
    WPP_SF_d(v12[2], v10, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, dwStartType);
    goto LABEL_55;
  }
  return result;
}

```

## disassembly

```asm
0x18003ef28  push    rbp
0x18003ef2a  push    rbx
0x18003ef2b  push    rsi
0x18003ef2c  push    rdi
0x18003ef2d  push    r14
0x18003ef2f  push    r15
0x18003ef31  lea     rbp, [rsp-2Fh]
0x18003ef36  sub     rsp, 0B8h
0x18003ef3d  mov     rax, cs:__security_cookie
0x18003ef44  xor     rax, rsp
0x18003ef47  mov     [rbp+57h+var_40], rax
0x18003ef4b  xorps   xmm0, xmm0
0x18003ef4e  lea     rcx, [rbp+57h+ServiceConfig]; void *
0x18003ef52  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18003ef56  mov     ebx, 40h ; '@'
0x18003ef5b  xor     edx, edx; Val
0x18003ef5d  mov     r8d, ebx; Size
0x18003ef60  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003ef64  call    memset_0
0x18003ef69  xor     edx, edx; unsigned int
0x18003ef6b  mov     [rbp+57h+pcbBytesNeeded], 0
0x18003ef72  lea     rcx, aNetlogonServic; "\\NETLOGON_SERVICE_STARTED"
0x18003ef79  call    ?NlWaitForEvent@@YAJPEAGK@Z; NlWaitForEvent(ushort *,ulong)
0x18003ef7e  test    eax, eax
0x18003ef80  jns     loc_18003F2B2
0x18003ef86  call    ?NlDoingSetup@@YAEXZ; NlDoingSetup(void)
0x18003ef8b  test    al, al
0x18003ef8d  jz      short loc_18003EF99
0x18003ef8f  mov     eax, 0C0000192h
0x18003ef94  jmp     loc_18003F2B2
0x18003ef99  xor     edx, edx; lpDatabaseName
0x18003ef9b  xor     ecx, ecx; lpMachineName
0x18003ef9d  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003efa1  call    cs:__imp_OpenSCManagerW
0x18003efa7  mov     r15, rax
0x18003efaa  test    rax, rax
0x18003efad  jnz     short loc_18003EFF6
0x18003efaf  mov     rax, cs:WPP_GLOBAL_Control
0x18003efb6  lea     rbx, WPP_GLOBAL_Control
0x18003efbd  cmp     rax, rbx
0x18003efc0  jz      short loc_18003EFEC
0x18003efc2  test    byte ptr [rax+1Ch], 8
0x18003efc6  jz      short loc_18003EFEC
0x18003efc8  call    cs:__imp_GetLastError
0x18003efce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efd5  lea     edx, [r15+14h]
0x18003efd9  mov     r9d, eax
0x18003efdc  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003efe3  mov     rcx, [rcx+10h]
0x18003efe7  call    WPP_SF_d
0x18003efec  mov     ebx, 0C0000192h
0x18003eff1  jmp     loc_18003F2B0
0x18003eff6  xor     esi, esi
0x18003eff8  lea     rdx, ServiceName; "NETLOGON"
0x18003efff  mov     rcx, r15; hSCManager
0x18003f002  lea     edi, [rsi+5]
0x18003f005  mov     r8d, edi; dwDesiredAccess
0x18003f008  call    cs:__imp_OpenServiceW
0x18003f00e  mov     r14, rax
0x18003f011  test    rax, rax
0x18003f014  jnz     short loc_18003F045
0x18003f016  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f01d  lea     rbx, WPP_GLOBAL_Control
0x18003f024  cmp     rcx, rbx
0x18003f027  jz      loc_18003F280
0x18003f02d  test    byte ptr [rcx+1Ch], 8
0x18003f031  jz      loc_18003F280
0x18003f037  call    cs:__imp_GetLastError
0x18003f03d  lea     edx, [rsi+15h]
0x18003f040  jmp     loc_18003F266
0x18003f045  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18003f049  mov     r8d, ebx; cbBufSize
0x18003f04c  lea     rdx, [rbp+57h+ServiceConfig]; lpServiceConfig
0x18003f050  mov     rcx, r14; hService
0x18003f053  call    cs:__imp_QueryServiceConfigW
0x18003f059  test    eax, eax
0x18003f05b  jz      short loc_18003F066
0x18003f05d  lea     rax, [rbp+57h+ServiceConfig]
0x18003f061  jmp     loc_18003F109
0x18003f066  call    cs:__imp_GetLastError
0x18003f06c  cmp     eax, 7Ah ; 'z'
0x18003f06f  jz      short loc_18003F09C
0x18003f071  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f078  lea     rbx, WPP_GLOBAL_Control
0x18003f07f  cmp     rcx, rbx
0x18003f082  jz      loc_18003F280
0x18003f088  test    byte ptr [rcx+1Ch], 8
0x18003f08c  jz      loc_18003F280
0x18003f092  mov     edx, 16h
0x18003f097  jmp     loc_18003F26D
0x18003f09c  mov     ecx, [rbp+57h+pcbBytesNeeded]
0x18003f09f  mov     rax, cs:qword_180088390
0x18003f0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0ab  mov     rsi, rax
0x18003f0ae  test    rax, rax
0x18003f0b1  jnz     short loc_18003F0BD
0x18003f0b3  mov     ebx, 0C0000017h
0x18003f0b8  jmp     loc_18003F285
0x18003f0bd  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x18003f0c1  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18003f0c5  mov     rdx, rsi; lpServiceConfig
0x18003f0c8  mov     rcx, r14; hService
0x18003f0cb  call    cs:__imp_QueryServiceConfigW
0x18003f0d1  test    eax, eax
0x18003f0d3  jnz     short loc_18003F106
0x18003f0d5  mov     rax, cs:WPP_GLOBAL_Control
0x18003f0dc  lea     rbx, WPP_GLOBAL_Control
0x18003f0e3  cmp     rax, rbx
0x18003f0e6  jz      loc_18003F280
0x18003f0ec  test    byte ptr [rax+1Ch], 8
0x18003f0f0  jz      loc_18003F280
0x18003f0f6  call    cs:__imp_GetLastError
0x18003f0fc  mov     edx, 17h
0x18003f101  jmp     loc_18003F266
0x18003f106  mov     rax, rsi
0x18003f109  mov     r9d, [rax+4]
0x18003f10d  cmp     r9d, 2
0x18003f111  jz      short loc_18003F13E
0x18003f113  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f11a  lea     rbx, WPP_GLOBAL_Control
0x18003f121  cmp     rcx, rbx
0x18003f124  jz      loc_18003F280
0x18003f12a  test    byte ptr [rcx+1Ch], 8
0x18003f12e  jz      loc_18003F280
0x18003f134  mov     edx, 18h
0x18003f139  jmp     loc_18003F270
0x18003f13e  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003f142  mov     rcx, r14; hService
0x18003f145  call    cs:__imp_QueryServiceStatus
0x18003f14b  test    eax, eax
0x18003f14d  jz      loc_18003F242
0x18003f153  mov     r9d, [rbp+57h+ServiceStatus.dwCurrentState]
0x18003f157  mov     eax, r9d
0x18003f15a  sub     eax, 1
0x18003f15d  jz      short loc_18003F194
0x18003f15f  sub     eax, 1
0x18003f162  jz      short loc_18003F19E
0x18003f164  cmp     eax, 2
0x18003f167  jz      short loc_18003F1CA
0x18003f169  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f170  lea     rbx, WPP_GLOBAL_Control
0x18003f177  cmp     rcx, rbx
0x18003f17a  jz      loc_18003F280
0x18003f180  test    byte ptr [rcx+1Ch], 8
0x18003f184  jz      loc_18003F280
0x18003f18a  mov     edx, 1Ch
0x18003f18f  jmp     loc_18003F270
0x18003f194  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18003f197  cmp     eax, 435h
0x18003f19c  jnz     short loc_18003F1D1
0x18003f19e  mov     edx, 0Ah; unsigned int
0x18003f1a3  lea     rcx, aNetlogonServic; "\\NETLOGON_SERVICE_STARTED"
0x18003f1aa  call    ?NlWaitForEvent@@YAJPEAGK@Z; NlWaitForEvent(ushort *,ulong)
0x18003f1af  mov     ebx, eax
0x18003f1b1  cmp     eax, 0C0000192h
0x18003f1b6  jnz     loc_18003F285
0x18003f1bc  add     edi, 0FFFFFFFFh
0x18003f1bf  jnz     loc_18003F13E
0x18003f1c5  jmp     loc_18003F280
0x18003f1ca  xor     ebx, ebx
0x18003f1cc  jmp     loc_18003F285
0x18003f1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1d8  lea     rbx, WPP_GLOBAL_Control
0x18003f1df  cmp     rcx, rbx
0x18003f1e2  jz      short loc_18003F210
0x18003f1e4  test    byte ptr [rcx+1Ch], 8
0x18003f1e8  jz      short loc_18003F210
0x18003f1ea  mov     rcx, [rcx+10h]
0x18003f1ee  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003f1f5  mov     edx, 1Ah
0x18003f1fa  mov     [rsp+0E0h+var_C0], eax
0x18003f1fe  mov     r9d, eax
0x18003f201  call    WPP_SF_dd
0x18003f206  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18003f209  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f210  cmp     eax, 42Ah
0x18003f215  jnz     short loc_18003F280
0x18003f217  cmp     rcx, rbx
0x18003f21a  jz      short loc_18003F280
0x18003f21c  test    byte ptr [rcx+1Ch], 8
0x18003f220  jz      short loc_18003F280
0x18003f222  mov     r9d, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x18003f226  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003f22d  mov     rcx, [rcx+10h]
0x18003f231  mov     edx, 1Bh
0x18003f236  mov     [rsp+0E0h+var_C0], r9d
0x18003f23b  call    WPP_SF_dd
0x18003f240  jmp     short loc_18003F280
0x18003f242  mov     rax, cs:WPP_GLOBAL_Control
0x18003f249  lea     rbx, WPP_GLOBAL_Control
0x18003f250  cmp     rax, rbx
0x18003f253  jz      short loc_18003F280
0x18003f255  test    byte ptr [rax+1Ch], 8
0x18003f259  jz      short loc_18003F280
0x18003f25b  call    cs:__imp_GetLastError
0x18003f261  mov     edx, 19h
0x18003f266  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f26d  mov     r9d, eax
0x18003f270  mov     rcx, [rcx+10h]
0x18003f274  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003f27b  call    WPP_SF_d
0x18003f280  mov     ebx, 0C0000192h
0x18003f285  mov     rcx, r15; hSCObject
0x18003f288  call    cs:__imp_CloseServiceHandle
0x18003f28e  test    r14, r14
0x18003f291  jz      short loc_18003F29C
0x18003f293  mov     rcx, r14; hSCObject
0x18003f296  call    cs:__imp_CloseServiceHandle
0x18003f29c  test    rsi, rsi
0x18003f29f  jz      short loc_18003F2B0
0x18003f2a1  mov     rax, cs:qword_180088398
0x18003f2a8  mov     rcx, rsi
0x18003f2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2b0  mov     eax, ebx
0x18003f2b2  mov     rcx, [rbp+57h+var_40]
0x18003f2b6  xor     rcx, rsp; StackCookie
0x18003f2b9  call    __security_check_cookie
0x18003f2be  add     rsp, 0B8h
0x18003f2c5  pop     r15
0x18003f2c7  pop     r14
0x18003f2c9  pop     rdi
0x18003f2ca  pop     rsi
0x18003f2cb  pop     rbx
0x18003f2cc  pop     rbp
0x18003f2cd  retn
```
