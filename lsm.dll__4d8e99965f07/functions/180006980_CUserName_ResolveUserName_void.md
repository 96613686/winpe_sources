# CUserName::ResolveUserName(void *)

- ea: `0x180006980`
- end: `0x18000703f`
- name: `?ResolveUserName@CUserName@@AEAAJPEAX@Z`
- size: `1727`
- prototype: `int(CUserName *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800051f0`
- `0x180008f40`

## callees

- `0x180006980`
- `0x1800077a0`
- `0x180007cc8`
- `0x180050214`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180006b37`
- `ntdll!RtlEqualSid` at `0x180006b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800069ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800069ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006a2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006a8c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006abc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006b1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006a2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006a8c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006abc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006b1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006bbe`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006bbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006e5f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006e5f`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x180006bf6`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x180006bf6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006de5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006fd9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006de5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006fd9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d47`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d90`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006da0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d47`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006d90`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006da0`

## string_xrefs

- `0x180006d14`: `StringCchCopyN failed: 0x%x in %s`
- `0x180006e12`: `LookupAccountSid failed: 0x%x`
- `0x180006e34`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180006e9f`: `Impersonate.StopImpersonating failed: 0x%x in %s`
- `0x180006f93`: `CImpersonate::ImpersonateUser`
- `0x180006f49`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x180006f78`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`
- `0x180006f62`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`

## pseudocode

