# MSCryptKDImportKey

- ea: `0x18000f790`
- end: `0x18000ff24`
- name: `MSCryptKDImportKey`
- size: `1940`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007e940`

## callees

- `0x18000e090`
- `0x18000f790`
- `0x18000ff30`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180041010`
- `0x1800a4232`
- `0x1800a4300`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000fa44`
- `ntoskrnl!ExAllocatePool2` at `0x18000fa44`
- `ntoskrnl!SkIsSecureKernel` at `0x18000fd90`
- `ntoskrnl!SkIsSecureKernel` at `0x18000fd90`
- `ntoskrnl!SkAllocatePool` at `0x18000fe60`
- `ntoskrnl!SkAllocatePool` at `0x18000fe60`

## string_xrefs

- `0x18000f95b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fb01`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fb57`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fbbf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fc0a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fc37`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fcac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fd04`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fd5b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fd84`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fdb1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fdde`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fe77`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fe9f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000fef7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800a5ab9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDImportKey(
        _DWORD *a1,
        int a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned int a8,
        int a9)
{
  unsigned int v9; // edi
  int v12; // r13d
  __int64 v13; // rdx
  char *v14; // rbx
  char *v15; // rax
  char v16; // cl
  const void *v17; // r14
  unsigned int v18; // ecx
  unsigned int v19; // ebx
  char v20; // r14
  void *v21; // rcx
  void *v22; // rax
  int v23; // r8d
  int v24; // eax
  void *Pool; // rax
  int v26; // edx
  int v27; // r8d
  wchar_t *v28; // rcx
  unsigned int (__fastcall **SymCryptMacAlgorithm)(__int64, __int64, __int64); // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  int v33; // edx
  int v34; // r8d
  __int64 v35; // r9
  size_t Size[2]; // [rsp+40h] [rbp-38h] BYREF

  v9 = 0;
  LODWORD(Size[0]) = 0;
  if ( a9 )
  {
    v19 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        198);
    return v19;
  }
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        7);
    goto LABEL_54;
  }
  if ( a1[1] != 1297301836 || *a1 != 20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
    goto LABEL_54;
  }
  v12 = a1[2];
  if ( (unsigned int)(v12 - 393217) > 6 )
  {
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      286);
LABEL_54:
    v19 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v33 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v33 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v33,
          (_DWORD)a3,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          208);
    }
    return v19;
  }
  if ( !a5 || !a7 )
  {
    v35 = 2014;
    goto LABEL_93;
  }
  if ( !a3 )
  {
    v35 = 2021;
LABEL_93:
    v19 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v35);
    return v19;
  }
  if ( !a4 )
  {
    v35 = 2028;
    goto LABEL_93;
  }
  if ( wcscmp_0(a3, L"KeyDataBlob") )
  {
    v19 = -1073741637;
    DebugTraceError(
      3221225659LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      2137);
    return v19;
  }
  if ( a8 < 0xC || (v13 = (unsigned int)a7[2], a8 < (unsigned __int64)(v13 + 12)) )
  {
    v35 = 2045;
    goto LABEL_93;
  }
  if ( *a7 != 1296188491 || a7[1] != 1 )
  {
    v35 = 2053;
    goto LABEL_93;
  }
  v14 = (char *)(a7 + 3);
  if ( v12 != 393223 )
  {
    v17 = 0;
    goto LABEL_20;
  }
  v15 = (char *)Size + 3;
  do
  {
    v16 = *v14++;
    *v15-- = v16;
  }
  while ( v15 >= (char *)Size );
  v9 = Size[0];
  if ( LODWORD(Size[0]) > (unsigned __int64)(v13 - 4) )
  {
    v35 = 2074;
    goto LABEL_93;
  }
  v17 = a7 + 4;
  v13 = (unsigned int)(-4 - LODWORD(Size[0]) + v13);
  v14 = (char *)a7 + LODWORD(Size[0]) + 16;
LABEL_20:
  if ( !v14 )
  {
    v19 = -1073741811;
    v20 = 13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        0,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        98);
    goto LABEL_28;
  }
  if ( v12 != 393217 && (unsigned int)(v12 - 393218) > 5 )
  {
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      286);
    v19 = -1073741816;
    v20 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v34,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        110);
LABEL_28:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        0,
        (unsigned int)"Status",
        v20,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        41);
    return v19;
  }
  if ( a6 < 0x280 )
  {
    v19 = -1073741789;
    v20 = 35;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        0,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        118);
    goto LABEL_28;
  }
  v18 = 0;
  *(_DWORD *)a5 = a1[3];
  *(_DWORD *)(a5 + 4) = 1297304409;
  *(_DWORD *)(a5 + 8) = a1[2];
  *(_DWORD *)(a5 + 32) = a1[4];
  *(_QWORD *)(a5 + 40) = a1;
  *(_DWORD *)(a5 + 48) = 0;
  *(_QWORD *)(a5 + 72) = 0;
  *(_QWORD *)(a5 + 56) = 0;
  *(_DWORD *)(a5 + 64) = 0;
  *(_DWORD *)(a5 + 16) = v13;
  switch ( a1[2] )
  {
    case 0x60001:
    case 0x60002:
    case 0x60003:
    case 0x60004:
    case 0x60005:
    case 0x60006:
    case 0x60007:
      v18 = 2048;
      break;
    default:
      break;
  }
  if ( (unsigned int)v13 > v18 )
  {
    v19 = -1073741811;
    v20 = 13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        0,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        194);
    goto LABEL_28;
  }
  *(_DWORD *)(a5 + 12) = 8 * v13;
  v22 = (void *)MSCryptAlloc((unsigned int)v13, v13);
  *(_QWORD *)(a5 + 24) = v22;
  if ( !v22 )
  {
    v19 = -1073741801;
    v20 = 23;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v23,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        213);
    goto LABEL_28;
  }
  memmove(v22, v14, *(unsigned int *)(a5 + 16));
  if ( !v17 || !v9 )
  {
LABEL_45:
    *a4 = a5;
    return 0;
  }
  LOBYTE(v24) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    v24 = ((int)SkIsSecureKernel() >> 31) + 2;
    g_TrustedEnvironment = v24;
  }
  if ( (v24 & 2) != 0 )
    Pool = (void *)SkAllocatePool(512, v9, 1650945603);
  else
    Pool = (void *)ExAllocatePool2(64, v9, 1650945603);
  *(_QWORD *)(a5 + 56) = Pool;
  if ( Pool )
  {
    memmove(Pool, v17, v9);
    v28 = *(wchar_t **)(a5 + 56);
    *(_DWORD *)(a5 + 64) = v9;
    SymCryptMacAlgorithm = (unsigned int (__fastcall **)(__int64, __int64, __int64))GetSymCryptMacAlgorithm(v28);
    *(_QWORD *)(a5 + 72) = SymCryptMacAlgorithm;
    if ( SymCryptMacAlgorithm )
    {
      v30 = *(unsigned int *)(a5 + 16);
      v31 = *(_QWORD *)(a5 + 24);
      *(_QWORD *)(a5 + 624) = SymCryptMacAlgorithm;
      if ( !(*SymCryptMacAlgorithm)(a5 + 80, v31, v30) )
      {
        *(_DWORD *)(a5 + 48) = 1;
        goto LABEL_45;
      }
      v19 = -1073741823;
      DebugTraceError(
        3221225473LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        2127);
    }
    else
    {
      v19 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        2115);
    }
  }
  else
  {
    v19 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v27,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        54);
  }
  v21 = *(void **)(a5 + 56);
  if ( v21 )
  {
    MSCryptFree(v21);
    *(_QWORD *)(a5 + 56) = 0;
  }
  MSCryptKDDestroyKey(a5);
  return v19;
}

```

