# MSCryptKDGenerateSymmetricKey

- ea: `0x180011ee0`
- end: `0x180012204`
- name: `MSCryptKDGenerateSymmetricKey`
- size: `804`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007e2f0`

## callees

- `0x18000e090`
- `0x18001155c`
- `0x180011ee0`
- `0x1800123d0`
- `0x1800a45c0`

## string_xrefs

- `0x180011fc5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18001201b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800120b2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800120ea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180012137`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180012176`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800121d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGenerateSymmetricKey(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        void *Src,
        unsigned int a6,
        int a7)
{
  __int64 v7; // rbx
  _QWORD *v8; // rsi
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  void *v12; // rax
  int v13; // edx
  int v14; // r8d
  char v15; // [rsp+30h] [rbp-38h]

  v7 = a3;
  v8 = a2;
  if ( !Src || a7 )
  {
    v9 = -1073741811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v9;
    v15 = 98;
    goto LABEL_13;
  }
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        7);
    goto LABEL_18;
  }
  if ( a1[1] != 1297301836 || *a1 != 20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
    goto LABEL_18;
  }
  if ( (unsigned int)(a1[2] - 393217) > 6 )
  {
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      286);
LABEL_18:
    v9 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        110);
    return v9;
  }
  if ( a4 < 0x280 )
  {
    v9 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        118);
    return v9;
  }
  LODWORD(a2) = a6;
  LODWORD(a3) = 0;
  *(_DWORD *)v7 = a1[3];
  *(_DWORD *)(v7 + 4) = 1297304409;
  *(_DWORD *)(v7 + 8) = a1[2];
  *(_DWORD *)(v7 + 32) = a1[4];
  *(_QWORD *)(v7 + 40) = a1;
  *(_DWORD *)(v7 + 48) = 0;
  *(_QWORD *)(v7 + 72) = 0;
  *(_QWORD *)(v7 + 56) = 0;
  *(_DWORD *)(v7 + 64) = 0;
  *(_DWORD *)(v7 + 16) = a6;
  switch ( a1[2] )
  {
    case 0x60001:
    case 0x60002:
    case 0x60003:
    case 0x60004:
    case 0x60005:
    case 0x60006:
    case 0x60007:
      LODWORD(a3) = 2048;
      break;
    default:
      break;
  }
  if ( a6 > (unsigned int)a3 )
  {
    v9 = -1073741811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v9;
    v15 = -62;
LABEL_13:
    WPP_SF_sDsd(
      v10[3],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v15);
    return v9;
  }
  *(_DWORD *)(v7 + 12) = 8 * a6;
  v12 = (void *)MSCryptAlloc(a6, a6);
  *(_QWORD *)(v7 + 24) = v12;
  if ( !v12 )
  {
    v9 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v14,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        213);
    return v9;
  }
  memmove(v12, Src, *(unsigned int *)(v7 + 16));
  if ( v8 )
    *v8 = v7;
  return 0;
}

