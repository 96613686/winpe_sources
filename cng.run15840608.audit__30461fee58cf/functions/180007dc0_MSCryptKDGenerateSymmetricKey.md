# MSCryptKDGenerateSymmetricKey

- ea: `0x180007dc0`
- end: `0x1800080e4`
- name: `MSCryptKDGenerateSymmetricKey`
- size: `804`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180074150`

## callees

- `0x180003f70`
- `0x18000743c`
- `0x180007dc0`
- `0x1800082b0`
- `0x18009da40`

## string_xrefs

- `0x180007ea5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180007efb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180007f92`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180007fca`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180008017`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180008056`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800080b7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
  v12 = (void *)MSCryptAlloc(a6);
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
0x180007dc0  push    rbx
0x180007dc2  push    rbp
0x180007dc3  push    rsi
0x180007dc4  push    rdi
0x180007dc5  sub     rsp, 48h
0x180007dc9  mov     rdi, [rsp+68h+Src]
0x180007dd1  mov     rbx, r8
0x180007dd4  mov     rsi, rdx
0x180007dd7  test    rdi, rdi
0x180007dda  jz      loc_180008083
0x180007de0  cmp     [rsp+68h+arg_30], 0
0x180007de8  jnz     loc_180008083
0x180007dee  test    rcx, rcx
0x180007df1  jz      loc_180007ED5
0x180007df7  cmp     dword ptr [rcx+4], 4D53414Ch
0x180007dfe  jnz     loc_180008030
0x180007e04  cmp     dword ptr [rcx], 14h
0x180007e07  jnz     loc_180008030
0x180007e0d  mov     eax, [rcx+8]
0x180007e10  sub     eax, 60001h
0x180007e15  cmp     eax, 6
0x180007e18  ja      loc_1800080B7
0x180007e1e  cmp     r9d, 280h
0x180007e25  jb      loc_180007F9B
0x180007e2b  mov     eax, [rcx+0Ch]
0x180007e2e  xor     ebp, ebp
0x180007e30  mov     edx, [rsp+68h+arg_28]
0x180007e37  mov     r8d, ebp
0x180007e3a  mov     [rbx], eax
0x180007e3c  mov     dword ptr [rbx+4], 4D534B59h
0x180007e43  mov     eax, [rcx+8]
0x180007e46  mov     [rbx+8], eax
0x180007e49  mov     eax, [rcx+10h]
0x180007e4c  mov     [rbx+20h], eax
0x180007e4f  mov     [rbx+28h], rcx
0x180007e53  mov     [rbx+30h], ebp
0x180007e56  mov     [rbx+48h], rbp
0x180007e5a  mov     [rbx+38h], rbp
0x180007e5e  mov     [rbx+40h], ebp
0x180007e61  mov     [rbx+10h], edx
0x180007e64  mov     eax, [rcx+8]
0x180007e67  add     eax, 0FFF9FFFFh; switch 7 cases
0x180007e6c  cmp     eax, 6
0x180007e6f  jbe     loc_18009F1E6
0x180007e75  cmp     edx, r8d; jumptable 000000018009F1F7 default case
0x180007e78  jbe     loc_180007F55
0x180007e7e  mov     ebx, 0C000000Dh
0x180007e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e8a  lea     rdi, WPP_GLOBAL_Control
0x180007e91  cmp     rcx, rdi
0x180007e94  jz      short loc_180007EC9
0x180007e96  mov     eax, [rcx+2Ch]
0x180007e99  test    al, 1
0x180007e9b  jz      short loc_180007EC9
0x180007e9d  mov     dword ptr [rsp+68h+var_38], 5C2h
0x180007ea5  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007eac  mov     [rsp+68h+var_40], rsi
0x180007eb1  mov     [rsp+68h+var_48], 0C000000Dh
0x180007eb9  mov     rcx, [rcx+18h]
0x180007ebd  lea     r9, aStatus; "Status"
0x180007ec4  call    WPP_SF_sDsd
0x180007ec9  mov     eax, ebx
0x180007ecb  add     rsp, 48h
0x180007ecf  pop     rdi
0x180007ed0  pop     rsi
0x180007ed1  pop     rbp
0x180007ed2  pop     rbx
0x180007ed3  retn
0x180007ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007edc  lea     rdi, WPP_GLOBAL_Control
0x180007ee3  cmp     rcx, rdi
0x180007ee6  jz      loc_180007F92
0x180007eec  mov     eax, [rcx+2Ch]
0x180007eef  test    al, 1
0x180007ef1  jz      loc_180007F92
0x180007ef7  mov     rcx, [rcx+18h]
0x180007efb  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f02  mov     dword ptr [rsp+68h+var_38], 107h
0x180007f0a  lea     r9, aStatus; "Status"
0x180007f11  mov     [rsp+68h+var_40], rsi
0x180007f16  mov     [rsp+68h+var_48], 0C0000008h
0x180007f1e  call    WPP_SF_sDsd
0x180007f23  mov     ebx, 0C0000008h
0x180007f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f2f  cmp     rcx, rdi
0x180007f32  jz      short loc_180007EC9
0x180007f34  mov     eax, [rcx+2Ch]
0x180007f37  test    al, 1
0x180007f39  jz      short loc_180007EC9
0x180007f3b  mov     dword ptr [rsp+68h+var_38], 56Eh
0x180007f43  mov     [rsp+68h+var_40], rsi
0x180007f48  mov     [rsp+68h+var_48], 0C0000008h
0x180007f50  jmp     loc_180007EB9
0x180007f55  lea     eax, ds:0[rdx*8]
0x180007f5c  mov     rcx, rdx
0x180007f5f  mov     [rbx+0Ch], eax
0x180007f62  call    MSCryptAlloc
0x180007f67  mov     [rbx+18h], rax
0x180007f6b  test    rax, rax
0x180007f6e  jz      short loc_180007FE8
0x180007f70  mov     r8d, [rbx+10h]; Size
0x180007f74  mov     rdx, rdi; Src
0x180007f77  mov     rcx, rax; void *
0x180007f7a  call    memmove
0x180007f7f  test    rsi, rsi
0x180007f82  jnz     short loc_180007FE3
0x180007f84  mov     ebx, ebp
0x180007f86  mov     eax, ebx
0x180007f88  add     rsp, 48h
0x180007f8c  pop     rdi
0x180007f8d  pop     rsi
0x180007f8e  pop     rbp
0x180007f8f  pop     rbx
0x180007f90  retn
0x180007f92  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f99  jmp     short loc_180007F23
0x180007f9b  mov     ebx, 0C0000023h
0x180007fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fa7  lea     rdi, WPP_GLOBAL_Control
0x180007fae  cmp     rcx, rdi
0x180007fb1  jz      loc_180007EC9
0x180007fb7  mov     eax, [rcx+2Ch]
0x180007fba  test    al, 1
0x180007fbc  jz      loc_180007EC9
0x180007fc2  mov     dword ptr [rsp+68h+var_38], 576h
0x180007fca  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007fd1  mov     [rsp+68h+var_40], rsi
0x180007fd6  mov     [rsp+68h+var_48], 0C0000023h
0x180007fde  jmp     loc_180007EB9
0x180007fe3  mov     [rsi], rbx
0x180007fe6  jmp     short loc_180007F84
0x180007fe8  mov     ebx, 0C0000017h
0x180007fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ff4  lea     rdi, WPP_GLOBAL_Control
0x180007ffb  cmp     rcx, rdi
0x180007ffe  jz      loc_180007EC9
0x180008004  mov     eax, [rcx+2Ch]
0x180008007  test    al, 1
0x180008009  jz      loc_180007EC9
0x18000800f  mov     dword ptr [rsp+68h+var_38], 5D5h
0x180008017  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000801e  mov     [rsp+68h+var_40], rsi
0x180008023  mov     [rsp+68h+var_48], 0C0000017h
0x18000802b  jmp     loc_180007EB9
0x180008030  mov     rcx, cs:WPP_GLOBAL_Control
0x180008037  lea     rdi, WPP_GLOBAL_Control
0x18000803e  cmp     rcx, rdi
0x180008041  jz      loc_180007F92
0x180008047  mov     eax, [rcx+2Ch]
0x18000804a  test    al, 1
0x18000804c  jz      loc_180007F92
0x180008052  mov     rcx, [rcx+18h]
0x180008056  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000805d  mov     dword ptr [rsp+68h+var_38], 111h
0x180008065  lea     r9, aStatus; "Status"
0x18000806c  mov     [rsp+68h+var_40], rsi
0x180008071  mov     [rsp+68h+var_48], 0C0000008h
0x180008079  call    WPP_SF_sDsd
0x18000807e  jmp     loc_180007F23
0x180008083  mov     ebx, 0C000000Dh
0x180008088  mov     rcx, cs:WPP_GLOBAL_Control
0x18000808f  lea     rdi, WPP_GLOBAL_Control
0x180008096  cmp     rcx, rdi
0x180008099  jz      loc_180007EC9
0x18000809f  mov     eax, [rcx+2Ch]
0x1800080a2  test    al, 1
0x1800080a4  jz      loc_180007EC9
0x1800080aa  mov     dword ptr [rsp+68h+var_38], 562h
0x1800080b2  jmp     loc_180007EA5
0x1800080b7  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800080be  mov     r9d, 11Eh
0x1800080c4  mov     r8, rsi
0x1800080c7  lea     rdx, aStatus; "Status"
0x1800080ce  mov     ecx, 0C0000008h
0x1800080d3  call    DebugTraceError
0x1800080d8  lea     rdi, WPP_GLOBAL_Control
0x1800080df  jmp     loc_180007F23
0x18009f1e6  lea     rcx, cs:180000000h
0x18009f1ed  mov     eax, ds:(jpt_18009F1F7 - 180000000h)[rcx+rax*4]
0x18009f1f4  add     rax, rcx
0x18009f1f7  jmp     rax; switch jump
0x18009f1fd  mov     r8d, 800h; jumptable 000000018009F1F7 cases 393217-393223
0x18009f203  jmp     def_18009F1F7; jumptable 000000018009F1F7 default case
```
