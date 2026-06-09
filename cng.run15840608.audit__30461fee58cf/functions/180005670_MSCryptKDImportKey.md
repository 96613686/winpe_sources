# MSCryptKDImportKey

- ea: `0x180005670`
- end: `0x180005e04`
- name: `MSCryptKDImportKey`
- size: `1940`
- prototype: `__int64 __fastcall(_DWORD *, int, const wchar_t *, _QWORD *, __int64, unsigned int, _DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800747a0`

## callees

- `0x180003f70`
- `0x180005670`
- `0x180005e10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180036fa0`
- `0x18009d746`
- `0x18009d860`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180005924`
- `ntoskrnl!ExAllocatePool2` at `0x180005924`
- `ntoskrnl!SkIsSecureKernel` at `0x180005c70`
- `ntoskrnl!SkIsSecureKernel` at `0x180005c70`
- `ntoskrnl!SkAllocatePool` at `0x180005d40`
- `ntoskrnl!SkAllocatePool` at `0x180005d40`

## string_xrefs

- `0x18000583b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800059e1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005a37`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005a9f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005aea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005b17`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005b8c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005be4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005c3b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005c64`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005c91`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005cbe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005d57`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005d7f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005dd7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18009ed1b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  void *Pool; // rax
  int v28; // edx
  int v29; // r8d
  wchar_t *v30; // rcx
  unsigned int (__fastcall **SymCryptMacAlgorithm)(__int64, __int64, __int64); // rax
  __int64 v32; // r8
  __int64 v33; // rdx
  int v35; // edx
  int v36; // r8d
  __int64 v37; // r9
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
      v35 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v35 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v35,
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
    v37 = 2014;
    goto LABEL_93;
  }
  if ( !a3 )
  {
    v37 = 2021;
LABEL_93:
    v19 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v37);
    return v19;
  }
  if ( !a4 )
  {
    v37 = 2028;
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
    v37 = 2045;
    goto LABEL_93;
  }
  if ( *a7 != 1296188491 || a7[1] != 1 )
  {
    v37 = 2053;
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
    v37 = 2074;
    goto LABEL_93;
  }
  v17 = a7 + 4;
  LODWORD(v13) = -4 - LODWORD(Size[0]) + v13;
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
        v36,
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
  v22 = (void *)MSCryptAlloc((unsigned int)v13);
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
  LOBYTE(v26) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    v26 = ((int)SkIsSecureKernel(v25, v24) >> 31) + 2;
    g_TrustedEnvironment = v26;
  }
  if ( (v26 & 2) != 0 )
    Pool = (void *)SkAllocatePool(512, v9, 1650945603);
  else
    Pool = (void *)ExAllocatePool2(64, v9, 1650945603);
  *(_QWORD *)(a5 + 56) = Pool;
  if ( Pool )
  {
    memmove(Pool, v17, v9);
    v30 = *(wchar_t **)(a5 + 56);
    *(_DWORD *)(a5 + 64) = v9;
    SymCryptMacAlgorithm = (unsigned int (__fastcall **)(__int64, __int64, __int64))GetSymCryptMacAlgorithm(v30);
    *(_QWORD *)(a5 + 72) = SymCryptMacAlgorithm;
    if ( SymCryptMacAlgorithm )
    {
      v32 = *(unsigned int *)(a5 + 16);
      v33 = *(_QWORD *)(a5 + 24);
      *(_QWORD *)(a5 + 624) = SymCryptMacAlgorithm;
      if ( !(*SymCryptMacAlgorithm)(a5 + 80, v33, v32) )
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
        v28,
        v29,
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
0x180005670  mov     rax, rsp
0x180005673  mov     [rax+10h], rbx
0x180005677  mov     [rax+18h], rbp
0x18000567b  push    rsi
0x18000567c  push    rdi
0x18000567d  push    r12
0x18000567f  push    r14
0x180005681  push    r15
0x180005683  sub     rsp, 50h
0x180005687  xor     edi, edi
0x180005689  mov     r12, r9
0x18000568c  mov     rsi, rcx
0x18000568f  mov     [rax-38h], edi
0x180005692  cmp     [rsp+78h+arg_40], edi
0x180005699  jnz     loc_180005BB9
0x18000569f  mov     [rax+8], r13
0x1800056a3  test    rcx, rcx
0x1800056a6  jz      loc_180005A19
0x1800056ac  cmp     dword ptr [rcx+4], 4D53414Ch
0x1800056b3  jnz     loc_180005B66
0x1800056b9  cmp     dword ptr [rcx], 14h
0x1800056bc  jnz     loc_180005B66
0x1800056c2  mov     r13d, [rcx+8]
0x1800056c6  lea     eax, [r13-60001h]
0x1800056cd  cmp     eax, 6
0x1800056d0  ja      loc_180005CBE
0x1800056d6  mov     r15, [rsp+78h+arg_20]
0x1800056de  test    r15, r15
0x1800056e1  jz      loc_180005DF9
0x1800056e7  mov     r14, [rsp+78h+arg_30]
0x1800056ef  test    r14, r14
0x1800056f2  jz      loc_180005DF9
0x1800056f8  test    r8, r8
0x1800056fb  jz      loc_180005CEB
0x180005701  test    r9, r9
0x180005704  jz      loc_180005CF6
0x18000570a  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180005711  mov     rcx, r8; Str1
0x180005714  call    wcscmp_0
0x180005719  test    eax, eax
0x18000571b  jnz     loc_180005DD1
0x180005721  mov     eax, [rsp+78h+arg_38]
0x180005728  cmp     eax, 0Ch
0x18000572b  jb      loc_180005DC6
0x180005731  mov     edx, [r14+8]
0x180005735  lea     rcx, [rdx+0Ch]
0x180005739  cmp     rax, rcx
0x18000573c  jb      loc_180005DC6
0x180005742  cmp     dword ptr [r14], 4D42444Bh
0x180005749  jnz     loc_180005DBB
0x18000574f  cmp     dword ptr [r14+4], 1
0x180005754  jnz     loc_180005DBB
0x18000575a  lea     rbx, [r14+0Ch]
0x18000575e  cmp     r13d, 60007h
0x180005765  jnz     loc_180005A0E
0x18000576b  lea     rax, [rsp+78h+Size+3]
0x180005770  movzx   ecx, byte ptr [rbx]
0x180005773  lea     rbx, [rbx+1]
0x180005777  mov     [rax], cl
0x180005779  dec     rax
0x18000577c  lea     rcx, [rsp+78h+Size]
0x180005781  cmp     rax, rcx
0x180005784  jnb     short loc_180005770
0x180005786  mov     edi, dword ptr [rsp+78h+Size]
0x18000578a  lea     rax, [rdx-4]
0x18000578e  cmp     rdi, rax
0x180005791  ja      loc_180005D01
0x180005797  add     r14, 10h
0x18000579b  mov     eax, 0FFFFFFFCh
0x1800057a0  sub     eax, edi
0x1800057a2  add     edx, eax
0x1800057a4  xor     r8d, r8d
0x1800057a7  lea     rbx, [r14+rdi]
0x1800057ab  mov     rbp, r8
0x1800057ae  test    rbx, rbx
0x1800057b1  jz      loc_180005C11
0x1800057b7  cmp     r13d, 60001h
0x1800057be  jnz     loc_180005D0C
0x1800057c4  cmp     [rsp+78h+arg_28], 280h
0x1800057cf  jb      loc_180005A89
0x1800057d5  mov     eax, [rsi+0Ch]
0x1800057d8  mov     ecx, r8d
0x1800057db  mov     [r15], eax
0x1800057de  mov     dword ptr [r15+4], 4D534B59h
0x1800057e6  mov     eax, [rsi+8]
0x1800057e9  mov     [r15+8], eax
0x1800057ed  mov     eax, [rsi+10h]
0x1800057f0  mov     [r15+20h], eax
0x1800057f4  mov     [r15+28h], rsi
0x1800057f8  mov     [r15+30h], r8d
0x1800057fc  mov     [r15+48h], r8
0x180005800  mov     [r15+38h], r8
0x180005804  mov     [r15+40h], r8d
0x180005808  mov     [r15+10h], edx
0x18000580c  mov     eax, [rsi+8]
0x18000580f  add     eax, 0FFF9FFFFh; switch 7 cases
0x180005814  cmp     eax, 6
0x180005817  jbe     loc_18009ECE8
0x18000581d  cmp     edx, ecx; jumptable 000000018009ECFA default case
0x18000581f  jbe     loc_1800058B2
0x180005825  mov     ebx, 0C000000Dh
0x18000582a  mov     r14d, ebx
0x18000582d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005834  lea     rsi, WPP_GLOBAL_Control
0x18000583b  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005842  cmp     rcx, rsi
0x180005845  jz      short loc_180005852
0x180005847  mov     eax, [rcx+2Ch]
0x18000584a  test    al, 1
0x18000584c  jnz     loc_180005DA1
0x180005852  mov     r15, r8
0x180005855  mov     rcx, cs:WPP_GLOBAL_Control
0x18000585c  cmp     rcx, rsi
0x18000585f  jz      short loc_18000588A
0x180005861  mov     eax, [rcx+2Ch]
0x180005864  test    al, 1
0x180005866  jz      short loc_18000588A
0x180005868  mov     rcx, [rcx+18h]
0x18000586c  lea     r9, aStatus; "Status"
0x180005873  mov     [rsp+78h+var_48], 829h
0x18000587b  mov     [rsp+78h+var_50], rdi
0x180005880  mov     [rsp+78h+var_58], r14d
0x180005885  call    WPP_SF_sDsd
0x18000588a  test    rbp, rbp
0x18000588d  jz      loc_180005992
0x180005893  mov     rcx, [r15+38h]; P
0x180005897  test    rcx, rcx
0x18000589a  jz      loc_18009ED0D
0x1800058a0  call    MSCryptFree
0x1800058a5  mov     qword ptr [r15+38h], 0
0x1800058ad  jmp     loc_18009ED0D
0x1800058b2  lea     eax, ds:0[rdx*8]
0x1800058b9  mov     ecx, edx
0x1800058bb  mov     [r15+0Ch], eax
0x1800058bf  call    MSCryptAlloc
0x1800058c4  mov     [r15+18h], rax
0x1800058c8  test    rax, rax
0x1800058cb  jz      loc_180005AD4
0x1800058d1  mov     r8d, [r15+10h]; Size
0x1800058d5  mov     rdx, rbx; Src
0x1800058d8  mov     rcx, rax; void *
0x1800058db  call    memmove
0x1800058e0  mov     rbp, r15
0x1800058e3  test    r14, r14
0x1800058e6  jz      loc_18000598C
0x1800058ec  test    edi, edi
0x1800058ee  jz      loc_18000598C
0x1800058f4  mov     eax, 8
0x1800058f9  mov     ebx, edi
0x1800058fb  cmovz   ebx, eax
0x1800058fe  mov     esi, edi
0x180005900  mov     eax, cs:g_TrustedEnvironment
0x180005906  test    eax, eax
0x180005908  jz      loc_180005C70
0x18000590e  mov     r8d, 62676E43h
0x180005914  mov     rdx, rbx
0x180005917  test    al, 2
0x180005919  jnz     loc_180005D3B
0x18000591f  mov     ecx, 40h ; '@'
0x180005924  call    cs:__imp_ExAllocatePool2
0x18000592b  nop     dword ptr [rax+rax+00h]
0x180005930  mov     [r15+38h], rax
0x180005934  test    rax, rax
0x180005937  jz      short loc_1800059B6
0x180005939  mov     r8, rsi; Size
0x18000593c  mov     rdx, r14; Src
0x18000593f  mov     rcx, rax; void *
0x180005942  call    memmove
0x180005947  mov     rcx, [r15+38h]; Str1
0x18000594b  mov     [r15+40h], edi
0x18000594f  call    GetSymCryptMacAlgorithm
0x180005954  mov     [r15+48h], rax
0x180005958  test    rax, rax
0x18000595b  jz      loc_180005D51
0x180005961  mov     r8d, [r15+10h]
0x180005965  lea     rcx, [r15+50h]
0x180005969  mov     rdx, [r15+18h]
0x18000596d  mov     [rcx+220h], rax
0x180005974  mov     rax, [rax]
0x180005977  call    _guard_dispatch_icall
0x18000597c  test    eax, eax
0x18000597e  jnz     loc_180005D79
0x180005984  mov     dword ptr [r15+30h], 1
0x18000598c  mov     [r12], r15
0x180005990  xor     ebx, ebx
0x180005992  mov     r13, [rsp+78h+arg_0]
0x18000599a  lea     r11, [rsp+78h+var_28]
0x18000599f  mov     eax, ebx
0x1800059a1  mov     rbx, [r11+38h]
0x1800059a5  mov     rbp, [r11+40h]
0x1800059a9  mov     rsp, r11
0x1800059ac  pop     r15
0x1800059ae  pop     r14
0x1800059b0  pop     r12
0x1800059b2  pop     rdi
0x1800059b3  pop     rsi
0x1800059b4  retn
0x1800059b6  mov     ebx, 0C0000017h
0x1800059bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059c2  lea     rsi, WPP_GLOBAL_Control
0x1800059c9  cmp     rcx, rsi
0x1800059cc  jz      loc_180005893
0x1800059d2  mov     eax, [rcx+2Ch]
0x1800059d5  test    al, 1
0x1800059d7  jz      loc_180005893
0x1800059dd  mov     rcx, [rcx+18h]
0x1800059e1  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800059e8  mov     [rsp+78h+var_48], 836h
0x1800059f0  lea     r9, aStatus; "Status"
0x1800059f7  mov     [rsp+78h+var_50], rdi
0x1800059fc  mov     [rsp+78h+var_58], 0C0000017h
0x180005a04  call    WPP_SF_sDsd
0x180005a09  jmp     loc_180005893
0x180005a0e  xor     r8d, r8d
0x180005a11  mov     r14d, r8d
0x180005a14  jmp     loc_1800057AB
0x180005a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a20  lea     rsi, WPP_GLOBAL_Control
0x180005a27  cmp     rcx, rsi
0x180005a2a  jz      short loc_180005A37
0x180005a2c  mov     eax, [rcx+2Ch]
0x180005a2f  test    al, 1
0x180005a31  jnz     loc_180005C8D
0x180005a37  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005a3e  mov     ebx, 0C0000008h
0x180005a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a4a  cmp     rcx, rsi
0x180005a4d  jz      loc_180005992
0x180005a53  mov     edx, [rcx+2Ch]
0x180005a56  test    dl, 1
0x180005a59  jz      loc_180005992
0x180005a5f  mov     rcx, [rcx+18h]
0x180005a63  lea     r9, aStatus; "Status"
0x180005a6a  mov     [rsp+78h+var_48], 7D0h
0x180005a72  mov     [rsp+78h+var_50], rdi
0x180005a77  mov     [rsp+78h+var_58], 0C0000008h
0x180005a7f  call    WPP_SF_sDsd
0x180005a84  jmp     loc_180005992
0x180005a89  mov     ebx, 0C0000023h
0x180005a8e  mov     r14d, ebx
0x180005a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a98  lea     rsi, WPP_GLOBAL_Control
0x180005a9f  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005aa6  cmp     rcx, rsi
0x180005aa9  jz      loc_180005852
0x180005aaf  mov     eax, [rcx+2Ch]
0x180005ab2  test    al, 1
0x180005ab4  jz      loc_180005852
0x180005aba  mov     [rsp+78h+var_48], 576h
0x180005ac2  mov     [rsp+78h+var_50], rdi
0x180005ac7  mov     [rsp+78h+var_58], 0C0000023h
0x180005acf  jmp     loc_180005C4F
0x180005ad4  mov     ebx, 0C0000017h
0x180005ad9  mov     r14d, ebx
0x180005adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ae3  lea     rsi, WPP_GLOBAL_Control
0x180005aea  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005af1  cmp     rcx, rsi
0x180005af4  jz      short loc_180005B5E
0x180005af6  mov     eax, [rcx+2Ch]
0x180005af9  test    al, 1
0x180005afb  jz      short loc_180005B5E
0x180005afd  mov     [rsp+78h+var_48], 5D5h
0x180005b05  mov     [rsp+78h+var_50], rdi
0x180005b0a  mov     [rsp+78h+var_58], 0C0000017h
0x180005b12  jmp     loc_180005C4F
0x180005b17  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b1e  mov     r9d, 11Eh
0x180005b24  mov     r8, rdi
0x180005b27  lea     rdx, aStatus; "Status"
0x180005b2e  mov     ecx, 0C0000008h
0x180005b33  call    DebugTraceError
0x180005b38  mov     ebx, 0C0000008h
0x180005b3d  mov     r14d, ebx
0x180005b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b47  lea     rsi, WPP_GLOBAL_Control
0x180005b4e  cmp     rcx, rsi
0x180005b51  jz      short loc_180005B5E
0x180005b53  mov     eax, [rcx+2Ch]
0x180005b56  test    al, 1
0x180005b58  jnz     loc_180005D21
0x180005b5e  xor     r8d, r8d
0x180005b61  jmp     loc_180005852
0x180005b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b6d  lea     rsi, WPP_GLOBAL_Control
0x180005b74  cmp     rcx, rsi
0x180005b77  jz      loc_180005A37
0x180005b7d  mov     eax, [rcx+2Ch]
0x180005b80  test    al, 1
0x180005b82  jz      loc_180005A37
0x180005b88  mov     rcx, [rcx+18h]
0x180005b8c  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b93  mov     [rsp+78h+var_48], 111h
0x180005b9b  lea     r9, aStatus; "Status"
0x180005ba2  mov     [rsp+78h+var_50], rdi
0x180005ba7  mov     [rsp+78h+var_58], 0C0000008h
0x180005baf  call    WPP_SF_sDsd
0x180005bb4  jmp     loc_180005A3E
0x180005bb9  mov     ebx, 0C000000Dh
0x180005bbe  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
