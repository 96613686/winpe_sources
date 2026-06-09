# EapMsChapv2DecryptPassword

- ea: `0x180002530`
- end: `0x18000294d`
- name: `EapMsChapv2DecryptPassword`
- size: `1053`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002040`
- `0x18000b9b4`

## callees

- `0x180002530`
- `0x180003bd0`
- `0x180006a20`
- `0x180013b20`
- `0x180014610`
- `0x180025efc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002674`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800028c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002674`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800028c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800026b2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800027b6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800027fd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800026b2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800027b6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800027fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028bd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000276d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000276d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000263f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000267e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000263f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000267e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028d6`
- `CRYPT32!CryptUnprotectData` at `0x18000286a`
- `CRYPT32!CryptUnprotectData` at `0x18000286a`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180002635`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180002635`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180002706`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180002706`

## pseudocode

```c
__int64 __fastcall EapMsChapv2DecryptPassword(__int64 a1, void *a2)
{
  int v4; // r15d
  DWORD v5; // esi
  DWORD v6; // ecx
  int v7; // r14d
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // eax
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+48h] [rbp-C0h] BYREF
  int pProtectionType_4; // [rsp+4Ch] [rbp-BCh] BYREF
  DATA_BLOB pProtectionType_8; // [rsp+50h] [rbp-B8h] BYREF
  DATA_BLOB hMem_8; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR pszCredentials[264]; // [rsp+78h] [rbp-90h] BYREF

  v4 = 0;
  v5 = 0;
  pProtectionType = CredUnprotected;
  memset_0(pszCredentials, 0, 0x202u);
  v6 = *(_DWORD *)(a1 + 784);
  pProtectionType_4 = 256;
  hMem_8 = 0;
  pProtectionType_8 = 0;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids);
    LocalFree(pProtectionType_8.pbData);
    goto LABEL_51;
  }
  v7 = 0;
  if ( (*(_DWORD *)(a1 + 4) & 0x200) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids);
    if ( !CredIsProtectedW((LPWSTR)(a1 + 788), &pProtectionType) )
    {
      LastError = GetLastError();
      v5 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v10 = 17;
LABEL_39:
        WPP_SF_d(v9[2], v10, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, LastError);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    if ( NtCurrentTeb()->IsImpersonating )
    {
      if ( pProtectionType == CredTrustedProtection )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v5 = LastError;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v10 = 18;
            goto LABEL_39;
          }
LABEL_40:
          LocalFree(pProtectionType_8.pbData);
          goto LABEL_51;
        }
        v4 = 1;
      }
    }
    else if ( pProtectionType == CredUserProtection )
    {
      if ( !ImpersonateLoggedOnUser(a2) )
      {
        LastError = GetLastError();
        v5 = LastError;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v10 = 19;
          goto LABEL_39;
        }
        goto LABEL_40;
      }
      v7 = 1;
    }
    if ( CredUnprotectW(0, (LPWSTR)(a1 + 788), *(_DWORD *)(a1 + 784) >> 1, pszCredentials, (DWORD *)&pProtectionType_4) )
    {
      if ( WideCharToMultiByte(0, 0x400u, pszCredentials, pProtectionType_4, (LPSTR)(a1 + 269), 256, 0, 0) > 0 )
      {
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        *(_DWORD *)(a1 + 784) = 0;
        goto LABEL_30;
      }
      v11 = GetLastError();
      v5 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v13 = 21;
        goto LABEL_25;
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v13 = 20;
LABEL_25:
        WPP_SF_d(v12[2], v13, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v11);
      }
    }
LABEL_30:
    LocalFree(pProtectionType_8.pbData);
    if ( v4 && !ImpersonateLoggedOnUser(a2) && !v5 )
      v5 = GetLastError();
    goto LABEL_47;
  }
  hMem_8.cbData = v6;
  hMem_8.pbData = (BYTE *)(a1 + 788);
  if ( !NtCurrentTeb()->IsImpersonating && a2 )
  {
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      LastError = GetLastError();
      v5 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v10 = 22;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    v7 = 1;
  }
  if ( CryptUnprotectData(&hMem_8, 0, 0, 0, 0, 0, &pProtectionType_8) )
  {
    memcpy_0((void *)(a1 + 269), pProtectionType_8.pbData, pProtectionType_8.cbData);
  }
  else
  {
    v14 = GetLastError();
    v5 = v14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v14);
  }
  LocalFree(pProtectionType_8.pbData);
