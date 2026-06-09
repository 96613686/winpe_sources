# I_GetContentEncryptKey

- ea: `0x1800122c4`
- end: `0x18001256e`
- name: `I_GetContentEncryptKey`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000260c`
- `0x180007274`

## callees

- `0x18000e120`
- `0x180010890`
- `0x1800122c4`
- `0x180016e90`
- `0x18001f151`
- `0x180020010`

## string_xrefs

- `0x180012512`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_GetContentEncryptKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned int *a6)
{
  unsigned int v6; // ebx
  __int64 v7; // r11
  __int64 v8; // rcx
  _BYTE *v9; // rdi
  __int64 *v10; // r10
  unsigned int v11; // r12d
  __int64 v12; // rdx
  _QWORD *v13; // r15
  __int64 v14; // r13
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rsi
  unsigned int v18; // eax
  __int64 v19; // rax
  _QWORD *v20; // r9
  bool v21; // zf
  __int64 v22; // r9
  _BYTE *v23; // rcx
  __int64 v24; // rax
  unsigned int v26; // [rsp+48h] [rbp-39h] BYREF
  int v27; // [rsp+4Ch] [rbp-35h]
  _BYTE *v28; // [rsp+50h] [rbp-31h] BYREF
  _QWORD *v29; // [rsp+58h] [rbp-29h]
  _QWORD *v30; // [rsp+60h] [rbp-21h]
  __int64 v31; // [rsp+68h] [rbp-19h]
  __int64 v32; // [rsp+70h] [rbp-11h]
  _QWORD *v33; // [rsp+78h] [rbp-9h]

  v6 = 0;
  v7 = a1;
  v26 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v9 = 0;
  v10 = (__int64 *)a3;
  v28 = 0;
  *a5 = 0;
  v11 = 0;
  v12 = *(_QWORD *)(v7 + 32);
  v27 = -1;
  v31 = v8;
  *a6 = 0;
  v33 = (_QWORD *)(v8 + 8);
  v13 = (_QWORD *)(v8 + 8);
  v32 = v12;
  v29 = (_QWORD *)(v12 + 48);
  v30 = (_QWORD *)(v12 + 48);
  while ( v11 < *(_DWORD *)v8 )
  {
    v13 = (_QWORD *)(v8 + 8);
    v14 = *(_QWORD *)(v8 + 8);
    v15 = 32LL * v11;
    if ( !*(_DWORD *)(v15 + v14) )
    {
      v20 = v29;
      v6 = -2146893785;
      goto LABEL_25;
    }
    v16 = *(unsigned int *)(v15 + v14 + 16);
    v30 = (_QWORD *)(v12 + 48);
    v17 = *(_QWORD *)(v12 + 48) + 160 * v16;
    if ( *(_DWORD *)(v15 + v14) <= 1u )
    {
      if ( *(_DWORD *)v17 == 5 && *(_DWORD *)(v17 + 8) == 12 )
      {
        if ( !memcmp_0(*(const void **)(v17 + 16), g_rgbObjDraCert, *(unsigned int *)(v17 + 8)) )
        {
          v27 = v11;
          goto LABEL_18;
        }
        v10 = (__int64 *)a3;
      }
      v18 = NCryptUnprotectKey(
              *(_QWORD *)(*(_QWORD *)(v15 + v14 + 8) + 16LL),
              v17,
              v10,
              a4,
              (__int64)&v28,
              (__int64)&v26,
              a2);
    }
    else
    {
      v18 = I_UnprotectCombinerRecipientKey(v7, v11, v17, (__int64)v10, a4, &v28, &v26);
    }
    v9 = v28;
    v6 = v18;
    if ( !v18 )
    {
      v10 = (__int64 *)a3;
      goto LABEL_22;
    }
    if ( v28 )
    {
      v19 = v26;
      if ( v26 )
      {
        do
        {
          *v9++ = 0;
          --v19;
        }
        while ( v19 );
        v9 = v28;
      }
      (*(void (__fastcall **)(_BYTE *))(a3 + 16))(v9);
      v9 = 0;
      v28 = 0;
    }
LABEL_18:
    v10 = (__int64 *)a3;
    ++v11;
    v8 = v31;
    v7 = a1;
    v12 = v32;
  }
  if ( v6 )
  {
    v20 = v30;
  }
  else
  {
LABEL_22:
    v13 = v33;
    v20 = v29;
    if ( v9 )
      goto LABEL_29;
  }
LABEL_25:
  if ( v27 < 0 )
  {
    v21 = (a2 & 0x80u) == 0;
    v22 = 1634;
  }
  else
  {
    _mm_lfence();
    v6 = NCryptUnprotectKey(
           *(_QWORD *)(*(_QWORD *)(32LL * v27 + *v13 + 8) + 16LL),
           *v20 + 160LL * *(unsigned int *)(32LL * v27 + *v13 + 16),
           v10,
           a4,
           (__int64)&v28,
           (__int64)&v26,
           a2);
    if ( !v6 )
    {
      v9 = v28;
LABEL_29:
      *a5 = v9;
      *a6 = v26;
      return v6;
    }
    v21 = (a2 & 0x80u) == 0;
    v22 = 1618;
  }
  if ( v21 )
    v6 = -2146893780;
  DebugTraceError(
    v6,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
    v22);
  v23 = v28;
  if ( v28 )
  {
    v24 = v26;
    if ( v26 )
    {
      do
      {
        *v23++ = 0;
        --v24;
      }
      while ( v24 );
    }
    (*(void (**)(void))(a3 + 16))();
  }
  return v6;
}

```

