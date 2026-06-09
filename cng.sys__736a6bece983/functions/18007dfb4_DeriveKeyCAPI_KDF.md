# DeriveKeyCAPI_KDF

- ea: `0x18007dfb4`
- end: `0x18007e29b`
- name: `DeriveKeyCAPI_KDF`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003a8e0`

## callees

- `0x180002530`
- `0x180003f70`
- `0x180004320`
- `0x1800051d4`
- `0x180005590`
- `0x180006470`
- `0x18000743c`
- `0x180031d70`
- `0x18003ac50`
- `0x18003c470`
- `0x18007dfb4`
- `0x18007ea28`
- `0x18009f780`

## string_xrefs

- `0x18007e097`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e101`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e226`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

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
  wchar_t *v10; // r14
  __int64 v11; // r9
  int ParameterList; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // r15
  unsigned int v18; // eax
  const wchar_t *v19; // rdx
  unsigned __int64 v20; // r12
  size_t v21; // r13
  wchar_t *v22; // rax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int HashProperty; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  unsigned int v30; // r15d
  __int64 v31; // rax
  _BYTE *v32; // rdx
  size_t Size; // [rsp+30h] [rbp-38h]
  int v35; // [rsp+40h] [rbp-28h]
  unsigned int v36; // [rsp+44h] [rbp-24h] BYREF
  int v37[2]; // [rsp+48h] [rbp-20h] BYREF
  int v38[2]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v40; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v41; // [rsp+C0h] [rbp+58h]
  unsigned int v42; // [rsp+C8h] [rbp+60h]

  v42 = a4;
  v41 = a3;
  *(_QWORD *)v37 = 0;
  *(_QWORD *)v38 = 0;
  v8 = 0;
  LODWORD(v40) = 0;
  v9 = 0;
  v36 = 0;
  v10 = 0;
  if ( !a2 )
  {
    v11 = 1434;
LABEL_28:
    v23 = -1073741811;
    v29 = 3221225485LL;
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
  v15 = *(_DWORD *)(a1 + 32);
  v35 = v15;
  _mm_lfence();
  v16 = *(_QWORD *)(a2 + 8);
  v17 = 2LL * ParameterList;
  v18 = *(_DWORD *)(v16 + 16LL * ParameterList);
  if ( (v18 & 1) != 0 || v18 < 2 )
  {
    v11 = 1478;
    goto LABEL_28;
  }
  v19 = *(const wchar_t **)(v16 + 8 * v17 + 8);
  v20 = (unsigned __int64)v18 >> 1;
  v21 = v18;
  if ( v19[v20 - 1] )
  {
    v22 = (wchar_t *)MSCryptAlloc(v18 + 2LL, v19, v13, v14);
    v10 = v22;
    if ( !v22 )
    {
      v23 = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        1493);
      goto LABEL_30;
    }
    memmove(v22, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v17 + 8), v21);
    v15 = v35;
    v10[v20] = 0;
    v19 = v10;
  }
  v24 = MSCryptOpenHashProvider((__int64 *)v38, v19, (unsigned int)(v15 != 0) + 32);
  v23 = v24;
  if ( v24 )
  {
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1517);
    v8 = *(_QWORD *)v38;
    goto LABEL_30;
  }
  v8 = *(_QWORD *)v38;
  HashProperty = MSCryptGetHashProperty(*(_DWORD **)v38, L"ObjectLength", &v40, 4u, &v36, 0);
  v23 = HashProperty;
  if ( HashProperty )
  {
    v11 = 1531;
  }
  else
  {
    v9 = (_BYTE *)MSCryptAlloc((unsigned int)v40, v26, v27, v28);
    if ( !v9 )
    {
      v23 = -1073741801;
      v11 = 1539;
      v29 = 3221225495LL;
      goto LABEL_29;
    }
    LODWORD(Size) = 0;
    HashProperty = MSCryptCreateMultiHash(v8, (int)v37, 0, (int)v9, v40, 0, Size, 0);
    v23 = HashProperty;
    if ( HashProperty )
    {
      v11 = 1555;
    }
    else
    {
      HashProperty = MSCryptHashData(*(__int64 *)v37, *(_QWORD *)(a1 + 24), *(_DWORD *)(a1 + 16), 0);
      v23 = HashProperty;
      if ( HashProperty )
      {
        v11 = 1566;
      }
      else
      {
        v30 = v42;
        HashProperty = CapiKDF(*(_QWORD *)v37, v41, v42, a6);
        v23 = HashProperty;
        if ( !HashProperty )
        {
          v23 = 0;
          *a5 = v30;
          goto LABEL_30;
        }
        v11 = 1578;
      }
    }
  }
  v29 = HashProperty;
LABEL_29:
  DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v11);
LABEL_30:
  if ( *(_QWORD *)v37 )
    MSCryptDestroyHash();
  if ( v9 )
  {
    v31 = (unsigned int)v40;
    v32 = v9;
    if ( (_DWORD)v40 )
    {
      do
      {
        *v32++ = 0;
        --v31;
      }
      while ( v31 );
    }
    MSCryptFree(v9);
  }
  if ( v8 )
    MSCryptCloseHashProvider(v8, 0);
  if ( v10 )
    MSCryptFree(v10);
  return v23;
}

```

