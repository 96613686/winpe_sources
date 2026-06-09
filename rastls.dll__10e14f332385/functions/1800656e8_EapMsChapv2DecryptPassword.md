# EapMsChapv2DecryptPassword

- ea: `0x1800656e8`
- end: `0x180065abc`
- name: `EapMsChapv2DecryptPassword`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064f60`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x18003623c`
- `0x180036254`
- `0x1800656e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006582f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006592a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006582f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006592a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a63`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180065920`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180065920`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a2c`
- `CRYPT32!CryptUnprotectData` at `0x1800659e5`
- `CRYPT32!CryptUnprotectData` at `0x1800659e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180065825`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180065a55`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180065825`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180065a55`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065867`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065987`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065a3a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065867`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065987`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180065a3a`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800657cc`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800657cc`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800658be`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x1800658be`

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
0x1800656e8  mov     [rsp-8+arg_10], rbx
0x1800656ed  mov     [rsp-8+arg_18], rsi
0x1800656f2  push    rbp
0x1800656f3  push    rdi
0x1800656f4  push    r12
0x1800656f6  push    r14
0x1800656f8  push    r15
0x1800656fa  lea     rbp, [rsp-190h]
0x180065702  sub     rsp, 290h
0x180065709  mov     rax, cs:__security_cookie
0x180065710  xor     rax, rsp
0x180065713  mov     [rbp+1B0h+var_30], rax
0x18006571a  mov     r14, rdx
0x18006571d  mov     rdi, rcx
0x180065720  xor     ebx, ebx
0x180065722  lea     rcx, [rsp+2B0h+pszCredentials]; void *
0x180065727  xor     edx, edx; Val
0x180065729  mov     [rsp+2B0h+pProtectionType], ebx
0x18006572d  mov     r8d, 202h; Size
0x180065733  xor     r15d, r15d
0x180065736  xor     r12d, r12d
0x180065739  call    memset_0
0x18006573e  mov     ecx, [rdi+310h]
0x180065744  lea     rsi, WPP_GLOBAL_Control
0x18006574b  mov     [rsp+2B0h+var_26C], 100h
0x180065753  xorps   xmm0, xmm0
0x180065756  xorps   xmm1, xmm1
0x180065759  movups  xmmword ptr [rsp+2B0h+pDataIn.cbData], xmm0
0x18006575e  movups  xmmword ptr [rsp+2B0h+pDataOut.cbData], xmm1
0x180065763  test    ecx, ecx
0x180065765  jnz     short loc_18006578F
0x180065767  mov     rcx, cs:WPP_GLOBAL_Control
0x18006576e  cmp     rcx, rsi
0x180065771  jz      loc_180065A20
0x180065777  mov     rcx, [rcx+10h]
0x18006577b  lea     edx, [rbx+0Fh]
0x18006577e  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180065785  call    WPP_SF_
0x18006578a  jmp     loc_180065A20
0x18006578f  test    dword ptr [rdi+4], 200h
0x180065796  jz      loc_180065963
0x18006579c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800657a3  cmp     rcx, rsi
0x1800657a6  jz      short loc_1800657BD
0x1800657a8  mov     rcx, [rcx+10h]
0x1800657ac  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x1800657b3  mov     edx, 10h
0x1800657b8  call    WPP_SF_
0x1800657bd  lea     rsi, [rdi+314h]
0x1800657c4  mov     rcx, rsi; pszProtectedCredentials
0x1800657c7  lea     rdx, [rsp+2B0h+pProtectionType]; pProtectionType
0x1800657cc  call    cs:__imp_CredIsProtectedW
0x1800657d2  test    eax, eax
0x1800657d4  jnz     short loc_180065812
0x1800657d6  call    cs:__imp_GetLastError
0x1800657dc  mov     ebx, eax
0x1800657de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800657e5  lea     rdi, WPP_GLOBAL_Control
0x1800657ec  cmp     rcx, rdi
0x1800657ef  jz      loc_180065A27
0x1800657f5  mov     edx, 11h
0x1800657fa  mov     rcx, [rcx+10h]
0x1800657fe  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180065805  mov     r9d, eax
0x180065808  call    WPP_SF_d
0x18006580d  jmp     loc_180065A27
0x180065812  mov     eax, gs:179Ch
0x18006581a  test    eax, eax
0x18006581c  jz      short loc_18006585D
0x18006581e  cmp     [rsp+2B0h+pProtectionType], 2
0x180065823  jnz     short loc_1800658A0
0x180065825  call    cs:__imp_RevertToSelf
0x18006582b  test    eax, eax
0x18006582d  jnz     short loc_180065855
0x18006582f  call    cs:__imp_GetLastError
0x180065835  mov     ebx, eax
0x180065837  mov     rcx, cs:WPP_GLOBAL_Control
0x18006583e  lea     rdi, WPP_GLOBAL_Control
0x180065845  cmp     rcx, rdi
0x180065848  jz      loc_180065A27
0x18006584e  mov     edx, 12h
0x180065853  jmp     short loc_1800657FA
0x180065855  mov     r12d, 1
0x18006585b  jmp     short loc_1800658A0
0x18006585d  cmp     [rsp+2B0h+pProtectionType], 1
0x180065862  jnz     short loc_1800658A0
0x180065864  mov     rcx, r14; hToken
0x180065867  call    cs:__imp_ImpersonateLoggedOnUser
0x18006586d  test    eax, eax
0x18006586f  jnz     short loc_18006589A
0x180065871  call    cs:__imp_GetLastError
0x180065877  mov     ebx, eax
0x180065879  mov     rcx, cs:WPP_GLOBAL_Control
0x180065880  lea     rdi, WPP_GLOBAL_Control
0x180065887  cmp     rcx, rdi
0x18006588a  jz      loc_180065A27
0x180065890  mov     edx, 13h
0x180065895  jmp     loc_1800657FA
0x18006589a  mov     r15d, 1
0x1800658a0  mov     r8d, [rdi+310h]
0x1800658a7  lea     rax, [rsp+2B0h+var_26C]
0x1800658ac  shr     r8d, 1; cchProtectedCredentials
0x1800658af  lea     r9, [rsp+2B0h+pszCredentials]; pszCredentials
0x1800658b4  mov     rdx, rsi; pszProtectedCredentials
0x1800658b7  mov     [rsp+2B0h+pcchMaxChars], rax; pcchMaxChars
0x1800658bc  xor     ecx, ecx; fAsSelf
0x1800658be  call    cs:__imp_CredUnprotectW
0x1800658c4  test    eax, eax
0x1800658c6  jnz     short loc_1800658F1
0x1800658c8  call    cs:__imp_GetLastError
0x1800658ce  mov     ebx, eax
0x1800658d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800658d7  lea     rdi, WPP_GLOBAL_Control
0x1800658de  cmp     rcx, rdi
0x1800658e1  jz      loc_180065A27
0x1800658e7  mov     edx, 14h
0x1800658ec  jmp     loc_1800657FA
0x1800658f1  mov     r9d, [rsp+2B0h+var_26C]; cchWideChar
0x1800658f6  lea     rax, [rdi+10Dh]
0x1800658fd  mov     [rsp+2B0h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180065902  lea     r8, [rsp+2B0h+pszCredentials]; lpWideCharStr
0x180065907  mov     [rsp+2B0h+lpDefaultChar], rbx; lpDefaultChar
0x18006590c  mov     edx, 400h; dwFlags
0x180065911  mov     [rsp+2B0h+cbMultiByte], 100h; cbMultiByte
0x180065919  xor     ecx, ecx; CodePage
0x18006591b  mov     [rsp+2B0h+pcchMaxChars], rax; lpMultiByteStr
0x180065920  call    cs:__imp_WideCharToMultiByte
0x180065926  test    eax, eax
0x180065928  jg      short loc_180065953
0x18006592a  call    cs:__imp_GetLastError
0x180065930  mov     ebx, eax
0x180065932  mov     rcx, cs:WPP_GLOBAL_Control
0x180065939  lea     rdi, WPP_GLOBAL_Control
0x180065940  cmp     rcx, rdi
0x180065943  jz      loc_180065A27
0x180065949  mov     edx, 15h
0x18006594e  jmp     loc_1800657FA
0x180065953  btr     dword ptr [rdi+4], 9
0x180065958  mov     [rdi+310h], ebx
0x18006595e  jmp     loc_180065A20
0x180065963  lea     rax, [rdi+314h]
0x18006596a  mov     [rsp+2B0h+pDataIn.cbData], ecx
0x18006596e  mov     [rsp+2B0h+pDataIn.pbData], rax
0x180065973  mov     eax, gs:179Ch
0x18006597b  test    eax, eax
0x18006597d  jnz     short loc_1800659C5
0x18006597f  test    r14, r14
0x180065982  jz      short loc_1800659C5
0x180065984  mov     rcx, r14; hToken
0x180065987  call    cs:__imp_ImpersonateLoggedOnUser
0x18006598d  test    eax, eax
0x18006598f  jnz     short loc_1800659BF
0x180065991  call    cs:__imp_GetLastError
0x180065997  mov     ebx, eax
0x180065999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800659a0  cmp     rcx, rsi
0x1800659a3  jz      short loc_180065A20
0x1800659a5  mov     edx, 16h
0x1800659aa  mov     rcx, [rcx+10h]
0x1800659ae  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x1800659b5  mov     r9d, eax
0x1800659b8  call    WPP_SF_d
0x1800659bd  jmp     short loc_180065A20
0x1800659bf  mov     r15d, 1
0x1800659c5  lea     rax, [rsp+2B0h+pDataOut]
0x1800659ca  xor     r9d, r9d; pvReserved
0x1800659cd  mov     [rsp+2B0h+lpDefaultChar], rax; pDataOut
0x1800659d2  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x1800659d7  mov     [rsp+2B0h+cbMultiByte], ebx; dwFlags
0x1800659db  xor     r8d, r8d; pOptionalEntropy
0x1800659de  xor     edx, edx; ppszDataDescr
0x1800659e0  mov     [rsp+2B0h+pcchMaxChars], rbx; pPromptStruct
0x1800659e5  call    cs:__imp_CryptUnprotectData
0x1800659eb  test    eax, eax
0x1800659ed  jnz     short loc_180065A0A
0x1800659ef  call    cs:__imp_GetLastError
0x1800659f5  mov     ebx, eax
0x1800659f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800659fe  cmp     rcx, rsi
0x180065a01  jz      short loc_180065A20
0x180065a03  mov     edx, 17h
0x180065a08  jmp     short loc_1800659AA
0x180065a0a  mov     r8d, [rsp+2B0h+pDataOut.cbData]; Size
0x180065a0f  lea     rcx, [rdi+10Dh]; void *
0x180065a16  mov     rdx, [rsp+2B0h+pDataOut.pbData]; Src
0x180065a1b  call    memcpy_0
0x180065a20  lea     rdi, WPP_GLOBAL_Control
0x180065a27  mov     rcx, [rsp+2B0h+pDataOut.pbData]; hMem
0x180065a2c  call    cs:__imp_LocalFree
0x180065a32  test    r12d, r12d
0x180065a35  jz      short loc_180065A50
0x180065a37  mov     rcx, r14; hToken
0x180065a3a  call    cs:__imp_ImpersonateLoggedOnUser
0x180065a40  test    eax, eax
0x180065a42  jnz     short loc_180065A50
0x180065a44  test    ebx, ebx
0x180065a46  jnz     short loc_180065A50
0x180065a48  call    cs:__imp_GetLastError
0x180065a4e  mov     ebx, eax
0x180065a50  test    r15d, r15d
0x180065a53  jz      short loc_180065A6B
0x180065a55  call    cs:__imp_RevertToSelf
0x180065a5b  test    eax, eax
0x180065a5d  jnz     short loc_180065A6B
0x180065a5f  test    ebx, ebx
0x180065a61  jnz     short loc_180065A6B
0x180065a63  call    cs:__imp_GetLastError
0x180065a69  mov     ebx, eax
0x180065a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180065a72  cmp     rcx, rdi
0x180065a75  jz      short loc_180065A8F
0x180065a77  mov     rcx, [rcx+10h]
0x180065a7b  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180065a82  mov     edx, 18h
0x180065a87  mov     r9d, ebx
0x180065a8a  call    WPP_SF_d
0x180065a8f  mov     eax, ebx
0x180065a91  mov     rcx, [rbp+1B0h+var_30]
0x180065a98  xor     rcx, rsp; StackCookie
0x180065a9b  call    __security_check_cookie
0x180065aa0  lea     r11, [rsp+2B0h+var_20]
0x180065aa8  mov     rbx, [r11+40h]
0x180065aac  mov     rsi, [r11+48h]
0x180065ab0  mov     rsp, r11
0x180065ab3  pop     r15
0x180065ab5  pop     r14
0x180065ab7  pop     r12
0x180065ab9  pop     rdi
0x180065aba  pop     rbp
0x180065abb  retn
```