## disassembly

```asm
0x18000f790  mov     rax, rsp
0x18000f793  mov     [rax+10h], rbx
0x18000f797  mov     [rax+18h], rbp
0x18000f79b  push    rsi
0x18000f79c  push    rdi
0x18000f79d  push    r12
0x18000f79f  push    r14
0x18000f7a1  push    r15
0x18000f7a3  sub     rsp, 50h
0x18000f7a7  xor     edi, edi
0x18000f7a9  mov     r12, r9
0x18000f7ac  mov     rsi, rcx
0x18000f7af  mov     [rax-38h], edi
0x18000f7b2  cmp     [rsp+78h+arg_40], edi
0x18000f7b9  jnz     loc_18000FCD9
0x18000f7bf  mov     [rax+8], r13
0x18000f7c3  test    rcx, rcx
0x18000f7c6  jz      loc_18000FB39
0x18000f7cc  cmp     dword ptr [rcx+4], 4D53414Ch
0x18000f7d3  jnz     loc_18000FC86
0x18000f7d9  cmp     dword ptr [rcx], 14h
0x18000f7dc  jnz     loc_18000FC86
0x18000f7e2  mov     r13d, [rcx+8]
0x18000f7e6  lea     eax, [r13-60001h]
0x18000f7ed  cmp     eax, 6
0x18000f7f0  ja      loc_18000FDDE
0x18000f7f6  mov     r15, [rsp+78h+arg_20]
0x18000f7fe  test    r15, r15
0x18000f801  jz      loc_18000FF19
0x18000f807  mov     r14, [rsp+78h+arg_30]
0x18000f80f  test    r14, r14
0x18000f812  jz      loc_18000FF19
0x18000f818  test    r8, r8
0x18000f81b  jz      loc_18000FE0B
0x18000f821  test    r9, r9
0x18000f824  jz      loc_18000FE16
0x18000f82a  lea     rdx, aKeydatablob; "KeyDataBlob"
0x18000f831  mov     rcx, r8; Str1
0x18000f834  call    wcscmp_0
0x18000f839  test    eax, eax
0x18000f83b  jnz     loc_18000FEF1
0x18000f841  mov     eax, [rsp+78h+arg_38]
0x18000f848  cmp     eax, 0Ch
0x18000f84b  jb      loc_18000FEE6
0x18000f851  mov     edx, [r14+8]
0x18000f855  lea     rcx, [rdx+0Ch]
0x18000f859  cmp     rax, rcx
0x18000f85c  jb      loc_18000FEE6
0x18000f862  cmp     dword ptr [r14], 4D42444Bh
0x18000f869  jnz     loc_18000FEDB
0x18000f86f  cmp     dword ptr [r14+4], 1
0x18000f874  jnz     loc_18000FEDB
0x18000f87a  lea     rbx, [r14+0Ch]
0x18000f87e  cmp     r13d, 60007h
0x18000f885  jnz     loc_18000FB2E
0x18000f88b  lea     rax, [rsp+78h+Size+3]
0x18000f890  movzx   ecx, byte ptr [rbx]
0x18000f893  lea     rbx, [rbx+1]
0x18000f897  mov     [rax], cl
0x18000f899  dec     rax
0x18000f89c  lea     rcx, [rsp+78h+Size]
0x18000f8a1  cmp     rax, rcx
0x18000f8a4  jnb     short loc_18000F890
0x18000f8a6  mov     edi, dword ptr [rsp+78h+Size]
0x18000f8aa  lea     rax, [rdx-4]
0x18000f8ae  cmp     rdi, rax
0x18000f8b1  ja      loc_18000FE21
0x18000f8b7  add     r14, 10h
0x18000f8bb  mov     eax, 0FFFFFFFCh
0x18000f8c0  sub     eax, edi
0x18000f8c2  add     edx, eax
0x18000f8c4  xor     r8d, r8d
0x18000f8c7  lea     rbx, [r14+rdi]
0x18000f8cb  mov     rbp, r8
0x18000f8ce  test    rbx, rbx
0x18000f8d1  jz      loc_18000FD31
0x18000f8d7  cmp     r13d, 60001h
0x18000f8de  jnz     loc_18000FE2C
0x18000f8e4  cmp     [rsp+78h+arg_28], 280h
0x18000f8ef  jb      loc_18000FBA9
0x18000f8f5  mov     eax, [rsi+0Ch]
0x18000f8f8  mov     ecx, r8d
0x18000f8fb  mov     [r15], eax
0x18000f8fe  mov     dword ptr [r15+4], 4D534B59h
0x18000f906  mov     eax, [rsi+8]
0x18000f909  mov     [r15+8], eax
0x18000f90d  mov     eax, [rsi+10h]
0x18000f910  mov     [r15+20h], eax
0x18000f914  mov     [r15+28h], rsi
0x18000f918  mov     [r15+30h], r8d
0x18000f91c  mov     [r15+48h], r8
0x18000f920  mov     [r15+38h], r8
0x18000f924  mov     [r15+40h], r8d
0x18000f928  mov     [r15+10h], edx
0x18000f92c  mov     eax, [rsi+8]
0x18000f92f  add     eax, 0FFF9FFFFh; switch 7 cases
0x18000f934  cmp     eax, 6
0x18000f937  jbe     loc_1800A5A86
0x18000f93d  cmp     edx, ecx; jumptable 00000001800A5A98 default case
0x18000f93f  jbe     loc_18000F9D2
0x18000f945  mov     ebx, 0C000000Dh
0x18000f94a  mov     r14d, ebx
0x18000f94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f954  lea     rsi, WPP_GLOBAL_Control
0x18000f95b  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f962  cmp     rcx, rsi
0x18000f965  jz      short loc_18000F972
0x18000f967  mov     eax, [rcx+2Ch]
0x18000f96a  test    al, 1
0x18000f96c  jnz     loc_18000FEC1
0x18000f972  mov     r15, r8
0x18000f975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97c  cmp     rcx, rsi
0x18000f97f  jz      short loc_18000F9AA
0x18000f981  mov     eax, [rcx+2Ch]
0x18000f984  test    al, 1
0x18000f986  jz      short loc_18000F9AA
0x18000f988  mov     rcx, [rcx+18h]
0x18000f98c  lea     r9, aStatus; "Status"
0x18000f993  mov     [rsp+78h+var_48], 829h
0x18000f99b  mov     [rsp+78h+var_50], rdi
0x18000f9a0  mov     [rsp+78h+var_58], r14d
0x18000f9a5  call    WPP_SF_sDsd
0x18000f9aa  test    rbp, rbp
0x18000f9ad  jz      loc_18000FAB2
0x18000f9b3  mov     rcx, [r15+38h]; P
0x18000f9b7  test    rcx, rcx
0x18000f9ba  jz      loc_1800A5AAB
0x18000f9c0  call    MSCryptFree
0x18000f9c5  mov     qword ptr [r15+38h], 0
0x18000f9cd  jmp     loc_1800A5AAB
0x18000f9d2  lea     eax, ds:0[rdx*8]
0x18000f9d9  mov     ecx, edx
0x18000f9db  mov     [r15+0Ch], eax
0x18000f9df  call    MSCryptAlloc
0x18000f9e4  mov     [r15+18h], rax
0x18000f9e8  test    rax, rax
0x18000f9eb  jz      loc_18000FBF4
0x18000f9f1  mov     r8d, [r15+10h]; Size
0x18000f9f5  mov     rdx, rbx; Src
0x18000f9f8  mov     rcx, rax; void *
0x18000f9fb  call    memmove
0x18000fa00  mov     rbp, r15
0x18000fa03  test    r14, r14
0x18000fa06  jz      loc_18000FAAC
0x18000fa0c  test    edi, edi
0x18000fa0e  jz      loc_18000FAAC
0x18000fa14  mov     eax, 8
0x18000fa19  mov     ebx, edi
0x18000fa1b  cmovz   ebx, eax
0x18000fa1e  mov     esi, edi
0x18000fa20  mov     eax, cs:g_TrustedEnvironment
0x18000fa26  test    eax, eax
0x18000fa28  jz      loc_18000FD90
0x18000fa2e  mov     r8d, 62676E43h
0x18000fa34  mov     rdx, rbx
0x18000fa37  test    al, 2
0x18000fa39  jnz     loc_18000FE5B
0x18000fa3f  mov     ecx, 40h ; '@'
0x18000fa44  call    cs:__imp_ExAllocatePool2
0x18000fa4b  nop     dword ptr [rax+rax+00h]
0x18000fa50  mov     [r15+38h], rax
0x18000fa54  test    rax, rax
0x18000fa57  jz      short loc_18000FAD6
0x18000fa59  mov     r8, rsi; Size
0x18000fa5c  mov     rdx, r14; Src
0x18000fa5f  mov     rcx, rax; void *
0x18000fa62  call    memmove
0x18000fa67  mov     rcx, [r15+38h]; Str1
0x18000fa6b  mov     [r15+40h], edi
0x18000fa6f  call    GetSymCryptMacAlgorithm
0x18000fa74  mov     [r15+48h], rax
0x18000fa78  test    rax, rax
0x18000fa7b  jz      loc_18000FE71
0x18000fa81  mov     r8d, [r15+10h]
0x18000fa85  lea     rcx, [r15+50h]
0x18000fa89  mov     rdx, [r15+18h]
0x18000fa8d  mov     [rcx+220h], rax
0x18000fa94  mov     rax, [rax]
0x18000fa97  call    _guard_dispatch_icall
0x18000fa9c  test    eax, eax
0x18000fa9e  jnz     loc_18000FE99
0x18000faa4  mov     dword ptr [r15+30h], 1
0x18000faac  mov     [r12], r15
0x18000fab0  xor     ebx, ebx
0x18000fab2  mov     r13, [rsp+78h+arg_0]
0x18000faba  lea     r11, [rsp+78h+var_28]
0x18000fabf  mov     eax, ebx
0x18000fac1  mov     rbx, [r11+38h]
0x18000fac5  mov     rbp, [r11+40h]
0x18000fac9  mov     rsp, r11
0x18000facc  pop     r15
0x18000face  pop     r14
0x18000fad0  pop     r12
0x18000fad2  pop     rdi
0x18000fad3  pop     rsi
0x18000fad4  retn
0x18000fad6  mov     ebx, 0C0000017h
0x18000fadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fae2  lea     rsi, WPP_GLOBAL_Control
0x18000fae9  cmp     rcx, rsi
0x18000faec  jz      loc_18000F9B3
0x18000faf2  mov     eax, [rcx+2Ch]
0x18000faf5  test    al, 1
0x18000faf7  jz      loc_18000F9B3
0x18000fafd  mov     rcx, [rcx+18h]
0x18000fb01  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fb08  mov     [rsp+78h+var_48], 836h
0x18000fb10  lea     r9, aStatus; "Status"
0x18000fb17  mov     [rsp+78h+var_50], rdi
0x18000fb1c  mov     [rsp+78h+var_58], 0C0000017h
0x18000fb24  call    WPP_SF_sDsd
0x18000fb29  jmp     loc_18000F9B3
0x18000fb2e  xor     r8d, r8d
0x18000fb31  mov     r14d, r8d
0x18000fb34  jmp     loc_18000F8CB
0x18000fb39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb40  lea     rsi, WPP_GLOBAL_Control
0x18000fb47  cmp     rcx, rsi
0x18000fb4a  jz      short loc_18000FB57
0x18000fb4c  mov     eax, [rcx+2Ch]
0x18000fb4f  test    al, 1
0x18000fb51  jnz     loc_18000FDAD
0x18000fb57  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fb5e  mov     ebx, 0C0000008h
0x18000fb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb6a  cmp     rcx, rsi
0x18000fb6d  jz      loc_18000FAB2
0x18000fb73  mov     edx, [rcx+2Ch]
0x18000fb76  test    dl, 1
0x18000fb79  jz      loc_18000FAB2
0x18000fb7f  mov     rcx, [rcx+18h]
0x18000fb83  lea     r9, aStatus; "Status"
0x18000fb8a  mov     [rsp+78h+var_48], 7D0h
0x18000fb92  mov     [rsp+78h+var_50], rdi
0x18000fb97  mov     [rsp+78h+var_58], 0C0000008h
0x18000fb9f  call    WPP_SF_sDsd
0x18000fba4  jmp     loc_18000FAB2
0x18000fba9  mov     ebx, 0C0000023h
0x18000fbae  mov     r14d, ebx
0x18000fbb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb8  lea     rsi, WPP_GLOBAL_Control
0x18000fbbf  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fbc6  cmp     rcx, rsi
0x18000fbc9  jz      loc_18000F972
0x18000fbcf  mov     eax, [rcx+2Ch]
0x18000fbd2  test    al, 1
0x18000fbd4  jz      loc_18000F972
0x18000fbda  mov     [rsp+78h+var_48], 576h
0x18000fbe2  mov     [rsp+78h+var_50], rdi
0x18000fbe7  mov     [rsp+78h+var_58], 0C0000023h
0x18000fbef  jmp     loc_18000FD6F
0x18000fbf4  mov     ebx, 0C0000017h
0x18000fbf9  mov     r14d, ebx
0x18000fbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc03  lea     rsi, WPP_GLOBAL_Control
0x18000fc0a  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fc11  cmp     rcx, rsi
0x18000fc14  jz      short loc_18000FC7E
0x18000fc16  mov     eax, [rcx+2Ch]
0x18000fc19  test    al, 1
0x18000fc1b  jz      short loc_18000FC7E
0x18000fc1d  mov     [rsp+78h+var_48], 5D5h
0x18000fc25  mov     [rsp+78h+var_50], rdi
0x18000fc2a  mov     [rsp+78h+var_58], 0C0000017h
0x18000fc32  jmp     loc_18000FD6F
0x18000fc37  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fc3e  mov     r9d, 11Eh
0x18000fc44  mov     r8, rdi
0x18000fc47  lea     rdx, aStatus; "Status"
0x18000fc4e  mov     ecx, 0C0000008h
0x18000fc53  call    DebugTraceError
0x18000fc58  mov     ebx, 0C0000008h
0x18000fc5d  mov     r14d, ebx
0x18000fc60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc67  lea     rsi, WPP_GLOBAL_Control
0x18000fc6e  cmp     rcx, rsi
0x18000fc71  jz      short loc_18000FC7E
0x18000fc73  mov     eax, [rcx+2Ch]
0x18000fc76  test    al, 1
0x18000fc78  jnz     loc_18000FE41
0x18000fc7e  xor     r8d, r8d
0x18000fc81  jmp     loc_18000F972
0x18000fc86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc8d  lea     rsi, WPP_GLOBAL_Control
0x18000fc94  cmp     rcx, rsi
0x18000fc97  jz      loc_18000FB57
0x18000fc9d  mov     eax, [rcx+2Ch]
0x18000fca0  test    al, 1
0x18000fca2  jz      loc_18000FB57
0x18000fca8  mov     rcx, [rcx+18h]
0x18000fcac  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fcb3  mov     [rsp+78h+var_48], 111h
0x18000fcbb  lea     r9, aStatus; "Status"
0x18000fcc2  mov     [rsp+78h+var_50], rdi
0x18000fcc7  mov     [rsp+78h+var_58], 0C0000008h
0x18000fccf  call    WPP_SF_sDsd
0x18000fcd4  jmp     loc_18000FB5E
0x18000fcd9  mov     ebx, 0C000000Dh
0x18000fcde  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
