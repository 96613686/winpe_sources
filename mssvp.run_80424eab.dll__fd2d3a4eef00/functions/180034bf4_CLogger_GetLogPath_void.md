# CLogger::GetLogPath(void)

- ea: `0x180034bf4`
- end: `0x180034e43`
- name: `?GetLogPath@CLogger@@AEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800345d8`

## callees

- `0x1800031c0`
- `0x180004080`
- `0x18000557c`
- `0x180006270`
- `0x180018ea8`
- `0x18002b28c`
- `0x180034954`
- `0x180034bf4`
- `0x180038ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034d89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034d89`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034d65`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c98`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034c52`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034c52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034c40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034cf1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034cdb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034cdb`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180034dd0`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180034dd0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034d4e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034d4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLogger::GetLogPath(__int64 a1, __int64 a2)
{
  signed int Error; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  PSID *v6; // rdi
  __int64 v7; // r8
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  int v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[1024]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ReferencedDomainName[1024]; // [rsp+A80h] [rbp+980h] BYREF

  v14 = a2;
  v13 = 0;
  Error = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_19;
  }
  if ( !TokenHandle )
    goto LABEL_20;
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = (PSID *)malloc(TokenInformationLength);
    if ( v6 )
      goto LABEL_9;
    Error = -2147024882;
  }
  else
  {
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    else
      Error = LastError;
    v6 = 0;
    if ( Error >= 0 )
    {
LABEL_9:
      if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
        Error = ResultFromLastError();
    }
  }
  CloseHandle(TokenHandle);
  if ( Error >= 0 )
  {
    if ( !v6 )
      goto LABEL_20;
    cchName = 1024;
    cchReferencedDomainName = 1024;
    TokenInformationLength = 0;
    if ( !LookupAccountSidW(
            0,
            *v6,
            Name,
            &cchName,
            ReferencedDomainName,
            &cchReferencedDomainName,
            (PSID_NAME_USE)&TokenInformationLength) )
      Error = ResultFromLastError();
LABEL_18:
    free(v6);
    if ( Error >= 0 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( v6 )
    goto LABEL_18;
LABEL_19:
  StringCchCopyW(Name, 0x400u, L"Unknown");
LABEL_20:
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    a2,
    &MultiByteStr);
  v13 = 1;
  if ( SHGetSpecialFolderPathW(0, pszPath, 35, 0) )
  {
    v7 = -1;
    do
      ++v7;
    while ( pszPath[v7] );
    ATL::CSimpleStringT<wchar_t,0>::SetString(a2, pszPath, v7);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(a2, "\\MSSearch\\Logs\\");
    ATL::CSimpleStringT<wchar_t,0>::Append(a2, Name);
  }
  return a2;
}

```

## disassembly