## disassembly

```asm
0x18007dfb4  mov     [rsp-40h+arg_18], r9d
0x18007dfb9  mov     [rsp-40h+arg_10], r8
0x18007dfbe  mov     [rsp-40h+arg_0], rcx
0x18007dfc3  push    rbp
0x18007dfc4  push    rbx
0x18007dfc5  push    rsi
0x18007dfc6  push    rdi
0x18007dfc7  push    r12
0x18007dfc9  push    r13
0x18007dfcb  push    r14
0x18007dfcd  push    r15
0x18007dfcf  mov     rbp, rsp
0x18007dfd2  sub     rsp, 68h
0x18007dfd6  xor     r12d, r12d
0x18007dfd9  mov     rbx, rdx
0x18007dfdc  mov     qword ptr [rbp+var_20], r12
0x18007dfe0  mov     r15, rcx
0x18007dfe3  mov     qword ptr [rbp+var_18], r12
0x18007dfe7  mov     edi, r12d
0x18007dfea  mov     dword ptr [rbp+arg_8], r12d
0x18007dfee  mov     esi, r12d
0x18007dff1  mov     [rbp+var_24], r12d
0x18007dff5  mov     r14d, r12d
0x18007dff8  test    rdx, rdx
0x18007dffb  jnz     short loc_18007E008
0x18007dffd  mov     r9d, 59Ah
0x18007e003  jmp     loc_18007E21C
0x18007e008  test    [rbp+arg_28], 0FFFFFFEFh
0x18007e00f  jz      short loc_18007E01C
0x18007e011  mov     r9d, 5A1h
0x18007e017  jmp     loc_18007E21C
0x18007e01c  mov     rax, [rbp+arg_20]
0x18007e020  xor     r8d, r8d
0x18007e023  xor     edx, edx
0x18007e025  mov     rcx, rbx
0x18007e028  mov     [rax], r12d
0x18007e02b  call    QueryParameterList
0x18007e030  test    eax, eax
0x18007e032  jns     short loc_18007E03F
0x18007e034  mov     r9d, 5BBh
0x18007e03a  jmp     loc_18007E21C
0x18007e03f  mov     ecx, [r15+20h]
0x18007e043  mov     [rbp+var_28], ecx
0x18007e046  lfence
0x18007e049  mov     rdx, [rbx+8]
0x18007e04d  movsxd  r15, eax
0x18007e050  add     r15, r15
0x18007e053  mov     eax, [rdx+r15*8]
0x18007e057  test    al, 1
0x18007e059  jnz     loc_18007E216
0x18007e05f  cmp     eax, 2
0x18007e062  jb      loc_18007E216
0x18007e068  mov     rdx, [rdx+r15*8+8]
0x18007e06d  mov     r12d, eax
0x18007e070  shr     r12, 1
0x18007e073  mov     r13d, eax
0x18007e076  xor     eax, eax
0x18007e078  cmp     ax, [rdx+r12*2-2]
0x18007e07e  jz      short loc_18007E0DD
0x18007e080  lea     rcx, [r13+2]
0x18007e084  call    MSCryptAlloc
0x18007e089  mov     r14, rax
0x18007e08c  test    rax, rax
0x18007e08f  jnz     short loc_18007E0BC
0x18007e091  mov     r9d, 5D5h
0x18007e097  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e09e  lea     rdx, aStatus; "Status"
0x18007e0a5  mov     ecx, 0C0000017h
0x18007e0aa  mov     ebx, 0C0000017h
0x18007e0af  call    DebugTraceError
0x18007e0b4  xor     r12d, r12d
0x18007e0b7  jmp     loc_18007E239
0x18007e0bc  mov     rdx, [rbx+8]
0x18007e0c0  mov     r8, r13; Size
0x18007e0c3  mov     rcx, r14; void *
0x18007e0c6  mov     rdx, [rdx+r15*8+8]; Src
0x18007e0cb  call    memmove
0x18007e0d0  mov     ecx, [rbp+var_28]
0x18007e0d3  xor     eax, eax
0x18007e0d5  mov     [r14+r12*2], ax
0x18007e0da  mov     rdx, r14
0x18007e0dd  neg     ecx
0x18007e0df  lea     rcx, [rbp+var_18]
0x18007e0e3  sbb     r8d, r8d
0x18007e0e6  neg     r8d
0x18007e0e9  add     r8d, 20h ; ' '
0x18007e0ed  call    MSCryptOpenHashProvider
0x18007e0f2  xor     r12d, r12d
0x18007e0f5  mov     ebx, eax
0x18007e0f7  test    eax, eax
0x18007e0f9  jz      short loc_18007E11F
0x18007e0fb  mov     r9d, 5EDh
0x18007e101  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e108  lea     rdx, aStatus; "Status"
0x18007e10f  mov     ecx, eax
0x18007e111  call    DebugTraceError
0x18007e116  mov     rdi, qword ptr [rbp+var_18]
0x18007e11a  jmp     loc_18007E239
0x18007e11f  mov     rdi, qword ptr [rbp+var_18]
0x18007e123  lea     rax, [rbp+var_24]
0x18007e127  mov     rcx, rdi
0x18007e12a  mov     dword ptr [rsp+68h+Src], r12d
0x18007e12f  mov     r9d, 4
0x18007e135  mov     qword ptr [rsp+68h+var_48], rax
0x18007e13a  lea     r8, [rbp+arg_8]
0x18007e13e  lea     rdx, aObjectlength; "ObjectLength"
0x18007e145  call    MSCryptGetHashProperty
0x18007e14a  mov     ebx, eax
0x18007e14c  test    eax, eax
0x18007e14e  jz      short loc_18007E15D
0x18007e150  mov     r9d, 5FBh
0x18007e156  mov     ecx, eax
0x18007e158  jmp     loc_18007E226
0x18007e15d  mov     ecx, dword ptr [rbp+arg_8]
0x18007e160  call    MSCryptAlloc
0x18007e165  mov     rsi, rax
0x18007e168  test    rax, rax
0x18007e16b  jnz     short loc_18007E182
0x18007e16d  mov     ebx, 0C0000017h
0x18007e172  mov     r9d, 603h
0x18007e178  mov     ecx, 0C0000017h
0x18007e17d  jmp     loc_18007E226
0x18007e182  mov     eax, dword ptr [rbp+arg_8]
0x18007e185  lea     rdx, [rbp+var_20]; int
0x18007e189  mov     [rsp+68h+var_30], r12d; int
0x18007e18e  mov     r9, rsi; int
0x18007e191  mov     dword ptr [rsp+68h+Size], r12d; Size
0x18007e196  xor     r8d, r8d; int
0x18007e199  mov     [rsp+68h+Src], r12; Src
0x18007e19e  mov     rcx, rdi; int
0x18007e1a1  mov     [rsp+68h+var_48], eax; int
0x18007e1a5  call    MSCryptCreateMultiHash
0x18007e1aa  mov     ebx, eax
0x18007e1ac  test    eax, eax
0x18007e1ae  jz      short loc_18007E1B8
0x18007e1b0  mov     r9d, 613h
0x18007e1b6  jmp     short loc_18007E156
0x18007e1b8  mov     rdx, [rbp+arg_0]
0x18007e1bc  xor     r9d, r9d
0x18007e1bf  mov     rcx, qword ptr [rbp+var_20]
0x18007e1c3  mov     r8d, [rdx+10h]
0x18007e1c7  mov     rdx, [rdx+18h]
0x18007e1cb  call    MSCryptHashData
0x18007e1d0  mov     ebx, eax
0x18007e1d2  test    eax, eax
0x18007e1d4  jz      short loc_18007E1E1
0x18007e1d6  mov     r9d, 61Eh
0x18007e1dc  jmp     loc_18007E156
0x18007e1e1  mov     r15d, [rbp+arg_18]
0x18007e1e5  mov     r8d, r15d
0x18007e1e8  mov     r9d, [rbp+arg_28]
0x18007e1ec  mov     rdx, [rbp+arg_10]
0x18007e1f0  mov     rcx, qword ptr [rbp+var_20]
0x18007e1f4  call    _CapiKDF
0x18007e1f9  mov     ebx, eax
0x18007e1fb  test    eax, eax
0x18007e1fd  jz      short loc_18007E20A
0x18007e1ff  mov     r9d, 62Ah
0x18007e205  jmp     loc_18007E156
0x18007e20a  mov     rax, [rbp+arg_20]
0x18007e20e  mov     ebx, r12d
0x18007e211  mov     [rax], r15d
0x18007e214  jmp     short loc_18007E239
0x18007e216  mov     r9d, 5C6h
0x18007e21c  mov     ebx, 0C000000Dh
0x18007e221  mov     ecx, 0C000000Dh
0x18007e226  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e22d  lea     rdx, aStatus; "Status"
0x18007e234  call    DebugTraceError
0x18007e239  mov     rcx, qword ptr [rbp+var_20]
0x18007e23d  test    rcx, rcx
0x18007e240  jz      short loc_18007E247
0x18007e242  call    MSCryptDestroyHash
0x18007e247  test    rsi, rsi
0x18007e24a  jz      short loc_18007E26B
0x18007e24c  mov     eax, dword ptr [rbp+arg_8]
0x18007e24f  mov     rdx, rsi
0x18007e252  test    rax, rax
0x18007e255  jz      short loc_18007E263
0x18007e257  mov     [rdx], r12b
0x18007e25a  inc     rdx
0x18007e25d  sub     rax, 1
0x18007e261  jnz     short loc_18007E257
0x18007e263  mov     rcx, rsi; P
0x18007e266  call    MSCryptFree
0x18007e26b  test    rdi, rdi
0x18007e26e  jz      short loc_18007E27A
0x18007e270  xor     edx, edx
0x18007e272  mov     rcx, rdi
0x18007e275  call    MSCryptCloseHashProvider
0x18007e27a  test    r14, r14
0x18007e27d  jz      short loc_18007E287
0x18007e27f  mov     rcx, r14; P
0x18007e282  call    MSCryptFree
0x18007e287  mov     eax, ebx
0x18007e289  add     rsp, 68h
0x18007e28d  pop     r15
0x18007e28f  pop     r14
0x18007e291  pop     r13
0x18007e293  pop     r12
0x18007e295  pop     rdi
0x18007e296  pop     rsi
0x18007e297  pop     rbx
0x18007e298  pop     rbp
0x18007e299  retn
```