```

## disassembly

```asm
0x180011ee0  push    rbx
0x180011ee2  push    rbp
0x180011ee3  push    rsi
0x180011ee4  push    rdi
0x180011ee5  sub     rsp, 48h
0x180011ee9  mov     rdi, [rsp+68h+Src]
0x180011ef1  mov     rbx, r8
0x180011ef4  mov     rsi, rdx
0x180011ef7  test    rdi, rdi
0x180011efa  jz      loc_1800121A3
0x180011f00  cmp     [rsp+68h+arg_30], 0
0x180011f08  jnz     loc_1800121A3
0x180011f0e  test    rcx, rcx
0x180011f11  jz      loc_180011FF5
0x180011f17  cmp     dword ptr [rcx+4], 4D53414Ch
0x180011f1e  jnz     loc_180012150
0x180011f24  cmp     dword ptr [rcx], 14h
0x180011f27  jnz     loc_180012150
0x180011f2d  mov     eax, [rcx+8]
0x180011f30  sub     eax, 60001h
0x180011f35  cmp     eax, 6
0x180011f38  ja      loc_1800121D7
0x180011f3e  cmp     r9d, 280h
0x180011f45  jb      loc_1800120BB
0x180011f4b  mov     eax, [rcx+0Ch]
0x180011f4e  xor     ebp, ebp
0x180011f50  mov     edx, [rsp+68h+arg_28]
0x180011f57  mov     r8d, ebp
0x180011f5a  mov     [rbx], eax
0x180011f5c  mov     dword ptr [rbx+4], 4D534B59h
0x180011f63  mov     eax, [rcx+8]
0x180011f66  mov     [rbx+8], eax
0x180011f69  mov     eax, [rcx+10h]
0x180011f6c  mov     [rbx+20h], eax
0x180011f6f  mov     [rbx+28h], rcx
0x180011f73  mov     [rbx+30h], ebp
0x180011f76  mov     [rbx+48h], rbp
0x180011f7a  mov     [rbx+38h], rbp
0x180011f7e  mov     [rbx+40h], ebp
0x180011f81  mov     [rbx+10h], edx
0x180011f84  mov     eax, [rcx+8]
0x180011f87  add     eax, 0FFF9FFFFh; switch 7 cases
0x180011f8c  cmp     eax, 6
0x180011f8f  jbe     loc_1800A5F84
0x180011f95  cmp     edx, r8d; jumptable 00000001800A5F95 default case
0x180011f98  jbe     loc_180012075
0x180011f9e  mov     ebx, 0C000000Dh
0x180011fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011faa  lea     rdi, WPP_GLOBAL_Control
0x180011fb1  cmp     rcx, rdi
0x180011fb4  jz      short loc_180011FE9
0x180011fb6  mov     eax, [rcx+2Ch]
0x180011fb9  test    al, 1
0x180011fbb  jz      short loc_180011FE9
0x180011fbd  mov     dword ptr [rsp+68h+var_38], 5C2h
0x180011fc5  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011fcc  mov     [rsp+68h+var_40], rsi
0x180011fd1  mov     [rsp+68h+var_48], 0C000000Dh
0x180011fd9  mov     rcx, [rcx+18h]
0x180011fdd  lea     r9, aStatus; "Status"
0x180011fe4  call    WPP_SF_sDsd
0x180011fe9  mov     eax, ebx
0x180011feb  add     rsp, 48h
0x180011fef  pop     rdi
0x180011ff0  pop     rsi
0x180011ff1  pop     rbp
0x180011ff2  pop     rbx
0x180011ff3  retn
0x180011ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ffc  lea     rdi, WPP_GLOBAL_Control
0x180012003  cmp     rcx, rdi
0x180012006  jz      loc_1800120B2
0x18001200c  mov     eax, [rcx+2Ch]
0x18001200f  test    al, 1
0x180012011  jz      loc_1800120B2
0x180012017  mov     rcx, [rcx+18h]
0x18001201b  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012022  mov     dword ptr [rsp+68h+var_38], 107h
0x18001202a  lea     r9, aStatus; "Status"
0x180012031  mov     [rsp+68h+var_40], rsi
0x180012036  mov     [rsp+68h+var_48], 0C0000008h
0x18001203e  call    WPP_SF_sDsd
0x180012043  mov     ebx, 0C0000008h
0x180012048  mov     rcx, cs:WPP_GLOBAL_Control
0x18001204f  cmp     rcx, rdi
0x180012052  jz      short loc_180011FE9
0x180012054  mov     eax, [rcx+2Ch]
0x180012057  test    al, 1
0x180012059  jz      short loc_180011FE9
0x18001205b  mov     dword ptr [rsp+68h+var_38], 56Eh
0x180012063  mov     [rsp+68h+var_40], rsi
0x180012068  mov     [rsp+68h+var_48], 0C0000008h
0x180012070  jmp     loc_180011FD9
0x180012075  lea     eax, ds:0[rdx*8]
0x18001207c  mov     rcx, rdx
0x18001207f  mov     [rbx+0Ch], eax
0x180012082  call    MSCryptAlloc
0x180012087  mov     [rbx+18h], rax
0x18001208b  test    rax, rax
0x18001208e  jz      short loc_180012108
0x180012090  mov     r8d, [rbx+10h]; Size
0x180012094  mov     rdx, rdi; Src
0x180012097  mov     rcx, rax; void *
0x18001209a  call    memmove
0x18001209f  test    rsi, rsi
0x1800120a2  jnz     short loc_180012103
0x1800120a4  mov     ebx, ebp
0x1800120a6  mov     eax, ebx
0x1800120a8  add     rsp, 48h
0x1800120ac  pop     rdi
0x1800120ad  pop     rsi
0x1800120ae  pop     rbp
0x1800120af  pop     rbx
0x1800120b0  retn
0x1800120b2  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800120b9  jmp     short loc_180012043
0x1800120bb  mov     ebx, 0C0000023h
0x1800120c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120c7  lea     rdi, WPP_GLOBAL_Control
0x1800120ce  cmp     rcx, rdi
0x1800120d1  jz      loc_180011FE9
0x1800120d7  mov     eax, [rcx+2Ch]
0x1800120da  test    al, 1
0x1800120dc  jz      loc_180011FE9
0x1800120e2  mov     dword ptr [rsp+68h+var_38], 576h
0x1800120ea  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800120f1  mov     [rsp+68h+var_40], rsi
0x1800120f6  mov     [rsp+68h+var_48], 0C0000023h
0x1800120fe  jmp     loc_180011FD9
0x180012103  mov     [rsi], rbx
0x180012106  jmp     short loc_1800120A4
0x180012108  mov     ebx, 0C0000017h
0x18001210d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012114  lea     rdi, WPP_GLOBAL_Control
0x18001211b  cmp     rcx, rdi
0x18001211e  jz      loc_180011FE9
0x180012124  mov     eax, [rcx+2Ch]
0x180012127  test    al, 1
0x180012129  jz      loc_180011FE9
0x18001212f  mov     dword ptr [rsp+68h+var_38], 5D5h
0x180012137  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001213e  mov     [rsp+68h+var_40], rsi
0x180012143  mov     [rsp+68h+var_48], 0C0000017h
0x18001214b  jmp     loc_180011FD9
0x180012150  mov     rcx, cs:WPP_GLOBAL_Control
0x180012157  lea     rdi, WPP_GLOBAL_Control
0x18001215e  cmp     rcx, rdi
0x180012161  jz      loc_1800120B2
0x180012167  mov     eax, [rcx+2Ch]
0x18001216a  test    al, 1
0x18001216c  jz      loc_1800120B2
0x180012172  mov     rcx, [rcx+18h]
0x180012176  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001217d  mov     dword ptr [rsp+68h+var_38], 111h
0x180012185  lea     r9, aStatus; "Status"
0x18001218c  mov     [rsp+68h+var_40], rsi
0x180012191  mov     [rsp+68h+var_48], 0C0000008h
0x180012199  call    WPP_SF_sDsd
0x18001219e  jmp     loc_180012043
0x1800121a3  mov     ebx, 0C000000Dh
0x1800121a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121af  lea     rdi, WPP_GLOBAL_Control
0x1800121b6  cmp     rcx, rdi
0x1800121b9  jz      loc_180011FE9
0x1800121bf  mov     eax, [rcx+2Ch]
0x1800121c2  test    al, 1
0x1800121c4  jz      loc_180011FE9
0x1800121ca  mov     dword ptr [rsp+68h+var_38], 562h
0x1800121d2  jmp     loc_180011FC5
0x1800121d7  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800121de  mov     r9d, 11Eh
0x1800121e4  mov     r8, rsi
0x1800121e7  lea     rdx, aStatus; "Status"
0x1800121ee  mov     ecx, 0C0000008h
0x1800121f3  call    DebugTraceError
0x1800121f8  lea     rdi, WPP_GLOBAL_Control
0x1800121ff  jmp     loc_180012043
0x1800a5f84  lea     rcx, cs:180000000h
0x1800a5f8b  mov     eax, ds:(jpt_1800A5F95 - 180000000h)[rcx+rax*4]
0x1800a5f92  add     rax, rcx
0x1800a5f95  jmp     rax; switch jump
0x1800a5f9b  mov     r8d, 800h; jumptable 00000001800A5F95 cases 393217-393223
0x1800a5fa1  jmp     def_1800A5F95; jumptable 00000001800A5F95 default case
```
