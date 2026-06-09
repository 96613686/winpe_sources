# ValidateEccKey

- ea: `0x18003d5f8`
- end: `0x18003d80c`
- name: `ValidateEccKey`
- size: `532`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800765c0`
- `0x1800769c0`
- `0x180076b00`
- `0x180076d9c`
- `0x180076e60`
- `0x1800770b0`
- `0x180077538`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003d5f8`

## string_xrefs

- `0x18003d6eb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a33c0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccKey(__int64 a1, int a2, int a3, int a4, _QWORD *a5)
{
  __int64 i; // rcx
  char *v7; // rax
  int *v8; // rax
  int v9; // edx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  __int64 v14; // r9

  if ( !a1 || !a5 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
    return v11;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
    return v11;
  }
  if ( a4 && !*(_QWORD *)(a1 + 16) )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        67);
    return v11;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v14 = 628;
LABEL_42:
      v11 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v14);
      return v11;
    }
    v7 = byte_1800A8E78;
    if ( !a2 )
      v7 = byte_1800A8DB8;
    if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)&v7[48 * i] )
      break;
  }
  if ( !a4 )
  {
LABEL_16:
    if ( !a3 || (v13 = *(_QWORD *)(a1 + 24)) != 0 && *(_BYTE *)(v13 + 4) )
    {
      *a5 = a1;
      return 0;
    }
    v14 = 637;
    goto LABEL_42;
  }
  v8 = &dword_1800A8E84;
  if ( !a2 )
    v8 = &dword_1800A8DC4;
  v9 = v8[12 * i];
  v10 = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 12LL);
  if ( v9 )
  {
    if ( v9 == v10 )
      goto LABEL_16;
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        101);
  }
  else
  {
    if ( (unsigned int)(v10 - 14) <= 0x34 )
      goto LABEL_16;
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        0,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        91);
  }
  return v11;
}

```

## disassembly

