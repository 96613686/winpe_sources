# BCryptDeriveKeyCapi

- ea: `0x180062240`
- end: `0x180062638`
- name: `BCryptDeriveKeyCapi`
- size: `1016`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_ALG_HANDLE hTargetAlg, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000ba50`
- `0x18000d5d0`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x180010600`
- `0x18001155c`
- `0x180012210`
- `0x180062240`
- `0x180065ca0`
- `0x1800a4232`
- `0x1800a4260`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x18006237a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800623eb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800625e4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  __int64 v10; // rdx
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  UCHAR *v15; // rax
  UCHAR *v16; // rdi
  NTSTATUS v17; // eax
  __int64 v18; // r9
  unsigned int v19; // r14d
  BOOL v20; // ebx
  NTSTATUS v21; // eax
  __int64 i; // r8
  UCHAR v23; // al
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-BCh] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_HASH_HANDLE hHasha; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR v29[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v30; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbInput[64]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR v32[64]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = cbDerivedKey;
  *(_DWORD *)pbOutput = 0;
  *(_QWORD *)v29 = 0;
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
    v12 = 7138;
    goto LABEL_45;
  }
  Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property >= 0 )
  {
    v14 = (unsigned int)(2 * *(_DWORD *)pbOutput);
    if ( (unsigned int)v14 >= (unsigned int)v5 && *(_DWORD *)pbOutput <= 0x40u )
    {
      v15 = (UCHAR *)MSCryptAlloc(v14, v10);
      v16 = v15;
      if ( !v15 )
      {
        v11 = -1073741801;
        v12 = 7183;
        v13 = 3221225495LL;
        goto LABEL_46;
      }
      v17 = BCryptFinishHash(hHash, v15, *(ULONG *)pbOutput, 0);
      v11 = v17;
      if ( v17 < 0 )
      {
        v18 = 7193;
LABEL_15:
        DebugTraceError((unsigned int)v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v18);
LABEL_42:
        MSCryptFree(v16);
        goto LABEL_47;
      }
      v19 = *(_DWORD *)pbOutput;
      v20 = *(_DWORD *)pbOutput < (unsigned int)v5;
      if ( hTargetAlg && (_DWORD)v5 == 16 && *(_DWORD *)pbOutput < 0x20u )
      {
        v21 = BCryptGetProperty(hTargetAlg, L"AlgorithmName", (PUCHAR)&v30, 8u, &pcbResult, 0);
        if ( v21 >= 0 )
        {
          if ( !wcscmp_0(&v30, L"AES") )
            v20 = 1;
        }
        else
        {
          DebugTraceError((unsigned int)v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7221);
        }
        v19 = *(_DWORD *)pbOutput;
      }
      if ( v20 )
      {
        memset(pbInput, 54, sizeof(pbInput));
        memset(v32, 92, sizeof(v32));
        for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
        {
          v23 = v16[i];
          pbInput[i] ^= v23;
          v32[i] ^= v23;
        }
        v17 = BCryptGetProperty(hHash, L"ProviderHandle", v29, 8u, &pcbResult, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7260;
          goto LABEL_15;
        }
        v17 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v29, &phHash, 0, 0, 0, 0, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7273;
          goto LABEL_15;
        }
        v17 = BCryptHashData(phHash, pbInput, 0x40u, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7283;
          goto LABEL_15;
        }
        v17 = BCryptFinishHash(phHash, v16, *(ULONG *)pbOutput, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7293;
          goto LABEL_15;
        }
        v17 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v29, &hHasha, 0, 0, 0, 0, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7306;
          goto LABEL_15;
        }
        v17 = BCryptHashData(hHasha, v32, 0x40u, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7316;
          goto LABEL_15;
        }
        v17 = BCryptFinishHash(hHasha, &v16[*(unsigned int *)pbOutput], *(ULONG *)pbOutput, 0);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 7326;
          goto LABEL_15;
        }
      }
      memmove(pbDerivedKey, v16, v5);
      v11 = 0;
      goto LABEL_42;
    }
    v12 = 7167;
LABEL_45:
    v13 = 3221225485LL;
    v11 = -1073741811;
    goto LABEL_46;
  }
  v12 = 7160;
  v13 = (unsigned int)Property;
LABEL_46:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
LABEL_47:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHasha )
    BCryptDestroyHash(hHasha);
  return v11;
}

