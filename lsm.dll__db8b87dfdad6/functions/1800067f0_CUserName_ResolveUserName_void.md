# CUserName::ResolveUserName(void *)

- ea: `0x1800067f0`
- end: `0x180006e05`
- name: `?ResolveUserName@CUserName@@AEAAJPEAX@Z`
- size: `1557`
- prototype: `__int64 __fastcall(PSID **this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800051b0`
- `0x180008b20`

## callees

- `0x1800067f0`
- `0x1800074c0`
- `0x1800079bc`
- `0x18004ce04`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000696b`
- `ntdll!RtlEqualSid` at `0x18000696b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000689a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000689a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cf4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006859`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006859`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000698f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000698f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000692d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000692d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000699d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000699d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006890`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800068de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006908`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006957`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006890`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800068de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006908`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006957`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800069d4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800069d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006c43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006c43`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x180006a06`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x180006a06`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006bdb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006da5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006bdb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180006da5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b56`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b60`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b92`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b9c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b56`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b60`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b92`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006b9c`

## string_xrefs

- `0x180006b23`: `StringCchCopyN failed: 0x%x in %s`
- `0x180006c18`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180006bfc`: `LookupAccountSid failed: 0x%x`
- `0x180006c7d`: `Impersonate.StopImpersonating failed: 0x%x in %s`
- `0x180006d5f`: `CImpersonate::ImpersonateUser`
- `0x180006d15`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x180006d2e`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x180006d44`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

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
0x1800067f0  mov     [rsp-38h+arg_0], rbx
0x1800067f5  push    rbp
0x1800067f6  push    rsi
0x1800067f7  push    rdi
0x1800067f8  push    r12
0x1800067fa  push    r13
0x1800067fc  push    r14
0x1800067fe  push    r15
0x180006800  mov     rbp, rsp
0x180006803  sub     rsp, 60h
0x180006807  xor     r12d, r12d
0x18000680a  mov     [rbp+arg_10], 0
0x180006810  mov     [rbp+UserName], r12
0x180006814  mov     edi, r12d
0x180006817  mov     [rbp+DomainName], r12
0x18000681b  mov     esi, r12d
0x18000681e  mov     [rbp+var_30], r12d
0x180006822  mov     r14, rdx
0x180006825  mov     [rbp+TokenHandle], r12
0x180006829  mov     r13, rcx
0x18000682c  mov     [rbp+TokenInformationLength], r12d
0x180006830  xor     r15b, r15b
0x180006833  mov     [rbp+cchName], 101h
0x18000683a  mov     [rbp+cchReferencedDomainName], 100h
0x180006841  call    cs:__imp_GetCurrentThread
0x180006847  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000684b  mov     edx, 0Eh; DesiredAccess
0x180006850  mov     rcx, rax; ThreadHandle
0x180006853  mov     r8d, 1; OpenAsSelf
0x180006859  call    cs:__imp_OpenThreadToken
0x18000685f  test    eax, eax
0x180006861  jz      loc_18000697E
0x180006867  mov     ebx, 55Fh
0x18000686c  test    r14, r14
0x18000686f  jz      loc_180006986
0x180006875  lea     rax, [rbp+TokenInformationLength]
0x180006879  mov     [rbp+TokenInformationLength], r12d
0x18000687d  xor     r9d, r9d; TokenInformationLength
0x180006880  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006885  xor     r8d, r8d; TokenInformation
0x180006888  mov     edx, 1; TokenInformationClass
0x18000688d  mov     rcx, r14; TokenHandle
0x180006890  call    cs:__imp_GetTokenInformation
0x180006896  test    eax, eax
0x180006898  jnz     short loc_1800068AB
0x18000689a  call    cs:__imp_GetLastError
0x1800068a0  mov     ebx, eax
0x1800068a2  cmp     eax, 7Ah ; 'z'
0x1800068a5  jnz     loc_180006D12
0x1800068ab  mov     ebx, [rbp+TokenInformationLength]
0x1800068ae  mov     ecx, 40h ; '@'; uFlags
0x1800068b3  mov     edx, ebx; uBytes
0x1800068b5  call    cs:__imp_LocalAlloc
0x1800068bb  mov     rdi, rax
0x1800068be  test    rax, rax
0x1800068c1  jz      loc_180006C5A
0x1800068c7  lea     rax, [rbp+TokenInformationLength]
0x1800068cb  mov     r9d, ebx; TokenInformationLength
0x1800068ce  mov     r8, rdi; TokenInformation
0x1800068d1  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800068d6  mov     edx, 1; TokenInformationClass
0x1800068db  mov     rcx, r14; TokenHandle
0x1800068de  call    cs:__imp_GetTokenInformation
0x1800068e4  test    eax, eax
0x1800068e6  jz      loc_180006C12
0x1800068ec  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800068f0  lea     rax, [rbp+TokenInformationLength]
0x1800068f4  xor     r9d, r9d; TokenInformationLength
0x1800068f7  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800068fc  xor     r8d, r8d; TokenInformation
0x1800068ff  mov     [rbp+TokenInformationLength], r12d
0x180006903  mov     edx, 1; TokenInformationClass
0x180006908  call    cs:__imp_GetTokenInformation
0x18000690e  test    eax, eax
0x180006910  jnz     short loc_180006923
0x180006912  call    cs:__imp_GetLastError
0x180006918  mov     ebx, eax
0x18000691a  cmp     eax, 7Ah ; 'z'
0x18000691d  jnz     loc_180006D2B
0x180006923  mov     ebx, [rbp+TokenInformationLength]
0x180006926  mov     ecx, 40h ; '@'; uFlags
0x18000692b  mov     edx, ebx; uBytes
0x18000692d  call    cs:__imp_LocalAlloc
0x180006933  mov     rsi, rax
0x180006936  test    rax, rax
0x180006939  jz      loc_180006C5A
0x18000693f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180006943  lea     rax, [rbp+TokenInformationLength]
0x180006947  mov     r9d, ebx; TokenInformationLength
0x18000694a  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000694f  mov     r8, rsi; TokenInformation
0x180006952  mov     edx, 1; TokenInformationClass
0x180006957  call    cs:__imp_GetTokenInformation
0x18000695d  test    eax, eax
0x18000695f  jz      loc_180006C12
0x180006965  mov     rdx, [rsi]; Sid2
0x180006968  mov     rcx, [rdi]; Sid1
0x18000696b  call    cs:__imp_RtlEqualSid
0x180006971  test    al, al
0x180006973  jz      loc_180006D44
0x180006979  mov     ebx, r12d
0x18000697c  jmp     short loc_180006986
0x18000697e  call    cs:__imp_GetLastError
0x180006984  mov     ebx, eax
0x180006986  mov     rcx, [rbp+TokenHandle]; hObject
0x18000698a  test    rcx, rcx
0x18000698d  jz      short loc_180006995
0x18000698f  call    cs:__imp_CloseHandle
0x180006995  test    rdi, rdi
0x180006998  jz      short loc_1800069A3
0x18000699a  mov     rcx, rdi; hMem
0x18000699d  call    cs:__imp_LocalFree
0x1800069a3  test    rsi, rsi
0x1800069a6  jz      short loc_1800069B1
0x1800069a8  mov     rcx, rsi; hMem
0x1800069ab  call    cs:__imp_LocalFree
0x1800069b1  test    ebx, ebx
0x1800069b3  jg      loc_180006C33
0x1800069b9  jns     short loc_1800069F1
0x1800069bb  cmp     ebx, 800703F0h
0x1800069c1  mov     r8d, r12d
0x1800069c4  cmovnz  r8d, ebx
0x1800069c8  test    r8d, r8d
0x1800069cb  js      loc_180006D5F
0x1800069d1  mov     rcx, r14; hToken
0x1800069d4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800069da  test    eax, eax
0x1800069dc  jz      loc_180006CB9
0x1800069e2  mov     r15b, 1
0x1800069e5  mov     byte ptr [rbp+arg_10], r15b
0x1800069e9  jmp     short loc_1800069F1
0x1800069eb  js      loc_180006D77
0x1800069f1  call    IsLsaGetUserNamePresent
0x1800069f6  test    al, al
0x1800069f8  jz      loc_180006BA4
0x1800069fe  lea     rdx, [rbp+DomainName]; DomainName
0x180006a02  lea     rcx, [rbp+UserName]; UserName
0x180006a06  call    cs:__imp_LsaGetUserName
0x180006a0c  test    eax, eax
0x180006a0e  jnz     loc_180006BA4
0x180006a14  mov     rax, [rbp+UserName]
0x180006a18  test    rax, rax
0x180006a1b  jz      loc_180006BA4
0x180006a21  mov     r8, [rax+8]
0x180006a25  test    r8, r8
0x180006a28  jz      loc_180006BA4
0x180006a2e  mov     r10, [rbp+DomainName]
0x180006a32  test    r10, r10
0x180006a35  jz      loc_180006BA4
0x180006a3b  cmp     [r10+8], r12
0x180006a3f  jz      loc_180006BA4
0x180006a45  mov     edx, [rbp+cchName]
0x180006a48  lea     r9, [r13+850h]
0x180006a4f  test    rdx, rdx
0x180006a52  jz      loc_180006C89
0x180006a58  cmp     rdx, 7FFFFFFFh
0x180006a5f  ja      loc_180006DC7
0x180006a65  movzx   ecx, word ptr [rax]
0x180006a68  shr     rcx, 1
0x180006a6b  nop     dword ptr [rax+rax+00h]
0x180006a70  test    rcx, rcx
0x180006a73  jz      short loc_180006A93
0x180006a75  movzx   eax, word ptr [r8]
0x180006a79  test    ax, ax
0x180006a7c  jz      short loc_180006A93
0x180006a7e  mov     [r9], ax
0x180006a82  add     r8, 2
0x180006a86  add     r9, 2
0x180006a8a  dec     rcx
0x180006a8d  sub     rdx, 1
0x180006a91  jnz     short loc_180006A70
0x180006a93  test    rdx, rdx
0x180006a96  lea     rcx, [r9-2]
0x180006a9a  mov     r11d, 8007007Ah
0x180006aa0  cmovnz  rcx, r9
0x180006aa4  mov     ebx, r11d
0x180006aa7  cmovnz  ebx, r12d
0x180006aab  mov     [rcx], r12w
0x180006aaf  jz      loc_180006C97
0x180006ab5  mov     eax, [rbp+cchReferencedDomainName]
0x180006ab8  lea     r8, [r13+650h]
0x180006abf  test    rax, rax
0x180006ac2  jz      loc_180006C9F
0x180006ac8  cmp     rax, 7FFFFFFFh
0x180006ace  ja      loc_180006DD1
0x180006ad4  mov     rcx, [rbp+DomainName]
0x180006ad8  mov     r9, [r10+8]
0x180006adc  movzx   edx, word ptr [rcx]
0x180006adf  shr     rdx, 1
0x180006ae2  test    rdx, rdx
0x180006ae5  jz      short loc_180006B05
0x180006ae7  movzx   ecx, word ptr [r9]
0x180006aeb  test    cx, cx
0x180006aee  jz      short loc_180006B05
0x180006af0  mov     [r8], cx
0x180006af4  add     r9, 2
0x180006af8  add     r8, 2
0x180006afc  dec     rdx
0x180006aff  sub     rax, 1
0x180006b03  jnz     short loc_180006AE2
0x180006b05  test    rax, rax
0x180006b08  lea     rdx, [r8-2]
0x180006b0c  cmovnz  rdx, r8
0x180006b10  cmovnz  r11d, r12d
0x180006b14  mov     [rdx], r12w
0x180006b18  mov     ebx, r11d
0x180006b1b  test    r11d, r11d
0x180006b1e  jns     short loc_180006B3B
0x180006b20  mov     r8d, r11d
0x180006b23  lea     rdx, aStringcchcopyn; "StringCchCopyN failed: 0x%x in %s"
0x180006b2a  lea     r9, aCusernameResol; "CUserName::ResolveUserName"
0x180006b31  mov     ecx, 8; int
0x180006b36  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006b3b  mov     rax, [rbp+UserName]
0x180006b3f  test    rax, rax
0x180006b42  jnz     short loc_180006B89
0x180006b44  mov     r10, [rbp+DomainName]
0x180006b48  test    r10, r10
0x180006b4b  jz      short loc_180006B66
0x180006b4d  mov     rcx, [r10+8]; Buffer
0x180006b51  test    rcx, rcx
0x180006b54  jz      short loc_180006B5C
0x180006b56  call    cs:__imp_LsaFreeMemory
0x180006b5c  mov     rcx, [rbp+DomainName]; Buffer
0x180006b60  call    cs:__imp_LsaFreeMemory
0x180006b66  lea     rcx, [rbp+arg_10]; this
0x180006b6a  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180006b6f  mov     eax, ebx
0x180006b71  mov     rbx, [rsp+60h+arg_0]
0x180006b79  add     rsp, 60h
0x180006b7d  pop     r15
0x180006b7f  pop     r14
0x180006b81  pop     r13
0x180006b83  pop     r12
0x180006b85  pop     rdi
0x180006b86  pop     rsi
0x180006b87  pop     rbp
0x180006b88  retn
0x180006b89  mov     rcx, [rax+8]; Buffer
0x180006b8d  test    rcx, rcx
0x180006b90  jz      short loc_180006B98
0x180006b92  call    cs:__imp_LsaFreeMemory
0x180006b98  mov     rcx, [rbp+UserName]; Buffer
0x180006b9c  call    cs:__imp_LsaFreeMemory
0x180006ba2  jmp     short loc_180006B44
0x180006ba4  test    r15b, r15b
0x180006ba7  jnz     loc_180006C43
0x180006bad  mov     rcx, [r13+648h]
0x180006bb4  lea     rax, [rbp+var_30]
0x180006bb8  mov     [rsp+60h+peUse], rax; peUse
0x180006bbd  lea     r9, [r13+650h]; ReferencedDomainName
0x180006bc4  lea     rax, [rbp+cchReferencedDomainName]
0x180006bc8  lea     rdx, [r13+850h]; Name
0x180006bcf  mov     [rsp+60h+ReturnLength], rax; cchReferencedDomainName
0x180006bd4  mov     rcx, [rcx]; Sid
0x180006bd7  lea     r8, [rbp+cchName]; cchName
0x180006bdb  call    cs:__imp_LookupAccountSidLocalW
0x180006be1  test    eax, eax
0x180006be3  jnz     loc_180006DDE
0x180006be9  call    cs:__imp_GetLastError
0x180006bef  mov     ebx, eax
0x180006bf1  test    eax, eax
0x180006bf3  jg      loc_180006CE6
0x180006bf9  mov     r8d, ebx
0x180006bfc  lea     rdx, aLookupaccounts_0; "LookupAccountSid failed: 0x%x"
0x180006c03  mov     ecx, 8; int
0x180006c08  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006c0d  jmp     loc_180006B3B
0x180006c12  call    cs:__imp_GetLastError
0x180006c18  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x180006c1f  mov     ecx, 8; int
0x180006c24  mov     r8d, eax
0x180006c27  mov     ebx, eax
0x180006c29  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006c2e  jmp     loc_180006986
0x180006c33  movzx   ebx, bx
0x180006c36  or      ebx, 80070000h
0x180006c3c  test    ebx, ebx
0x180006c3e  jmp     loc_1800069B9
0x180006c43  call    cs:__imp_RevertToSelf
0x180006c49  test    eax, eax
0x180006c4b  jz      loc_180006CF4
0x180006c51  mov     byte ptr [rbp+arg_10], r12b
0x180006c55  jmp     loc_180006BAD
0x180006c5a  mov     ebx, 8
0x180006c5f  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x180006c66  mov     ecx, ebx; int
0x180006c68  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006c6d  jmp     loc_180006986
0x180006c72  test    ebx, ebx
0x180006c74  jns     loc_180006BAD
0x180006c7a  mov     r8d, ebx
0x180006c7d  lea     rdx, aImpersonateSto; "Impersonate.StopImpersonating failed: 0"...
0x180006c84  jmp     loc_180006B2A
0x180006c89  mov     ebx, 80070057h
0x180006c8e  test    rdx, rdx
0x180006c91  jz      short loc_180006C97
0x180006c93  mov     [r9], r12w
0x180006c97  mov     r8d, ebx
0x180006c9a  jmp     loc_180006B23
  ... truncated ...
```