```c
__int64 __fastcall CUserName::ResolveUserName(PSID **this, void *a2)
{
  PSID *v2; // rdi
  PSID *v3; // rsi
  char v6; // r15
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD v12; // ebx
  bool v13; // sf
  int v14; // r8d
  PWSTR Buffer; // r8
  PLSA_UNICODE_STRING v16; // r10
  __int64 v17; // rdx
  _WORD *v18; // r9
  unsigned __int64 v19; // rcx
  _WORD *v20; // rcx
  int v21; // r11d
  unsigned int v22; // ebx
  __int64 v23; // rax
  _WORD *v24; // r8
  PWSTR v25; // r9
  unsigned __int64 v26; // rdx
  _WORD *v27; // rdx
  __int64 v28; // r8
  PWSTR v29; // rcx
  PWSTR v31; // rcx
  signed int v32; // eax
  signed int v33; // eax
  bool v34; // sf
  signed int v35; // eax
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD cchName; // [rsp+38h] [rbp-28h] BYREF
  PLSA_UNICODE_STRING UserName; // [rsp+40h] [rbp-20h] BYREF
  PLSA_UNICODE_STRING DomainName; // [rsp+48h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  __int16 v42; // [rsp+B0h] [rbp+50h] BYREF
  DWORD TokenInformationLength; // [rsp+B8h] [rbp+58h] BYREF

  v42 = 0;
  UserName = 0;
  v2 = 0;
  DomainName = 0;
  v3 = 0;
  peUse = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v6 = 0;
  cchName = 257;
  cchReferencedDomainName = 256;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  LastError = 1375;
  if ( !a2 )
    goto LABEL_14;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v9 = GetLastError();
    LastError = v9;
    if ( v9 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for input token, Error %x", v9);
      goto LABEL_14;
    }
  }
  v10 = TokenInformationLength;
  v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v2 )
    goto LABEL_73;
  if ( !GetTokenInformation(a2, TokenUser, v2, v10, &TokenInformationLength) )
  {
LABEL_70:
    LastError = GetLastError();
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get token infomration for input token, Error %x", LastError);
    goto LABEL_14;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v11 = GetLastError();
    LastError = v11;
    if ( v11 != 122 )
    {
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for current token, Error %x", v11);
      goto LABEL_14;
    }
  }
  v12 = TokenInformationLength;
  v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  if ( !v3 )
  {
LABEL_73:
    LastError = 8;
    _DbgPrintMessage(8, "CheckCurrentContext: FAILED to allocate memory");
    goto LABEL_14;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v3, v12, &TokenInformationLength) )
    goto LABEL_70;
  if ( RtlEqualSid(*v2, *v3) )
  {
    LastError = 0;
  }
  else
  {
    _DbgPrintMessage(4, "TERMSRV: CheckCurrentContext - Different user is being impersonated");
    LastError = 1375;
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    LocalFree(v2);
  if ( v3 )
    LocalFree(v3);
  v13 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = LastError < 0;
  }
  if ( !v13 )
    goto LABEL_29;
  v14 = 0;
  if ( LastError != -2147023888 )
    v14 = LastError;
  if ( v14 < 0 )
  {
    _DbgPrintMessage(8, "CheckCurrentContext failed: 0x%x in %s", v14, "CImpersonate::ImpersonateUser");
  }
  else
  {
    if ( ImpersonateLoggedOnUser(a2) )
    {
      v6 = 1;
      LOBYTE(v42) = 1;
      goto LABEL_29;
    }
    v33 = GetLastError();
    v34 = v33 < 0;
    if ( v33 > 0 )
      v34 = 1;
    if ( !v34 )
    {
LABEL_29:
      if ( (unsigned __int8)IsLsaGetUserNamePresent() )
      {
        if ( !LsaGetUserName(&UserName, &DomainName) )
        {
          if ( UserName )
          {
            Buffer = UserName->Buffer;
            if ( Buffer )
            {
              v16 = DomainName;
              if ( DomainName )
              {
                if ( DomainName->Buffer )
                {
                  v17 = cchName;
                  v18 = this + 266;
                  if ( cchName > 0x7FFFFFFFuLL )
                  {
                    v22 = -2147024809;
                    *v18 = 0;
                  }
                  else
                  {
                    v19 = (unsigned __int64)UserName->Length >> 1;
                    do
                    {
                      if ( !v19 )
                        break;
                      if ( !*Buffer )
                        break;
                      *v18++ = *Buffer++;
                      --v19;
                      --v17;
                    }
                    while ( v17 );
                    v20 = v18 - 1;
                    v21 = -2147024774;
                    if ( v17 )
                      v20 = v18;
                    v22 = -2147024774;
                    if ( v17 )
                      v22 = 0;
                    *v20 = 0;
                    if ( v17 )
                    {
                      v23 = cchReferencedDomainName;
                      v24 = this + 202;
                      if ( cchReferencedDomainName )
                      {
                        if ( cchReferencedDomainName > 0x7FFFFFFFuLL )
                        {
                          v22 = -2147024809;
                          v21 = -2147024809;
                          *v24 = 0;
LABEL_55:
                          v28 = (unsigned int)v21;
LABEL_56:
                          _DbgPrintMessage(8, "StringCchCopyN failed: 0x%x in %s", v28, "CUserName::ResolveUserName");
                          goto LABEL_57;
                        }
                        v25 = v16->Buffer;
                        v26 = (unsigned __int64)DomainName->Length >> 1;
                        do
                        {
                          if ( !v26 )
                            break;
                          if ( !*v25 )
                            break;
                          *v24++ = *v25++;
                          --v26;
                          --v23;
                        }
                        while ( v23 );
                        v27 = v24 - 1;
                        if ( v23 )
                        {
                          v27 = v24;
                          v21 = 0;
                        }
                        *v27 = 0;
                      }
                      else
                      {
                        v21 = -2147024809;
                      }
                      v22 = v21;
                      if ( v21 >= 0 )
                        goto LABEL_57;
                      goto LABEL_55;
                    }
                  }
                  v28 = v22;
                  goto LABEL_56;
                }
              }
            }
          }
        }
      }
      if ( v6 )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(v42) = 0;
        }
        else
        {
          v35 = GetLastError();
          v22 = v35;
          if ( v35 > 0 )
            v22 = (unsigned __int16)v35 | 0x80070000;
          if ( (v22 & 0x80000000) != 0 )
          {
            _DbgPrintMessage(8, "Impersonate.StopImpersonating failed: 0x%x in %s", v22, "CUserName::ResolveUserName");
            goto LABEL_57;
          }
        }
      }
      if ( !LookupAccountSidLocalW(
              *this[201],
              (LPWSTR)this + 1064,
              &cchName,
              (LPWSTR)this + 808,
              &cchReferencedDomainName,
              &peUse) )
      {
        v32 = GetLastError();
        v22 = v32;
        if ( v32 <= 0 )
        {
LABEL_69:
          _DbgPrintMessage(8, "LookupAccountSid failed: 0x%x", v22);
          goto LABEL_57;
        }
LABEL_82:
        v22 = (unsigned __int16)v32 | 0x80070000;
        goto LABEL_69;
      }
      if ( ((peUse - 1) & 0xFFFFFFFB) != 0 )
        goto LABEL_95;
LABEL_91:
      v22 = 0;
      goto LABEL_57;
    }
  }
  if ( !LookupAccountSidLocalW(
          *this[201],
          (LPWSTR)this + 1064,
          &cchName,
          (LPWSTR)this + 808,
          &cchReferencedDomainName,
          &peUse) )
  {
    v32 = GetLastError();
    v22 = v32;
    if ( v32 <= 0 )
      goto LABEL_69;
    goto LABEL_82;
  }
  if ( ((peUse - 1) & 0xFFFFFFFB) == 0 )
    goto LABEL_91;
LABEL_95:
  _DbgPrintMessage(8, "Expecting user account to logon");
  v22 = -2147024891;
LABEL_57:
  if ( UserName )
  {
    v31 = UserName->Buffer;
    if ( v31 )
      LsaFreeMemory(v31);
    LsaFreeMemory(UserName);
  }
  if ( DomainName )
  {
    v29 = DomainName->Buffer;
    if ( v29 )
      LsaFreeMemory(v29);
    LsaFreeMemory(DomainName);
  }
  CImpersonate::~CImpersonate((CImpersonate *)&v42);
  return v22;
}

```