```asm
0x18003d5f8  mov     [rsp+arg_0], rbx
0x18003d5fd  push    rdi
0x18003d5fe  sub     rsp, 40h
0x18003d602  mov     ebx, edx
0x18003d604  mov     r10, rcx
0x18003d607  test    rcx, rcx
0x18003d60a  jz      loc_18003D70D
0x18003d610  mov     r11, [rsp+48h+arg_20]
0x18003d615  test    r11, r11
0x18003d618  jz      loc_18003D70D
0x18003d61e  cmp     dword ptr [rcx+4], 4D534B59h
0x18003d625  jnz     loc_18003D6C0
0x18003d62b  test    r9d, r9d
0x18003d62e  jz      short loc_18003D63B
0x18003d630  cmp     qword ptr [rcx+10h], 0
0x18003d635  jz      loc_18003D7B1
0x18003d63b  xor     ecx, ecx
0x18003d63d  cmp     ecx, 4
0x18003d640  jnb     loc_18003D801
0x18003d646  lea     rdx, [rcx+rcx*2]
0x18003d64a  add     rdx, rdx
0x18003d64d  lea     rdi, byte_1800A8DB8
0x18003d654  test    ebx, ebx
0x18003d656  lea     rax, byte_1800A8E78
0x18003d65d  cmovz   rax, rdi
0x18003d661  mov     eax, [rax+rdx*8]
0x18003d664  cmp     [r10+8], eax
0x18003d668  jnz     loc_18003D736
0x18003d66e  test    r9d, r9d
0x18003d671  jz      short loc_18003D6A4
0x18003d673  test    ebx, ebx
0x18003d675  lea     rcx, dword_1800A8DC4
0x18003d67c  lea     rax, dword_1800A8E84
0x18003d683  cmovz   rax, rcx
0x18003d687  mov     edx, [rax+rdx*8]
0x18003d68a  mov     rax, [r10+10h]
0x18003d68e  mov     rcx, [rax]
0x18003d691  mov     eax, [rcx+0Ch]
0x18003d694  test    edx, edx
0x18003d696  jz      loc_18003D771
0x18003d69c  cmp     edx, eax
0x18003d69e  jnz     loc_18003D73D
0x18003d6a4  test    r8d, r8d
0x18003d6a7  jnz     loc_18003D7E5
0x18003d6ad  mov     [r11], r10
0x18003d6b0  xor     ebx, ebx
0x18003d6b2  mov     eax, ebx
0x18003d6b4  mov     rbx, [rsp+48h+arg_0]
0x18003d6b9  add     rsp, 40h
0x18003d6bd  pop     rdi
0x18003d6be  retn
0x18003d6c0  mov     ebx, 0C000000Dh
0x18003d6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d6cc  lea     rax, WPP_GLOBAL_Control
0x18003d6d3  cmp     rcx, rax
0x18003d6d6  jz      short loc_18003D6B2
0x18003d6d8  mov     eax, [rcx+2Ch]
0x18003d6db  test    al, 1
0x18003d6dd  jz      short loc_18003D6B2
0x18003d6df  mov     [rsp+48h+var_18], 23Ch
0x18003d6e7  mov     rcx, [rcx+18h]
0x18003d6eb  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d6f2  mov     [rsp+48h+var_20], rax
0x18003d6f7  lea     r9, aStatus; "Status"
0x18003d6fe  mov     [rsp+48h+var_28], 0C000000Dh
0x18003d706  call    WPP_SF_sDsd
0x18003d70b  jmp     short loc_18003D6B2
0x18003d70d  mov     ebx, 0C000000Dh
0x18003d712  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d719  lea     rax, WPP_GLOBAL_Control
0x18003d720  cmp     rcx, rax
0x18003d723  jz      short loc_18003D6B2
0x18003d725  mov     eax, [rcx+2Ch]
0x18003d728  test    al, 1
0x18003d72a  jz      short loc_18003D6B2
0x18003d72c  mov     [rsp+48h+var_18], 233h
0x18003d734  jmp     short loc_18003D6E7
0x18003d736  inc     ecx
0x18003d738  jmp     loc_18003D63D
0x18003d73d  mov     ebx, 0C000000Dh
0x18003d742  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d749  lea     rax, WPP_GLOBAL_Control
0x18003d750  cmp     rcx, rax
0x18003d753  jz      loc_18003D6B2
0x18003d759  mov     eax, [rcx+2Ch]
0x18003d75c  test    al, 1
0x18003d75e  jz      loc_18003D6B2
0x18003d764  mov     [rsp+48h+var_18], 265h
0x18003d76c  jmp     loc_18003D6E7
0x18003d771  add     eax, 0FFFFFFF2h
0x18003d774  cmp     eax, 34h ; '4'
0x18003d777  jbe     loc_18003D6A4
0x18003d77d  mov     ebx, 0C000000Dh
0x18003d782  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d789  lea     rax, WPP_GLOBAL_Control
0x18003d790  cmp     rcx, rax
0x18003d793  jz      loc_18003D6B2
0x18003d799  mov     eax, [rcx+2Ch]
0x18003d79c  test    al, 1
0x18003d79e  jz      loc_18003D6B2
0x18003d7a4  mov     [rsp+48h+var_18], 25Bh
0x18003d7ac  jmp     loc_18003D6E7
0x18003d7b1  mov     ebx, 0C000000Dh
0x18003d7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d7bd  lea     rax, WPP_GLOBAL_Control
0x18003d7c4  cmp     rcx, rax
0x18003d7c7  jz      loc_18003D6B2
0x18003d7cd  mov     eax, [rcx+2Ch]
0x18003d7d0  test    al, 1
0x18003d7d2  jz      loc_18003D6B2
0x18003d7d8  mov     [rsp+48h+var_18], 243h
0x18003d7e0  jmp     loc_18003D6E7
0x18003d7e5  mov     rax, [r10+18h]
0x18003d7e9  test    rax, rax
0x18003d7ec  jz      loc_1800A33BA
0x18003d7f2  cmp     byte ptr [rax+4], 0
0x18003d7f6  jnz     loc_18003D6AD
0x18003d7fc  jmp     loc_1800A33BA
0x18003d801  mov     r9d, 274h
0x18003d807  jmp     loc_1800A33C0
0x1800a33ba  mov     r9d, 27Dh
0x1800a33c0  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a33c7  mov     ecx, 0C000000Dh
0x1800a33cc  lea     rdx, aStatus; "Status"
0x1800a33d3  mov     ebx, 0C000000Dh
0x1800a33d8  call    DebugTraceError
0x1800a33dd  nop
0x1800a33de  jmp     loc_18003D6B2
```