## disassembly

```asm
0x1800122c4  mov     rax, rsp
0x1800122c7  mov     [rax+20h], r9
0x1800122cb  mov     [rax+18h], r8
0x1800122cf  mov     [rax+10h], edx
0x1800122d2  mov     [rax+8], rcx
0x1800122d6  push    rbp
0x1800122d7  push    rbx
0x1800122d8  push    rsi
0x1800122d9  push    rdi
0x1800122da  push    r12
0x1800122dc  push    r13
0x1800122de  push    r14
0x1800122e0  push    r15
0x1800122e2  lea     rbp, [rax-4Fh]
0x1800122e6  sub     rsp, 88h
0x1800122ed  mov     rax, [rbp+47h+arg_20]
0x1800122f1  xor     ebx, ebx
0x1800122f3  mov     r11, rcx
0x1800122f6  mov     [rbp+47h+var_80], ebx
0x1800122f9  mov     rcx, [rcx+8]
0x1800122fd  xor     edi, edi
0x1800122ff  mov     r10, r8
0x180012302  mov     [rbp+47h+var_78], rdi
0x180012306  mov     [rax], rbx
0x180012309  xor     r12d, r12d
0x18001230c  mov     rax, [rbp+47h+arg_28]
0x180012310  mov     rdx, [r11+20h]
0x180012314  mov     [rbp+47h+var_7C], 0FFFFFFFFh
0x18001231b  mov     [rbp+47h+var_60], rcx
0x18001231f  mov     [rax], ebx
0x180012321  lea     rax, [rcx+8]
0x180012325  lea     r9, [rdx+30h]
0x180012329  mov     [rbp+47h+var_50], rax
0x18001232d  mov     r15, rax
0x180012330  mov     [rbp+47h+var_58], rdx
0x180012334  mov     [rbp+47h+var_70], r9
0x180012338  mov     [rbp+47h+var_68], r9
0x18001233c  mov     eax, ebx
0x18001233e  cmp     r12d, [rcx]
0x180012341  jnb     loc_180012471
0x180012347  lea     r15, [rcx+8]
0x18001234b  mov     r14d, r12d
0x18001234e  mov     r13, [r15]
0x180012351  shl     r14, 5
0x180012355  cmp     dword ptr [r14+r13], 0
0x18001235a  jbe     loc_180012466
0x180012360  mov     eax, [r14+r13+10h]
0x180012365  add     rdx, 30h ; '0'
0x180012369  mov     [rbp+47h+var_68], rdx
0x18001236d  lea     rsi, [rax+rax*4]
0x180012371  shl     rsi, 5
0x180012375  add     rsi, [rdx]
0x180012378  cmp     dword ptr [r14+r13], 1
0x18001237d  jbe     short loc_1800123AD
0x18001237f  lea     rax, [rbp+47h+var_80]
0x180012383  mov     r9, r10
0x180012386  mov     [rsp+30h], rax
0x18001238b  mov     r8, rsi
0x18001238e  lea     rax, [rbp+47h+var_78]
0x180012392  mov     edx, r12d
0x180012395  mov     [rsp+0C0h+var_98], rax
0x18001239a  mov     rcx, r11
0x18001239d  mov     rax, [rbp+47h+arg_18]
0x1800123a1  mov     [rsp+0C0h+var_A0], rax
0x1800123a6  call    I_UnprotectCombinerRecipientKey
0x1800123ab  jmp     short loc_18001240B
0x1800123ad  cmp     dword ptr [rsi], 5
0x1800123b0  jnz     short loc_1800123DA
0x1800123b2  cmp     dword ptr [rsi+8], 0Ch
0x1800123b6  jnz     short loc_1800123DA
0x1800123b8  mov     r8d, [rsi+8]; Size
0x1800123bc  lea     rdx, g_rgbObjDraCert; Buf2
0x1800123c3  mov     rcx, [rsi+10h]; Buf1
0x1800123c7  call    memcmp_0
0x1800123cc  test    eax, eax
0x1800123ce  jnz     short loc_1800123D6
0x1800123d0  mov     [rbp+47h+var_7C], r12d
0x1800123d4  jmp     short loc_180012448
0x1800123d6  mov     r10, [rbp+47h+arg_10]
0x1800123da  mov     eax, [rbp+47h+arg_8]
0x1800123dd  mov     r8, r10
0x1800123e0  mov     rcx, [r14+r13+8]
0x1800123e5  mov     rdx, rsi
0x1800123e8  mov     r9, [rbp+47h+arg_18]
0x1800123ec  mov     [rsp+30h], eax
0x1800123f0  lea     rax, [rbp+47h+var_80]
0x1800123f4  mov     [rsp+0C0h+var_98], rax
0x1800123f9  lea     rax, [rbp+47h+var_78]
0x1800123fd  mov     rcx, [rcx+10h]
0x180012401  mov     [rsp+0C0h+var_A0], rax
0x180012406  call    NCryptUnprotectKey
0x18001240b  mov     rdi, [rbp+47h+var_78]
0x18001240f  mov     ebx, eax
0x180012411  test    eax, eax
0x180012413  jz      short loc_180012460
0x180012415  test    rdi, rdi
0x180012418  jz      short loc_180012448
0x18001241a  mov     eax, [rbp+47h+var_80]
0x18001241d  test    rax, rax
0x180012420  jz      short loc_180012432
0x180012422  mov     byte ptr [rdi], 0
0x180012425  inc     rdi
0x180012428  sub     rax, 1
0x18001242c  jnz     short loc_180012422
0x18001242e  mov     rdi, [rbp+47h+var_78]
0x180012432  mov     rax, [rbp+47h+arg_10]
0x180012436  mov     rcx, rdi
0x180012439  mov     rax, [rax+10h]
0x18001243d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012442  xor     edi, edi
0x180012444  mov     [rbp+47h+var_78], rdi
0x180012448  mov     r10, [rbp+47h+arg_10]
0x18001244c  inc     r12d
0x18001244f  mov     rcx, [rbp+47h+var_60]
0x180012453  mov     r11, [rbp+47h+arg_0]
0x180012457  mov     rdx, [rbp+47h+var_58]
0x18001245b  jmp     loc_18001233C
0x180012460  mov     r10, [rbp+47h+arg_10]
0x180012464  jmp     short loc_180012475
0x180012466  mov     r9, [rbp+47h+var_70]
0x18001246a  mov     ebx, 80090027h
0x18001246f  jmp     short loc_180012488
0x180012471  test    eax, eax
0x180012473  jnz     short loc_180012484
0x180012475  mov     r15, [rbp+47h+var_50]
0x180012479  mov     r9, [rbp+47h+var_70]
0x18001247d  test    rdi, rdi
0x180012480  jz      short loc_180012488
0x180012482  jmp     short loc_1800124F1
0x180012484  mov     r9, [rbp+47h+var_68]
0x180012488  movsxd  rdx, [rbp+47h+var_7C]
0x18001248c  test    edx, edx
0x18001248e  js      short loc_180012503
0x180012490  lfence
0x180012493  mov     rcx, [r15]
0x180012496  mov     r8, rdx
0x180012499  mov     esi, [rbp+47h+arg_8]
0x18001249c  shl     r8, 5
0x1800124a0  mov     [rsp+30h], esi
0x1800124a4  mov     eax, [r8+rcx+10h]
0x1800124a9  mov     rcx, [r8+rcx+8]
0x1800124ae  mov     r8, r10
0x1800124b1  lea     rdx, [rax+rax*4]
0x1800124b5  mov     rcx, [rcx+10h]
0x1800124b9  lea     rax, [rbp+47h+var_80]
0x1800124bd  mov     [rsp+0C0h+var_98], rax
0x1800124c2  lea     rax, [rbp+47h+var_78]
0x1800124c6  shl     rdx, 5
0x1800124ca  add     rdx, [r9]
0x1800124cd  mov     r9, [rbp+47h+arg_18]
0x1800124d1  mov     [rsp+0C0h+var_A0], rax
0x1800124d6  call    NCryptUnprotectKey
0x1800124db  mov     ebx, eax
0x1800124dd  test    eax, eax
0x1800124df  jz      short loc_1800124ED
0x1800124e1  test    sil, 80h
0x1800124e5  mov     r9d, 652h
0x1800124eb  jmp     short loc_18001250D
0x1800124ed  mov     rdi, [rbp+47h+var_78]
0x1800124f1  mov     rax, [rbp+47h+arg_20]
0x1800124f5  mov     rcx, [rbp+47h+arg_28]
0x1800124f9  mov     [rax], rdi
0x1800124fc  mov     eax, [rbp+47h+var_80]
0x1800124ff  mov     [rcx], eax
0x180012501  jmp     short loc_180012558
0x180012503  test    byte ptr [rbp+47h+arg_8], 80h
0x180012507  mov     r9d, 662h
0x18001250d  mov     eax, 8009002Ch
0x180012512  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012519  cmovz   ebx, eax
0x18001251c  lea     rdx, aStatus; "Status"
0x180012523  mov     ecx, ebx
0x180012525  call    DebugTraceError
0x18001252a  mov     rcx, [rbp+47h+var_78]
0x18001252e  test    rcx, rcx
0x180012531  jz      short loc_180012558
0x180012533  mov     eax, [rbp+47h+var_80]
0x180012536  test    rax, rax
0x180012539  jz      short loc_18001254B
0x18001253b  mov     byte ptr [rcx], 0
0x18001253e  inc     rcx
0x180012541  sub     rax, 1
0x180012545  jnz     short loc_18001253B
0x180012547  mov     rcx, [rbp+47h+var_78]
0x18001254b  mov     rax, [rbp+47h+arg_10]
0x18001254f  mov     rax, [rax+10h]
0x180012553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012558  mov     eax, ebx
0x18001255a  add     rsp, 88h
0x180012561  pop     r15
0x180012563  pop     r14
0x180012565  pop     r13
0x180012567  pop     r12
0x180012569  pop     rdi
0x18001256a  pop     rsi
0x18001256b  pop     rbx
0x18001256c  pop     rbp
0x18001256d  retn
```
