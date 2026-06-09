# DeriveKeyCAPI_KDF

- ea: `0x18007cfc4`
- end: `0x18007d2ab`
- name: `DeriveKeyCAPI_KDF`
- size: `743`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180039de0`

## callees

- `0x180002530`
- `0x180003f70`
- `0x180004320`
- `0x1800051d4`
- `0x180005590`
- `0x180006470`
- `0x18000743c`
- `0x180031270`
- `0x18003a150`
- `0x18003b970`
- `0x18007cfc4`
- `0x18007da38`
- `0x18009da40`

## string_xrefs

- `0x18007d0a7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d111`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d236`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyCAPI_KDF(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  __int64 v8; // rdi
  _BYTE *v9; // rsi
  _WORD *v10; // r14
  __int64 v11; // r9
  int ParameterList; // eax
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // r15
  unsigned int v16; // eax
  _WORD *v17; // rdx
  unsigned __int64 v18; // r12
  size_t v19; // r13
  _WORD *v20; // rax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  unsigned int HashProperty; // eax
  __int64 v24; // rcx
  unsigned int v25; // r15d
  __int64 v26; // rax
  _BYTE *v27; // rdx
  size_t Size; // [rsp+30h] [rbp-38h]
  int v30; // [rsp+40h] [rbp-28h]
  int v31; // [rsp+44h] [rbp-24h] BYREF
  int v32[2]; // [rsp+48h] [rbp-20h] BYREF
  int v33[2]; // [rsp+50h] [rbp-18h] BYREF
  int v35; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp+58h]
  unsigned int v37; // [rsp+C8h] [rbp+60h]

  v37 = a4;
  v36 = a3;
  *(_QWORD *)v32 = 0;
  *(_QWORD *)v33 = 0;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v31 = 0;
  v10 = 0;
  if ( !a2 )
  {
    v11 = 1434;
LABEL_28:
    v21 = -1073741811;
    v24 = 3221225485LL;
    goto LABEL_29;
  }
  if ( (a6 & 0xFFFFFFEF) != 0 )
  {
    v11 = 1441;
    goto LABEL_28;
  }
  *a5 = 0;
  ParameterList = QueryParameterList(a2, 0, 0);
  if ( ParameterList < 0 )
  {
    v11 = 1467;
    goto LABEL_28;
  }
  v13 = *(_DWORD *)(a1 + 32);
  v30 = v13;
  _mm_lfence();
  v14 = *(_QWORD *)(a2 + 8);
  v15 = 2LL * ParameterList;
  v16 = *(_DWORD *)(v14 + 16LL * ParameterList);
  if ( (v16 & 1) != 0 || v16 < 2 )
  {
    v11 = 1478;
    goto LABEL_28;
  }
  v17 = *(_WORD **)(v14 + 8 * v15 + 8);
  v18 = (unsigned __int64)v16 >> 1;
  v19 = v16;
  if ( v17[v18 - 1] )
  {
    v20 = (_WORD *)MSCryptAlloc(v16 + 2LL);
    v10 = v20;
    if ( !v20 )
    {
      v21 = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        1493);
      goto LABEL_30;
    }
    memmove(v20, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v15 + 8), v19);
    v13 = v30;
    v10[v18] = 0;
    v17 = v10;
  }
  v22 = MSCryptOpenHashProvider(v33, v17, (unsigned int)(v13 != 0) + 32);
  v21 = v22;
  if ( v22 )
  {
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1517);
    v8 = *(_QWORD *)v33;
    goto LABEL_30;
  }
  v8 = *(_QWORD *)v33;
  HashProperty = MSCryptGetHashProperty(*(_QWORD *)v33, L"ObjectLength", &v35, 4, &v31, 0);
  v21 = HashProperty;
  if ( HashProperty )
  {
    v11 = 1531;
  }
  else
  {
    v9 = (_BYTE *)MSCryptAlloc((unsigned int)v35);
    if ( !v9 )
    {
      v21 = -1073741801;
      v11 = 1539;
      v24 = 3221225495LL;
      goto LABEL_29;
    }
    LODWORD(Size) = 0;
    HashProperty = MSCryptCreateMultiHash(v8, (int)v32, 0, (int)v9, v35, 0, Size, 0);
    v21 = HashProperty;
    if ( HashProperty )
    {
      v11 = 1555;
    }
    else
    {
      HashProperty = MSCryptHashData(*(_QWORD *)v32, *(_QWORD *)(a1 + 24), *(unsigned int *)(a1 + 16), 0);
      v21 = HashProperty;
      if ( HashProperty )
      {
        v11 = 1566;
      }
      else
      {
        v25 = v37;
        HashProperty = CapiKDF(*(_QWORD *)v32, v36, v37, a6);
        v21 = HashProperty;
        if ( !HashProperty )
        {
          v21 = 0;
          *a5 = v25;
          goto LABEL_30;
        }
        v11 = 1578;
      }
    }
  }
  v24 = HashProperty;
