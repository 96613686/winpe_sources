# ImportEccKeyBlobWithoutParameters

- ea: `0x18004f89c`
- end: `0x18004fc8b`
- name: `ImportEccKeyBlobWithoutParameters`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180081178`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18004b628`
- `0x18004d684`
- `0x18004f89c`
- `0x18004fc94`
- `0x180050c88`
- `0x180050eec`
- `0x180051dd0`
- `0x180052d04`
- `0x180052e18`
- `0x18007f490`
- `0x18008052c`
- `0x1800a45c0`

## string_xrefs

- `0x18004f8f9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004f975`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004fa2d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004faad`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004fb89`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004fc69`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithoutParameters(
        __int64 a1,
        int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        char a7,
        _QWORD *a8)
{
  __int64 *v8; // rsi
  __int64 v9; // rdi
  int v10; // r10d
  __int64 v14; // r13
  int NistParametersForKeyMagic; // eax
  __int64 v16; // rbx
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // edx
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // ecx
  int KeyMagicForAlgId; // eax
  int v24; // eax
  int v25; // eax
  char *v26; // r14
  __int64 *v27; // rax
  unsigned int *v28; // r12
  __int64 v29; // r13
  __int64 v30; // rdx
  unsigned int v31; // r10d
  unsigned int v32; // eax
  char *v33; // rax
  size_t v35; // r8
  int v36; // r13d
  char *v37; // r15
  __int64 v38; // r9
  __int64 v39; // rcx
  int v40; // r12d
  __int64 v41; // rax
  unsigned int v42; // eax
  int v43; // [rsp+40h] [rbp-20h] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  __int64 v45; // [rsp+50h] [rbp-10h] BYREF
  int v47; // [rsp+A8h] [rbp+48h] BYREF

  v8 = *(__int64 **)(a1 + 16);
  v9 = 0;
  v10 = 0;
  v45 = 0;
  v43 = 0;
  v47 = 0;
  P = 0;
  v14 = a1;
  if ( !v8 )
  {
    NistParametersForKeyMagic = GetNistParametersForKeyMagic((unsigned int)*a2, &P);
    LODWORD(v16) = NistParametersForKeyMagic;
    if ( NistParametersForKeyMagic < 0 )
    {
      DebugTraceError(
        (unsigned int)NistParametersForKeyMagic,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        2005);
      v8 = (__int64 *)P;
      goto LABEL_42;
    }
    v10 = *a2;
    v8 = (__int64 *)P;
    v47 = *a2;
  }
  if ( a3 >= 8 && v8 )
  {
    v17 = *(_DWORD *)(*v8 + 12);
    v18 = a2[1];
    v19 = v17;
    if ( v17 <= *(_DWORD *)(*v8 + 16) )
      v19 = *(_DWORD *)(*v8 + 16);
    if ( a6 )
    {
      if ( v18 != v19 )
      {
        v20 = 2043;
        goto LABEL_13;
      }
    }
    else if ( v18 != v17 && v18 != v19 )
    {
      v20 = 2035;
LABEL_13:
      LODWORD(v16) = -1073741811;
      v21 = 3221225485LL;
LABEL_14:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v20);
      goto LABEL_42;
    }
    v22 = 2 * v18 + 8;
    if ( a6 )
      v22 += v18;
    if ( a3 < v22 )
    {
      v20 = 2057;
      goto LABEL_13;
    }
    if ( !v10 )
    {
      KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(v14 + 8), (_DWORD)v8, a5, a6, (__int64)&v47);
      LODWORD(v16) = KeyMagicForAlgId;
      if ( KeyMagicForAlgId < 0 )
      {
        v20 = 2070;
        v21 = (unsigned int)KeyMagicForAlgId;
        goto LABEL_14;
      }
      v10 = v47;
    }
    v24 = *a2;
    if ( *a2 != v10 && v24 != 1447314245 && v24 != 1346650949 && v24 != 1447772997 && v24 != 1347109701 )
    {
      v20 = 2086;
      goto LABEL_13;
    }
    v25 = AllocateGenericEccKey(&v45, &v43, a4, v14);
    LODWORD(v16) = v25;
    if ( v25 < 0 )
    {
      DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2093);
      v9 = v45;
      goto LABEL_40;
    }
    v47 = 0;
    v26 = 0;
    P = 0;
    v9 = v45;
    v27 = *(__int64 **)(v45 + 16);
    if ( !v27 )
    {
      *(_QWORD *)(v45 + 16) = v8;
      v27 = v8;
      v8 = 0;
    }
    v28 = (unsigned int *)(a2 + 2);
    v29 = *v27;
    if ( !(unsigned int)IsAllZeros(a2 + 2, (unsigned int)(2 * a2[1])) )
    {
      v32 = *(_DWORD *)(v29 + 12);
      if ( v31 <= v32 )
      {
        v26 = (char *)(a2 + 2);
        P = (PVOID)(unsigned int)v30;
      }
      else
      {
        v33 = (char *)MSCryptAlloc(2 * v32, v30);
        v26 = v33;
        if ( !v33 )
        {
          LODWORD(v16) = -1073741801;
          DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2125);
LABEL_39:
          v14 = a1;
          goto LABEL_40;
        }
        v35 = *(unsigned int *)(v29 + 12);
        P = (PVOID)(unsigned int)(2 * v35);
        memmove(v33, a2 + 2, v35);
        memmove(&v26[*(unsigned int *)(v29 + 12)], (char *)v28 + (unsigned int)a2[1], *(unsigned int *)(v29 + 12));
        v47 = 1;
      }
    }
    if ( a6 )
    {
      v36 = *(_DWORD *)(v29 + 16);
      v37 = (char *)v28 + (unsigned int)(2 * a2[1]);
    }
    else
    {
      v37 = 0;
      v36 = 0;
    }
    if ( (a7 & 0x20) == 0 || v37 && v26 )
    {
      v43 = BCryptFlagsToSymCryptKeyValidationFlags();
      v40 = a5 != 0 ? 4096 : 0x2000;
      v41 = SymCryptEckeyAllocate(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL));
      *(_QWORD *)(v9 + 24) = v41;
      if ( v41 )
      {
        v42 = SymCryptEckeySetValue(
                (_DWORD)v37,
                v36,
                (_DWORD)v26,
                (_DWORD)P,
                (unsigned int)(*(_DWORD *)(**(_QWORD **)(v9 + 16) + 4LL) != 3) + 1,
                2,
                v43 | (unsigned int)v40,
                v41);
        if ( !v42 )
        {
          *a8 = v9;
          v9 = 0;
LABEL_61:
          if ( v47 )
            MSCryptFree(v26);
          goto LABEL_39;
        }
        v16 = (unsigned int)SymcryptErrorCodeToNtStatus(v42);
        v39 = v16;
        v38 = 2184;
      }
      else
      {
        LODWORD(v16) = -1073741801;
        v38 = 2168;
        v39 = 3221225495LL;
      }
    }
    else
    {
      LODWORD(v16) = -1073741811;
      v38 = 2157;
      v39 = 3221225485LL;
    }
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v38);
    goto LABEL_61;
  }
  LODWORD(v16) = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2024);
LABEL_40:
  if ( v9 )
    MSCryptEccDestroyKeyPair(v9, a5);
LABEL_42:
  if ( !*(_QWORD *)(v14 + 16) && v8 )
    FreeGenericEccKeyParameters(v8);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18004f89c  mov     [rsp-38h+arg_10], rbx
0x18004f8a1  mov     [rsp-38h+arg_0], rcx
0x18004f8a6  push    rbp
0x18004f8a7  push    rsi
0x18004f8a8  push    rdi
0x18004f8a9  push    r12
0x18004f8ab  push    r13
0x18004f8ad  push    r14
0x18004f8af  push    r15
0x18004f8b1  mov     rbp, rsp
0x18004f8b4  sub     rsp, 60h
0x18004f8b8  mov     rsi, [rcx+10h]
0x18004f8bc  xor     edi, edi
0x18004f8be  xor     r10d, r10d
0x18004f8c1  mov     [rbp+var_10], rdi
0x18004f8c5  mov     [rbp+var_20], edi
0x18004f8c8  mov     r12d, r9d
0x18004f8cb  mov     [rbp+arg_8], r10d
0x18004f8cf  mov     r14d, r8d
0x18004f8d2  mov     [rbp+P], rdi
0x18004f8d6  mov     r15, rdx
0x18004f8d9  mov     r13, rcx
0x18004f8dc  test    rsi, rsi
0x18004f8df  jnz     short loc_18004F922
0x18004f8e1  mov     ecx, [r15]
0x18004f8e4  lea     rdx, [rbp+P]
0x18004f8e8  call    GetNistParametersForKeyMagic
0x18004f8ed  mov     ebx, eax
0x18004f8ef  test    eax, eax
0x18004f8f1  jns     short loc_18004F917
0x18004f8f3  mov     r9d, 7D5h
0x18004f8f9  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f900  lea     rdx, aStatus; "Status"
0x18004f907  mov     ecx, eax
0x18004f909  call    DebugTraceError
0x18004f90e  mov     rsi, [rbp+P]
0x18004f912  jmp     loc_18004FADE
0x18004f917  mov     r10d, [r15]
0x18004f91a  mov     rsi, [rbp+P]
0x18004f91e  mov     [rbp+arg_8], r10d
0x18004f922  cmp     r14d, 8
0x18004f926  jb      loc_18004FC63
0x18004f92c  test    rsi, rsi
0x18004f92f  jz      loc_18004FC63
0x18004f935  mov     rax, [rsi]
0x18004f938  mov     r9d, [rbp+arg_28]
0x18004f93c  mov     ecx, [rax+10h]
0x18004f93f  mov     r8d, [rax+0Ch]
0x18004f943  cmp     r8d, ecx
0x18004f946  mov     eax, [r15+4]
0x18004f94a  mov     edx, r8d
0x18004f94d  cmovbe  edx, ecx
0x18004f950  test    r9d, r9d
0x18004f953  jnz     short loc_18004F986
0x18004f955  cmp     eax, r8d
0x18004f958  jz      short loc_18004F992
0x18004f95a  cmp     eax, edx
0x18004f95c  jz      short loc_18004F992
0x18004f95e  mov     r9d, 7F3h
0x18004f964  mov     ebx, 0C000000Dh
0x18004f969  mov     ecx, 0C000000Dh
0x18004f96e  lea     rdx, aStatus; "Status"
0x18004f975  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f97c  call    DebugTraceError
0x18004f981  jmp     loc_18004FADE
0x18004f986  cmp     eax, edx
0x18004f988  jz      short loc_18004F992
0x18004f98a  mov     r9d, 7FBh
0x18004f990  jmp     short loc_18004F964
0x18004f992  lea     ecx, ds:8[rax*2]
0x18004f999  test    r9d, r9d
0x18004f99c  jz      short loc_18004F9A0
0x18004f99e  add     ecx, eax
0x18004f9a0  cmp     r14d, ecx
0x18004f9a3  jnb     short loc_18004F9AD
0x18004f9a5  mov     r9d, 809h
0x18004f9ab  jmp     short loc_18004F964
0x18004f9ad  test    r10d, r10d
0x18004f9b0  jnz     short loc_18004F9DF
0x18004f9b2  mov     r8d, [rbp+arg_20]
0x18004f9b6  lea     rax, [rbp+arg_8]
0x18004f9ba  mov     ecx, [r13+8]
0x18004f9be  mov     rdx, rsi
0x18004f9c1  mov     [rsp+60h+var_40], rax
0x18004f9c6  call    MSCryptEcGetKeyMagicForAlgId
0x18004f9cb  mov     ebx, eax
0x18004f9cd  test    eax, eax
0x18004f9cf  jns     short loc_18004F9DB
0x18004f9d1  mov     r9d, 816h
0x18004f9d7  mov     ecx, eax
0x18004f9d9  jmp     short loc_18004F96E
0x18004f9db  mov     r10d, [rbp+arg_8]
0x18004f9df  mov     eax, [r15]
0x18004f9e2  cmp     eax, r10d
0x18004f9e5  jz      short loc_18004FA0E
0x18004f9e7  cmp     eax, 56444345h
0x18004f9ec  jz      short loc_18004FA0E
0x18004f9ee  cmp     eax, 50444345h
0x18004f9f3  jz      short loc_18004FA0E
0x18004f9f5  cmp     eax, 564B4345h
0x18004f9fa  jz      short loc_18004FA0E
0x18004f9fc  cmp     eax, 504B4345h
0x18004fa01  jz      short loc_18004FA0E
0x18004fa03  mov     r9d, 826h
0x18004fa09  jmp     loc_18004F964
0x18004fa0e  mov     r9, r13
0x18004fa11  lea     rdx, [rbp+var_20]
0x18004fa15  mov     r8d, r12d
0x18004fa18  lea     rcx, [rbp+var_10]
0x18004fa1c  call    AllocateGenericEccKey
0x18004fa21  mov     ebx, eax
0x18004fa23  test    eax, eax
0x18004fa25  jns     short loc_18004FA4B
0x18004fa27  mov     r9d, 82Dh
0x18004fa2d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fa34  lea     rdx, aStatus; "Status"
0x18004fa3b  mov     ecx, eax
0x18004fa3d  call    DebugTraceError
0x18004fa42  mov     rdi, [rbp+var_10]
0x18004fa46  jmp     loc_18004FACE
0x18004fa4b  mov     [rbp+arg_8], edi
0x18004fa4e  xor     r14d, r14d
0x18004fa51  mov     [rbp+P], rdi
0x18004fa55  mov     rdi, [rbp+var_10]
0x18004fa59  mov     rax, [rdi+10h]
0x18004fa5d  test    rax, rax
0x18004fa60  jnz     short loc_18004FA6B
0x18004fa62  mov     [rdi+10h], rsi
0x18004fa66  mov     rax, rsi
0x18004fa69  xor     esi, esi
0x18004fa6b  mov     r10d, [r15+4]
0x18004fa6f  lea     r12, [r15+8]
0x18004fa73  mov     r13, [rax]
0x18004fa76  mov     rcx, r12
0x18004fa79  lea     edx, [r10+r10]
0x18004fa7d  call    IsAllZeros
0x18004fa82  test    eax, eax
0x18004fa84  jnz     loc_18004FB4A
0x18004fa8a  mov     eax, [r13+0Ch]
0x18004fa8e  cmp     r10d, eax
0x18004fa91  jbe     loc_18004FB41
0x18004fa97  lea     ecx, [rax+rax]
0x18004fa9a  call    MSCryptAlloc
0x18004fa9f  mov     r14, rax
0x18004faa2  test    rax, rax
0x18004faa5  jnz     short loc_18004FB0D
0x18004faa7  mov     r9d, 84Dh
0x18004faad  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fab4  lea     rdx, aStatus; "Status"
0x18004fabb  mov     ecx, 0C0000017h
0x18004fac0  mov     ebx, 0C0000017h
0x18004fac5  call    DebugTraceError
0x18004faca  mov     r13, [rbp+arg_0]
0x18004face  test    rdi, rdi
0x18004fad1  jz      short loc_18004FADE
0x18004fad3  mov     edx, [rbp+arg_20]
0x18004fad6  mov     rcx, rdi
0x18004fad9  call    MSCryptEccDestroyKeyPair
0x18004fade  cmp     qword ptr [r13+10h], 0
0x18004fae3  jnz     short loc_18004FAF2
0x18004fae5  test    rsi, rsi
0x18004fae8  jz      short loc_18004FAF2
0x18004faea  mov     rcx, rsi; P
0x18004faed  call    FreeGenericEccKeyParameters
0x18004faf2  mov     eax, ebx
0x18004faf4  mov     rbx, [rsp+60h+arg_10]
0x18004fafc  add     rsp, 60h
0x18004fb00  pop     r15
0x18004fb02  pop     r14
0x18004fb04  pop     r13
0x18004fb06  pop     r12
0x18004fb08  pop     rdi
0x18004fb09  pop     rsi
0x18004fb0a  pop     rbp
0x18004fb0b  retn
0x18004fb0d  mov     r8d, [r13+0Ch]; Size
0x18004fb11  mov     rdx, r12; Src
0x18004fb14  mov     rcx, r14; void *
0x18004fb17  lea     eax, [r8+r8]
0x18004fb1b  mov     [rbp+P], rax
0x18004fb1f  call    memmove
0x18004fb24  mov     r8d, [r13+0Ch]; Size
0x18004fb28  mov     edx, [r15+4]
0x18004fb2c  add     rdx, r12; Src
0x18004fb2f  lea     rcx, [r8+r14]; void *
0x18004fb33  call    memmove
0x18004fb38  mov     [rbp+arg_8], 1
0x18004fb3f  jmp     short loc_18004FB4A
0x18004fb41  mov     eax, edx
0x18004fb43  mov     r14, r12
0x18004fb46  mov     [rbp+P], rax
0x18004fb4a  cmp     [rbp+arg_28], 0
0x18004fb4e  jz      short loc_18004FB61
0x18004fb50  mov     eax, [r15+4]
0x18004fb54  mov     r13d, [r13+10h]
0x18004fb58  lea     r15d, [rax+rax]
0x18004fb5c  add     r15, r12
0x18004fb5f  jmp     short loc_18004FB67
0x18004fb61  xor     r15d, r15d
0x18004fb64  xor     r13d, r13d
0x18004fb67  mov     ecx, dword ptr [rbp+arg_30]
0x18004fb6a  test    cl, 20h
0x18004fb6d  jz      short loc_18004FBA1
0x18004fb6f  test    r15, r15
0x18004fb72  jz      short loc_18004FB79
0x18004fb74  test    r14, r14
0x18004fb77  jnz     short loc_18004FBA1
0x18004fb79  mov     ebx, 0C000000Dh
0x18004fb7e  mov     r9d, 86Dh
0x18004fb84  mov     ecx, 0C000000Dh
0x18004fb89  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fb90  lea     rdx, aStatus; "Status"
0x18004fb97  call    DebugTraceError
0x18004fb9c  jmp     loc_18004FC4C
0x18004fba1  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18004fba6  mov     ecx, [rbp+arg_20]
0x18004fba9  neg     ecx
0x18004fbab  mov     [rbp+var_20], eax
0x18004fbae  mov     rcx, [rdi+10h]
0x18004fbb2  sbb     r12d, r12d
0x18004fbb5  and     r12d, 0FFFFF000h
0x18004fbbc  add     r12d, 2000h
0x18004fbc3  mov     rcx, [rcx+8]
0x18004fbc7  call    SymCryptEckeyAllocate
0x18004fbcc  mov     [rdi+18h], rax
0x18004fbd0  mov     rcx, rax
0x18004fbd3  test    rax, rax
0x18004fbd6  jnz     short loc_18004FBEA
0x18004fbd8  mov     ebx, 0C0000017h
0x18004fbdd  mov     r9d, 878h
0x18004fbe3  mov     ecx, 0C0000017h
0x18004fbe8  jmp     short loc_18004FB89
0x18004fbea  mov     rax, [rdi+10h]
0x18004fbee  mov     rdx, r13
0x18004fbf1  or      r12d, [rbp+var_20]
0x18004fbf5  mov     r9, [rbp+P]
0x18004fbf9  mov     [rsp+60h+var_28], rcx
0x18004fbfe  mov     rcx, r15
0x18004fc01  mov     r8, [rax]
0x18004fc04  xor     eax, eax
0x18004fc06  mov     [rsp+60h+var_30], r12d
0x18004fc0b  mov     [rsp+60h+var_38], 2
0x18004fc13  cmp     dword ptr [r8+4], 3
0x18004fc18  mov     r8, r14
0x18004fc1b  setnz   al
0x18004fc1e  inc     eax
0x18004fc20  mov     dword ptr [rsp+60h+var_40], eax
0x18004fc24  call    SymCryptEckeySetValue
0x18004fc29  test    eax, eax
0x18004fc2b  jz      short loc_18004FC43
0x18004fc2d  mov     ecx, eax
0x18004fc2f  call    SymcryptErrorCodeToNtStatus
0x18004fc34  mov     ebx, eax
0x18004fc36  mov     ecx, eax
0x18004fc38  mov     r9d, 888h
0x18004fc3e  jmp     loc_18004FB89
0x18004fc43  mov     rax, [rbp+arg_38]
0x18004fc47  mov     [rax], rdi
0x18004fc4a  xor     edi, edi
0x18004fc4c  cmp     [rbp+arg_8], 0
0x18004fc50  jz      loc_18004FACA
0x18004fc56  mov     rcx, r14; P
0x18004fc59  call    MSCryptFree
0x18004fc5e  jmp     loc_18004FACA
0x18004fc63  mov     r9d, 7E8h
0x18004fc69  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fc70  lea     rdx, aStatus; "Status"
0x18004fc77  mov     ecx, 0C000000Dh
0x18004fc7c  mov     ebx, 0C000000Dh
0x18004fc81  call    DebugTraceError
0x18004fc86  jmp     loc_18004FACE
```