```

## disassembly

```asm
0x180062240  push    rbp
0x180062242  push    rbx
0x180062243  push    rsi
0x180062244  push    rdi
0x180062245  push    r12
0x180062247  push    r13
0x180062249  push    r14
0x18006224b  push    r15
0x18006224d  lea     rbp, [rsp-8]
0x180062252  sub     rsp, 108h
0x180062259  mov     rax, cs:__security_cookie
0x180062260  xor     rax, rsp
0x180062263  mov     [rbp+40h+var_50], rax
0x180062267  xor     r14d, r14d
0x18006226a  mov     esi, r9d
0x18006226d  mov     dword ptr [rsp+140h+pbOutput], r14d
0x180062272  mov     r13, r8
0x180062275  mov     qword ptr [rsp+140h+var_E8], r14
0x18006227a  mov     r12, rdx
0x18006227d  mov     [rsp+140h+phHash], r14
0x180062282  mov     r15, rcx
0x180062285  mov     [rsp+140h+hHash], r14
0x18006228a  mov     [rsp+140h+var_FC], r14d
0x18006228f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062296  lea     rax, WPP_GLOBAL_Control
0x18006229d  mov     ebx, [rbp+40h+dwFlags]
0x1800622a0  cmp     rcx, rax
0x1800622a3  jz      short loc_1800622CE
0x1800622a5  mov     eax, [rcx+2Ch]
0x1800622a8  test    al, 4
0x1800622aa  jz      short loc_1800622CE
0x1800622ac  mov     rcx, [rcx+18h]
0x1800622b0  lea     edx, [r14+29h]
0x1800622b4  mov     [rsp+140h+var_108], ebx
0x1800622b8  mov     r9, r15
0x1800622bb  mov     [rsp+140h+var_110], esi
0x1800622bf  mov     qword ptr [rsp+140h+cbSecret], r8
0x1800622c4  mov     [rsp+140h+pcbResult], r12
0x1800622c9  call    WPP_SF_qqqdD
0x1800622ce  test    ebx, ebx
0x1800622d0  jnz     loc_1800625D4
0x1800622d6  test    r13, r13
0x1800622d9  jz      loc_1800625D4
0x1800622df  test    esi, esi
0x1800622e1  jz      loc_1800625D4
0x1800622e7  lea     rax, [rsp+140h+var_FC]
0x1800622ec  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x1800622f1  lea     r9d, [rbx+4]; cbOutput
0x1800622f5  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1800622fa  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x1800622ff  mov     rcx, r15; hObject
0x180062302  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180062309  call    BCryptGetProperty
0x18006230e  mov     ebx, eax
0x180062310  test    eax, eax
0x180062312  jns     short loc_180062321
0x180062314  mov     r9d, 1BF8h
0x18006231a  mov     ecx, eax
0x18006231c  jmp     loc_1800625E4
0x180062321  mov     eax, dword ptr [rsp+140h+pbOutput]
0x180062325  lea     ecx, [rax+rax]
0x180062328  cmp     ecx, esi
0x18006232a  jb      loc_1800625CC
0x180062330  cmp     eax, 40h ; '@'
0x180062333  ja      loc_1800625CC
0x180062339  call    MSCryptAlloc
0x18006233e  mov     rdi, rax
0x180062341  test    rax, rax
0x180062344  jnz     short loc_18006235B
0x180062346  mov     ebx, 0C0000017h
0x18006234b  mov     r9d, 1C0Fh
0x180062351  mov     ecx, 0C0000017h
0x180062356  jmp     loc_1800625E4
0x18006235b  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x180062360  xor     r9d, r9d; dwFlags
0x180062363  mov     rdx, rdi; pbOutput
0x180062366  mov     rcx, r15; hHash
0x180062369  call    BCryptFinishHash
0x18006236e  mov     ebx, eax
0x180062370  test    eax, eax
0x180062372  jns     short loc_180062394
0x180062374  mov     r9d, 1C19h
0x18006237a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180062381  mov     ecx, eax
0x180062383  lea     rdx, aStatus; "Status"
0x18006238a  call    DebugTraceError
0x18006238f  jmp     loc_1800625C2
0x180062394  mov     ebx, r14d
0x180062397  mov     eax, 1
0x18006239c  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x1800623a1  cmp     r14d, esi
0x1800623a4  cmovb   ebx, eax
0x1800623a7  test    r12, r12
0x1800623aa  jz      short loc_180062422
0x1800623ac  cmp     esi, 10h
0x1800623af  jnz     short loc_180062422
0x1800623b1  cmp     r14d, 20h ; ' '
0x1800623b5  jnb     short loc_180062422
0x1800623b7  lea     rax, [rsp+140h+var_FC]
0x1800623bc  mov     [rsp+140h+cbSecret], 0; dwFlags
0x1800623c4  lea     r9d, [rsi-8]; cbOutput
0x1800623c8  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1800623cd  lea     r8, [rsp+140h+var_D8]; pbOutput
0x1800623d2  mov     rcx, r12; hObject
0x1800623d5  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800623dc  call    BCryptGetProperty
0x1800623e1  test    eax, eax
0x1800623e3  jns     short loc_180062402
0x1800623e5  mov     r9d, 1C35h
0x1800623eb  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800623f2  lea     rdx, aStatus; "Status"
0x1800623f9  mov     ecx, eax
0x1800623fb  call    DebugTraceError
0x180062400  jmp     short loc_18006241D
0x180062402  lea     rdx, aAes; "AES"
0x180062409  lea     rcx, [rsp+140h+var_D8]; Str1
0x18006240e  call    wcscmp_0
0x180062413  test    eax, eax
0x180062415  mov     eax, 1
0x18006241a  cmovz   ebx, eax
0x18006241d  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x180062422  test    ebx, ebx
0x180062424  jz      loc_1800625AE
0x18006242a  mov     r12d, 40h ; '@'
0x180062430  lea     rcx, [rsp+140h+pbInput]; void *
0x180062435  mov     r8d, r12d; Size
0x180062438  lea     edx, [r12-0Ah]; Val
0x18006243d  call    memset
0x180062442  mov     r8d, r12d; Size
0x180062445  lea     edx, [r12+1Ch]; Val
0x18006244a  lea     rcx, [rbp+40h+var_90]; void *
0x18006244e  call    memset
0x180062453  xor     r8d, r8d
0x180062456  test    r14d, r14d
0x180062459  jz      short loc_180062471
0x18006245b  mov     al, [r8+rdi]
0x18006245f  xor     [rsp+r8+140h+pbInput], al
0x180062464  xor     [rbp+r8+40h+var_90], al
0x180062469  inc     r8d
0x18006246c  cmp     r8d, r14d
0x18006246f  jb      short loc_18006245B
0x180062471  xor     r14d, r14d
0x180062474  lea     rax, [rsp+140h+var_FC]
0x180062479  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x18006247e  lea     r8, [rsp+140h+var_E8]; pbOutput
0x180062483  lea     rdx, aProviderhandle; "ProviderHandle"
0x18006248a  mov     [rsp+140h+pcbResult], rax; pcbResult
0x18006248f  mov     rcx, r15; hObject
0x180062492  lea     r9d, [r14+8]; cbOutput
0x180062496  call    BCryptGetProperty
0x18006249b  mov     ebx, eax
0x18006249d  test    eax, eax
0x18006249f  jns     short loc_1800624AC
0x1800624a1  mov     r9d, 1C5Ch
0x1800624a7  jmp     loc_18006237A
0x1800624ac  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x1800624b1  lea     rdx, [rsp+140h+phHash]; phHash
0x1800624b6  mov     [rsp+140h+var_110], r14d; dwFlags
0x1800624bb  xor     r9d, r9d; cbHashObject
0x1800624be  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x1800624c3  xor     r8d, r8d; pbHashObject
0x1800624c6  mov     [rsp+140h+pcbResult], r14; pbSecret
0x1800624cb  call    BCryptCreateHash
0x1800624d0  mov     ebx, eax
0x1800624d2  test    eax, eax
0x1800624d4  jns     short loc_1800624E1
0x1800624d6  mov     r9d, 1C69h
0x1800624dc  jmp     loc_18006237A
0x1800624e1  mov     rcx, [rsp+140h+phHash]; hHash
0x1800624e6  lea     rdx, [rsp+140h+pbInput]; pbInput
0x1800624eb  xor     r9d, r9d; dwFlags
0x1800624ee  mov     r8d, r12d; cbInput
0x1800624f1  call    BCryptHashData
0x1800624f6  mov     ebx, eax
0x1800624f8  test    eax, eax
0x1800624fa  jns     short loc_180062507
0x1800624fc  mov     r9d, 1C73h
0x180062502  jmp     loc_18006237A
0x180062507  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x18006250c  xor     r9d, r9d; dwFlags
0x18006250f  mov     rcx, [rsp+140h+phHash]; hHash
0x180062514  mov     rdx, rdi; pbOutput
0x180062517  call    BCryptFinishHash
0x18006251c  mov     ebx, eax
0x18006251e  test    eax, eax
0x180062520  jns     short loc_18006252D
0x180062522  mov     r9d, 1C7Dh
0x180062528  jmp     loc_18006237A
0x18006252d  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x180062532  lea     rdx, [rsp+140h+hHash]; phHash
0x180062537  mov     [rsp+140h+var_110], r14d; dwFlags
0x18006253c  xor     r9d, r9d; cbHashObject
0x18006253f  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x180062544  xor     r8d, r8d; pbHashObject
0x180062547  mov     [rsp+140h+pcbResult], r14; pbSecret
0x18006254c  call    BCryptCreateHash
0x180062551  mov     ebx, eax
0x180062553  test    eax, eax
0x180062555  jns     short loc_180062562
0x180062557  mov     r9d, 1C8Ah
0x18006255d  jmp     loc_18006237A
0x180062562  mov     rcx, [rsp+140h+hHash]; hHash
0x180062567  lea     rdx, [rbp+40h+var_90]; pbInput
0x18006256b  xor     r9d, r9d; dwFlags
0x18006256e  mov     r8d, r12d; cbInput
0x180062571  call    BCryptHashData
0x180062576  mov     ebx, eax
0x180062578  test    eax, eax
0x18006257a  jns     short loc_180062587
0x18006257c  mov     r9d, 1C94h
0x180062582  jmp     loc_18006237A
0x180062587  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x18006258c  xor     r9d, r9d; dwFlags
0x18006258f  mov     rcx, [rsp+140h+hHash]; hHash
0x180062594  lea     rdx, [rdi+r8]; pbOutput
0x180062598  call    BCryptFinishHash
0x18006259d  mov     ebx, eax
0x18006259f  test    eax, eax
0x1800625a1  jns     short loc_1800625B1
0x1800625a3  mov     r9d, 1C9Eh
0x1800625a9  jmp     loc_18006237A
0x1800625ae  xor     r14d, r14d
0x1800625b1  mov     r8, rsi; Size
0x1800625b4  mov     rdx, rdi; Src
0x1800625b7  mov     rcx, r13; void *
0x1800625ba  call    memmove
0x1800625bf  mov     ebx, r14d
0x1800625c2  mov     rcx, rdi; P
0x1800625c5  call    MSCryptFree
0x1800625ca  jmp     short loc_1800625F7
0x1800625cc  mov     r9d, 1BFFh
0x1800625d2  jmp     short loc_1800625DA
0x1800625d4  mov     r9d, 1BE2h
0x1800625da  mov     ecx, 0C000000Dh
0x1800625df  mov     ebx, 0C000000Dh
0x1800625e4  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800625eb  lea     rdx, aStatus; "Status"
0x1800625f2  call    DebugTraceError
0x1800625f7  mov     rcx, [rsp+140h+phHash]; hHash
0x1800625fc  test    rcx, rcx
0x1800625ff  jz      short loc_180062606
0x180062601  call    BCryptDestroyHash
0x180062606  mov     rcx, [rsp+140h+hHash]; hHash
0x18006260b  test    rcx, rcx
0x18006260e  jz      short loc_180062615
0x180062610  call    BCryptDestroyHash
0x180062615  mov     eax, ebx
0x180062617  mov     rcx, [rbp+40h+var_50]
0x18006261b  xor     rcx, rsp; StackCookie
0x18006261e  call    __security_check_cookie
0x180062623  add     rsp, 108h
0x18006262a  pop     r15
0x18006262c  pop     r14
0x18006262e  pop     r13
0x180062630  pop     r12
0x180062632  pop     rdi
0x180062633  pop     rsi
0x180062634  pop     rbx
0x180062635  pop     rbp
0x180062636  retn
```
