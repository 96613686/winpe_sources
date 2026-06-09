# CMapiUrl::InitFormattedUrlSid(void)

- ea: `0x18002941c`
- end: `0x1800295c8`
- name: `?InitFormattedUrlSid@CMapiUrl@@CAJXZ`
- size: `428`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800188a8`
- `0x18001cadc`
- `0x18002974c`

## callees

- `0x1800031c0`
- `0x18000557c`
- `0x180018ea8`
- `0x18002941c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800295a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800295a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029576`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029461`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029461`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029451`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029437`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800294fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800294fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002956b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002956b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029521`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029521`

## pseudocode

```c
__int64 CMapiUrl::InitFormattedUrlSid(void)
{
  signed int Error; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void **v3; // rdi
  void *v4; // rcx
  LPWSTR TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  Error = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&CMapiUrl::s_userSidLock);
  if ( *((_DWORD *)CMapiUrl::s_userSid - 4) )
    goto LABEL_21;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_21;
  }
  if ( !TokenHandle )
    goto LABEL_21;
  LODWORD(TokenInformationLength) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v3 = (void **)malloc((unsigned int)TokenInformationLength);
    if ( !v3 )
    {
      Error = -2147024882;
      goto LABEL_12;
    }
    goto LABEL_10;
  }
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  else
    Error = LastError;
  v3 = 0;
  if ( Error >= 0 )
  {
LABEL_10:
    if ( !GetTokenInformation(
            TokenHandle,
            TokenUser,
            v3,
            (DWORD)TokenInformationLength,
            (PDWORD)&TokenInformationLength) )
      Error = ResultFromLastError();
  }
LABEL_12:
  CloseHandle(TokenHandle);
  if ( Error < 0 )
  {
    if ( v3 )
LABEL_20:
      free(v3);
  }
  else if ( v3 )
  {
    v4 = *v3;
    TokenInformationLength = 0;
    if ( ConvertSidToStringSidW(v4, &TokenInformationLength) )
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(&CMapiUrl::s_userSid, L"{", 1);
      ATL::CSimpleStringT<wchar_t,0>::Append(&CMapiUrl::s_userSid, TokenInformationLength);
      ATL::CSimpleStringT<wchar_t,0>::Append(&CMapiUrl::s_userSid, L"}");
      LocalFree(TokenInformationLength);
    }
    else
    {
      Error = ResultFromLastError();
    }
    goto LABEL_20;
  }
LABEL_21:
  LeaveCriticalSection((LPCRITICAL_SECTION)&CMapiUrl::s_userSidLock);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002941c  mov     [rsp-8+arg_10], rbx
0x180029421  mov     [rsp-8+arg_18], rdi
0x180029426  push    rbp
0x180029427  mov     rbp, rsp
0x18002942a  sub     rsp, 30h
0x18002942e  lea     rcx, ?s_userSidLock@CMapiUrl@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180029435  xor     ebx, ebx
0x180029437  call    cs:__imp_EnterCriticalSection
0x18002943d  mov     rax, cs:?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x180029444  cmp     [rax-10h], ebx
0x180029447  jnz     loc_1800295A9
0x18002944d  mov     [rbp+TokenHandle], rbx
0x180029451  call    cs:__imp_GetCurrentProcess
0x180029457  mov     rcx, rax; ProcessHandle
0x18002945a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002945e  lea     edx, [rbx+8]; DesiredAccess
0x180029461  call    cs:__imp_OpenProcessToken
0x180029467  test    eax, eax
0x180029469  jnz     short loc_18002947A
0x18002946b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180029470  mov     ebx, eax
0x180029472  test    eax, eax
0x180029474  js      loc_1800295A9
0x18002947a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002947e  test    rcx, rcx
0x180029481  jz      loc_1800295A9
0x180029487  xor     r9d, r9d; TokenInformationLength
0x18002948a  mov     dword ptr [rbp+TokenInformationLength], 0
0x180029491  lea     rax, [rbp+TokenInformationLength]
0x180029495  xor     r8d, r8d; TokenInformation
0x180029498  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002949d  lea     edx, [r9+1]; TokenInformationClass
0x1800294a1  call    cs:__imp_GetTokenInformation
0x1800294a7  call    cs:__imp_GetLastError
0x1800294ad  cmp     eax, 7Ah ; 'z'
0x1800294b0  jz      loc_180029573
0x1800294b6  test    eax, eax
0x1800294b8  jg      short loc_1800294BE
0x1800294ba  mov     ebx, eax
0x1800294bc  jmp     short loc_1800294C7
0x1800294be  movzx   ebx, ax
0x1800294c1  or      ebx, 80070000h
0x1800294c7  xor     edi, edi
0x1800294c9  test    ebx, ebx
0x1800294cb  js      short loc_1800294F7
0x1800294cd  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x1800294d1  lea     rax, [rbp+TokenInformationLength]
0x1800294d5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800294d9  mov     r8, rdi; TokenInformation
0x1800294dc  mov     edx, 1; TokenInformationClass
0x1800294e1  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800294e6  call    cs:__imp_GetTokenInformation
0x1800294ec  test    eax, eax
0x1800294ee  jnz     short loc_1800294F7
0x1800294f0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800294f5  mov     ebx, eax
0x1800294f7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800294fb  call    cs:__imp_CloseHandle
0x180029501  test    ebx, ebx
0x180029503  js      loc_18002959B
0x180029509  test    rdi, rdi
0x18002950c  jz      loc_1800295A9
0x180029512  mov     rcx, [rdi]; Sid
0x180029515  lea     rdx, [rbp+TokenInformationLength]; StringSid
0x180029519  mov     [rbp+TokenInformationLength], 0
0x180029521  call    cs:__imp_ConvertSidToStringSidW
0x180029527  test    eax, eax
0x180029529  jz      short loc_180029592
0x18002952b  mov     r8d, 1
0x180029531  lea     rdx, asc_180042E10; "{"
0x180029538  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002953f  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180029544  mov     rdx, [rbp+TokenInformationLength]
0x180029548  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002954f  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180029554  lea     rdx, asc_180042DC8; "}"
0x18002955b  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x180029562  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180029567  mov     rcx, [rbp+TokenInformationLength]; hMem
0x18002956b  call    cs:__imp_LocalFree
0x180029571  jmp     short loc_1800295A0
0x180029573  mov     ecx, dword ptr [rbp+TokenInformationLength]; Size
0x180029576  call    cs:__imp_malloc
0x18002957c  mov     rdi, rax
0x18002957f  test    rax, rax
0x180029582  jnz     loc_1800294CD
0x180029588  mov     ebx, 8007000Eh
0x18002958d  jmp     loc_1800294F7
0x180029592  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180029597  mov     ebx, eax
0x180029599  jmp     short loc_1800295A0
0x18002959b  test    rdi, rdi
0x18002959e  jz      short loc_1800295A9
0x1800295a0  mov     rcx, rdi; Block
0x1800295a3  call    cs:__imp_free
0x1800295a9  lea     rcx, ?s_userSidLock@CMapiUrl@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x1800295b0  call    cs:__imp_LeaveCriticalSection
0x1800295b6  mov     rdi, [rsp+30h+arg_18]
0x1800295bb  mov     eax, ebx
0x1800295bd  mov     rbx, [rsp+30h+arg_10]
0x1800295c2  add     rsp, 30h
0x1800295c6  pop     rbp
0x1800295c7  retn
```