LABEL_29:
  DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v11);
LABEL_30:
  if ( *(_QWORD *)v32 )
    MSCryptDestroyHash();
  if ( v9 )
  {
    v26 = (unsigned int)v35;
    v27 = v9;
    if ( v35 )
    {
      do
      {
        *v27++ = 0;
        --v26;
      }
      while ( v26 );
    }
    MSCryptFree(v9);
  }
  if ( v8 )
    MSCryptCloseHashProvider(v8, 0);
  if ( v10 )
    MSCryptFree(v10);
  return v21;
}

```

## disassembly

```asm
0x18007cfc4  mov     [rsp-40h+arg_18], r9d
0x18007cfc9  mov     [rsp-40h+arg_10], r8
0x18007cfce  mov     [rsp-40h+arg_0], rcx
0x18007cfd3  push    rbp
0x18007cfd4  push    rbx
0x18007cfd5  push    rsi
0x18007cfd6  push    rdi
0x18007cfd7  push    r12
0x18007cfd9  push    r13
0x18007cfdb  push    r14
0x18007cfdd  push    r15
0x18007cfdf  mov     rbp, rsp
0x18007cfe2  sub     rsp, 68h
0x18007cfe6  xor     r12d, r12d
0x18007cfe9  mov     rbx, rdx
0x18007cfec  mov     qword ptr [rbp+var_20], r12
0x18007cff0  mov     r15, rcx
0x18007cff3  mov     qword ptr [rbp+var_18], r12
0x18007cff7  mov     edi, r12d
0x18007cffa  mov     [rbp+arg_8], r12d
0x18007cffe  mov     esi, r12d
0x18007d001  mov     [rbp+var_24], r12d
0x18007d005  mov     r14d, r12d
0x18007d008  test    rdx, rdx
0x18007d00b  jnz     short loc_18007D018
0x18007d00d  mov     r9d, 59Ah
0x18007d013  jmp     loc_18007D22C
0x18007d018  test    [rbp+arg_28], 0FFFFFFEFh
0x18007d01f  jz      short loc_18007D02C
0x18007d021  mov     r9d, 5A1h
0x18007d027  jmp     loc_18007D22C
0x18007d02c  mov     rax, [rbp+arg_20]
0x18007d030  xor     r8d, r8d
0x18007d033  xor     edx, edx
0x18007d035  mov     rcx, rbx
0x18007d038  mov     [rax], r12d
0x18007d03b  call    QueryParameterList
0x18007d040  test    eax, eax
0x18007d042  jns     short loc_18007D04F
0x18007d044  mov     r9d, 5BBh
0x18007d04a  jmp     loc_18007D22C
0x18007d04f  mov     ecx, [r15+20h]
0x18007d053  mov     [rbp+var_28], ecx
0x18007d056  lfence
0x18007d059  mov     rdx, [rbx+8]
0x18007d05d  movsxd  r15, eax
0x18007d060  add     r15, r15
0x18007d063  mov     eax, [rdx+r15*8]
0x18007d067  test    al, 1
0x18007d069  jnz     loc_18007D226
0x18007d06f  cmp     eax, 2
0x18007d072  jb      loc_18007D226
0x18007d078  mov     rdx, [rdx+r15*8+8]
0x18007d07d  mov     r12d, eax
0x18007d080  shr     r12, 1
0x18007d083  mov     r13d, eax
0x18007d086  xor     eax, eax
0x18007d088  cmp     ax, [rdx+r12*2-2]
0x18007d08e  jz      short loc_18007D0ED
0x18007d090  lea     rcx, [r13+2]
0x18007d094  call    MSCryptAlloc
0x18007d099  mov     r14, rax
0x18007d09c  test    rax, rax
0x18007d09f  jnz     short loc_18007D0CC
0x18007d0a1  mov     r9d, 5D5h
0x18007d0a7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d0ae  lea     rdx, aStatus; "Status"
0x18007d0b5  mov     ecx, 0C0000017h
0x18007d0ba  mov     ebx, 0C0000017h
0x18007d0bf  call    DebugTraceError
0x18007d0c4  xor     r12d, r12d
0x18007d0c7  jmp     loc_18007D249
0x18007d0cc  mov     rdx, [rbx+8]
0x18007d0d0  mov     r8, r13; Size
0x18007d0d3  mov     rcx, r14; void *
0x18007d0d6  mov     rdx, [rdx+r15*8+8]; Src
0x18007d0db  call    memmove
0x18007d0e0  mov     ecx, [rbp+var_28]
0x18007d0e3  xor     eax, eax
0x18007d0e5  mov     [r14+r12*2], ax
0x18007d0ea  mov     rdx, r14
0x18007d0ed  neg     ecx
0x18007d0ef  lea     rcx, [rbp+var_18]
0x18007d0f3  sbb     r8d, r8d
0x18007d0f6  neg     r8d
0x18007d0f9  add     r8d, 20h ; ' '
0x18007d0fd  call    MSCryptOpenHashProvider
0x18007d102  xor     r12d, r12d
0x18007d105  mov     ebx, eax
0x18007d107  test    eax, eax
0x18007d109  jz      short loc_18007D12F
0x18007d10b  mov     r9d, 5EDh
0x18007d111  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d118  lea     rdx, aStatus; "Status"
0x18007d11f  mov     ecx, eax
0x18007d121  call    DebugTraceError
0x18007d126  mov     rdi, qword ptr [rbp+var_18]
0x18007d12a  jmp     loc_18007D249
0x18007d12f  mov     rdi, qword ptr [rbp+var_18]
0x18007d133  lea     rax, [rbp+var_24]
0x18007d137  mov     rcx, rdi
0x18007d13a  mov     dword ptr [rsp+68h+Src], r12d
0x18007d13f  mov     r9d, 4
0x18007d145  mov     qword ptr [rsp+68h+var_48], rax
0x18007d14a  lea     r8, [rbp+arg_8]
0x18007d14e  lea     rdx, aObjectlength; "ObjectLength"
0x18007d155  call    MSCryptGetHashProperty
0x18007d15a  mov     ebx, eax
0x18007d15c  test    eax, eax
0x18007d15e  jz      short loc_18007D16D
0x18007d160  mov     r9d, 5FBh
0x18007d166  mov     ecx, eax
0x18007d168  jmp     loc_18007D236
0x18007d16d  mov     ecx, [rbp+arg_8]
0x18007d170  call    MSCryptAlloc
0x18007d175  mov     rsi, rax
0x18007d178  test    rax, rax
0x18007d17b  jnz     short loc_18007D192
0x18007d17d  mov     ebx, 0C0000017h
0x18007d182  mov     r9d, 603h
0x18007d188  mov     ecx, 0C0000017h
0x18007d18d  jmp     loc_18007D236
0x18007d192  mov     eax, [rbp+arg_8]
0x18007d195  lea     rdx, [rbp+var_20]; int
0x18007d199  mov     [rsp+68h+var_30], r12d; int
0x18007d19e  mov     r9, rsi; int
0x18007d1a1  mov     dword ptr [rsp+68h+Size], r12d; Size
0x18007d1a6  xor     r8d, r8d; int
0x18007d1a9  mov     [rsp+68h+Src], r12; Src
0x18007d1ae  mov     rcx, rdi; int
0x18007d1b1  mov     [rsp+68h+var_48], eax; int
0x18007d1b5  call    MSCryptCreateMultiHash
0x18007d1ba  mov     ebx, eax
0x18007d1bc  test    eax, eax
0x18007d1be  jz      short loc_18007D1C8
0x18007d1c0  mov     r9d, 613h
0x18007d1c6  jmp     short loc_18007D166
0x18007d1c8  mov     rdx, [rbp+arg_0]
0x18007d1cc  xor     r9d, r9d
0x18007d1cf  mov     rcx, qword ptr [rbp+var_20]
0x18007d1d3  mov     r8d, [rdx+10h]
0x18007d1d7  mov     rdx, [rdx+18h]
0x18007d1db  call    MSCryptHashData
0x18007d1e0  mov     ebx, eax
0x18007d1e2  test    eax, eax
0x18007d1e4  jz      short loc_18007D1F1
0x18007d1e6  mov     r9d, 61Eh
0x18007d1ec  jmp     loc_18007D166
0x18007d1f1  mov     r15d, [rbp+arg_18]
0x18007d1f5  mov     r8d, r15d
0x18007d1f8  mov     r9d, [rbp+arg_28]
0x18007d1fc  mov     rdx, [rbp+arg_10]
0x18007d200  mov     rcx, qword ptr [rbp+var_20]
0x18007d204  call    _CapiKDF
0x18007d209  mov     ebx, eax
0x18007d20b  test    eax, eax
0x18007d20d  jz      short loc_18007D21A
0x18007d20f  mov     r9d, 62Ah
0x18007d215  jmp     loc_18007D166
0x18007d21a  mov     rax, [rbp+arg_20]
0x18007d21e  mov     ebx, r12d
0x18007d221  mov     [rax], r15d
0x18007d224  jmp     short loc_18007D249
0x18007d226  mov     r9d, 5C6h
0x18007d22c  mov     ebx, 0C000000Dh
0x18007d231  mov     ecx, 0C000000Dh
0x18007d236  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d23d  lea     rdx, aStatus; "Status"
0x18007d244  call    DebugTraceError
0x18007d249  mov     rcx, qword ptr [rbp+var_20]
0x18007d24d  test    rcx, rcx
0x18007d250  jz      short loc_18007D257
0x18007d252  call    MSCryptDestroyHash
0x18007d257  test    rsi, rsi
0x18007d25a  jz      short loc_18007D27B
0x18007d25c  mov     eax, [rbp+arg_8]
0x18007d25f  mov     rdx, rsi
0x18007d262  test    rax, rax
0x18007d265  jz      short loc_18007D273
0x18007d267  mov     [rdx], r12b
0x18007d26a  inc     rdx
0x18007d26d  sub     rax, 1
0x18007d271  jnz     short loc_18007D267
0x18007d273  mov     rcx, rsi; P
0x18007d276  call    MSCryptFree
0x18007d27b  test    rdi, rdi
0x18007d27e  jz      short loc_18007D28A
0x18007d280  xor     edx, edx
0x18007d282  mov     rcx, rdi
0x18007d285  call    MSCryptCloseHashProvider
0x18007d28a  test    r14, r14
0x18007d28d  jz      short loc_18007D297
0x18007d28f  mov     rcx, r14; P
0x18007d292  call    MSCryptFree
0x18007d297  mov     eax, ebx
0x18007d299  add     rsp, 68h
0x18007d29d  pop     r15
0x18007d29f  pop     r14
0x18007d2a1  pop     r13
0x18007d2a3  pop     r12
0x18007d2a5  pop     rdi
0x18007d2a6  pop     rsi
0x18007d2a7  pop     rbx
0x18007d2a8  pop     rbp
0x18007d2a9  retn
```
