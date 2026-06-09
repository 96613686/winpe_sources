# MSCryptGetProperty

- ea: `0x1800218d0`
- end: `0x180021c05`
- name: `MSCryptGetProperty`
- size: `821`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800210a0`
- `0x180021480`
- `0x180089854`

## callees

- `0x18001155c`
- `0x1800218d0`
- `0x1800442f0`
- `0x1800469f8`
- `0x18004b3c4`
- `0x180089900`
- `0x1800a4232`
- `0x1800a4244`
- `0x1800a45c0`

## string_xrefs

- `0x180021bde`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180021afb`: `[ BCRYPT_FIPS_SERVICE_INDICATOR]`
- `0x180021ae1`: `Algorithm Providers and Properties\n\nEncryption and Decryption\n	For symmetric encryption, hKey must not be created with hAlgorithm referring to BCRYPT_3DES_ALGORITHM, BCRYPT_3DES_112_ALGORITHM, BCRYPT_DES_ALGORITHM,  BCRYPT_DESX_ALGORITHM, BCRYPT_RC2_ALGORITHM, BCRYPT_RC4_ALGORITHM in the preceding call to BCryptGenerateSymmetricKey.\n	For asymmetric encryption, if pszAlgId is specified as BCRYPT_RSA_ALGORITHM in the preceding call to BCryptOpenAlgorithmProvider, the subsequent call to BCryptE`

## pseudocode

```c
__int64 __fastcall MSCryptGetProperty(__int64 a1, wchar_t *a2, _OWORD *a3, unsigned int a4, unsigned int *a5, int a6)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  _DWORD *v13; // rbp
  unsigned int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  wchar_t *v20; // rcx
  int AlgProperty; // eax
  int v22; // eax

  if ( (a6 & 0xFFFFFF7F) != 0 )
  {
    v10 = 2218;
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_60:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v10);
    return v11;
  }
  v13 = (_DWORD *)validateMSCryptSymmObject();
  if ( !v13 )
  {
    v10 = 2227;
LABEL_59:
    v12 = 3221225480LL;
    v11 = -1073741816;
    goto LABEL_60;
  }
  if ( !a5 )
  {
    v10 = 2234;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v14 = (unsigned __int16)v13[2] - 1;
    if ( v14 >= 9 )
    {
      v10 = 2245;
      goto LABEL_59;
    }
    v15 = 14LL * v14;
    v16 = -1;
    do
      ++v16;
    while ( (&off_1800AC088)[v15][v16] );
    v17 = 2 * v16 + 2;
    *a5 = v17;
    if ( !a3 )
      return 0;
    if ( a4 < v17 )
    {
      v10 = 2260;
LABEL_17:
      v11 = -1073741789;
      v12 = 3221225507LL;
      goto LABEL_60;
    }
    memmove(a3, (&off_1800AC088)[v15], v17);
    return 0;
  }
  if ( !wcscmp_0(a2, L"BlockLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 < 4 )
    {
      v10 = 2281;
      goto LABEL_17;
    }
    v18 = v13[4];
LABEL_24:
    *(_DWORD *)a3 = v18;
    return 0;
  }
  if ( !wcscmp_0(a2, L"MessageBlockLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 < 4 )
    {
      v10 = 2303;
      goto LABEL_17;
    }
    v18 = v13[5];
    goto LABEL_24;
  }
  if ( !wcscmp_0(a2, L"ChainingMode") )
  {
    *a5 = 32;
    if ( a3 )
    {
      if ( a4 < 0x20 )
      {
        v10 = 2327;
        goto LABEL_17;
      }
      v19 = (unsigned int)v13[3];
      if ( (unsigned int)v19 >= 6 )
      {
        v10 = 2334;
        goto LABEL_59;
      }
      v20 = rgpszChainModeNameArray[v19];
      *a3 = *(_OWORD *)v20;
      a3[1] = *((_OWORD *)v20 + 1);
    }
    return 0;
  }
  if ( !wcscmp_0(a2, L"DeprecatedDoNotUse3555") )
  {
    if ( a3 )
    {
      if ( a4 < 0xFED )
      {
        *a5 = 0;
        v10 = 2360;
        goto LABEL_17;
      }
      memmove(a3, aAlgorithmProvi, 0xFEDu);
    }
    *a5 = 4077;
    return 0;
  }
  if ( !wcsncmp_0(a2, L"[ BCRYPT_FIPS_SERVICE_INDICATOR]", 0x20u) )
  {
    if ( !a3 )
    {
      *a5 = 4;
      return 0;
    }
    if ( a4 < 4 )
    {
      *a5 = 0;
      v10 = 2389;
      goto LABEL_17;
    }
    AlgProperty = ApprovedServicesIndicator(a2);
    v11 = AlgProperty;
    if ( AlgProperty >= 0 )
    {
      *(_DWORD *)a3 = 0;
      *a5 = 4;
      return v11;
    }
    v10 = 2397;
LABEL_50:
    v12 = (unsigned int)AlgProperty;
    goto LABEL_60;
  }
  v22 = v13[1];
  if ( v22 == 1297306433 )
  {
    AlgProperty = MSCryptGetAlgProperty(a1, a2, a3, a4, a5, a6);
    v11 = AlgProperty;
    if ( AlgProperty >= 0 )
      return v11;
    v10 = 2418;
    goto LABEL_50;
  }
  if ( v22 != 1297306443 )
  {
    v10 = 2439;
    goto LABEL_59;
  }
  AlgProperty = MSCryptGetKeyProperty(a1, a2, a3, a4, a5);
  v11 = AlgProperty;
  if ( AlgProperty < 0 )
  {
    v10 = 2432;
    goto LABEL_50;
  }
  return v11;
}

```

