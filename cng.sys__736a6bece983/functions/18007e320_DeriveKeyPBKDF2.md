# DeriveKeyPBKDF2

- ea: `0x18007e320`
- end: `0x18007e81a`
- name: `DeriveKeyPBKDF2`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
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
- `0x180040e98`
- `0x18007e320`
- `0x18007ec84`
- `0x18009f780`

## string_xrefs

- `0x18007e3a7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e530`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e6bc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e710`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007e7d4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyPBKDF2(__int64 a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5, int a6)
{
  _DWORD *v7; // rsi
  _WORD *v8; // r13
  int v9; // r15d
  int KeyBitLength; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 ParameterList; // rbx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  _QWORD *v21; // rbx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdi
  __int64 v26; // rax
  _WORD *v27; // rdx
  unsigned __int64 v28; // rsi
  size_t v29; // r14
  _WORD *v30; // rax
  unsigned int v31; // eax
  int HashProperty; // eax
  __int64 v33; // r9
  __int64 v34; // rcx
  unsigned int v35; // r15d
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  _BYTE *v39; // r12
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  _BYTE *v43; // r14
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  char *v48; // rdi
  unsigned int i; // eax
  unsigned int v50; // eax
  int v51; // ebx
  unsigned int v52; // r15d
  _BYTE *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  _BYTE *v56; // rcx
  __int64 v57; // rax
  _BYTE *v58; // rcx
  unsigned int v60; // [rsp+68h] [rbp-19h] BYREF
  __int64 v61; // [rsp+6Ch] [rbp-15h] BYREF
  int v62; // [rsp+74h] [rbp-Dh] BYREF
  __int64 v63; // [rsp+78h] [rbp-9h] BYREF
  size_t Size; // [rsp+80h] [rbp-1h] BYREF
  __int64 v65; // [rsp+88h] [rbp+7h]
  __int64 v66; // [rsp+90h] [rbp+Fh]
  __int64 v68; // [rsp+E0h] [rbp+5Fh] BYREF
  void *v69; // [rsp+E8h] [rbp+67h]

  v69 = a3;
  Size = 0;
  LODWORD(v63) = 0;
  v7 = 0;
  LODWORD(v61) = 0;
  v8 = 0;
  LODWORD(v68) = 0;
  v60 = 0;
  v62 = 0;
  if ( !a2 || a6 )
  {
    v11 = -1073741811;
    v33 = 881;
    v34 = 3221225485LL;
    goto LABEL_62;
  }
  *a5 = 0;
  v9 = *(_DWORD *)(a1 + 32);
  KeyBitLength = GetKeyBitLength(a2, a4, &v62);
  v11 = KeyBitLength;
  if ( KeyBitLength < 0 )
  {
    v12 = 909;
    v13 = (unsigned int)KeyBitLength;
LABEL_5:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v12);
    return v11;
  }
  ParameterList = (int)QueryParameterList(a2, 17, 0);
  v16 = QueryParameterList(v15, 15, 0);
  if ( v16 >= 0 )
  {
    if ( (int)ParameterList >= 0 )
    {
      v12 = 938;
LABEL_9:
      v11 = -1073741811;
      v13 = 3221225485LL;
      goto LABEL_5;
    }
    v17 = v16;
    goto LABEL_11;
  }
  if ( (int)ParameterList >= 0 )
  {
    v17 = ParameterList;
LABEL_11:
    v18 = *(_QWORD *)(a2 + 8);
    v19 = 2 * v17;
    v65 = *(_QWORD *)(v18 + 8 * v19 + 8);
    HIDWORD(v61) = *(_DWORD *)(v18 + 8 * v19);
    goto LABEL_15;
  }
  HIDWORD(v61) = 0;
  v65 = 0;
LABEL_15:
  v20 = QueryParameterList(a2, 16, 0);
  v21 = (_QWORD *)(a2 + 8);
  if ( v20 < 0 )
  {
    v66 = 10000;
  }
  else
  {
    if ( *(_DWORD *)(*v21 + 16LL * v20) != 8 )
    {
      v12 = 968;
      goto LABEL_9;
    }
    _mm_lfence();
    v66 = **(_QWORD **)(*v21 + 16LL * v20 + 8);
    if ( !v66 )
    {
      v12 = 978;
      goto LABEL_9;
    }
  }
  v22 = QueryParameterList(a2, 0, 0);
  if ( v22 < 0 )
  {
    v12 = 1004;
    goto LABEL_9;
  }
  _mm_lfence();
  v25 = 2LL * v22;
  v26 = *(unsigned int *)(*v21 + 16LL * v22);
  if ( (v26 & 1) != 0 || (unsigned int)v26 < 2 )
  {
    v12 = 1015;
    goto LABEL_9;
  }
  v27 = *(_WORD **)(*v21 + 8 * v25 + 8);
  v28 = (unsigned __int64)(unsigned int)v26 >> 1;
  v29 = (unsigned int)v26;
  if ( v27[v28 - 1] )
  {
    v30 = (_WORD *)MSCryptAlloc(v26 + 2, v27, v23, v24);
    v8 = v30;
    if ( !v30 )
    {
      v11 = -1073741801;
      v12 = 1030;
      v13 = 3221225495LL;
      goto LABEL_5;
    }
    memmove(v30, *(const void **)(*v21 + 8 * v25 + 8), v29);
    v27 = v8;
    v8[v28] = 0;
  }
  v31 = MSCryptOpenHashProvider(&Size, v27, (unsigned int)(v9 != 0) + 40);
  v11 = v31;
  if ( !v31 )
  {
    v7 = (_DWORD *)Size;
    if ( (unsigned int)MSCryptGetHashProperty((_DWORD *)Size, L"IsKeyedHash", &v63, 4u, &v60, 0) || !(_DWORD)v63 )
    {
      v11 = -1073741816;
      v33 = 1071;
      v34 = 3221225480LL;
      goto LABEL_62;
    }
    HashProperty = MSCryptGetHashProperty(v7, L"HashDigestLength", &v68, 4u, &v60, 0);
    v11 = HashProperty;
    if ( HashProperty )
    {
      v33 = 1084;
LABEL_35:
      v34 = (unsigned int)HashProperty;
LABEL_62:
      DebugTraceError(v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v33);
      goto LABEL_63;
    }
    LODWORD(Size) = (unsigned int)(v62 + 7) >> 3;
    v35 = ((int)v68 + (int)Size - 1) / (unsigned int)v68;
    HashProperty = MSCryptGetHashProperty(v7, L"ObjectLength", &v61, 4u, &v60, 0);
    v11 = HashProperty;
    if ( HashProperty < 0 )
    {
      v33 = 1103;
      goto LABEL_35;
    }
    v39 = (_BYTE *)MSCryptAlloc((unsigned int)v68, v36, v37, v38);
    v43 = (_BYTE *)MSCryptAlloc((unsigned int)v61, v40, v41, v42);
    v47 = MSCryptAlloc((unsigned int)v68 * v35, v44, v45, v46);
    v48 = (char *)v47;
    if ( v39 && v43 && v47 )
    {
      for ( i = 0; i < v35; i = v60 )
      {
        v60 = i + 1;
        v50 = PBKDF2(
                v7,
                *(_QWORD *)(a1 + 24),
                *(unsigned int *)(a1 + 16),
                v65,
                HIDWORD(v61),
                v66,
                i + 1,
                v43,
                v61,
                v39,
                &v48[(unsigned int)v68 * i],
                v68);
        v11 = v50;
        if ( v50 )
        {
          DebugTraceError(
            v50,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            1137);
          goto LABEL_48;
        }
      }
      v51 = Size;
      memmove(v69, v48, (unsigned int)Size);
      *((_BYTE *)v69 + (unsigned int)(v51 - 1)) &= -1 << (8 * v51 - v62);
      *a5 = v51;
      v11 = 0;
    }
    else
    {
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        1116);
      v11 = -1073741801;
      if ( !v48 )
      {
LABEL_51:
        if ( v43 )
        {
          v55 = (unsigned int)v61;
          v56 = v43;
          if ( (_DWORD)v61 )
          {
            do
            {
              *v56++ = 0;
              --v55;
            }
            while ( v55 );
          }
          MSCryptFree(v43);
        }
        if ( v39 )
        {
          v57 = (unsigned int)v68;
          v58 = v39;
          if ( (_DWORD)v68 )
          {
            do
            {
              *v58++ = 0;
              --v57;
            }
            while ( v57 );
          }
          MSCryptFree(v39);
        }
        goto LABEL_63;
      }
    }
LABEL_48:
    v52 = v68 * v35;
    v53 = v48;
    v54 = v52;
    if ( v52 )
    {
      do
      {
        *v53++ = 0;
        --v54;
      }
      while ( v54 );
    }
    MSCryptFree(v48);
    goto LABEL_51;
  }
  DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1055);
  v7 = (_DWORD *)Size;
LABEL_63:
  if ( v7 )
    MSCryptCloseHashProvider(v7, 0);
  if ( v8 )
    MSCryptFree(v8);
  return v11;
}

```