```asm
0x180034bf4  mov     [rsp-8+arg_0], rbx
0x180034bf9  mov     [rsp-8+arg_10], rsi
0x180034bfe  push    rbp
0x180034bff  push    rdi
0x180034c00  push    r14
0x180034c02  lea     rbp, [rsp-1190h]
0x180034c0a  mov     eax, 1290h
0x180034c0f  call    _alloca_probe
0x180034c14  sub     rsp, rax
0x180034c17  mov     rax, cs:__security_cookie
0x180034c1e  xor     rax, rsp
0x180034c21  mov     [rbp+11A0h+var_20], rax
0x180034c28  mov     rsi, rdx
0x180034c2b  mov     [rsp+12A0h+var_1240], rdx
0x180034c30  xor     r14d, r14d
0x180034c33  mov     [rsp+12A0h+var_1248], r14d
0x180034c38  mov     ebx, r14d
0x180034c3b  mov     [rsp+12A0h+TokenHandle], r14
0x180034c40  call    cs:__imp_GetCurrentProcess
0x180034c46  mov     rcx, rax; ProcessHandle
0x180034c49  lea     r8, [rsp+12A0h+TokenHandle]; TokenHandle
0x180034c4e  lea     edx, [r14+8]; DesiredAccess
0x180034c52  call    cs:__imp_OpenProcessToken
0x180034c58  test    eax, eax
0x180034c5a  jnz     short loc_180034C6B
0x180034c5c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180034c61  mov     ebx, eax
0x180034c63  test    eax, eax
0x180034c65  js      loc_180034D93
0x180034c6b  mov     rcx, [rsp+12A0h+TokenHandle]; TokenHandle
0x180034c70  test    rcx, rcx
0x180034c73  jz      loc_180034DAB
0x180034c79  mov     [rsp+12A0h+TokenInformationLength], r14d
0x180034c7e  lea     rax, [rsp+12A0h+TokenInformationLength]
0x180034c83  mov     [rsp+12A0h+ReturnLength], rax; ReturnLength
0x180034c88  xor     r9d, r9d; TokenInformationLength
0x180034c8b  xor     r8d, r8d; TokenInformation
0x180034c8e  lea     edx, [r9+1]; TokenInformationClass
0x180034c92  call    cs:__imp_GetTokenInformation
0x180034c98  call    cs:__imp_GetLastError
0x180034c9e  cmp     eax, 7Ah ; 'z'
0x180034ca1  jz      loc_180034D61
0x180034ca7  test    eax, eax
0x180034ca9  jg      short loc_180034CAF
0x180034cab  mov     ebx, eax
0x180034cad  jmp     short loc_180034CB8
0x180034caf  movzx   ebx, ax
0x180034cb2  or      ebx, 80070000h
0x180034cb8  mov     rdi, r14
0x180034cbb  test    ebx, ebx
0x180034cbd  js      short loc_180034CEC
0x180034cbf  lea     rax, [rsp+12A0h+TokenInformationLength]
0x180034cc4  mov     [rsp+12A0h+ReturnLength], rax; ReturnLength
0x180034cc9  mov     r9d, [rsp+12A0h+TokenInformationLength]; TokenInformationLength
0x180034cce  mov     r8, rdi; TokenInformation
0x180034cd1  mov     edx, 1; TokenInformationClass
0x180034cd6  mov     rcx, [rsp+12A0h+TokenHandle]; TokenHandle
0x180034cdb  call    cs:__imp_GetTokenInformation
0x180034ce1  test    eax, eax
0x180034ce3  jnz     short loc_180034CEC
0x180034ce5  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180034cea  mov     ebx, eax
0x180034cec  mov     rcx, [rsp+12A0h+TokenHandle]; hObject
0x180034cf1  call    cs:__imp_CloseHandle
0x180034cf7  test    ebx, ebx
0x180034cf9  js      loc_180034D81
0x180034cff  test    rdi, rdi
0x180034d02  jz      loc_180034DAB
0x180034d08  mov     [rsp+12A0h+cchName], 400h
0x180034d10  mov     [rsp+12A0h+var_1250], 400h
0x180034d18  mov     [rsp+12A0h+TokenInformationLength], r14d
0x180034d1d  lea     rax, [rsp+12A0h+TokenInformationLength]
0x180034d22  mov     [rsp+12A0h+peUse], rax; peUse
0x180034d27  lea     rax, [rsp+12A0h+var_1250]
0x180034d2c  mov     [rsp+12A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180034d31  lea     rax, [rbp+11A0h+ReferencedDomainName]
0x180034d38  mov     [rsp+12A0h+ReturnLength], rax; ReferencedDomainName
0x180034d3d  lea     r9, [rsp+12A0h+cchName]; cchName
0x180034d42  lea     r8, [rbp+11A0h+Name]; Name
0x180034d49  mov     rdx, [rdi]; Sid
0x180034d4c  xor     ecx, ecx; lpSystemName
0x180034d4e  call    cs:__imp_LookupAccountSidW
0x180034d54  test    eax, eax
0x180034d56  jnz     short loc_180034D86
0x180034d58  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180034d5d  mov     ebx, eax
0x180034d5f  jmp     short loc_180034D86
0x180034d61  mov     ecx, [rsp+12A0h+TokenInformationLength]; Size
0x180034d65  call    cs:__imp_malloc
0x180034d6b  mov     rdi, rax
0x180034d6e  test    rax, rax
0x180034d71  jnz     loc_180034CBF
0x180034d77  mov     ebx, 8007000Eh
0x180034d7c  jmp     loc_180034CEC
0x180034d81  test    rdi, rdi
0x180034d84  jz      short loc_180034D93
0x180034d86  mov     rcx, rdi; Block
0x180034d89  call    cs:__imp_free
0x180034d8f  test    ebx, ebx
0x180034d91  jns     short loc_180034DAB
0x180034d93  lea     r8, aUnknown_0; "Unknown"
0x180034d9a  mov     edx, 400h; unsigned __int64
0x180034d9f  lea     rcx, [rbp+11A0h+Name]; wchar_t *
0x180034da6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180034dab  lea     rdx, MultiByteStr
0x180034db2  mov     rcx, rsi
0x180034db5  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x180034dba  mov     [rsp+12A0h+var_1248], 1
0x180034dc2  xor     r9d, r9d; fCreate
0x180034dc5  lea     r8d, [r9+23h]; csidl
0x180034dc9  lea     rdx, [rsp+12A0h+pszPath]; pszPath
0x180034dce  xor     ecx, ecx; hwnd
0x180034dd0  call    cs:__imp_SHGetSpecialFolderPathW
0x180034dd6  test    eax, eax
0x180034dd8  jz      short loc_180034E18
0x180034dda  lea     rax, [rsp+12A0h+pszPath]
0x180034ddf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180034de3  inc     r8
0x180034de6  cmp     [rax+r8*2], r14w
0x180034deb  jnz     short loc_180034DE3
0x180034ded  lea     rdx, [rsp+12A0h+pszPath]
0x180034df2  mov     rcx, rsi
0x180034df5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180034dfa  lea     rdx, aMssearchLogs; "\\MSSearch\\Logs\\"
0x180034e01  mov     rcx, rsi
0x180034e04  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180034e09  lea     rdx, [rbp+11A0h+Name]
0x180034e10  mov     rcx, rsi
0x180034e13  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180034e18  mov     rax, rsi
0x180034e1b  mov     rcx, [rbp+11A0h+var_20]
0x180034e22  xor     rcx, rsp; StackCookie
0x180034e25  call    __security_check_cookie
0x180034e2a  lea     r11, [rsp+12A0h+var_10]
0x180034e32  mov     rbx, [r11+20h]
0x180034e36  mov     rsi, [r11+30h]
0x180034e3a  mov     rsp, r11
0x180034e3d  pop     r14
0x180034e3f  pop     rdi
0x180034e40  pop     rbp
0x180034e41  retn
```