LABEL_47:
  if ( v7 && !RevertToSelf() && !v5 )
    v5 = GetLastError();
LABEL_51:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180002530  mov     r11, rsp
0x180002533  push    rbp
0x180002534  push    rsi
0x180002535  lea     rbp, [r11-1C8h]
0x18000253c  sub     rsp, 2B8h
0x180002543  mov     rax, cs:__security_cookie
0x18000254a  xor     rax, rsp
0x18000254d  mov     [rbp+1C0h+var_40], rax
0x180002554  mov     [r11+18h], rbx
0x180002558  mov     r8d, 202h; Size
0x18000255e  mov     [r11-18h], rdi
0x180002562  mov     rbx, rcx
0x180002565  mov     [r11-20h], r12
0x180002569  lea     rcx, [rsp+2C0h+pszCredentials]; void *
0x18000256e  mov     [r11-38h], r15
0x180002572  mov     r12, rdx
0x180002575  xor     r15d, r15d
0x180002578  xor     edx, edx; Val
0x18000257a  mov     esi, r15d
0x18000257d  mov     [rsp+2C0h+pProtectionType], r15d
0x180002582  call    memset_0
0x180002587  mov     ecx, [rbx+310h]
0x18000258d  xorps   xmm0, xmm0
0x180002590  mov     [rsp+2C0h+pProtectionType+4], 100h
0x180002598  xorps   xmm1, xmm1
0x18000259b  movups  xmmword ptr [rsp+2C0h+hMem+8], xmm0
0x1800025a0  movups  xmmword ptr [rsp+2C0h+pProtectionType+8], xmm1
0x1800025a5  test    ecx, ecx
0x1800025a7  jnz     short loc_1800025E1
0x1800025a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025b0  lea     rdi, WPP_GLOBAL_Control
0x1800025b7  cmp     rcx, rdi
0x1800025ba  jz      short loc_1800025D1
0x1800025bc  mov     rcx, [rcx+10h]
0x1800025c0  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x1800025c7  mov     edx, 0Fh
0x1800025cc  call    WPP_SF_
0x1800025d1  mov     rcx, qword ptr [rsp+2C0h+hMem]; hMem
0x1800025d6  call    cs:__imp_LocalFree
0x1800025dc  jmp     loc_1800028EE
0x1800025e1  test    dword ptr [rbx+4], 200h
0x1800025e8  lea     rdi, WPP_GLOBAL_Control
0x1800025ef  mov     [rsp+2C0h+var_20], r13
0x1800025f7  mov     [rsp+2C0h+var_28], r14
0x1800025ff  mov     r14d, r15d
0x180002602  jz      loc_1800027D9
0x180002608  mov     rcx, cs:WPP_GLOBAL_Control
0x18000260f  cmp     rcx, rdi
0x180002612  jz      short loc_180002629
0x180002614  mov     rcx, [rcx+10h]
0x180002618  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x18000261f  mov     edx, 10h
0x180002624  call    WPP_SF_
0x180002629  lea     rdx, [rsp+2C0h+pProtectionType]; pProtectionType
0x18000262e  lea     rcx, [rbx+314h]; pszProtectedCredentials
0x180002635  call    cs:__imp_CredIsProtectedW
0x18000263b  test    eax, eax
0x18000263d  jnz     short loc_180002661
0x18000263f  call    cs:__imp_GetLastError
0x180002645  mov     esi, eax
0x180002647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000264e  cmp     rcx, rdi
0x180002651  jz      loc_180002833
0x180002657  mov     edx, 11h
0x18000265c  jmp     loc_180002820
0x180002661  mov     eax, gs:179Ch
0x180002669  test    eax, eax
0x18000266b  jz      short loc_1800026A8
0x18000266d  cmp     [rsp+2C0h+pProtectionType], 2
0x180002672  jnz     short loc_1800026E4
0x180002674  call    cs:__imp_RevertToSelf
0x18000267a  test    eax, eax
0x18000267c  jnz     short loc_1800026A0
0x18000267e  call    cs:__imp_GetLastError
0x180002684  mov     esi, eax
0x180002686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000268d  cmp     rcx, rdi
0x180002690  jz      loc_180002833
0x180002696  mov     edx, 12h
0x18000269b  jmp     loc_180002820
0x1800026a0  mov     r15d, 1
0x1800026a6  jmp     short loc_1800026E4
0x1800026a8  cmp     [rsp+2C0h+pProtectionType], 1
0x1800026ad  jnz     short loc_1800026E4
0x1800026af  mov     rcx, r12; hToken
0x1800026b2  call    cs:__imp_ImpersonateLoggedOnUser
0x1800026b8  test    eax, eax
0x1800026ba  jnz     short loc_1800026DE
0x1800026bc  call    cs:__imp_GetLastError
0x1800026c2  mov     esi, eax
0x1800026c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026cb  cmp     rcx, rdi
0x1800026ce  jz      loc_180002833
0x1800026d4  mov     edx, 13h
0x1800026d9  jmp     loc_180002820
0x1800026de  mov     r14d, 1
0x1800026e4  mov     r8d, [rbx+310h]
0x1800026eb  lea     rax, [rsp+2C0h+pProtectionType+4]
0x1800026f0  shr     r8d, 1; cchProtectedCredentials
0x1800026f3  lea     r9, [rsp+2C0h+pszCredentials]; pszCredentials
0x1800026f8  lea     rdx, [rbx+314h]; pszProtectedCredentials
0x1800026ff  mov     [rsp+2C0h+pcchMaxChars], rax; pcchMaxChars
0x180002704  xor     ecx, ecx; fAsSelf
0x180002706  call    cs:__imp_CredUnprotectW
0x18000270c  test    eax, eax
0x18000270e  jnz     short loc_18000273E
0x180002710  call    cs:__imp_GetLastError
0x180002716  mov     esi, eax
0x180002718  mov     rcx, cs:WPP_GLOBAL_Control
0x18000271f  cmp     rcx, rdi
0x180002722  jz      short loc_18000279F
0x180002724  mov     edx, 14h
0x180002729  mov     rcx, [rcx+10h]
0x18000272d  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180002734  mov     r9d, eax
0x180002737  call    WPP_SF_d
0x18000273c  jmp     short loc_18000279F
0x18000273e  mov     r9d, [rsp+2C0h+pProtectionType+4]; cchWideChar
0x180002743  lea     rax, [rbx+10Dh]
0x18000274a  mov     [rsp+2C0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18000274f  lea     r8, [rsp+2C0h+pszCredentials]; lpWideCharStr
0x180002754  mov     [rsp+2C0h+lpDefaultChar], rsi; lpDefaultChar
0x180002759  mov     edx, 400h; dwFlags
0x18000275e  mov     [rsp+2C0h+cbMultiByte], 100h; cbMultiByte
0x180002766  xor     ecx, ecx; CodePage
0x180002768  mov     [rsp+2C0h+pcchMaxChars], rax; lpMultiByteStr
0x18000276d  call    cs:__imp_WideCharToMultiByte
0x180002773  test    eax, eax
0x180002775  jg      short loc_180002792
0x180002777  call    cs:__imp_GetLastError
0x18000277d  mov     esi, eax
0x18000277f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002786  cmp     rcx, rdi
0x180002789  jz      short loc_18000279F
0x18000278b  mov     edx, 15h
0x180002790  jmp     short loc_180002729
0x180002792  and     dword ptr [rbx+4], 0FFFFFDFFh
0x180002799  mov     [rbx+310h], esi
0x18000279f  mov     rcx, qword ptr [rsp+2C0h+hMem]; hMem
0x1800027a4  call    cs:__imp_LocalFree
0x1800027aa  test    r15d, r15d
0x1800027ad  jz      loc_1800028C3
0x1800027b3  mov     rcx, r12; hToken
0x1800027b6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800027bc  test    eax, eax
0x1800027be  jnz     loc_1800028C3
0x1800027c4  test    esi, esi
0x1800027c6  jnz     loc_1800028C3
0x1800027cc  call    cs:__imp_GetLastError
0x1800027d2  mov     esi, eax
0x1800027d4  jmp     loc_1800028C3
0x1800027d9  lea     rax, [rbx+314h]
0x1800027e0  mov     dword ptr [rsp+2C0h+hMem+8], ecx
0x1800027e4  mov     qword ptr [rsp+2C0h+hMem+10h], rax
0x1800027e9  mov     eax, gs:179Ch
0x1800027f1  test    eax, eax
0x1800027f3  jnz     short loc_180002849
0x1800027f5  test    r12, r12
0x1800027f8  jz      short loc_180002849
0x1800027fa  mov     rcx, r12; hToken
0x1800027fd  call    cs:__imp_ImpersonateLoggedOnUser
0x180002803  test    eax, eax
0x180002805  jnz     short loc_180002843
0x180002807  call    cs:__imp_GetLastError
0x18000280d  mov     esi, eax
0x18000280f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002816  cmp     rcx, rdi
0x180002819  jz      short loc_180002833
0x18000281b  mov     edx, 16h
0x180002820  mov     rcx, [rcx+10h]
0x180002824  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x18000282b  mov     r9d, eax
0x18000282e  call    WPP_SF_d
0x180002833  mov     rcx, qword ptr [rsp+2C0h+hMem]; hMem
0x180002838  call    cs:__imp_LocalFree
0x18000283e  jmp     loc_1800028DE
0x180002843  mov     r14d, 1
0x180002849  lea     rax, [rsp+2C0h+pProtectionType+8]
0x18000284e  xor     r9d, r9d; pvReserved
0x180002851  mov     [rsp+2C0h+lpDefaultChar], rax; pDataOut
0x180002856  lea     rcx, [rsp+2C0h+hMem+8]; pDataIn
0x18000285b  mov     [rsp+2C0h+cbMultiByte], r15d; dwFlags
0x180002860  xor     r8d, r8d; pOptionalEntropy
0x180002863  xor     edx, edx; ppszDataDescr
0x180002865  mov     [rsp+2C0h+pcchMaxChars], r15; pPromptStruct
0x18000286a  call    cs:__imp_CryptUnprotectData
0x180002870  test    eax, eax
0x180002872  jnz     short loc_1800028A2
0x180002874  call    cs:__imp_GetLastError
0x18000287a  mov     esi, eax
0x18000287c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002883  cmp     rcx, rdi
0x180002886  jz      short loc_1800028B8
0x180002888  mov     rcx, [rcx+10h]
0x18000288c  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180002893  mov     edx, 17h
0x180002898  mov     r9d, eax
0x18000289b  call    WPP_SF_d
0x1800028a0  jmp     short loc_1800028B8
0x1800028a2  mov     r8d, [rsp+2C0h+pProtectionType+8]; Size
0x1800028a7  lea     rcx, [rbx+10Dh]; void *
0x1800028ae  mov     rdx, qword ptr [rsp+2C0h+hMem]; Src
0x1800028b3  call    memcpy_0
0x1800028b8  mov     rcx, qword ptr [rsp+2C0h+hMem]; hMem
0x1800028bd  call    cs:__imp_LocalFree
0x1800028c3  test    r14d, r14d
0x1800028c6  jz      short loc_1800028DE
0x1800028c8  call    cs:__imp_RevertToSelf
0x1800028ce  test    eax, eax
0x1800028d0  jnz     short loc_1800028DE
0x1800028d2  test    esi, esi
0x1800028d4  jnz     short loc_1800028DE
0x1800028d6  call    cs:__imp_GetLastError
0x1800028dc  mov     esi, eax
0x1800028de  mov     r13, [rsp+2C0h+var_20]
0x1800028e6  mov     r14, [rsp+2C0h+var_28]
0x1800028ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028f5  mov     r15, [rsp+2C0h+var_30]
0x1800028fd  cmp     rcx, rdi
0x180002900  mov     rdi, [rsp+2B0h]
0x180002908  mov     r12, [rsp+2C0h+var_18]
0x180002910  mov     rbx, [rsp+2C0h+arg_10]
0x180002918  jz      short loc_180002932
0x18000291a  mov     rcx, [rcx+10h]
0x18000291e  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x180002925  mov     edx, 18h
0x18000292a  mov     r9d, esi
0x18000292d  call    WPP_SF_d
0x180002932  mov     eax, esi
0x180002934  mov     rcx, [rbp+1C0h+var_40]
0x18000293b  xor     rcx, rsp; StackCookie
0x18000293e  call    __security_check_cookie
0x180002943  add     rsp, 2B8h
0x18000294a  pop     rsi
0x18000294b  pop     rbp
0x18000294c  retn
```