## disassembly

```asm
0x18007e320  mov     rax, rsp
0x18007e323  mov     [rax+20h], rbx
0x18007e327  mov     [rax+18h], r8
0x18007e32b  mov     [rax+8], rcx
0x18007e32f  push    rbp
0x18007e330  push    rsi
0x18007e331  push    rdi
0x18007e332  push    r12
0x18007e334  push    r13
0x18007e336  push    r14
0x18007e338  push    r15
0x18007e33a  lea     rbp, [rax-4Fh]
0x18007e33e  sub     rsp, 90h
0x18007e345  xor     r12d, r12d
0x18007e348  mov     rdi, rdx
0x18007e34b  mov     [rbp+47h+Size], r12
0x18007e34f  mov     rax, rcx
0x18007e352  mov     dword ptr [rbp+47h+var_50], r12d
0x18007e356  mov     esi, r12d
0x18007e359  mov     [rbp+47h+var_5C], r12d
0x18007e35d  mov     r13d, r12d
0x18007e360  mov     dword ptr [rbp+47h+arg_8], r12d
0x18007e364  mov     [rbp+47h+var_60], r12d
0x18007e368  mov     [rbp+47h+var_54], r12d
0x18007e36c  test    rdx, rdx
0x18007e36f  jz      loc_18007E7BD
0x18007e375  cmp     [rbp+47h+arg_28], r12d
0x18007e379  jnz     loc_18007E7BD
0x18007e37f  mov     rcx, [rbp+47h+arg_20]
0x18007e383  lea     r8, [rbp+47h+var_54]
0x18007e387  mov     edx, r9d
0x18007e38a  mov     [rcx], r12d
0x18007e38d  mov     rcx, rdi
0x18007e390  mov     r15d, [rax+20h]
0x18007e394  call    GetKeyBitLength
0x18007e399  mov     ebx, eax
0x18007e39b  test    eax, eax
0x18007e39d  jns     short loc_18007E3BF
0x18007e39f  mov     r9d, 38Dh
0x18007e3a5  mov     ecx, eax
0x18007e3a7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e3ae  lea     rdx, aStatus; "Status"
0x18007e3b5  call    DebugTraceError
0x18007e3ba  jmp     loc_18007E7FC
0x18007e3bf  xor     r8d, r8d
0x18007e3c2  mov     rcx, rdi
0x18007e3c5  lea     edx, [r8+11h]
0x18007e3c9  call    QueryParameterList
0x18007e3ce  xor     r8d, r8d
0x18007e3d1  movsxd  rbx, eax
0x18007e3d4  lea     edx, [r8+0Fh]
0x18007e3d8  call    QueryParameterList
0x18007e3dd  test    eax, eax
0x18007e3df  js      short loc_18007E412
0x18007e3e1  test    ebx, ebx
0x18007e3e3  js      short loc_18007E3F7
0x18007e3e5  mov     r9d, 3AAh
0x18007e3eb  mov     ebx, 0C000000Dh
0x18007e3f0  mov     ecx, 0C000000Dh
0x18007e3f5  jmp     short loc_18007E3A7
0x18007e3f7  movsxd  rcx, eax
0x18007e3fa  mov     rax, [rdi+8]
0x18007e3fe  add     rcx, rcx
0x18007e401  mov     rsi, [rax+rcx*8+8]
0x18007e406  mov     [rbp+47h+var_40], rsi
0x18007e40a  mov     esi, [rax+rcx*8]
0x18007e40d  mov     [rbp+47h+var_58], esi
0x18007e410  jmp     short loc_18007E423
0x18007e412  test    ebx, ebx
0x18007e414  js      short loc_18007E41B
0x18007e416  mov     rcx, rbx
0x18007e419  jmp     short loc_18007E3FA
0x18007e41b  mov     [rbp+47h+var_58], r12d
0x18007e41f  mov     [rbp+47h+var_40], r12
0x18007e423  xor     r8d, r8d
0x18007e426  mov     rcx, rdi
0x18007e429  lea     edx, [r8+10h]
0x18007e42d  call    QueryParameterList
0x18007e432  lea     rbx, [rdi+8]
0x18007e436  test    eax, eax
0x18007e438  js      short loc_18007E473
0x18007e43a  movsxd  rcx, eax
0x18007e43d  mov     rax, [rbx]
0x18007e440  add     rcx, rcx
0x18007e443  cmp     dword ptr [rax+rcx*8], 8
0x18007e447  jz      short loc_18007E451
0x18007e449  mov     r9d, 3C8h
0x18007e44f  jmp     short loc_18007E3EB
0x18007e451  lfence
0x18007e454  mov     rax, [rbx]
0x18007e457  mov     rcx, [rax+rcx*8+8]
0x18007e45c  mov     rsi, [rcx]
0x18007e45f  mov     [rbp+47h+var_38], rsi
0x18007e463  test    rsi, rsi
0x18007e466  jnz     short loc_18007E47B
0x18007e468  mov     r9d, 3D2h
0x18007e46e  jmp     loc_18007E3EB
0x18007e473  mov     [rbp+47h+var_38], 2710h
0x18007e47b  xor     r8d, r8d
0x18007e47e  xor     edx, edx
0x18007e480  mov     rcx, rdi
0x18007e483  call    QueryParameterList
0x18007e488  test    eax, eax
0x18007e48a  jns     short loc_18007E497
0x18007e48c  mov     r9d, 3ECh
0x18007e492  jmp     loc_18007E3EB
0x18007e497  lfence
0x18007e49a  mov     rdx, [rbx]
0x18007e49d  movsxd  rdi, eax
0x18007e4a0  add     rdi, rdi
0x18007e4a3  mov     eax, [rdx+rdi*8]
0x18007e4a6  test    al, 1
0x18007e4a8  jnz     loc_18007E7B2
0x18007e4ae  cmp     eax, 2
0x18007e4b1  jb      loc_18007E7B2
0x18007e4b7  mov     rdx, [rdx+rdi*8+8]
0x18007e4bc  mov     esi, eax
0x18007e4be  shr     rsi, 1
0x18007e4c1  mov     r14d, eax
0x18007e4c4  cmp     r12w, [rdx+rsi*2-2]
0x18007e4ca  jz      short loc_18007E50E
0x18007e4cc  lea     rcx, [rax+2]
0x18007e4d0  call    MSCryptAlloc
0x18007e4d5  mov     r13, rax
0x18007e4d8  test    rax, rax
0x18007e4db  jnz     short loc_18007E4F2
0x18007e4dd  mov     ebx, 0C0000017h
0x18007e4e2  mov     r9d, 406h
0x18007e4e8  mov     ecx, 0C0000017h
0x18007e4ed  jmp     loc_18007E3A7
0x18007e4f2  mov     rdx, [rbx]
0x18007e4f5  mov     r8, r14; Size
0x18007e4f8  mov     rcx, r13; void *
0x18007e4fb  mov     rdx, [rdx+rdi*8+8]; Src
0x18007e500  call    memmove
0x18007e505  mov     rdx, r13
0x18007e508  mov     [r13+rsi*2+0], r12w
0x18007e50e  neg     r15d
0x18007e511  lea     rcx, [rbp+47h+Size]
0x18007e515  sbb     r8d, r8d
0x18007e518  neg     r8d
0x18007e51b  add     r8d, 28h ; '('
0x18007e51f  call    MSCryptOpenHashProvider
0x18007e524  mov     ebx, eax
0x18007e526  test    eax, eax
0x18007e528  jz      short loc_18007E54E
0x18007e52a  mov     r9d, 41Fh
0x18007e530  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e537  lea     rdx, aStatus; "Status"
0x18007e53e  mov     ecx, eax
0x18007e540  call    DebugTraceError
0x18007e545  mov     rsi, [rbp+47h+Size]
0x18007e549  jmp     loc_18007E7E0
0x18007e54e  mov     rsi, [rbp+47h+Size]
0x18007e552  lea     rax, [rbp+47h+var_60]
0x18007e556  mov     edi, 4
0x18007e55b  mov     [rsp+0C0h+var_98], r12d
0x18007e560  mov     r9d, edi
0x18007e563  mov     [rsp+0C0h+var_A0], rax
0x18007e568  mov     rcx, rsi
0x18007e56b  lea     r8, [rbp+47h+var_50]
0x18007e56f  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18007e576  call    MSCryptGetHashProperty
0x18007e57b  test    eax, eax
0x18007e57d  jnz     loc_18007E7A0
0x18007e583  cmp     dword ptr [rbp+47h+var_50], r12d
0x18007e587  jz      loc_18007E7A0
0x18007e58d  lea     rax, [rbp+47h+var_60]
0x18007e591  mov     [rsp+0C0h+var_98], r12d
0x18007e596  mov     r9d, edi
0x18007e599  mov     [rsp+0C0h+var_A0], rax
0x18007e59e  lea     r8, [rbp+47h+arg_8]
0x18007e5a2  mov     rcx, rsi
0x18007e5a5  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007e5ac  call    MSCryptGetHashProperty
0x18007e5b1  mov     ebx, eax
0x18007e5b3  test    eax, eax
0x18007e5b5  jz      short loc_18007E5C4
0x18007e5b7  mov     r9d, 43Ch
0x18007e5bd  mov     ecx, eax
0x18007e5bf  jmp     loc_18007E7CD
0x18007e5c4  mov     eax, [rbp+47h+var_54]
0x18007e5c7  lea     r8, [rbp+47h+var_5C]
0x18007e5cb  add     eax, 7
0x18007e5ce  mov     [rsp+0C0h+var_98], r12d
0x18007e5d3  shr     eax, 3
0x18007e5d6  xor     edx, edx
0x18007e5d8  mov     dword ptr [rbp+47h+Size], eax
0x18007e5db  mov     r9d, edi
0x18007e5de  dec     eax
0x18007e5e0  mov     rcx, rsi
0x18007e5e3  add     eax, dword ptr [rbp+47h+arg_8]
0x18007e5e6  div     dword ptr [rbp+47h+arg_8]
0x18007e5e9  lea     rdx, aObjectlength; "ObjectLength"
0x18007e5f0  mov     r15d, eax
0x18007e5f3  lea     rax, [rbp+47h+var_60]
0x18007e5f7  mov     [rsp+0C0h+var_A0], rax
0x18007e5fc  call    MSCryptGetHashProperty
0x18007e601  mov     ebx, eax
0x18007e603  test    eax, eax
0x18007e605  jns     short loc_18007E60F
0x18007e607  mov     r9d, 44Fh
0x18007e60d  jmp     short loc_18007E5BD
0x18007e60f  mov     ecx, dword ptr [rbp+47h+arg_8]
0x18007e612  call    MSCryptAlloc
0x18007e617  mov     ecx, [rbp+47h+var_5C]
0x18007e61a  mov     r12, rax
0x18007e61d  call    MSCryptAlloc
0x18007e622  mov     ecx, r15d
0x18007e625  mov     r14, rax
0x18007e628  imul    ecx, dword ptr [rbp+47h+arg_8]
0x18007e62c  call    MSCryptAlloc
0x18007e631  mov     rdi, rax
0x18007e634  test    r12, r12
0x18007e637  jz      loc_18007E70A
0x18007e63d  test    r14, r14
0x18007e640  jz      loc_18007E70A
0x18007e646  test    rax, rax
0x18007e649  jz      loc_18007E70A
0x18007e64f  xor     eax, eax
0x18007e651  cmp     eax, r15d
0x18007e654  jnb     short loc_18007E6D3
0x18007e656  mov     ecx, dword ptr [rbp+47h+arg_8]
0x18007e659  lea     edx, [rax+1]
0x18007e65c  mov     r9, [rbp+47h+var_40]
0x18007e660  mov     [rsp+58h], ecx
0x18007e664  imul    eax, ecx
0x18007e667  mov     rcx, rsi
0x18007e66a  mov     [rbp+47h+var_60], edx
0x18007e66d  add     rax, rdi
0x18007e670  mov     qword ptr [rsp+0C0h+var_70], rax
0x18007e675  mov     eax, [rbp+47h+var_5C]
0x18007e678  mov     [rsp+0C0h+var_78], r12
0x18007e67d  mov     dword ptr [rsp+0C0h+var_80], eax
0x18007e681  mov     rax, [rbp+47h+var_38]
0x18007e685  mov     qword ptr [rsp+0C0h+var_88], r14
0x18007e68a  mov     dword ptr [rsp+0C0h+var_90], edx
0x18007e68e  mov     qword ptr [rsp+0C0h+var_98], rax
0x18007e693  mov     eax, [rbp+47h+var_58]
0x18007e696  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18007e69a  mov     rax, [rbp+47h+arg_0]
0x18007e69e  mov     r8d, [rax+10h]
0x18007e6a2  mov     rdx, [rax+18h]
0x18007e6a6  call    _PBKDF2
0x18007e6ab  mov     ebx, eax
0x18007e6ad  test    eax, eax
0x18007e6af  jnz     short loc_18007E6B6
0x18007e6b1  mov     eax, [rbp+47h+var_60]
0x18007e6b4  jmp     short loc_18007E651
0x18007e6b6  mov     r9d, 471h
0x18007e6bc  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e6c3  lea     rdx, aStatus; "Status"
0x18007e6ca  mov     ecx, eax
0x18007e6cc  call    DebugTraceError
0x18007e6d1  jmp     short loc_18007E732
0x18007e6d3  mov     ebx, dword ptr [rbp+47h+Size]
0x18007e6d6  mov     rdx, rdi; Src
0x18007e6d9  mov     rcx, [rbp+47h+arg_10]; void *
0x18007e6dd  mov     r8d, ebx; Size
0x18007e6e0  call    memmove
0x18007e6e5  lea     ecx, ds:0[rbx*8]
0x18007e6ec  mov     eax, 0FFh
0x18007e6f1  sub     ecx, [rbp+47h+var_54]
0x18007e6f4  lea     edx, [rbx-1]
0x18007e6f7  shl     al, cl
0x18007e6f9  mov     rcx, [rbp+47h+arg_10]
0x18007e6fd  and     [rdx+rcx], al
0x18007e700  mov     rax, [rbp+47h+arg_20]
0x18007e704  mov     [rax], ebx
0x18007e706  xor     ebx, ebx
0x18007e708  jmp     short loc_18007E732
0x18007e70a  mov     r9d, 45Ch
0x18007e710  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e717  lea     rdx, aStatus; "Status"
0x18007e71e  mov     ecx, 0C0000017h
0x18007e723  call    DebugTraceError
0x18007e728  mov     ebx, 0C0000017h
0x18007e72d  test    rdi, rdi
0x18007e730  jz      short loc_18007E756
0x18007e732  imul    r15d, dword ptr [rbp+47h+arg_8]
0x18007e737  mov     rax, rdi
0x18007e73a  mov     ecx, r15d
0x18007e73d  test    r15d, r15d
0x18007e740  jz      short loc_18007E74E
0x18007e742  mov     byte ptr [rax], 0
0x18007e745  inc     rax
0x18007e748  sub     rcx, 1
0x18007e74c  jnz     short loc_18007E742
0x18007e74e  mov     rcx, rdi; P
0x18007e751  call    MSCryptFree
0x18007e756  test    r14, r14
0x18007e759  jz      short loc_18007E77A
0x18007e75b  mov     eax, [rbp+47h+var_5C]
0x18007e75e  mov     rcx, r14
0x18007e761  test    rax, rax
0x18007e764  jz      short loc_18007E772
0x18007e766  mov     byte ptr [rcx], 0
0x18007e769  inc     rcx
0x18007e76c  sub     rax, 1
0x18007e770  jnz     short loc_18007E766
  ... truncated ...
```
