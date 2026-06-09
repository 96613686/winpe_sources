# BCryptDeriveKeyCapi

- ea: `0x180058070`
- end: `0x180058468`
- name: `BCryptDeriveKeyCapi`
- size: `1016`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_ALG_HANDLE hTargetAlg, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001930`
- `0x1800034b0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x1800064e0`
- `0x18000743c`
- `0x1800080f0`
- `0x180058070`
- `0x18005bad0`
- `0x18009d746`
- `0x18009d820`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x1800581aa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005821b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058414`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyCapi(
        BCRYPT_HASH_HANDLE hHash,
        BCRYPT_ALG_HANDLE hTargetAlg,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  size_t v5; // rsi
  NTSTATUS Property; // eax
  NTSTATUS v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rcx
  UCHAR *v14; // rax
  UCHAR *v15; // rdi
  NTSTATUS v16; // eax
  __int64 v17; // r9
  unsigned int v18; // r14d
  BOOL v19; // ebx
  NTSTATUS v20; // eax
  __int64 i; // r8
  UCHAR v22; // al
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-BCh] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_HASH_HANDLE hHasha; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR v28[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v29; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbInput[64]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR v31[64]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = cbDerivedKey;
  *(_DWORD *)pbOutput = 0;
  *(_QWORD *)v28 = 0;
  phHash = 0;
  hHasha = 0;
  pcbResult = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      41,
      pbDerivedKey,
      hHash,
      hTargetAlg,
      pbDerivedKey,
      cbDerivedKey,
      dwFlags);
  if ( dwFlags || !pbDerivedKey || !(_DWORD)v5 )
  {
    v11 = 7138;
    goto LABEL_45;
  }
  Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  v10 = Property;
  if ( Property >= 0 )
  {
    v13 = (unsigned int)(2 * *(_DWORD *)pbOutput);
    if ( (unsigned int)v13 >= (unsigned int)v5 && *(_DWORD *)pbOutput <= 0x40u )
    {
      v14 = (UCHAR *)MSCryptAlloc(v13);
      v15 = v14;
      if ( !v14 )
      {
        v10 = -1073741801;
        v11 = 7183;
        v12 = 3221225495LL;
        goto LABEL_46;
      }
      v16 = BCryptFinishHash(hHash, v14, *(ULONG *)pbOutput, 0);
      v10 = v16;
      if ( v16 < 0 )
      {
        v17 = 7193;
LABEL_15:
        DebugTraceError((unsigned int)v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v17);
LABEL_42:
        MSCryptFree(v15);
        goto LABEL_47;
      }
      v18 = *(_DWORD *)pbOutput;
      v19 = *(_DWORD *)pbOutput < (unsigned int)v5;
      if ( hTargetAlg && (_DWORD)v5 == 16 && *(_DWORD *)pbOutput < 0x20u )
      {
        v20 = BCryptGetProperty(hTargetAlg, L"AlgorithmName", (PUCHAR)&v29, 8u, &pcbResult, 0);
        if ( v20 >= 0 )
        {
          if ( !wcscmp_0(&v29, L"AES") )
            v19 = 1;
        }
        else
        {
          DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7221);
        }
        v18 = *(_DWORD *)pbOutput;
      }
      if ( v19 )
      {
        memset(pbInput, 54, sizeof(pbInput));
        memset(v31, 92, sizeof(v31));
        for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
        {
          v22 = v15[i];
          pbInput[i] ^= v22;
          v31[i] ^= v22;
        }
        v16 = BCryptGetProperty(hHash, L"ProviderHandle", v28, 8u, &pcbResult, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7260;
          goto LABEL_15;
        }
        v16 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v28, &phHash, 0, 0, 0, 0, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7273;
          goto LABEL_15;
        }
        v16 = BCryptHashData(phHash, pbInput, 0x40u, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7283;
          goto LABEL_15;
        }
        v16 = BCryptFinishHash(phHash, v15, *(ULONG *)pbOutput, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7293;
          goto LABEL_15;
        }
        v16 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v28, &hHasha, 0, 0, 0, 0, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7306;
          goto LABEL_15;
        }
        v16 = BCryptHashData(hHasha, v31, 0x40u, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7316;
          goto LABEL_15;
        }
        v16 = BCryptFinishHash(hHasha, &v15[*(unsigned int *)pbOutput], *(ULONG *)pbOutput, 0);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 7326;
          goto LABEL_15;
        }
      }
      memmove(pbDerivedKey, v15, v5);
      v10 = 0;
      goto LABEL_42;
    }
    v11 = 7167;