## disassembly

```asm
0x180006980  mov     [rsp-38h+arg_0], rbx
0x180006985  push    rbp
0x180006986  push    rsi
0x180006987  push    rdi
0x180006988  push    r12
0x18000698a  push    r13
0x18000698c  push    r14
0x18000698e  push    r15
0x180006990  mov     rbp, rsp
0x180006993  sub     rsp, 60h
0x180006997  xor     r12d, r12d
0x18000699a  mov     [rbp+arg_10], 0
0x1800069a0  mov     [rbp+UserName], r12
0x1800069a4  mov     edi, r12d
0x1800069a7  mov     [rbp+DomainName], r12
0x1800069ab  mov     esi, r12d
0x1800069ae  mov     [rbp+var_30], r12d
0x1800069b2  mov     r14, rdx
0x1800069b5  mov     [rbp+TokenHandle], r12
0x1800069b9  mov     r13, rcx
0x1800069bc  mov     [rbp+TokenInformationLength], r12d
0x1800069c0  xor     r15b, r15b
0x1800069c3  mov     [rbp+cchName], 101h
0x1800069ca  mov     [rbp+cchReferencedDomainName], 100h
0x1800069d1  call    cs:__imp_GetCurrentThread
0x1800069d8  nop     dword ptr [rax+rax+00h]
0x1800069dd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800069e1  mov     edx, 0Eh; DesiredAccess
0x1800069e6  mov     rcx, rax; ThreadHandle
0x1800069e9  mov     r8d, 1; OpenAsSelf
0x1800069ef  call    cs:__imp_OpenThreadToken
0x1800069f6  nop     dword ptr [rax+rax+00h]
0x1800069fb  test    eax, eax
0x1800069fd  jz      loc_180006B50
0x180006a03  mov     ebx, 55Fh
0x180006a08  test    r14, r14
0x180006a0b  jz      loc_180006B5E
0x180006a11  lea     rax, [rbp+TokenInformationLength]
0x180006a15  mov     [rbp+TokenInformationLength], r12d
0x180006a19  xor     r9d, r9d; TokenInformationLength
0x180006a1c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006a21  xor     r8d, r8d; TokenInformation
0x180006a24  mov     edx, 1; TokenInformationClass
0x180006a29  mov     rcx, r14; TokenHandle
0x180006a2c  call    cs:__imp_GetTokenInformation
0x180006a33  nop     dword ptr [rax+rax+00h]
0x180006a38  test    eax, eax
0x180006a3a  jnz     short loc_180006A53
0x180006a3c  call    cs:__imp_GetLastError
0x180006a43  nop     dword ptr [rax+rax+00h]
0x180006a48  mov     ebx, eax
0x180006a4a  cmp     eax, 7Ah ; 'z'
0x180006a4d  jnz     loc_180006F46
0x180006a53  mov     ebx, [rbp+TokenInformationLength]
0x180006a56  mov     ecx, 40h ; '@'; uFlags
0x180006a5b  mov     edx, ebx; uBytes
0x180006a5d  call    cs:__imp_LocalAlloc
0x180006a64  nop     dword ptr [rax+rax+00h]
0x180006a69  mov     rdi, rax
0x180006a6c  test    rax, rax
0x180006a6f  jz      loc_180006E7C
0x180006a75  lea     rax, [rbp+TokenInformationLength]
0x180006a79  mov     r9d, ebx; TokenInformationLength
0x180006a7c  mov     r8, rdi; TokenInformation
0x180006a7f  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006a84  mov     edx, 1; TokenInformationClass
0x180006a89  mov     rcx, r14; TokenHandle
0x180006a8c  call    cs:__imp_GetTokenInformation
0x180006a93  nop     dword ptr [rax+rax+00h]
0x180006a98  test    eax, eax
0x180006a9a  jz      loc_180006E28
0x180006aa0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180006aa4  lea     rax, [rbp+TokenInformationLength]
0x180006aa8  xor     r9d, r9d; TokenInformationLength
0x180006aab  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006ab0  xor     r8d, r8d; TokenInformation
0x180006ab3  mov     [rbp+TokenInformationLength], r12d
0x180006ab7  mov     edx, 1; TokenInformationClass
0x180006abc  call    cs:__imp_GetTokenInformation
0x180006ac3  nop     dword ptr [rax+rax+00h]
0x180006ac8  test    eax, eax
0x180006aca  jnz     short loc_180006AE3
0x180006acc  call    cs:__imp_GetLastError
0x180006ad3  nop     dword ptr [rax+rax+00h]
0x180006ad8  mov     ebx, eax
0x180006ada  cmp     eax, 7Ah ; 'z'
0x180006add  jnz     loc_180006F5F
0x180006ae3  mov     ebx, [rbp+TokenInformationLength]
0x180006ae6  mov     ecx, 40h ; '@'; uFlags
0x180006aeb  mov     edx, ebx; uBytes
0x180006aed  call    cs:__imp_LocalAlloc
0x180006af4  nop     dword ptr [rax+rax+00h]
0x180006af9  mov     rsi, rax
0x180006afc  test    rax, rax
0x180006aff  jz      loc_180006E7C
0x180006b05  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180006b09  lea     rax, [rbp+TokenInformationLength]
0x180006b0d  mov     r9d, ebx; TokenInformationLength
0x180006b10  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006b15  mov     r8, rsi; TokenInformation
0x180006b18  mov     edx, 1; TokenInformationClass
0x180006b1d  call    cs:__imp_GetTokenInformation
0x180006b24  nop     dword ptr [rax+rax+00h]
0x180006b29  test    eax, eax
0x180006b2b  jz      loc_180006E28
0x180006b31  mov     rdx, [rsi]; Sid2
0x180006b34  mov     rcx, [rdi]; Sid1
0x180006b37  call    cs:__imp_RtlEqualSid
0x180006b3e  nop     dword ptr [rax+rax+00h]
0x180006b43  test    al, al
0x180006b45  jz      loc_180006F78
0x180006b4b  mov     ebx, r12d
0x180006b4e  jmp     short loc_180006B5E
0x180006b50  call    cs:__imp_GetLastError
0x180006b57  nop     dword ptr [rax+rax+00h]
0x180006b5c  mov     ebx, eax
0x180006b5e  mov     rcx, [rbp+TokenHandle]; hObject
0x180006b62  test    rcx, rcx
0x180006b65  jz      short loc_180006B73
0x180006b67  call    cs:__imp_CloseHandle
0x180006b6e  nop     dword ptr [rax+rax+00h]
0x180006b73  test    rdi, rdi
0x180006b76  jz      short loc_180006B87
0x180006b78  mov     rcx, rdi; hMem
0x180006b7b  call    cs:__imp_LocalFree
0x180006b82  nop     dword ptr [rax+rax+00h]
0x180006b87  test    rsi, rsi
0x180006b8a  jz      short loc_180006B9B
0x180006b8c  mov     rcx, rsi; hMem
0x180006b8f  call    cs:__imp_LocalFree
0x180006b96  nop     dword ptr [rax+rax+00h]
0x180006b9b  test    ebx, ebx
0x180006b9d  jg      loc_180006E4F
0x180006ba3  jns     short loc_180006BE1
0x180006ba5  cmp     ebx, 800703F0h
0x180006bab  mov     r8d, r12d
0x180006bae  cmovnz  r8d, ebx
0x180006bb2  test    r8d, r8d
0x180006bb5  js      loc_180006F93
0x180006bbb  mov     rcx, r14; hToken
0x180006bbe  call    cs:__imp_ImpersonateLoggedOnUser
0x180006bc5  nop     dword ptr [rax+rax+00h]
0x180006bca  test    eax, eax
0x180006bcc  jz      loc_180006EDB
0x180006bd2  mov     r15b, 1
0x180006bd5  mov     byte ptr [rbp+arg_10], r15b
0x180006bd9  jmp     short loc_180006BE1
0x180006bdb  js      loc_180006FAB
0x180006be1  call    IsLsaGetUserNamePresent
0x180006be6  test    al, al
0x180006be8  jz      loc_180006DAE
0x180006bee  lea     rdx, [rbp+DomainName]; DomainName
0x180006bf2  lea     rcx, [rbp+UserName]; UserName
0x180006bf6  call    cs:__imp_LsaGetUserName
0x180006bfd  nop     dword ptr [rax+rax+00h]
0x180006c02  test    eax, eax
0x180006c04  jnz     loc_180006DAE
0x180006c0a  mov     rax, [rbp+UserName]
0x180006c0e  test    rax, rax
0x180006c11  jz      loc_180006DAE
0x180006c17  mov     r8, [rax+8]
0x180006c1b  test    r8, r8
0x180006c1e  jz      loc_180006DAE
0x180006c24  mov     r10, [rbp+DomainName]
0x180006c28  test    r10, r10
0x180006c2b  jz      loc_180006DAE
0x180006c31  cmp     [r10+8], r12
0x180006c35  jz      loc_180006DAE
0x180006c3b  mov     edx, [rbp+cchName]
0x180006c3e  lea     r9, [r13+850h]
0x180006c45  test    rdx, rdx
0x180006c48  jz      loc_180006EAB
0x180006c4e  cmp     rdx, 7FFFFFFFh
0x180006c55  ja      loc_180007001
0x180006c5b  movzx   ecx, word ptr [rax]
0x180006c5e  shr     rcx, 1
0x180006c61  test    rcx, rcx
0x180006c64  jz      short loc_180006C84
0x180006c66  movzx   eax, word ptr [r8]
0x180006c6a  test    ax, ax
0x180006c6d  jz      short loc_180006C84
0x180006c6f  mov     [r9], ax
0x180006c73  add     r8, 2
0x180006c77  add     r9, 2
0x180006c7b  dec     rcx
0x180006c7e  sub     rdx, 1
0x180006c82  jnz     short loc_180006C61
0x180006c84  test    rdx, rdx
0x180006c87  lea     rcx, [r9-2]
0x180006c8b  mov     r11d, 8007007Ah
0x180006c91  cmovnz  rcx, r9
0x180006c95  mov     ebx, r11d
0x180006c98  cmovnz  ebx, r12d
0x180006c9c  mov     [rcx], r12w
0x180006ca0  jz      loc_180006EB9
0x180006ca6  mov     eax, [rbp+cchReferencedDomainName]
0x180006ca9  lea     r8, [r13+650h]
0x180006cb0  test    rax, rax
0x180006cb3  jz      loc_180006EC1
0x180006cb9  cmp     rax, 7FFFFFFFh
0x180006cbf  ja      loc_18000700B
0x180006cc5  mov     rcx, [rbp+DomainName]
0x180006cc9  mov     r9, [r10+8]
0x180006ccd  movzx   edx, word ptr [rcx]
0x180006cd0  shr     rdx, 1
0x180006cd3  test    rdx, rdx
0x180006cd6  jz      short loc_180006CF6
0x180006cd8  movzx   ecx, word ptr [r9]
0x180006cdc  test    cx, cx
0x180006cdf  jz      short loc_180006CF6
0x180006ce1  mov     [r8], cx
0x180006ce5  add     r9, 2
0x180006ce9  add     r8, 2
0x180006ced  dec     rdx
0x180006cf0  sub     rax, 1
0x180006cf4  jnz     short loc_180006CD3
0x180006cf6  test    rax, rax
0x180006cf9  lea     rdx, [r8-2]
0x180006cfd  cmovnz  rdx, r8
0x180006d01  cmovnz  r11d, r12d
0x180006d05  mov     [rdx], r12w
0x180006d09  mov     ebx, r11d
0x180006d0c  test    r11d, r11d
0x180006d0f  jns     short loc_180006D2C
0x180006d11  mov     r8d, r11d
0x180006d14  lea     rdx, aStringcchcopyn; "StringCchCopyN failed: 0x%x in %s"
0x180006d1b  lea     r9, aCusernameResol; "CUserName::ResolveUserName"
0x180006d22  mov     ecx, 8; int
0x180006d27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006d2c  mov     rax, [rbp+UserName]
0x180006d30  test    rax, rax
0x180006d33  jnz     short loc_180006D87
0x180006d35  mov     r10, [rbp+DomainName]
0x180006d39  test    r10, r10
0x180006d3c  jz      short loc_180006D63
0x180006d3e  mov     rcx, [r10+8]; Buffer
0x180006d42  test    rcx, rcx
0x180006d45  jz      short loc_180006D53
0x180006d47  call    cs:__imp_LsaFreeMemory
0x180006d4e  nop     dword ptr [rax+rax+00h]
0x180006d53  mov     rcx, [rbp+DomainName]; Buffer
0x180006d57  call    cs:__imp_LsaFreeMemory
0x180006d5e  nop     dword ptr [rax+rax+00h]
0x180006d63  lea     rcx, [rbp+arg_10]; this
0x180006d67  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180006d6c  mov     eax, ebx
0x180006d6e  mov     rbx, [rsp+60h+arg_0]
0x180006d76  add     rsp, 60h
0x180006d7a  pop     r15
0x180006d7c  pop     r14
0x180006d7e  pop     r13
0x180006d80  pop     r12
0x180006d82  pop     rdi
0x180006d83  pop     rsi
0x180006d84  pop     rbp
0x180006d85  retn
0x180006d87  mov     rcx, [rax+8]; Buffer
0x180006d8b  test    rcx, rcx
0x180006d8e  jz      short loc_180006D9C
0x180006d90  call    cs:__imp_LsaFreeMemory
0x180006d97  nop     dword ptr [rax+rax+00h]
0x180006d9c  mov     rcx, [rbp+UserName]; Buffer
0x180006da0  call    cs:__imp_LsaFreeMemory
0x180006da7  nop     dword ptr [rax+rax+00h]
0x180006dac  jmp     short loc_180006D35
0x180006dae  test    r15b, r15b
0x180006db1  jnz     loc_180006E5F
0x180006db7  mov     rcx, [r13+648h]
0x180006dbe  lea     rax, [rbp+var_30]
0x180006dc2  mov     [rsp+60h+peUse], rax; peUse
0x180006dc7  lea     r9, [r13+650h]; ReferencedDomainName
0x180006dce  lea     rax, [rbp+cchReferencedDomainName]
0x180006dd2  lea     rdx, [r13+850h]; Name
0x180006dd9  mov     [rsp+60h+ReturnLength], rax; cchReferencedDomainName
0x180006dde  mov     rcx, [rcx]; Sid
0x180006de1  lea     r8, [rbp+cchName]; cchName
0x180006de5  call    cs:__imp_LookupAccountSidLocalW
0x180006dec  nop     dword ptr [rax+rax+00h]
0x180006df1  test    eax, eax
0x180006df3  jnz     loc_180007018
0x180006df9  call    cs:__imp_GetLastError
0x180006e00  nop     dword ptr [rax+rax+00h]
0x180006e05  mov     ebx, eax
0x180006e07  test    eax, eax
0x180006e09  jg      loc_180006F14
0x180006e0f  mov     r8d, ebx
0x180006e12  lea     rdx, aLookupaccounts_0; "LookupAccountSid failed: 0x%x"
0x180006e19  mov     ecx, 8; int
0x180006e1e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006e23  jmp     loc_180006D2C
0x180006e28  call    cs:__imp_GetLastError
0x180006e2f  nop     dword ptr [rax+rax+00h]
0x180006e34  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x180006e3b  mov     ecx, 8; int
0x180006e40  mov     r8d, eax
0x180006e43  mov     ebx, eax
0x180006e45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006e4a  jmp     loc_180006B5E
0x180006e4f  movzx   ebx, bx
0x180006e52  or      ebx, 80070000h
  ... truncated ...
```
