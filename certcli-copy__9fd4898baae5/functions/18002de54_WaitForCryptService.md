# WaitForCryptService

- ea: `0x18002de54`
- end: `0x18002e149`
- name: `WaitForCryptService`
- size: `757`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002d564`

## callees

- `0x18002dacc`
- `0x18002dc70`
- `0x18002dd1c`
- `0x18002de54`
- `0x18002e1e0`
- `0x180039740`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002df56`
- `msvcrt!_wcsicmp` at `0x18002df99`
- `msvcrt!_wcsicmp` at `0x18002df56`
- `msvcrt!_wcsicmp` at `0x18002df99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e055`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e119`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e055`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e119`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002deca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002deef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e023`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002deca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002deef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e023`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002e076`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002e076`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e099`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e108`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e111`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e099`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e108`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e111`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002de94`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002de94`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002df37`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002df37`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002e048`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002e048`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18002dfe1`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18002dfe1`

## pseudocode

```c
__int64 WaitForCryptService()
{
  SC_HANDLE v0; // rax
  unsigned int v1; // edx
  unsigned __int16 *v2; // rcx
  unsigned int v3; // r9d
  SC_HANDLE v4; // rbp
  int v6; // esi
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  SC_HANDLE v9; // rdi
  unsigned int v10; // r9d
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r9d
  DWORD v14; // ebx
  int v15; // ebx
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  unsigned int v18; // r9d
  int CryptSvcForceStartPolicy; // eax
  unsigned int v20; // r8d
  unsigned int v21; // r12d
  int v22; // eax
  int v23; // esi
  DWORD v24; // r8d
  SC_HANDLE v25; // rax
  SC_HANDLE v26; // r15
  DWORD LastError; // r14d
  BOOL started; // eax
  DWORD v29; // ebx
  int v30; // [rsp+20h] [rbp-498h]
  int v31; // [rsp+28h] [rbp-490h]
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-488h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-480h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+60h] [rbp-458h] BYREF

  if ( dword_18006B180 )
    return (unsigned int)dword_18006B184;
  v0 = OpenSCManagerW(0, 0, 1u);
  v4 = v0;
  if ( !v0 )
  {
    ErrLog_LogError(v2, v1, 0x14Du, v3, v30, v31);
    return 0;
  }
  v6 = 1;
  v9 = OpenServiceW(v0, L"CryptSvc", 5u);
  if ( v9 || (ErrLog_LogError(v8, v7, 0x159u, v10, v30, v31), v6 = 0, (v9 = OpenServiceW(v4, L"CryptSvc", 4u)) != 0) )
  {
    v15 = 0;
    if ( !v6 )
      goto LABEL_18;
    pcbBytesNeeded = 1024;
    if ( QueryServiceConfigW(v9, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
    {
      if ( ServiceConfig.dwStartType != 4 )
        goto LABEL_18;
      if ( !_wcsicmp(L"CryptSvc", L"cryptsvc") )
      {
        CryptSvcForceStartPolicy = GetCryptSvcForceStartPolicy();
        if ( CryptSvcForceStartPolicy )
        {
          if ( !(unsigned int)ForceCryptServiceToStart(L"cryptsvc", (unsigned int)(CryptSvcForceStartPolicy != 2) + 2) )
          {
            v20 = 385;
            goto LABEL_41;
          }
          goto LABEL_17;
        }
      }
      if ( _wcsicmp(L"CryptSvc", L"ProtectedStorage") )
      {
        SetLastError(0x422u);
        v20 = 408;
      }
      else
      {
        if ( (unsigned int)ForceCryptServiceToStart(L"ProtectedStorage", 3u) )
        {
LABEL_17:
          v15 = 1;
LABEL_18:
          v21 = 1000 * GetServiceWaitTimeout();
          while ( 1 )
          {
            v22 = WaitServiceState(v9, 73, v21);
            v23 = v22;
            if ( !v22 )
              break;
            if ( v22 == 4 )
            {
              dword_18006B184 = 1;
              dword_18006B180 = 1;
              goto LABEL_42;
            }
            if ( v15 )
            {
              SetLastError(0x5B4u);
              v20 = 448;
              goto LABEL_41;
            }
            v24 = 64;
            *(_OWORD *)&ServiceStatus.dwServiceType = 0;
            if ( v22 != 7 )
              v24 = 16;
            *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
            v25 = OpenServiceW(v4, L"CryptSvc", v24);
            v26 = v25;
            if ( !v25 )
            {
              v20 = 472;
              goto LABEL_41;
            }
            LastError = 0;
            if ( v23 == 7 )
              started = ControlService(v25, 3u, &ServiceStatus);
            else
              started = StartServiceW(v25, 0, 0);
            if ( !started )
              LastError = GetLastError();
            v29 = 0;
            if ( LastError != 1056 )
              v29 = LastError;
            CloseServiceHandle(v26);
            if ( v29 )
            {
              SetLastError(v29);
              v20 = 492;
              goto LABEL_41;
            }
            v15 = 1;
          }
          v20 = 435;
          goto LABEL_41;
        }
        v20 = 398;
      }
    }
    else
    {
      v20 = 415;
    }
LABEL_41:
    ErrLog_LogError(v17, v16, v20, v18, v30, v31);
LABEL_42:
    v14 = GetLastError();
    CloseServiceHandle(v9);
    goto LABEL_44;
  }
  ErrLog_LogError(v12, v11, 0x160u, v13, v30, v31);
  v14 = GetLastError();
LABEL_44:
  CloseServiceHandle(v4);
  SetLastError(v14);
  return (unsigned int)dword_18006B184;
}

```

## disassembly

```asm
0x18002de54  push    rbx
0x18002de56  push    rbp
0x18002de57  push    rsi
0x18002de58  push    rdi
0x18002de59  push    r12
0x18002de5b  push    r13
0x18002de5d  push    r14
0x18002de5f  push    r15
0x18002de61  sub     rsp, 478h
0x18002de68  mov     rax, cs:__security_cookie
0x18002de6f  xor     rax, rsp
0x18002de72  mov     [rsp+4B8h+var_58], rax
0x18002de7a  cmp     cs:dword_18006B180, 0
0x18002de81  jnz     loc_18002E11F
0x18002de87  mov     r13d, 1
0x18002de8d  xor     edx, edx; lpDatabaseName
0x18002de8f  mov     r8d, r13d; dwDesiredAccess
0x18002de92  xor     ecx, ecx; lpMachineName
0x18002de94  call    cs:__imp_OpenSCManagerW
0x18002de9a  mov     rbp, rax
0x18002de9d  test    rax, rax
0x18002dea0  jnz     short loc_18002DEB4
0x18002dea2  mov     r8d, 14Dh; unsigned int
0x18002dea8  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002dead  xor     eax, eax
0x18002deaf  jmp     loc_18002E125
0x18002deb4  lea     r14, aCryptsvc_0; "CryptSvc"
0x18002debb  mov     r8d, 5; dwDesiredAccess
0x18002dec1  mov     rdx, r14; lpServiceName
0x18002dec4  mov     rcx, rbp; hSCManager
0x18002dec7  mov     esi, r13d
0x18002deca  call    cs:__imp_OpenServiceW
0x18002ded0  mov     rdi, rax
0x18002ded3  test    rax, rax
0x18002ded6  jnz     short loc_18002DF15
0x18002ded8  mov     r8d, 159h; unsigned int
0x18002dede  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002dee3  lea     r8d, [rdi+4]; dwDesiredAccess
0x18002dee7  mov     rdx, r14; lpServiceName
0x18002deea  mov     rcx, rbp; hSCManager
0x18002deed  xor     esi, esi
0x18002deef  call    cs:__imp_OpenServiceW
0x18002def5  mov     rdi, rax
0x18002def8  test    rax, rax
0x18002defb  jnz     short loc_18002DF15
0x18002defd  mov     r8d, 160h; unsigned int
0x18002df03  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002df08  call    cs:__imp_GetLastError
0x18002df0e  mov     ebx, eax
0x18002df10  jmp     loc_18002E10E
0x18002df15  xor     ebx, ebx
0x18002df17  test    esi, esi
0x18002df19  jz      loc_18002DFC8
0x18002df1f  mov     r8d, 400h; cbBufSize
0x18002df25  lea     r9, [rsp+4B8h+pcbBytesNeeded]; pcbBytesNeeded
0x18002df2a  lea     rdx, [rsp+4B8h+ServiceConfig]; lpServiceConfig
0x18002df2f  mov     [rsp+4B8h+pcbBytesNeeded], r8d
0x18002df34  mov     rcx, rdi; hService
0x18002df37  call    cs:__imp_QueryServiceConfigW
0x18002df3d  test    eax, eax
0x18002df3f  jz      loc_18002E066
0x18002df45  cmp     [rsp+4B8h+ServiceConfig.dwStartType], 4
0x18002df4a  jnz     short loc_18002DFC8
0x18002df4c  lea     rdx, aCryptsvc; "cryptsvc"
0x18002df53  mov     rcx, r14; String1
0x18002df56  call    cs:__imp__wcsicmp
0x18002df5c  test    eax, eax
0x18002df5e  jnz     short loc_18002DF8F
0x18002df60  call    GetCryptSvcForceStartPolicy
0x18002df65  test    eax, eax
0x18002df67  jz      short loc_18002DF8F
0x18002df69  xor     edx, edx
0x18002df6b  lea     rcx, aCryptsvc; "cryptsvc"
0x18002df72  cmp     eax, 2
0x18002df75  setnz   dl
0x18002df78  add     edx, 2; dwStartType
0x18002df7b  call    ForceCryptServiceToStart
0x18002df80  test    eax, eax
0x18002df82  jnz     short loc_18002DFC5
0x18002df84  mov     r8d, 181h
0x18002df8a  jmp     loc_18002E0F3
0x18002df8f  lea     rdx, aProtectedstora; "ProtectedStorage"
0x18002df96  mov     rcx, r14; String1
0x18002df99  call    cs:__imp__wcsicmp
0x18002df9f  test    eax, eax
0x18002dfa1  jnz     loc_18002E050
0x18002dfa7  lea     edx, [rax+3]; dwStartType
0x18002dfaa  lea     rcx, aProtectedstora; "ProtectedStorage"
0x18002dfb1  call    ForceCryptServiceToStart
0x18002dfb6  test    eax, eax
0x18002dfb8  jnz     short loc_18002DFC5
0x18002dfba  mov     r8d, 18Eh
0x18002dfc0  jmp     loc_18002E0F3
0x18002dfc5  mov     ebx, r13d
0x18002dfc8  call    GetServiceWaitTimeout
0x18002dfcd  imul    r12d, eax, 3E8h
0x18002dfd4  xor     r9d, r9d
0x18002dfd7  mov     r8d, r12d
0x18002dfda  mov     rcx, rdi
0x18002dfdd  lea     edx, [r9+49h]
0x18002dfe1  call    cs:__imp_WaitServiceState
0x18002dfe7  mov     esi, eax
0x18002dfe9  test    eax, eax
0x18002dfeb  jz      loc_18002E0ED
0x18002dff1  cmp     eax, 4
0x18002dff4  jz      loc_18002E0DD
0x18002dffa  test    ebx, ebx
0x18002dffc  jnz     loc_18002E0CA
0x18002e002  xorps   xmm0, xmm0
0x18002e005  lea     eax, [rbx+10h]
0x18002e008  lea     r8d, [rbx+40h]
0x18002e00c  cmp     esi, 7
0x18002e00f  movups  xmmword ptr [rsp+4B8h+ServiceStatus.dwServiceType], xmm0
0x18002e014  cmovnz  r8d, eax; dwDesiredAccess
0x18002e018  mov     rdx, r14; lpServiceName
0x18002e01b  mov     rcx, rbp; hSCManager
0x18002e01e  movups  xmmword ptr [rsp+4B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002e023  call    cs:__imp_OpenServiceW
0x18002e029  mov     r15, rax
0x18002e02c  test    rax, rax
0x18002e02f  jz      loc_18002E0C2
0x18002e035  xor     r14d, r14d
0x18002e038  mov     rcx, rax; hService
0x18002e03b  cmp     esi, 7
0x18002e03e  jnz     short loc_18002E071
0x18002e040  lea     r8, [rsp+4B8h+ServiceStatus]; lpServiceStatus
0x18002e045  lea     edx, [rbx+3]; dwControl
0x18002e048  call    cs:__imp_ControlService
0x18002e04e  jmp     short loc_18002E07C
0x18002e050  mov     ecx, 422h; dwErrCode
0x18002e055  call    cs:__imp_SetLastError
0x18002e05b  mov     r8d, 198h
0x18002e061  jmp     loc_18002E0F3
0x18002e066  mov     r8d, 19Fh
0x18002e06c  jmp     loc_18002E0F3
0x18002e071  xor     r8d, r8d; lpServiceArgVectors
0x18002e074  xor     edx, edx; dwNumServiceArgs
0x18002e076  call    cs:__imp_StartServiceW
0x18002e07c  test    eax, eax
0x18002e07e  jnz     short loc_18002E089
0x18002e080  call    cs:__imp_GetLastError
0x18002e086  mov     r14d, eax
0x18002e089  xor     ebx, ebx
0x18002e08b  mov     rcx, r15; hSCObject
0x18002e08e  cmp     r14d, 420h
0x18002e095  cmovnz  ebx, r14d
0x18002e099  call    cs:__imp_CloseServiceHandle
0x18002e09f  test    ebx, ebx
0x18002e0a1  jnz     short loc_18002E0B2
0x18002e0a3  mov     ebx, r13d
0x18002e0a6  lea     r14, aCryptsvc_0; "CryptSvc"
0x18002e0ad  jmp     loc_18002DFD4
0x18002e0b2  mov     ecx, ebx; dwErrCode
0x18002e0b4  call    cs:__imp_SetLastError
0x18002e0ba  mov     r8d, 1ECh
0x18002e0c0  jmp     short loc_18002E0F3
0x18002e0c2  mov     r8d, 1D8h
0x18002e0c8  jmp     short loc_18002E0F3
0x18002e0ca  mov     ecx, 5B4h; dwErrCode
0x18002e0cf  call    cs:__imp_SetLastError
0x18002e0d5  mov     r8d, 1C0h
0x18002e0db  jmp     short loc_18002E0F3
0x18002e0dd  mov     cs:dword_18006B184, r13d
0x18002e0e4  mov     cs:dword_18006B180, r13d
0x18002e0eb  jmp     short loc_18002E0F8
0x18002e0ed  mov     r8d, 1B3h; unsigned int
0x18002e0f3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18002e0f8  call    cs:__imp_GetLastError
0x18002e0fe  mov     ebx, eax
0x18002e100  test    rdi, rdi
0x18002e103  jz      short loc_18002E10E
0x18002e105  mov     rcx, rdi; hSCObject
0x18002e108  call    cs:__imp_CloseServiceHandle
0x18002e10e  mov     rcx, rbp; hSCObject
0x18002e111  call    cs:__imp_CloseServiceHandle
0x18002e117  mov     ecx, ebx; dwErrCode
0x18002e119  call    cs:__imp_SetLastError
0x18002e11f  mov     eax, cs:dword_18006B184
0x18002e125  mov     rcx, [rsp+4B8h+var_58]
0x18002e12d  xor     rcx, rsp; StackCookie
0x18002e130  call    __security_check_cookie
0x18002e135  add     rsp, 478h
0x18002e13c  pop     r15
0x18002e13e  pop     r14
0x18002e140  pop     r13
0x18002e142  pop     r12
0x18002e144  pop     rdi
0x18002e145  pop     rsi
0x18002e146  pop     rbp
0x18002e147  pop     rbx
0x18002e148  retn
```