LABEL_45:
    v12 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_46;
  }
  v11 = 7160;
  v12 = (unsigned int)Property;
LABEL_46:
  DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v11);
LABEL_47:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHasha )
    BCryptDestroyHash(hHasha);
  return v10;
}

```

## disassembly

```asm
0x180058070  push    rbp
0x180058072  push    rbx
0x180058073  push    rsi
0x180058074  push    rdi
0x180058075  push    r12
0x180058077  push    r13
0x180058079  push    r14
0x18005807b  push    r15
0x18005807d  lea     rbp, [rsp-8]
0x180058082  sub     rsp, 108h
0x180058089  mov     rax, cs:__security_cookie
0x180058090  xor     rax, rsp
0x180058093  mov     [rbp+40h+var_50], rax
0x180058097  xor     r14d, r14d
0x18005809a  mov     esi, r9d
0x18005809d  mov     dword ptr [rsp+140h+pbOutput], r14d
0x1800580a2  mov     r13, r8
0x1800580a5  mov     qword ptr [rsp+140h+var_E8], r14
0x1800580aa  mov     r12, rdx
0x1800580ad  mov     [rsp+140h+phHash], r14
0x1800580b2  mov     r15, rcx
0x1800580b5  mov     [rsp+140h+hHash], r14
0x1800580ba  mov     [rsp+140h+var_FC], r14d
0x1800580bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580c6  lea     rax, WPP_GLOBAL_Control
0x1800580cd  mov     ebx, [rbp+40h+dwFlags]
0x1800580d0  cmp     rcx, rax
0x1800580d3  jz      short loc_1800580FE
0x1800580d5  mov     eax, [rcx+2Ch]
0x1800580d8  test    al, 4
0x1800580da  jz      short loc_1800580FE
0x1800580dc  mov     rcx, [rcx+18h]
0x1800580e0  lea     edx, [r14+29h]
0x1800580e4  mov     [rsp+140h+var_108], ebx
0x1800580e8  mov     r9, r15
0x1800580eb  mov     [rsp+140h+var_110], esi
0x1800580ef  mov     qword ptr [rsp+140h+cbSecret], r8
0x1800580f4  mov     [rsp+140h+pcbResult], r12
0x1800580f9  call    WPP_SF_qqqdD
0x1800580fe  test    ebx, ebx
0x180058100  jnz     loc_180058404
0x180058106  test    r13, r13
0x180058109  jz      loc_180058404
0x18005810f  test    esi, esi
0x180058111  jz      loc_180058404
0x180058117  lea     rax, [rsp+140h+var_FC]
0x18005811c  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x180058121  lea     r9d, [rbx+4]; cbOutput
0x180058125  mov     [rsp+140h+pcbResult], rax; pcbResult
0x18005812a  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x18005812f  mov     rcx, r15; hObject
0x180058132  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180058139  call    BCryptGetProperty
0x18005813e  mov     ebx, eax
0x180058140  test    eax, eax
0x180058142  jns     short loc_180058151
0x180058144  mov     r9d, 1BF8h
0x18005814a  mov     ecx, eax
0x18005814c  jmp     loc_180058414
0x180058151  mov     eax, dword ptr [rsp+140h+pbOutput]
0x180058155  lea     ecx, [rax+rax]
0x180058158  cmp     ecx, esi
0x18005815a  jb      loc_1800583FC
0x180058160  cmp     eax, 40h ; '@'
0x180058163  ja      loc_1800583FC
0x180058169  call    MSCryptAlloc
0x18005816e  mov     rdi, rax
0x180058171  test    rax, rax
0x180058174  jnz     short loc_18005818B
0x180058176  mov     ebx, 0C0000017h
0x18005817b  mov     r9d, 1C0Fh
0x180058181  mov     ecx, 0C0000017h
0x180058186  jmp     loc_180058414
0x18005818b  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x180058190  xor     r9d, r9d; dwFlags
0x180058193  mov     rdx, rdi; pbOutput
0x180058196  mov     rcx, r15; hHash
0x180058199  call    BCryptFinishHash
0x18005819e  mov     ebx, eax
0x1800581a0  test    eax, eax
0x1800581a2  jns     short loc_1800581C4
0x1800581a4  mov     r9d, 1C19h
0x1800581aa  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800581b1  mov     ecx, eax
0x1800581b3  lea     rdx, aStatus; "Status"
0x1800581ba  call    DebugTraceError
0x1800581bf  jmp     loc_1800583F2
0x1800581c4  mov     ebx, r14d
0x1800581c7  mov     eax, 1
0x1800581cc  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x1800581d1  cmp     r14d, esi
0x1800581d4  cmovb   ebx, eax
0x1800581d7  test    r12, r12
0x1800581da  jz      short loc_180058252
0x1800581dc  cmp     esi, 10h
0x1800581df  jnz     short loc_180058252
0x1800581e1  cmp     r14d, 20h ; ' '
0x1800581e5  jnb     short loc_180058252
0x1800581e7  lea     rax, [rsp+140h+var_FC]
0x1800581ec  mov     [rsp+140h+cbSecret], 0; dwFlags
0x1800581f4  lea     r9d, [rsi-8]; cbOutput
0x1800581f8  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1800581fd  lea     r8, [rsp+140h+var_D8]; pbOutput
0x180058202  mov     rcx, r12; hObject
0x180058205  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18005820c  call    BCryptGetProperty
0x180058211  test    eax, eax
0x180058213  jns     short loc_180058232
0x180058215  mov     r9d, 1C35h
0x18005821b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058222  lea     rdx, aStatus; "Status"
0x180058229  mov     ecx, eax
0x18005822b  call    DebugTraceError
0x180058230  jmp     short loc_18005824D
0x180058232  lea     rdx, aAes; "AES"
0x180058239  lea     rcx, [rsp+140h+var_D8]; Str1
0x18005823e  call    wcscmp_0
0x180058243  test    eax, eax
0x180058245  mov     eax, 1
0x18005824a  cmovz   ebx, eax
0x18005824d  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x180058252  test    ebx, ebx
0x180058254  jz      loc_1800583DE
0x18005825a  mov     r12d, 40h ; '@'
0x180058260  lea     rcx, [rsp+140h+pbInput]; void *
0x180058265  mov     r8d, r12d; Size
0x180058268  lea     edx, [r12-0Ah]; Val
0x18005826d  call    memset
0x180058272  mov     r8d, r12d; Size
0x180058275  lea     edx, [r12+1Ch]; Val
0x18005827a  lea     rcx, [rbp+40h+var_90]; void *
0x18005827e  call    memset
0x180058283  xor     r8d, r8d
0x180058286  test    r14d, r14d
0x180058289  jz      short loc_1800582A1
0x18005828b  mov     al, [r8+rdi]
0x18005828f  xor     [rsp+r8+140h+pbInput], al
0x180058294  xor     [rbp+r8+40h+var_90], al
0x180058299  inc     r8d
0x18005829c  cmp     r8d, r14d
0x18005829f  jb      short loc_18005828B
0x1800582a1  xor     r14d, r14d
0x1800582a4  lea     rax, [rsp+140h+var_FC]
0x1800582a9  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x1800582ae  lea     r8, [rsp+140h+var_E8]; pbOutput
0x1800582b3  lea     rdx, aProviderhandle; "ProviderHandle"
0x1800582ba  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1800582bf  mov     rcx, r15; hObject
0x1800582c2  lea     r9d, [r14+8]; cbOutput
0x1800582c6  call    BCryptGetProperty
0x1800582cb  mov     ebx, eax
0x1800582cd  test    eax, eax
0x1800582cf  jns     short loc_1800582DC
0x1800582d1  mov     r9d, 1C5Ch
0x1800582d7  jmp     loc_1800581AA
0x1800582dc  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x1800582e1  lea     rdx, [rsp+140h+phHash]; phHash
0x1800582e6  mov     [rsp+140h+var_110], r14d; dwFlags
0x1800582eb  xor     r9d, r9d; cbHashObject
0x1800582ee  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x1800582f3  xor     r8d, r8d; pbHashObject
0x1800582f6  mov     [rsp+140h+pcbResult], r14; pbSecret
0x1800582fb  call    BCryptCreateHash
0x180058300  mov     ebx, eax
0x180058302  test    eax, eax
0x180058304  jns     short loc_180058311
0x180058306  mov     r9d, 1C69h
0x18005830c  jmp     loc_1800581AA
0x180058311  mov     rcx, [rsp+140h+phHash]; hHash
0x180058316  lea     rdx, [rsp+140h+pbInput]; pbInput
0x18005831b  xor     r9d, r9d; dwFlags
0x18005831e  mov     r8d, r12d; cbInput
0x180058321  call    BCryptHashData
0x180058326  mov     ebx, eax
0x180058328  test    eax, eax
0x18005832a  jns     short loc_180058337
0x18005832c  mov     r9d, 1C73h
0x180058332  jmp     loc_1800581AA
0x180058337  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x18005833c  xor     r9d, r9d; dwFlags
0x18005833f  mov     rcx, [rsp+140h+phHash]; hHash
0x180058344  mov     rdx, rdi; pbOutput
0x180058347  call    BCryptFinishHash
0x18005834c  mov     ebx, eax
0x18005834e  test    eax, eax
0x180058350  jns     short loc_18005835D
0x180058352  mov     r9d, 1C7Dh
0x180058358  jmp     loc_1800581AA
0x18005835d  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x180058362  lea     rdx, [rsp+140h+hHash]; phHash
0x180058367  mov     [rsp+140h+var_110], r14d; dwFlags
0x18005836c  xor     r9d, r9d; cbHashObject
0x18005836f  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x180058374  xor     r8d, r8d; pbHashObject
0x180058377  mov     [rsp+140h+pcbResult], r14; pbSecret
0x18005837c  call    BCryptCreateHash
0x180058381  mov     ebx, eax
0x180058383  test    eax, eax
0x180058385  jns     short loc_180058392
0x180058387  mov     r9d, 1C8Ah
0x18005838d  jmp     loc_1800581AA
0x180058392  mov     rcx, [rsp+140h+hHash]; hHash
0x180058397  lea     rdx, [rbp+40h+var_90]; pbInput
0x18005839b  xor     r9d, r9d; dwFlags
0x18005839e  mov     r8d, r12d; cbInput
0x1800583a1  call    BCryptHashData
0x1800583a6  mov     ebx, eax
0x1800583a8  test    eax, eax
0x1800583aa  jns     short loc_1800583B7
0x1800583ac  mov     r9d, 1C94h
0x1800583b2  jmp     loc_1800581AA
0x1800583b7  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x1800583bc  xor     r9d, r9d; dwFlags
0x1800583bf  mov     rcx, [rsp+140h+hHash]; hHash
0x1800583c4  lea     rdx, [rdi+r8]; pbOutput
0x1800583c8  call    BCryptFinishHash
0x1800583cd  mov     ebx, eax
0x1800583cf  test    eax, eax
0x1800583d1  jns     short loc_1800583E1
0x1800583d3  mov     r9d, 1C9Eh
0x1800583d9  jmp     loc_1800581AA
0x1800583de  xor     r14d, r14d
0x1800583e1  mov     r8, rsi; Size
0x1800583e4  mov     rdx, rdi; Src
0x1800583e7  mov     rcx, r13; void *
0x1800583ea  call    memmove
0x1800583ef  mov     ebx, r14d
0x1800583f2  mov     rcx, rdi; P
0x1800583f5  call    MSCryptFree
0x1800583fa  jmp     short loc_180058427
0x1800583fc  mov     r9d, 1BFFh
0x180058402  jmp     short loc_18005840A
0x180058404  mov     r9d, 1BE2h
0x18005840a  mov     ecx, 0C000000Dh
0x18005840f  mov     ebx, 0C000000Dh
0x180058414  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005841b  lea     rdx, aStatus; "Status"
0x180058422  call    DebugTraceError
0x180058427  mov     rcx, [rsp+140h+phHash]; hHash
0x18005842c  test    rcx, rcx
0x18005842f  jz      short loc_180058436
0x180058431  call    BCryptDestroyHash
0x180058436  mov     rcx, [rsp+140h+hHash]; hHash
0x18005843b  test    rcx, rcx
0x18005843e  jz      short loc_180058445
0x180058440  call    BCryptDestroyHash
0x180058445  mov     eax, ebx
0x180058447  mov     rcx, [rbp+40h+var_50]
0x18005844b  xor     rcx, rsp; StackCookie
0x18005844e  call    __security_check_cookie
0x180058453  add     rsp, 108h
0x18005845a  pop     r15
0x18005845c  pop     r14
0x18005845e  pop     r13
0x180058460  pop     r12
0x180058462  pop     rdi
0x180058463  pop     rsi
0x180058464  pop     rbx
0x180058465  pop     rbp
0x180058466  retn
```