## disassembly

```asm
0x1800218d0  push    rbx
0x1800218d2  push    rbp
0x1800218d3  push    rsi
0x1800218d4  push    rdi
0x1800218d5  push    r12
0x1800218d7  push    r13
0x1800218d9  push    r14
0x1800218db  push    r15
0x1800218dd  sub     rsp, 38h
0x1800218e1  mov     r12d, [rsp+78h+arg_28]
0x1800218e9  mov     ebx, r9d
0x1800218ec  mov     rdi, r8
0x1800218ef  mov     r14, rdx
0x1800218f2  mov     r15, rcx
0x1800218f5  test    r12d, 0FFFFFF7Fh
0x1800218fc  jz      short loc_180021913
0x1800218fe  mov     r9d, 8AAh
0x180021904  mov     ebx, 0C000000Dh
0x180021909  mov     ecx, 0C000000Dh
0x18002190e  jmp     loc_180021BDE
0x180021913  call    validateMSCryptSymmObject
0x180021918  xor     r13d, r13d
0x18002191b  mov     rbp, rax
0x18002191e  test    rax, rax
0x180021921  jnz     short loc_18002192E
0x180021923  mov     r9d, 8B3h
0x180021929  jmp     loc_180021BD4
0x18002192e  mov     rsi, [rsp+78h+arg_20]
0x180021936  test    rsi, rsi
0x180021939  jnz     short loc_180021943
0x18002193b  mov     r9d, 8BAh
0x180021941  jmp     short loc_180021904
0x180021943  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18002194a  mov     rcx, r14; Str1
0x18002194d  call    wcscmp_0
0x180021952  test    eax, eax
0x180021954  jnz     short loc_1800219D5
0x180021956  mov     eax, [rbp+8]
0x180021959  movzx   ecx, ax
0x18002195c  dec     ecx
0x18002195e  cmp     ecx, 9
0x180021961  jb      short loc_18002196E
0x180021963  mov     r9d, 8C5h
0x180021969  jmp     loc_180021BD4
0x18002196e  mov     eax, ecx
0x180021970  lea     rcx, cs:180000000h
0x180021977  imul    rdx, rax, 70h ; 'p'
0x18002197b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002197f  mov     r8, [rdx+rcx+0AC088h]
0x180021987  inc     rax
0x18002198a  cmp     [r8+rax*2], r13w
0x18002198f  jnz     short loc_180021987
0x180021991  lea     eax, ds:2[rax*2]
0x180021998  mov     [rsi], eax
0x18002199a  test    rdi, rdi
0x18002199d  jnz     short loc_1800219A7
0x18002199f  mov     ebx, r13d
0x1800219a2  jmp     loc_180021BF1
0x1800219a7  cmp     ebx, eax
0x1800219a9  jnb     short loc_1800219C0
0x1800219ab  mov     r9d, 8D4h
0x1800219b1  mov     ebx, 0C0000023h
0x1800219b6  mov     ecx, 0C0000023h
0x1800219bb  jmp     loc_180021BDE
0x1800219c0  mov     rdx, [rdx+rcx+0AC088h]; Src
0x1800219c8  mov     rcx, rdi; void *
0x1800219cb  mov     r8d, eax; Size
0x1800219ce  call    memmove
0x1800219d3  jmp     short loc_18002199F
0x1800219d5  lea     rdx, aBlocklength; "BlockLength"
0x1800219dc  mov     rcx, r14; Str1
0x1800219df  call    wcscmp_0
0x1800219e4  test    eax, eax
0x1800219e6  jnz     short loc_180021A07
0x1800219e8  mov     dword ptr [rsi], 4
0x1800219ee  test    rdi, rdi
0x1800219f1  jz      short loc_18002199F
0x1800219f3  cmp     ebx, 4
0x1800219f6  jnb     short loc_180021A00
0x1800219f8  mov     r9d, 8E9h
0x1800219fe  jmp     short loc_1800219B1
0x180021a00  mov     eax, [rbp+10h]
0x180021a03  mov     [rdi], eax
0x180021a05  jmp     short loc_18002199F
0x180021a07  lea     rdx, aMessageblockle; "MessageBlockLength"
0x180021a0e  mov     rcx, r14; Str1
0x180021a11  call    wcscmp_0
0x180021a16  test    eax, eax
0x180021a18  jnz     short loc_180021A3E
0x180021a1a  mov     dword ptr [rsi], 4
0x180021a20  test    rdi, rdi
0x180021a23  jz      loc_18002199F
0x180021a29  cmp     ebx, 4
0x180021a2c  jnb     short loc_180021A39
0x180021a2e  mov     r9d, 8FFh
0x180021a34  jmp     loc_1800219B1
0x180021a39  mov     eax, [rbp+14h]
0x180021a3c  jmp     short loc_180021A03
0x180021a3e  lea     rdx, aChainingmode; "ChainingMode"
0x180021a45  mov     rcx, r14; Str1
0x180021a48  call    wcscmp_0
0x180021a4d  test    eax, eax
0x180021a4f  jnz     short loc_180021AA5
0x180021a51  mov     dword ptr [rsi], 20h ; ' '
0x180021a57  test    rdi, rdi
0x180021a5a  jz      loc_18002199F
0x180021a60  cmp     ebx, 20h ; ' '
0x180021a63  jnb     short loc_180021A70
0x180021a65  mov     r9d, 917h
0x180021a6b  jmp     loc_1800219B1
0x180021a70  mov     eax, [rbp+0Ch]
0x180021a73  cmp     eax, 6
0x180021a76  jb      short loc_180021A83
0x180021a78  mov     r9d, 91Eh
0x180021a7e  jmp     loc_180021BD4
0x180021a83  lea     rcx, cs:180000000h
0x180021a8a  mov     rcx, ds:rva rgpszChainModeNameArray[rcx+rax*8]
0x180021a92  movups  xmm0, xmmword ptr [rcx]
0x180021a95  movups  xmmword ptr [rdi], xmm0
0x180021a98  movups  xmm1, xmmword ptr [rcx+10h]
0x180021a9c  movups  xmmword ptr [rdi+10h], xmm1
0x180021aa0  jmp     loc_18002199F
0x180021aa5  lea     rdx, aDeprecateddono; "DeprecatedDoNotUse3555"
0x180021aac  mov     rcx, r14; Str1
0x180021aaf  call    wcscmp_0
0x180021ab4  test    eax, eax
0x180021ab6  jnz     short loc_180021AF5
0x180021ab8  test    rdi, rdi
0x180021abb  jnz     short loc_180021AC8
0x180021abd  mov     dword ptr [rsi], 0FEDh
0x180021ac3  jmp     loc_18002199F
0x180021ac8  cmp     ebx, 0FEDh
0x180021ace  jnb     short loc_180021ADE
0x180021ad0  mov     [rsi], r13d
0x180021ad3  mov     r9d, 938h
0x180021ad9  jmp     loc_1800219B1
0x180021ade  mov     rcx, rdi; void *
0x180021ae1  lea     rdx, aAlgorithmProvi; "Algorithm Providers and Properties\n\nE"...
0x180021ae8  mov     r8d, 0FEDh; Size
0x180021aee  call    memmove
0x180021af3  jmp     short loc_180021ABD
0x180021af5  mov     r8d, 20h ; ' '; MaxCount
0x180021afb  lea     rdx, aBcryptFipsServ; "[ BCRYPT_FIPS_SERVICE_INDICATOR]"
0x180021b02  mov     rcx, r14; Str1
0x180021b05  call    wcsncmp_0
0x180021b0a  test    eax, eax
0x180021b0c  jnz     short loc_180021B70
0x180021b0e  mov     [rsp+78h+arg_28], r13d
0x180021b16  test    rdi, rdi
0x180021b19  jnz     short loc_180021B26
0x180021b1b  mov     dword ptr [rsi], 4
0x180021b21  jmp     loc_18002199F
0x180021b26  cmp     ebx, 4
0x180021b29  jnb     short loc_180021B39
0x180021b2b  mov     [rsi], r13d
0x180021b2e  mov     r9d, 955h
0x180021b34  jmp     loc_1800219B1
0x180021b39  lea     rdx, [rsp+78h+arg_28]
0x180021b41  mov     rcx, r14; Src
0x180021b44  call    ApprovedServicesIndicator
0x180021b49  mov     ebx, eax
0x180021b4b  test    eax, eax
0x180021b4d  jns     short loc_180021B5C
0x180021b4f  mov     r9d, 95Dh
0x180021b55  mov     ecx, eax
0x180021b57  jmp     loc_180021BDE
0x180021b5c  mov     eax, [rsp+78h+arg_28]
0x180021b63  mov     [rdi], eax
0x180021b65  mov     dword ptr [rsi], 4
0x180021b6b  jmp     loc_180021BF1
0x180021b70  mov     eax, [rbp+4]
0x180021b73  cmp     eax, 4D535341h
0x180021b78  jnz     short loc_180021BA3
0x180021b7a  mov     [rsp+78h+var_50], r12d
0x180021b7f  mov     r9d, ebx
0x180021b82  mov     r8, rdi
0x180021b85  mov     [rsp+78h+var_58], rsi
0x180021b8a  mov     rdx, r14
0x180021b8d  mov     rcx, r15
0x180021b90  call    MSCryptGetAlgProperty
0x180021b95  mov     ebx, eax
0x180021b97  test    eax, eax
0x180021b99  jns     short loc_180021BF1
0x180021b9b  mov     r9d, 972h
0x180021ba1  jmp     short loc_180021B55
0x180021ba3  cmp     eax, 4D53534Bh
0x180021ba8  jnz     short loc_180021BCE
0x180021baa  mov     r9d, ebx
0x180021bad  mov     [rsp+78h+var_58], rsi
0x180021bb2  mov     r8, rdi
0x180021bb5  mov     rdx, r14
0x180021bb8  mov     rcx, r15
0x180021bbb  call    MSCryptGetKeyProperty
0x180021bc0  mov     ebx, eax
0x180021bc2  test    eax, eax
0x180021bc4  jns     short loc_180021BF1
0x180021bc6  mov     r9d, 980h
0x180021bcc  jmp     short loc_180021B55
0x180021bce  mov     r9d, 987h
0x180021bd4  mov     ecx, 0C0000008h
0x180021bd9  mov     ebx, 0C0000008h
0x180021bde  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021be5  lea     rdx, aStatus; "Status"
0x180021bec  call    DebugTraceError
0x180021bf1  mov     eax, ebx
0x180021bf3  add     rsp, 38h
0x180021bf7  pop     r15
0x180021bf9  pop     r14
0x180021bfb  pop     r13
0x180021bfd  pop     r12
0x180021bff  pop     rdi
0x180021c00  pop     rsi
0x180021c01  pop     rbp
0x180021c02  pop     rbx
0x180021c03  retn
```
