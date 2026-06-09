# EapMsChapv2DecryptPassword

- ea: `0x180069300`
- end: `0x18006974f`
- name: `EapMsChapv2DecryptPassword`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068b08`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180038e4c`
- `0x180038e64`
- `0x180069300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006945d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006950e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006957c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006945d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800694ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006950e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006957c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800695ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696ef`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006956c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006956c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800696a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800696a0`
- `CRYPT32!CryptUnprotectData` at `0x18006964d`
- `CRYPT32!CryptUnprotectData` at `0x18006964d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006944d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800696db`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006944d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800696db`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006949b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800695df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800696b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006949b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800695df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800696b4`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800693e4`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800693e4`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800694fe`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800694fe`

## pseudocode

```c
__int64 __fastcall EapMsChapv2DecryptPassword(__int64 a1, void *a2)
{
  DWORD v4; // ebx
  int v5; // r15d
  int v6; // r12d
  DWORD v7; // ecx
  DWORD v8; // eax
  struct _EAPTLS_CONTROL_BLOCK *v9; // rcx
  __int64 v10; // rdx
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchMaxChars; // [rsp+44h] [rbp-BCh] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszCredentials[264]; // [rsp+70h] [rbp-90h] BYREF

  v4 = 0;
  pProtectionType = CredUnprotected;
  v5 = 0;
  v6 = 0;
  memset_0(pszCredentials, 0, 0x202u);
  v7 = *(_DWORD *)(a1 + 784);
  pcchMaxChars = 256;
  pDataIn = 0;
  pDataOut = 0;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids);
    goto LABEL_40;
  }
  if ( (*(_DWORD *)(a1 + 4) & 0x200) == 0 )
  {
    pDataIn.cbData = v7;
    pDataIn.pbData = (BYTE *)(a1 + 788);
    if ( !NtCurrentTeb()->IsImpersonating && a2 )
    {
      if ( !ImpersonateLoggedOnUser(a2) )
      {
        LastError = GetLastError();
        v4 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_40;
        v13 = 22;
        goto LABEL_34;
      }
      v5 = 1;
    }
    if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
    {
      memcpy_0((void *)(a1 + 269), pDataOut.pbData, pDataOut.cbData);
      goto LABEL_40;
    }
    LastError = GetLastError();
    v4 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v13 = 23;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, LastError);
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids);
  if ( !CredIsProtectedW((LPWSTR)(a1 + 788), &pProtectionType) )
  {
    v8 = GetLastError();
    v4 = v8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v10 = 17;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v8);
    goto LABEL_40;
  }
  if ( NtCurrentTeb()->IsImpersonating )
  {
    if ( pProtectionType == CredTrustedProtection )
    {
      if ( !RevertToSelf() )
      {
        v8 = GetLastError();
        v4 = v8;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_40;
        v10 = 18;
        goto LABEL_10;
      }
      v6 = 1;
    }
  }
  else if ( pProtectionType == CredUserProtection )
  {
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      v8 = GetLastError();
      v4 = v8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_40;
      v10 = 19;
      goto LABEL_10;
    }
    v5 = 1;
  }
  if ( !CredUnprotectW(0, (LPWSTR)(a1 + 788), *(_DWORD *)(a1 + 784) >> 1, pszCredentials, &pcchMaxChars) )
  {
    v8 = GetLastError();
    v4 = v8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v10 = 20;
    goto LABEL_10;
  }
  if ( WideCharToMultiByte(0, 0x400u, pszCredentials, pcchMaxChars, (LPSTR)(a1 + 269), 256, 0, 0) > 0 )
  {
    *(_DWORD *)(a1 + 4) &= ~0x200u;
    *(_DWORD *)(a1 + 784) = 0;
    goto LABEL_40;
  }
  v8 = GetLastError();
  v4 = v8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v10 = 21;
    goto LABEL_10;
  }
LABEL_40:
  LocalFree(pDataOut.pbData);
  if ( v6 && !ImpersonateLoggedOnUser(a2) && !v4 )
    v4 = GetLastError();
  if ( v5 && !RevertToSelf() && !v4 )
    v4 = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180069300  mov     [rsp-8+arg_10], rbx
