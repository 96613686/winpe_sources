# NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)

- ea: `0x1800ce554`
- end: `0x1800ce7da`
- name: `?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z`
- size: `646`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d1f8`

## callees

- `0x180014dd4`
- `0x180046650`
- `0x180047330`
- `0x1800ce554`
- `0x1800cebec`
- `0x1800ced58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce74e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ce793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ce793`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce5bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce5a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce744`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce76c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce744`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce76c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ce66c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ce66c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce5ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce5ff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ce676`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ce676`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce6b5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce6b5`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800ce70a`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800ce70a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800ce620`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800ce620`
- `KERNELBASE!GetIsEdpEnabled` at `0x1800ce62d`
- `KERNELBASE!GetIsEdpEnabled` at `0x1800ce62d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(NSecurityLibrary *this, void **a2, int *a3)
{
  unsigned int v5; // edi
  HANDLE CurrentThread; // rax
  void *v7; // rcx
  DWORD LastError; // ebx
  int IsEdpEnabled; // eax
  int v10; // esi
  void *v11; // rcx
  void *v12; // rdx
  HANDLE v13; // rcx
  HANDLE v14; // rcx
  void *v15; // rdx
  HANDLE v16; // rcx
  void *v17; // rdx
  __int64 v18; // rax
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-C8h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE *TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h]
  _BYTE pSid[80]; // [rsp+B0h] [rbp-50h] BYREF

  TokenHandle = (void *)-1LL;
  Token = (HANDLE)-1LL;
  TokenInformationLength = 88;
  v5 = 0;
  *(_QWORD *)this = 0;
  *(_DWORD *)a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    goto LABEL_42;
  memset_0(&TokenInformation, 0, 0x58u);
  v7 = TokenHandle;
  if ( TokenHandle == (void *)-1LL )
    v7 = 0;
  if ( !GetTokenInformation(v7, TokenIntegrityLevel, &TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_5;
  if ( IsWellKnownSid(TokenInformation, WinLowLabelSid) )
    *(_DWORD *)a2 = 1;
  IsEdpEnabled = GetIsEdpEnabled();
  v10 = IsEdpEnabled;
  if ( !*(_DWORD *)a2 && !IsEdpEnabled )
    goto LABEL_28;
  v11 = TokenHandle;
  if ( TokenHandle == (void *)-1LL )
    v11 = 0;
  if ( DuplicateTokenEx(v11, 0x8Eu, 0, SecurityImpersonation, TokenImpersonation, &Token) && RevertToSelf() )
  {
    if ( v10 )
    {
      v13 = Token;
      if ( Token == (HANDLE)-1LL )
        v13 = 0;
      NSecurityLibrary::SetTokenEnterpriseExempt(v13, v12);
    }
    if ( *(_DWORD *)a2 )
    {
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinMediumLabelSid, 0, pSid, cbSid) )
        goto LABEL_20;
      memset_0(&TokenInformation, 0, 0x58u);
      TokenInformation = pSid;
      v25 = 96;
      v14 = Token;
      if ( Token == (HANDLE)-1LL )
        v14 = 0;
      if ( !SetTokenInformation(v14, TokenIntegrityLevel, &TokenInformation, 0x58u) )
        goto LABEL_20;
      v16 = Token;
      if ( Token == (HANDLE)-1LL )
        v16 = 0;
      if ( !(unsigned int)NSecurityLibrary::RemoveModernAttributes(v16, v15) )
      {
LABEL_20:
        LastError = GetLastError();
LABEL_33:
        v17 = TokenHandle;
        if ( TokenHandle == (void *)-1LL )
          v17 = 0;
        SetThreadToken(0, v17);
        goto LABEL_36;
      }
    }
    v10 = 1;
LABEL_28:
    v5 = 1;
    LastError = 0;
    if ( Token != (HANDLE)-1LL && Token )
    {
      if ( SetThreadToken(0, Token) )
        goto LABEL_36;
      LastError = GetLastError();
      v5 = 0;
    }
    if ( v10 )
      goto LABEL_33;
LABEL_36:
    if ( v5 )
    {
      v18 = -1;
      if ( TokenHandle != (void *)-1LL )
      {
        v18 = (__int64)TokenHandle;
        TokenHandle = (void *)-1LL;
      }
      *(_QWORD *)this = v18;
    }
    goto LABEL_40;
  }
LABEL_5:
  LastError = GetLastError();
LABEL_40:
  if ( LastError )
    SetLastError(LastError);
