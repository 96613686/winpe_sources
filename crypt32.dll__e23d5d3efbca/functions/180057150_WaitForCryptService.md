# WaitForCryptService

- ea: `0x180057150`
- end: `0x1800572e4`
- name: `WaitForCryptService`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180056fb0`

## callees

- `0x180057150`
- `0x1800572ec`
- `0x1800bec20`
- `0x1800bf558`
- `0x1801144a8`
- `0x18011464c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118e82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057258`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118e11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057258`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118e11`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180057190`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180057190`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180118e78`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180118e78`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800571b6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180057296`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180118e46`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800571b6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180057296`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180118e46`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180057247`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180057250`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180118e9b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180057247`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180057250`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180118e9b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800571e6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800571e6`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180118e6b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180118e6b`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180057214`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180057214`

## pseudocode

```c
SC_HANDLE WaitForCryptService()
{
  SC_HANDLE result; // rax
  SC_HANDLE v1; // rsi
  int v2; // ebp
  SC_HANDLE v3; // rbx
  int v4; // edi
  unsigned int v5; // r12d
  int v6; // eax
  int v7; // ebp
  DWORD v8; // edi
  int CryptSvcForceStartPolicy; // eax
  const WCHAR *v10; // rcx
  DWORD v11; // edx
  DWORD v12; // ecx
  DWORD v13; // r8d
  SC_HANDLE v14; // rax
  SC_HANDLE v15; // r15
  DWORD LastError; // r14d
  BOOL started; // eax
  DWORD v18; // edi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-488h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-480h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+50h] [rbp-458h] BYREF

  if ( dword_18015D7B0 )
    return (SC_HANDLE)(unsigned int)dword_18015D7C0;
  result = OpenSCManagerW(0, 0, 1u);
  v1 = result;
  if ( result )
  {
    v2 = 1;
    v3 = OpenServiceW(result, L"CryptSvc", 5u);
    if ( v3 || (v2 = 0, (v3 = OpenServiceW(v1, L"CryptSvc", 4u)) != 0) )
    {
      v4 = 0;
      if ( !v2 )
        goto LABEL_7;
      pcbBytesNeeded = 1024;
      if ( QueryServiceConfigW(v3, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
      {
        if ( ServiceConfig.dwStartType != 4 )
          goto LABEL_7;
        if ( wcsicmp(L"CryptSvc", L"cryptsvc") || (CryptSvcForceStartPolicy = GetCryptSvcForceStartPolicy()) == 0 )
        {
          if ( wcsicmp(L"CryptSvc", L"ProtectedStorage") )
          {
            v12 = 1058;
LABEL_27:
            SetLastError(v12);
            goto LABEL_11;
          }
          v11 = 3;
          v10 = L"ProtectedStorage";
        }
        else
        {
          v10 = L"cryptsvc";
          v11 = (CryptSvcForceStartPolicy != 2) + 2;
        }
        if ( (unsigned int)ForceCryptServiceToStart(v10, v11) )
        {
          v4 = 1;
LABEL_7:
          v5 = 1000 * GetServiceWaitTimeout();
          while ( 1 )
          {
            v6 = WaitServiceState(v3, 73, v5);
            v7 = v6;
            if ( !v6 )
              break;
            if ( v6 == 4 )
            {
              dword_18015D7C0 = 1;
              dword_18015D7B0 = 1;
              break;
            }
            if ( v4 )
            {
              v12 = 1460;
              goto LABEL_27;
            }
            v13 = 64;
            *(_OWORD *)&ServiceStatus.dwServiceType = 0;
            if ( v6 != 7 )
              v13 = 16;
            *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
            v14 = OpenServiceW(v1, L"CryptSvc", v13);
            v15 = v14;
            if ( !v14 )
              break;
            LastError = 0;
            if ( v7 == 7 )
              started = ControlService(v14, 3u, &ServiceStatus);
            else
              started = StartServiceW(v14, 0, 0);
            if ( !started )
              LastError = GetLastError();
            v18 = 0;
            if ( LastError != 1056 )
              v18 = LastError;
            CloseServiceHandle(v15);
            if ( v18 )
            {
              v12 = v18;
              goto LABEL_27;
            }
            v4 = 1;
          }
        }
      }
    }
LABEL_11:
    v8 = GetLastError();
    if ( v3 )
      CloseServiceHandle(v3);
    CloseServiceHandle(v1);
    SetLastError(v8);
    return (SC_HANDLE)(unsigned int)dword_18015D7C0;
  }
  return result;
}

```

## disassembly

```asm
0x180057150  push    rbx
0x180057152  push    rbp
0x180057153  push    rsi
0x180057154  push    rdi
0x180057155  push    r12
0x180057157  push    r13
0x180057159  push    r14
0x18005715b  push    r15
0x18005715d  sub     rsp, 468h
0x180057164  mov     rax, cs:__security_cookie
0x18005716b  xor     rax, rsp
0x18005716e  mov     [rsp+4A8h+var_58], rax
0x180057176  cmp     cs:dword_18015D7B0, 0
0x18005717d  jnz     loc_18005725E
0x180057183  mov     r13d, 1
0x180057189  xor     edx, edx; lpDatabaseName
0x18005718b  mov     r8d, r13d; dwDesiredAccess
0x18005718e  xor     ecx, ecx; lpMachineName
0x180057190  call    cs:__imp_OpenSCManagerW
0x180057196  mov     rsi, rax
0x180057199  test    rax, rax
0x18005719c  jz      loc_180057288
0x1800571a2  lea     r14, aCryptsvc_0; "CryptSvc"
0x1800571a9  mov     rcx, rax; hSCManager
0x1800571ac  mov     rdx, r14; lpServiceName
0x1800571af  lea     r8d, [r13+4]; dwDesiredAccess
0x1800571b3  mov     ebp, r13d
0x1800571b6  call    cs:__imp_OpenServiceW
0x1800571bc  mov     rbx, rax
0x1800571bf  test    rax, rax
0x1800571c2  jz      loc_18005728A
0x1800571c8  xor     edi, edi
0x1800571ca  test    ebp, ebp
0x1800571cc  jz      short loc_1800571FB
0x1800571ce  mov     r8d, 400h; cbBufSize
0x1800571d4  lea     r9, [rsp+4A8h+pcbBytesNeeded]; pcbBytesNeeded
0x1800571d9  lea     rdx, [rsp+4A8h+ServiceConfig]; lpServiceConfig
0x1800571de  mov     [rsp+4A8h+pcbBytesNeeded], r8d
0x1800571e3  mov     rcx, rbx; hService
0x1800571e6  call    cs:__imp_QueryServiceConfigW
0x1800571ec  test    eax, eax
0x1800571ee  jz      short loc_180057237
0x1800571f0  cmp     [rsp+4A8h+ServiceConfig.dwStartType], 4
0x1800571f5  jz      loc_1800572A9
0x1800571fb  call    GetServiceWaitTimeout
0x180057200  imul    r12d, eax, 3E8h
0x180057207  xor     r9d, r9d
0x18005720a  mov     r8d, r12d
0x18005720d  mov     rcx, rbx
0x180057210  lea     edx, [r9+49h]
0x180057214  call    cs:__imp_WaitServiceState
0x18005721a  mov     ebp, eax
0x18005721c  test    eax, eax
0x18005721e  jz      short loc_180057237
0x180057220  cmp     eax, 4
0x180057223  jnz     loc_180118E1D
0x180057229  mov     cs:dword_18015D7C0, r13d
0x180057230  mov     cs:dword_18015D7B0, r13d
0x180057237  call    cs:__imp_GetLastError
0x18005723d  mov     edi, eax
0x18005723f  test    rbx, rbx
0x180057242  jz      short loc_18005724D
0x180057244  mov     rcx, rbx; hSCObject
0x180057247  call    cs:__imp_CloseServiceHandle
0x18005724d  mov     rcx, rsi; hSCObject
0x180057250  call    cs:__imp_CloseServiceHandle
0x180057256  mov     ecx, edi; dwErrCode
0x180057258  call    cs:__imp_SetLastError
0x18005725e  mov     eax, cs:dword_18015D7C0
0x180057264  mov     rcx, [rsp+4A8h+var_58]
0x18005726c  xor     rcx, rsp; StackCookie
0x18005726f  call    __security_check_cookie
0x180057274  add     rsp, 468h
0x18005727b  pop     r15
0x18005727d  pop     r14
0x18005727f  pop     r13
0x180057281  pop     r12
0x180057283  pop     rdi
0x180057284  pop     rsi
0x180057285  pop     rbp
0x180057286  pop     rbx
0x180057287  retn
0x180057288  jmp     short loc_180057264
0x18005728a  xor     ebp, ebp
0x18005728c  mov     rdx, r14; lpServiceName
0x18005728f  mov     rcx, rsi; hSCManager
0x180057292  lea     r8d, [rbp+4]; dwDesiredAccess
0x180057296  call    cs:__imp_OpenServiceW
0x18005729c  mov     rbx, rax
0x18005729f  test    rax, rax
0x1800572a2  jz      short loc_180057237
0x1800572a4  jmp     loc_1800571C8
0x1800572a9  lea     rdx, aCryptsvc; "cryptsvc"
0x1800572b0  mov     rcx, r14; String1
0x1800572b3  call    _wcsicmp
0x1800572b8  test    eax, eax
0x1800572ba  jnz     loc_180118DD6
0x1800572c0  call    GetCryptSvcForceStartPolicy
0x1800572c5  test    eax, eax
0x1800572c7  jz      loc_180118DD6
0x1800572cd  xor     edx, edx
0x1800572cf  lea     rcx, aCryptsvc; "cryptsvc"
0x1800572d6  cmp     eax, 2
0x1800572d9  setnz   dl
0x1800572dc  add     edx, 2
0x1800572df  jmp     loc_180118DF3
0x180118dd6  lea     rdx, aProtectedstora; "ProtectedStorage"
0x180118ddd  mov     rcx, r14; String1
0x180118de0  call    _wcsicmp
0x180118de5  test    eax, eax
0x180118de7  jnz     short loc_180118E08
0x180118de9  lea     edx, [rax+3]; dwStartType
0x180118dec  lea     rcx, aProtectedstora; "ProtectedStorage"
0x180118df3  call    ForceCryptServiceToStart
0x180118df8  test    eax, eax
0x180118dfa  jz      loc_180057237
0x180118e00  mov     edi, r13d
0x180118e03  jmp     loc_1800571FB
0x180118e08  mov     ecx, 422h
0x180118e0d  jmp     short loc_180118E11
0x180118e0f  mov     ecx, edi; dwErrCode
0x180118e11  call    cs:__imp_SetLastError
0x180118e17  nop
0x180118e18  jmp     loc_180057237
0x180118e1d  test    edi, edi
0x180118e1f  jnz     loc_180118EB8
0x180118e25  xorps   xmm0, xmm0
0x180118e28  lea     eax, [rdi+10h]
0x180118e2b  lea     r8d, [rdi+40h]
0x180118e2f  cmp     ebp, 7
0x180118e32  movups  xmmword ptr [rsp+4A8h+ServiceStatus.dwServiceType], xmm0
0x180118e37  cmovnz  r8d, eax; dwDesiredAccess
0x180118e3b  mov     rdx, r14; lpServiceName
0x180118e3e  mov     rcx, rsi; hSCManager
0x180118e41  movups  xmmword ptr [rsp+4A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180118e46  call    cs:__imp_OpenServiceW
0x180118e4c  mov     r15, rax
0x180118e4f  test    rax, rax
0x180118e52  jz      loc_180057237
0x180118e58  xor     r14d, r14d
0x180118e5b  mov     rcx, rax; hService
0x180118e5e  cmp     ebp, 7
0x180118e61  jnz     short loc_180118E73
0x180118e63  lea     r8, [rsp+4A8h+ServiceStatus]; lpServiceStatus
0x180118e68  lea     edx, [rdi+3]; dwControl
0x180118e6b  call    cs:__imp_ControlService
0x180118e71  jmp     short loc_180118E7E
0x180118e73  xor     r8d, r8d; lpServiceArgVectors
0x180118e76  xor     edx, edx; dwNumServiceArgs
0x180118e78  call    cs:__imp_StartServiceW
0x180118e7e  test    eax, eax
0x180118e80  jnz     short loc_180118E8B
0x180118e82  call    cs:__imp_GetLastError
0x180118e88  mov     r14d, eax
0x180118e8b  xor     edi, edi
0x180118e8d  mov     rcx, r15; hSCObject
0x180118e90  cmp     r14d, 420h
0x180118e97  cmovnz  edi, r14d
0x180118e9b  call    cs:__imp_CloseServiceHandle
0x180118ea1  test    edi, edi
0x180118ea3  jnz     loc_180118E0F
0x180118ea9  mov     edi, r13d
0x180118eac  lea     r14, aCryptsvc_0; "CryptSvc"
0x180118eb3  jmp     loc_180057207
0x180118eb8  mov     ecx, 5B4h
0x180118ebd  jmp     loc_180118E11
```