0x180069305  mov     [rsp-8+arg_18], rsi
0x18006930a  push    rbp
0x18006930b  push    rdi
0x18006930c  push    r12
0x18006930e  push    r14
0x180069310  push    r15
0x180069312  lea     rbp, [rsp-190h]
0x18006931a  sub     rsp, 290h
0x180069321  mov     rax, cs:__security_cookie
0x180069328  xor     rax, rsp
0x18006932b  mov     [rbp+1B0h+var_30], rax
0x180069332  mov     r14, rdx
0x180069335  mov     rdi, rcx
0x180069338  xor     ebx, ebx
0x18006933a  lea     rcx, [rsp+2B0h+pszCredentials]; void *
0x18006933f  xor     edx, edx; Val
0x180069341  mov     [rsp+2B0h+pProtectionType], ebx
0x180069345  mov     r8d, 202h; Size
0x18006934b  xor     r15d, r15d
0x18006934e  xor     r12d, r12d
0x180069351  call    memset_0
0x180069356  mov     ecx, [rdi+310h]
0x18006935c  lea     rsi, WPP_GLOBAL_Control
0x180069363  mov     [rsp+2B0h+var_26C], 100h
0x18006936b  xorps   xmm0, xmm0
0x18006936e  xorps   xmm1, xmm1
0x180069371  movups  xmmword ptr [rsp+2B0h+pDataIn.cbData], xmm0
0x180069376  movups  xmmword ptr [rsp+2B0h+pDataOut.cbData], xmm1
0x18006937b  test    ecx, ecx
0x18006937d  jnz     short loc_1800693A7
0x18006937f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069386  cmp     rcx, rsi
0x180069389  jz      loc_180069694
0x18006938f  mov     rcx, [rcx+10h]
0x180069393  lea     edx, [rbx+0Fh]
0x180069396  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x18006939d  call    WPP_SF_
0x1800693a2  jmp     loc_180069694
0x1800693a7  test    dword ptr [rdi+4], 200h
0x1800693ae  jz      loc_1800695BB
0x1800693b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800693bb  cmp     rcx, rsi
0x1800693be  jz      short loc_1800693D5
0x1800693c0  mov     rcx, [rcx+10h]
0x1800693c4  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x1800693cb  mov     edx, 10h
0x1800693d0  call    WPP_SF_
0x1800693d5  lea     rsi, [rdi+314h]
0x1800693dc  mov     rcx, rsi; pszProtectedCredentials
0x1800693df  lea     rdx, [rsp+2B0h+pProtectionType]; pProtectionType
0x1800693e4  call    cs:__imp_CredIsProtectedW
0x1800693eb  nop     dword ptr [rax+rax+00h]
0x1800693f0  test    eax, eax
0x1800693f2  jnz     short loc_180069436
0x1800693f4  call    cs:__imp_GetLastError
0x1800693fb  nop     dword ptr [rax+rax+00h]
0x180069400  mov     ebx, eax
0x180069402  mov     rcx, cs:WPP_GLOBAL_Control
0x180069409  lea     rdi, WPP_GLOBAL_Control
0x180069410  cmp     rcx, rdi
0x180069413  jz      loc_18006969B
0x180069419  mov     edx, 11h
0x18006941e  mov     rcx, [rcx+10h]
0x180069422  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180069429  mov     r9d, eax
0x18006942c  call    WPP_SF_d
0x180069431  jmp     loc_18006969B
0x180069436  mov     eax, gs:179Ch
0x18006943e  test    eax, eax
0x180069440  jz      short loc_180069491
0x180069442  cmp     [rsp+2B0h+pProtectionType], 2
0x180069447  jnz     loc_1800694E0
0x18006944d  call    cs:__imp_RevertToSelf
0x180069454  nop     dword ptr [rax+rax+00h]
0x180069459  test    eax, eax
0x18006945b  jnz     short loc_180069489
0x18006945d  call    cs:__imp_GetLastError
0x180069464  nop     dword ptr [rax+rax+00h]
0x180069469  mov     ebx, eax
0x18006946b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069472  lea     rdi, WPP_GLOBAL_Control
0x180069479  cmp     rcx, rdi
0x18006947c  jz      loc_18006969B
0x180069482  mov     edx, 12h
0x180069487  jmp     short loc_18006941E
0x180069489  mov     r12d, 1
0x18006948f  jmp     short loc_1800694E0
0x180069491  cmp     [rsp+2B0h+pProtectionType], 1
0x180069496  jnz     short loc_1800694E0
0x180069498  mov     rcx, r14; hToken
0x18006949b  call    cs:__imp_ImpersonateLoggedOnUser
0x1800694a2  nop     dword ptr [rax+rax+00h]
0x1800694a7  test    eax, eax
0x1800694a9  jnz     short loc_1800694DA
0x1800694ab  call    cs:__imp_GetLastError
0x1800694b2  nop     dword ptr [rax+rax+00h]
0x1800694b7  mov     ebx, eax
0x1800694b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800694c0  lea     rdi, WPP_GLOBAL_Control
0x1800694c7  cmp     rcx, rdi
0x1800694ca  jz      loc_18006969B
0x1800694d0  mov     edx, 13h
0x1800694d5  jmp     loc_18006941E
0x1800694da  mov     r15d, 1
0x1800694e0  mov     r8d, [rdi+310h]
0x1800694e7  lea     rax, [rsp+2B0h+var_26C]
0x1800694ec  shr     r8d, 1; cchProtectedCredentials
0x1800694ef  lea     r9, [rsp+2B0h+pszCredentials]; pszCredentials
0x1800694f4  mov     rdx, rsi; pszProtectedCredentials
0x1800694f7  mov     [rsp+2B0h+pcchMaxChars], rax; pcchMaxChars
0x1800694fc  xor     ecx, ecx; fAsSelf
0x1800694fe  call    cs:__imp_CredUnprotectW
0x180069505  nop     dword ptr [rax+rax+00h]
0x18006950a  test    eax, eax
0x18006950c  jnz     short loc_18006953D
0x18006950e  call    cs:__imp_GetLastError
0x180069515  nop     dword ptr [rax+rax+00h]
0x18006951a  mov     ebx, eax
0x18006951c  mov     rcx, cs:WPP_GLOBAL_Control
0x180069523  lea     rdi, WPP_GLOBAL_Control
0x18006952a  cmp     rcx, rdi
0x18006952d  jz      loc_18006969B
0x180069533  mov     edx, 14h
0x180069538  jmp     loc_18006941E
0x18006953d  mov     r9d, [rsp+2B0h+var_26C]; cchWideChar
0x180069542  lea     rax, [rdi+10Dh]
0x180069549  mov     [rsp+2B0h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18006954e  lea     r8, [rsp+2B0h+pszCredentials]; lpWideCharStr
0x180069553  mov     [rsp+2B0h+lpDefaultChar], rbx; lpDefaultChar
0x180069558  mov     edx, 400h; dwFlags
0x18006955d  mov     [rsp+2B0h+cbMultiByte], 100h; cbMultiByte
0x180069565  xor     ecx, ecx; CodePage
0x180069567  mov     [rsp+2B0h+pcchMaxChars], rax; lpMultiByteStr
0x18006956c  call    cs:__imp_WideCharToMultiByte
0x180069573  nop     dword ptr [rax+rax+00h]
0x180069578  test    eax, eax
0x18006957a  jg      short loc_1800695AB
0x18006957c  call    cs:__imp_GetLastError
0x180069583  nop     dword ptr [rax+rax+00h]
0x180069588  mov     ebx, eax
0x18006958a  mov     rcx, cs:WPP_GLOBAL_Control
0x180069591  lea     rdi, WPP_GLOBAL_Control
0x180069598  cmp     rcx, rdi
0x18006959b  jz      loc_18006969B
0x1800695a1  mov     edx, 15h
0x1800695a6  jmp     loc_18006941E
0x1800695ab  btr     dword ptr [rdi+4], 9
0x1800695b0  mov     [rdi+310h], ebx
0x1800695b6  jmp     loc_180069694
0x1800695bb  lea     rax, [rdi+314h]
0x1800695c2  mov     [rsp+2B0h+pDataIn.cbData], ecx
0x1800695c6  mov     [rsp+2B0h+pDataIn.pbData], rax
0x1800695cb  mov     eax, gs:179Ch
0x1800695d3  test    eax, eax
0x1800695d5  jnz     short loc_18006962D
0x1800695d7  test    r14, r14
0x1800695da  jz      short loc_18006962D
0x1800695dc  mov     rcx, r14; hToken
0x1800695df  call    cs:__imp_ImpersonateLoggedOnUser
0x1800695e6  nop     dword ptr [rax+rax+00h]
0x1800695eb  test    eax, eax
0x1800695ed  jnz     short loc_180069627
0x1800695ef  call    cs:__imp_GetLastError
0x1800695f6  nop     dword ptr [rax+rax+00h]
0x1800695fb  mov     ebx, eax
0x1800695fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180069604  cmp     rcx, rsi
0x180069607  jz      loc_180069694
0x18006960d  mov     edx, 16h
0x180069612  mov     rcx, [rcx+10h]
0x180069616  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x18006961d  mov     r9d, eax
0x180069620  call    WPP_SF_d
0x180069625  jmp     short loc_180069694
0x180069627  mov     r15d, 1
0x18006962d  lea     rax, [rsp+2B0h+pDataOut]
0x180069632  xor     r9d, r9d; pvReserved
0x180069635  mov     [rsp+2B0h+lpDefaultChar], rax; pDataOut
0x18006963a  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x18006963f  mov     [rsp+2B0h+cbMultiByte], ebx; dwFlags
0x180069643  xor     r8d, r8d; pOptionalEntropy
0x180069646  xor     edx, edx; ppszDataDescr
0x180069648  mov     [rsp+2B0h+pcchMaxChars], rbx; pPromptStruct
0x18006964d  call    cs:__imp_CryptUnprotectData
0x180069654  nop     dword ptr [rax+rax+00h]
0x180069659  test    eax, eax
0x18006965b  jnz     short loc_18006967E
0x18006965d  call    cs:__imp_GetLastError
0x180069664  nop     dword ptr [rax+rax+00h]
0x180069669  mov     ebx, eax
0x18006966b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069672  cmp     rcx, rsi
0x180069675  jz      short loc_180069694
0x180069677  mov     edx, 17h
0x18006967c  jmp     short loc_180069612
0x18006967e  mov     r8d, [rsp+2B0h+pDataOut.cbData]; Size
0x180069683  lea     rcx, [rdi+10Dh]; void *
0x18006968a  mov     rdx, [rsp+2B0h+pDataOut.pbData]; Src
0x18006968f  call    memcpy_0
0x180069694  lea     rdi, WPP_GLOBAL_Control
0x18006969b  mov     rcx, [rsp+2B0h+pDataOut.pbData]; hMem
0x1800696a0  call    cs:__imp_LocalFree
0x1800696a7  nop     dword ptr [rax+rax+00h]
0x1800696ac  test    r12d, r12d
0x1800696af  jz      short loc_1800696D6
0x1800696b1  mov     rcx, r14; hToken
0x1800696b4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800696bb  nop     dword ptr [rax+rax+00h]
0x1800696c0  test    eax, eax
0x1800696c2  jnz     short loc_1800696D6
0x1800696c4  test    ebx, ebx
0x1800696c6  jnz     short loc_1800696D6
0x1800696c8  call    cs:__imp_GetLastError
0x1800696cf  nop     dword ptr [rax+rax+00h]
0x1800696d4  mov     ebx, eax
0x1800696d6  test    r15d, r15d
0x1800696d9  jz      short loc_1800696FD
0x1800696db  call    cs:__imp_RevertToSelf
0x1800696e2  nop     dword ptr [rax+rax+00h]
0x1800696e7  test    eax, eax
0x1800696e9  jnz     short loc_1800696FD
0x1800696eb  test    ebx, ebx
0x1800696ed  jnz     short loc_1800696FD
0x1800696ef  call    cs:__imp_GetLastError
0x1800696f6  nop     dword ptr [rax+rax+00h]
0x1800696fb  mov     ebx, eax
0x1800696fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180069704  cmp     rcx, rdi
0x180069707  jz      short loc_180069721
0x180069709  mov     rcx, [rcx+10h]
0x18006970d  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180069714  mov     edx, 18h
0x180069719  mov     r9d, ebx
0x18006971c  call    WPP_SF_d
0x180069721  mov     eax, ebx
0x180069723  mov     rcx, [rbp+1B0h+var_30]
0x18006972a  xor     rcx, rsp; StackCookie
0x18006972d  call    __security_check_cookie
0x180069732  lea     r11, [rsp+2B0h+var_20]
0x18006973a  mov     rbx, [r11+40h]
0x18006973e  mov     rsi, [r11+48h]
0x180069742  mov     rsp, r11
0x180069745  pop     r15
0x180069747  pop     r14
0x180069749  pop     r12
0x18006974b  pop     rdi
0x18006974c  pop     rbp
0x18006974d  retn
```