LABEL_42:
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&Token);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800ce554  mov     [rsp-8+arg_10], rbx
0x1800ce559  mov     [rsp-8+arg_18], rsi
0x1800ce55e  push    rbp
0x1800ce55f  push    rdi
0x1800ce560  push    r12
0x1800ce562  push    r13
0x1800ce564  push    r14
0x1800ce566  lea     rbp, [rsp-10h]
0x1800ce56b  sub     rsp, 110h
0x1800ce572  mov     rax, cs:__security_cookie
0x1800ce579  xor     rax, rsp
0x1800ce57c  mov     [rbp+30h+var_30], rax
0x1800ce580  mov     rbx, rdx
0x1800ce583  mov     r14, rcx
0x1800ce586  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800ce58a  mov     [rsp+130h+TokenHandle], r12
0x1800ce58f  mov     [rsp+130h+Token], r12
0x1800ce594  lea     esi, [r12+59h]
0x1800ce599  mov     [rsp+130h+TokenInformationLength], esi
0x1800ce59d  xor     edi, edi
0x1800ce59f  mov     [rcx], rdi
0x1800ce5a2  mov     [rdx], edi
0x1800ce5a4  call    cs:__imp_GetCurrentThread
0x1800ce5aa  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x1800ce5af  lea     r13d, [r12+2]
0x1800ce5b4  mov     r8d, r13d; OpenAsSelf
0x1800ce5b7  lea     edx, [rsi-4Ah]; DesiredAccess
0x1800ce5ba  mov     rcx, rax; ThreadHandle
0x1800ce5bd  call    cs:__imp_OpenThreadToken
0x1800ce5c3  test    eax, eax
0x1800ce5c5  jz      loc_1800CE79A
0x1800ce5cb  mov     r8d, esi; Size
0x1800ce5ce  xor     edx, edx; Val
0x1800ce5d0  lea     rcx, [rsp+130h+TokenInformation]; void *
0x1800ce5d5  call    memset_0
0x1800ce5da  mov     rcx, [rsp+130h+TokenHandle]
0x1800ce5df  xor     eax, eax
0x1800ce5e1  cmp     rcx, r12
0x1800ce5e4  cmovz   rcx, rax; TokenHandle
0x1800ce5e8  lea     rax, [rsp+130h+TokenInformationLength]
0x1800ce5ed  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x1800ce5f2  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x1800ce5f7  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x1800ce5fc  lea     edx, [rsi-3Fh]; TokenInformationClass
0x1800ce5ff  call    cs:__imp_GetTokenInformation
0x1800ce605  test    eax, eax
0x1800ce607  jnz     short loc_1800CE616
0x1800ce609  call    cs:__imp_GetLastError
0x1800ce60f  mov     ebx, eax
0x1800ce611  jmp     loc_1800CE78D
0x1800ce616  mov     edx, 42h ; 'B'; WellKnownSidType
0x1800ce61b  mov     rcx, [rsp+130h+TokenInformation]; pSid
0x1800ce620  call    cs:__imp_IsWellKnownSid
0x1800ce626  test    eax, eax
0x1800ce628  jz      short loc_1800CE62D
0x1800ce62a  mov     [rbx], r13d
0x1800ce62d  call    cs:__imp_GetIsEdpEnabled
0x1800ce633  mov     esi, eax
0x1800ce635  cmp     [rbx], edi
0x1800ce637  jnz     short loc_1800CE641
0x1800ce639  test    eax, eax
0x1800ce63b  jz      loc_1800CE72E
0x1800ce641  mov     rcx, [rsp+130h+TokenHandle]
0x1800ce646  xor     eax, eax
0x1800ce648  cmp     rcx, r12
0x1800ce64b  cmovz   rcx, rax; hExistingToken
0x1800ce64f  lea     rax, [rsp+130h+Token]
0x1800ce654  mov     [rsp+130h+phNewToken], rax; phNewToken
0x1800ce659  mov     r9d, 2; ImpersonationLevel
0x1800ce65f  mov     dword ptr [rsp+130h+ReturnLength], r9d; TokenType
0x1800ce664  xor     r8d, r8d; lpTokenAttributes
0x1800ce667  mov     edx, 8Eh; dwDesiredAccess
0x1800ce66c  call    cs:__imp_DuplicateTokenEx
0x1800ce672  test    eax, eax
0x1800ce674  jz      short loc_1800CE609
0x1800ce676  call    cs:__imp_RevertToSelf
0x1800ce67c  test    eax, eax
0x1800ce67e  jz      short loc_1800CE609
0x1800ce680  test    esi, esi
0x1800ce682  jz      short loc_1800CE697
0x1800ce684  mov     rcx, [rsp+130h+Token]
0x1800ce689  xor     eax, eax
0x1800ce68b  cmp     rcx, r12
0x1800ce68e  cmovz   rcx, rax; TokenHandle
0x1800ce692  call    ?SetTokenEnterpriseExempt@NSecurityLibrary@@YAXPEAX@Z; NSecurityLibrary::SetTokenEnterpriseExempt(void *)
0x1800ce697  cmp     [rbx], edi
0x1800ce699  jz      loc_1800CE72B
0x1800ce69f  mov     [rsp+130h+cbSid], 44h ; 'D'
0x1800ce6a7  lea     r9, [rsp+130h+cbSid]; cbSid
0x1800ce6ac  lea     r8, [rbp+30h+pSid]; pSid
0x1800ce6b0  xor     edx, edx; DomainSid
0x1800ce6b2  lea     ecx, [rdx+43h]; WellKnownSidType
0x1800ce6b5  call    cs:__imp_CreateWellKnownSid
0x1800ce6bb  test    eax, eax
0x1800ce6bd  jnz     short loc_1800CE6CC
0x1800ce6bf  call    cs:__imp_GetLastError
0x1800ce6c5  mov     ebx, eax
0x1800ce6c7  jmp     loc_1800CE75C
0x1800ce6cc  mov     ebx, 58h ; 'X'
0x1800ce6d1  mov     r8d, ebx; Size
0x1800ce6d4  xor     edx, edx; Val
0x1800ce6d6  lea     rcx, [rsp+130h+TokenInformation]; void *
0x1800ce6db  call    memset_0
0x1800ce6e0  lea     rax, [rbp+30h+pSid]
0x1800ce6e4  mov     [rsp+130h+TokenInformation], rax
0x1800ce6e9  mov     [rsp+130h+var_D8], 60h ; '`'
0x1800ce6f1  mov     rcx, [rsp+130h+Token]
0x1800ce6f6  xor     eax, eax
0x1800ce6f8  cmp     rcx, r12
0x1800ce6fb  cmovz   rcx, rax; TokenHandle
0x1800ce6ff  mov     r9d, ebx; TokenInformationLength
0x1800ce702  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x1800ce707  lea     edx, [rbx-3Fh]; TokenInformationClass
0x1800ce70a  call    cs:__imp_SetTokenInformation
0x1800ce710  test    eax, eax
0x1800ce712  jz      short loc_1800CE6BF
0x1800ce714  mov     rcx, [rsp+130h+Token]
0x1800ce719  xor     eax, eax
0x1800ce71b  cmp     rcx, r12
0x1800ce71e  cmovz   rcx, rax; TokenHandle
0x1800ce722  call    ?RemoveModernAttributes@NSecurityLibrary@@YAHPEAX@Z; NSecurityLibrary::RemoveModernAttributes(void *)
0x1800ce727  test    eax, eax
0x1800ce729  jz      short loc_1800CE6BF
0x1800ce72b  mov     esi, r13d
0x1800ce72e  mov     edi, r13d
0x1800ce731  xor     ebx, ebx
0x1800ce733  mov     rdx, [rsp+130h+Token]; Token
0x1800ce738  cmp     rdx, r12
0x1800ce73b  jz      short loc_1800CE758
0x1800ce73d  test    rdx, rdx
0x1800ce740  jz      short loc_1800CE758
0x1800ce742  xor     ecx, ecx; Thread
0x1800ce744  call    cs:__imp_SetThreadToken
0x1800ce74a  test    eax, eax
0x1800ce74c  jnz     short loc_1800CE772
0x1800ce74e  call    cs:__imp_GetLastError
0x1800ce754  mov     ebx, eax
0x1800ce756  xor     edi, edi
0x1800ce758  test    esi, esi
0x1800ce75a  jz      short loc_1800CE772
0x1800ce75c  mov     rdx, [rsp+130h+TokenHandle]
0x1800ce761  xor     eax, eax
0x1800ce763  cmp     rdx, r12
0x1800ce766  cmovz   rdx, rax; Token
0x1800ce76a  xor     ecx, ecx; Thread
0x1800ce76c  call    cs:__imp_SetThreadToken
0x1800ce772  test    edi, edi
0x1800ce774  jz      short loc_1800CE78D
0x1800ce776  mov     rax, r12
0x1800ce779  cmp     [rsp+130h+TokenHandle], r12
0x1800ce77e  jz      short loc_1800CE78A
0x1800ce780  mov     rax, [rsp+130h+TokenHandle]
0x1800ce785  mov     [rsp+130h+TokenHandle], r12
0x1800ce78a  mov     [r14], rax
0x1800ce78d  test    ebx, ebx
0x1800ce78f  jz      short loc_1800CE79A
0x1800ce791  mov     ecx, ebx; dwErrCode
0x1800ce793  call    cs:__imp_SetLastError
0x1800ce799  nop
0x1800ce79a  lea     rcx, [rsp+130h+Token]
0x1800ce79f  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800ce7a4  nop
0x1800ce7a5  lea     rcx, [rsp+130h+TokenHandle]
0x1800ce7aa  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800ce7af  nop
0x1800ce7b0  mov     eax, edi
0x1800ce7b2  mov     rcx, [rbp+30h+var_30]
0x1800ce7b6  xor     rcx, rsp; StackCookie
0x1800ce7b9  call    __security_check_cookie
0x1800ce7be  lea     r11, [rsp+130h+var_20]
0x1800ce7c6  mov     rbx, [r11+40h]
0x1800ce7ca  mov     rsi, [r11+48h]
0x1800ce7ce  mov     rsp, r11
0x1800ce7d1  pop     r14
0x1800ce7d3  pop     r13
0x1800ce7d5  pop     r12
0x1800ce7d7  pop     rdi
0x1800ce7d8  pop     rbp
0x1800ce7d9  retn
```
