# DeriveKeyPBKDF2

- ea: `0x18007d330`
- end: `0x18007d82a`
- name: `DeriveKeyPBKDF2`
- size: `1274`
- prototype: `__int64 __fastcall(__int64, __int64, void *, unsigned int, _DWORD *, int)`
- caller_count: `1`
- callee_count: `11`
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
- `0x180040308`
- `0x18007d330`
- `0x18007dc94`
- `0x18009da40`

## string_xrefs

- `0x18007d3b7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d540`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d6cc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d720`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007d7e4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyPBKDF2(__int64 a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5, int a6)
{
  size_t v7; // rsi
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
  __int64 v23; // rdi
  __int64 v24; // rax
  _WORD *v25; // rdx
  unsigned __int64 v26; // rsi
  size_t v27; // r14
  _WORD *v28; // rax
  unsigned int v29; // eax
  int HashProperty; // eax
  __int64 v31; // r9
  __int64 v32; // rcx
  unsigned int v33; // r15d
  _BYTE *v34; // r12
  _BYTE *v35; // r14
  __int64 v36; // rax
  char *v37; // rdi
  unsigned int i; // eax
  unsigned int v39; // eax
  int v40; // ebx
  unsigned int v41; // r15d
  _BYTE *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  _BYTE *v45; // rcx
  __int64 v46; // rax
  _BYTE *v47; // rcx
  unsigned int v49; // [rsp+68h] [rbp-19h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-15h] BYREF
  int v51; // [rsp+70h] [rbp-11h]
  int v52; // [rsp+74h] [rbp-Dh] BYREF
  int v53; // [rsp+78h] [rbp-9h] BYREF
  size_t Size; // [rsp+80h] [rbp-1h] BYREF
  __int64 v55; // [rsp+88h] [rbp+7h]
  __int64 v56; // [rsp+90h] [rbp+Fh]
  unsigned int v58; // [rsp+E0h] [rbp+5Fh] BYREF
  void *v59; // [rsp+E8h] [rbp+67h]

  v59 = a3;
  Size = 0;
  v53 = 0;
  v7 = 0;
  v50 = 0;
  v8 = 0;
  v58 = 0;
  v49 = 0;
  v52 = 0;
  if ( !a2 || a6 )
  {
    v11 = -1073741811;
    v31 = 881;
    v32 = 3221225485LL;
    goto LABEL_62;
  }
  *a5 = 0;
  v9 = *(_DWORD *)(a1 + 32);
  KeyBitLength = GetKeyBitLength(a2, a4, &v52);
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
    v55 = *(_QWORD *)(v18 + 8 * v19 + 8);
    v51 = *(_DWORD *)(v18 + 8 * v19);
    goto LABEL_15;
  }
  v51 = 0;
  v55 = 0;
LABEL_15:
  v20 = QueryParameterList(a2, 16, 0);
  v21 = (_QWORD *)(a2 + 8);
  if ( v20 < 0 )
  {
    v56 = 10000;
  }
  else
  {
    if ( *(_DWORD *)(*v21 + 16LL * v20) != 8 )
    {
      v12 = 968;
      goto LABEL_9;
    }
    _mm_lfence();
    v56 = **(_QWORD **)(*v21 + 16LL * v20 + 8);
    if ( !v56 )
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
  v23 = 2LL * v22;
  v24 = *(unsigned int *)(*v21 + 16LL * v22);
  if ( (v24 & 1) != 0 || (unsigned int)v24 < 2 )
  {
    v12 = 1015;
    goto LABEL_9;
  }
  v25 = *(_WORD **)(*v21 + 8 * v23 + 8);
  v26 = (unsigned __int64)(unsigned int)v24 >> 1;
  v27 = (unsigned int)v24;
  if ( v25[v26 - 1] )
  {
    v28 = (_WORD *)MSCryptAlloc(v24 + 2);
    v8 = v28;
    if ( !v28 )
    {
      v11 = -1073741801;
      v12 = 1030;
      v13 = 3221225495LL;
      goto LABEL_5;
    }
    memmove(v28, *(const void **)(*v21 + 8 * v23 + 8), v27);
    v25 = v8;
    v8[v26] = 0;
  }
  v29 = MSCryptOpenHashProvider(&Size, v25, (unsigned int)(v9 != 0) + 40);
  v11 = v29;
  if ( !v29 )
  {
    v7 = Size;
    if ( (unsigned int)MSCryptGetHashProperty(Size, L"IsKeyedHash", &v53, 4, &v49, 0) || !v53 )
    {
      v11 = -1073741816;
      v31 = 1071;
      v32 = 3221225480LL;
      goto LABEL_62;
    }
    HashProperty = MSCryptGetHashProperty(v7, L"HashDigestLength", &v58, 4, &v49, 0);
    v11 = HashProperty;
    if ( HashProperty )
    {
      v31 = 1084;
LABEL_35:
      v32 = (unsigned int)HashProperty;
LABEL_62:
      DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v31);
      goto LABEL_63;
    }
    LODWORD(Size) = (unsigned int)(v52 + 7) >> 3;
    v33 = (v58 + (_DWORD)Size - 1) / v58;
    HashProperty = MSCryptGetHashProperty(v7, L"ObjectLength", &v50, 4, &v49, 0);
    v11 = HashProperty;
    if ( HashProperty < 0 )
    {
      v31 = 1103;
      goto LABEL_35;
    }
    v34 = (_BYTE *)MSCryptAlloc(v58);
    v35 = (_BYTE *)MSCryptAlloc(v50);
    v36 = MSCryptAlloc(v58 * v33);
    v37 = (char *)v36;
    if ( v34 && v35 && v36 )
    {
      for ( i = 0; i < v33; i = v49 )
      {
        v49 = i + 1;
        v39 = PBKDF2(
                v7,
                *(_QWORD *)(a1 + 24),
                *(unsigned int *)(a1 + 16),
                v55,
                v51,
                v56,
                i + 1,
                v35,
                v50,
                v34,
                &v37[v58 * i],
                v58);
        v11 = v39;
        if ( v39 )
        {
          DebugTraceError(
            v39,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            1137);
          goto LABEL_48;
        }
      }
      v40 = Size;
      memmove(v59, v37, (unsigned int)Size);
      *((_BYTE *)v59 + (unsigned int)(v40 - 1)) &= -1 << (8 * v40 - v52);
      *a5 = v40;
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
      if ( !v37 )
      {
LABEL_51:
        if ( v35 )
        {
          v44 = v50;
          v45 = v35;
          if ( v50 )
          {
            do
            {
              *v45++ = 0;
              --v44;
            }
            while ( v44 );
          }
          MSCryptFree(v35);
        }
        if ( v34 )
        {
          v46 = v58;
          v47 = v34;
          if ( v58 )
          {
            do
            {
              *v47++ = 0;
              --v46;
            }
            while ( v46 );
          }
          MSCryptFree(v34);
        }
        goto LABEL_63;
      }
    }
LABEL_48:
    v41 = v58 * v33;
    v42 = v37;
    v43 = v41;
    if ( v41 )
    {
      do
      {
        *v42++ = 0;
        --v43;
      }
      while ( v43 );
    }
    MSCryptFree(v37);
    goto LABEL_51;
  }
  DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1055);
  v7 = Size;
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
0x18007d330  mov     rax, rsp
0x18007d333  mov     [rax+20h], rbx
0x18007d337  mov     [rax+18h], r8
0x18007d33b  mov     [rax+8], rcx
0x18007d33f  push    rbp
0x18007d340  push    rsi
0x18007d341  push    rdi
0x18007d342  push    r12
0x18007d344  push    r13
0x18007d346  push    r14
0x18007d348  push    r15
0x18007d34a  lea     rbp, [rax-4Fh]
0x18007d34e  sub     rsp, 90h
0x18007d355  xor     r12d, r12d
0x18007d358  mov     rdi, rdx
0x18007d35b  mov     [rbp+47h+Size], r12
0x18007d35f  mov     rax, rcx
0x18007d362  mov     [rbp+47h+var_50], r12d
0x18007d366  mov     esi, r12d
0x18007d369  mov     [rbp+47h+var_5C], r12d
0x18007d36d  mov     r13d, r12d
0x18007d370  mov     [rbp+47h+arg_8], r12d
0x18007d374  mov     [rbp+47h+var_60], r12d
0x18007d378  mov     [rbp+47h+var_54], r12d
0x18007d37c  test    rdx, rdx
0x18007d37f  jz      loc_18007D7CD
0x18007d385  cmp     [rbp+47h+arg_28], r12d
0x18007d389  jnz     loc_18007D7CD
0x18007d38f  mov     rcx, [rbp+47h+arg_20]
0x18007d393  lea     r8, [rbp+47h+var_54]
0x18007d397  mov     edx, r9d
0x18007d39a  mov     [rcx], r12d
0x18007d39d  mov     rcx, rdi
0x18007d3a0  mov     r15d, [rax+20h]
0x18007d3a4  call    GetKeyBitLength
0x18007d3a9  mov     ebx, eax
0x18007d3ab  test    eax, eax
0x18007d3ad  jns     short loc_18007D3CF
0x18007d3af  mov     r9d, 38Dh
0x18007d3b5  mov     ecx, eax
0x18007d3b7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d3be  lea     rdx, aStatus; "Status"
0x18007d3c5  call    DebugTraceError
0x18007d3ca  jmp     loc_18007D80C
0x18007d3cf  xor     r8d, r8d
0x18007d3d2  mov     rcx, rdi
0x18007d3d5  lea     edx, [r8+11h]
0x18007d3d9  call    QueryParameterList
0x18007d3de  xor     r8d, r8d
0x18007d3e1  movsxd  rbx, eax
0x18007d3e4  lea     edx, [r8+0Fh]
0x18007d3e8  call    QueryParameterList
0x18007d3ed  test    eax, eax
0x18007d3ef  js      short loc_18007D422
0x18007d3f1  test    ebx, ebx
0x18007d3f3  js      short loc_18007D407
0x18007d3f5  mov     r9d, 3AAh
0x18007d3fb  mov     ebx, 0C000000Dh
0x18007d400  mov     ecx, 0C000000Dh
0x18007d405  jmp     short loc_18007D3B7
0x18007d407  movsxd  rcx, eax
0x18007d40a  mov     rax, [rdi+8]
0x18007d40e  add     rcx, rcx
0x18007d411  mov     rsi, [rax+rcx*8+8]
0x18007d416  mov     [rbp+47h+var_40], rsi
0x18007d41a  mov     esi, [rax+rcx*8]
0x18007d41d  mov     [rbp+47h+var_58], esi
0x18007d420  jmp     short loc_18007D433
0x18007d422  test    ebx, ebx
0x18007d424  js      short loc_18007D42B
0x18007d426  mov     rcx, rbx
0x18007d429  jmp     short loc_18007D40A
0x18007d42b  mov     [rbp+47h+var_58], r12d
0x18007d42f  mov     [rbp+47h+var_40], r12
0x18007d433  xor     r8d, r8d
0x18007d436  mov     rcx, rdi
0x18007d439  lea     edx, [r8+10h]
0x18007d43d  call    QueryParameterList
0x18007d442  lea     rbx, [rdi+8]
0x18007d446  test    eax, eax
0x18007d448  js      short loc_18007D483
0x18007d44a  movsxd  rcx, eax
0x18007d44d  mov     rax, [rbx]
0x18007d450  add     rcx, rcx
0x18007d453  cmp     dword ptr [rax+rcx*8], 8
0x18007d457  jz      short loc_18007D461
0x18007d459  mov     r9d, 3C8h
0x18007d45f  jmp     short loc_18007D3FB
0x18007d461  lfence
0x18007d464  mov     rax, [rbx]
0x18007d467  mov     rcx, [rax+rcx*8+8]
0x18007d46c  mov     rsi, [rcx]
0x18007d46f  mov     [rbp+47h+var_38], rsi
0x18007d473  test    rsi, rsi
0x18007d476  jnz     short loc_18007D48B
0x18007d478  mov     r9d, 3D2h
0x18007d47e  jmp     loc_18007D3FB
0x18007d483  mov     [rbp+47h+var_38], 2710h
0x18007d48b  xor     r8d, r8d
0x18007d48e  xor     edx, edx
0x18007d490  mov     rcx, rdi
0x18007d493  call    QueryParameterList
0x18007d498  test    eax, eax
0x18007d49a  jns     short loc_18007D4A7
0x18007d49c  mov     r9d, 3ECh
0x18007d4a2  jmp     loc_18007D3FB
0x18007d4a7  lfence
0x18007d4aa  mov     rdx, [rbx]
0x18007d4ad  movsxd  rdi, eax
0x18007d4b0  add     rdi, rdi
0x18007d4b3  mov     eax, [rdx+rdi*8]
0x18007d4b6  test    al, 1
0x18007d4b8  jnz     loc_18007D7C2
0x18007d4be  cmp     eax, 2
0x18007d4c1  jb      loc_18007D7C2
0x18007d4c7  mov     rdx, [rdx+rdi*8+8]
0x18007d4cc  mov     esi, eax
0x18007d4ce  shr     rsi, 1
0x18007d4d1  mov     r14d, eax
0x18007d4d4  cmp     r12w, [rdx+rsi*2-2]
0x18007d4da  jz      short loc_18007D51E
0x18007d4dc  lea     rcx, [rax+2]
0x18007d4e0  call    MSCryptAlloc
0x18007d4e5  mov     r13, rax
0x18007d4e8  test    rax, rax
0x18007d4eb  jnz     short loc_18007D502
0x18007d4ed  mov     ebx, 0C0000017h
0x18007d4f2  mov     r9d, 406h
0x18007d4f8  mov     ecx, 0C0000017h
0x18007d4fd  jmp     loc_18007D3B7
0x18007d502  mov     rdx, [rbx]
0x18007d505  mov     r8, r14; Size
0x18007d508  mov     rcx, r13; void *
0x18007d50b  mov     rdx, [rdx+rdi*8+8]; Src
0x18007d510  call    memmove
0x18007d515  mov     rdx, r13
0x18007d518  mov     [r13+rsi*2+0], r12w
0x18007d51e  neg     r15d
0x18007d521  lea     rcx, [rbp+47h+Size]
0x18007d525  sbb     r8d, r8d
0x18007d528  neg     r8d
0x18007d52b  add     r8d, 28h ; '('
0x18007d52f  call    MSCryptOpenHashProvider
0x18007d534  mov     ebx, eax
0x18007d536  test    eax, eax
0x18007d538  jz      short loc_18007D55E
0x18007d53a  mov     r9d, 41Fh
0x18007d540  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d547  lea     rdx, aStatus; "Status"
0x18007d54e  mov     ecx, eax
0x18007d550  call    DebugTraceError
0x18007d555  mov     rsi, [rbp+47h+Size]
0x18007d559  jmp     loc_18007D7F0
0x18007d55e  mov     rsi, [rbp+47h+Size]
0x18007d562  lea     rax, [rbp+47h+var_60]
0x18007d566  mov     edi, 4
0x18007d56b  mov     [rsp+0C0h+var_98], r12d
0x18007d570  mov     r9d, edi
0x18007d573  mov     [rsp+0C0h+var_A0], rax
0x18007d578  mov     rcx, rsi
0x18007d57b  lea     r8, [rbp+47h+var_50]
0x18007d57f  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18007d586  call    MSCryptGetHashProperty
0x18007d58b  test    eax, eax
0x18007d58d  jnz     loc_18007D7B0
0x18007d593  cmp     [rbp+47h+var_50], r12d
0x18007d597  jz      loc_18007D7B0
0x18007d59d  lea     rax, [rbp+47h+var_60]
0x18007d5a1  mov     [rsp+0C0h+var_98], r12d
0x18007d5a6  mov     r9d, edi
0x18007d5a9  mov     [rsp+0C0h+var_A0], rax
0x18007d5ae  lea     r8, [rbp+47h+arg_8]
0x18007d5b2  mov     rcx, rsi
0x18007d5b5  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007d5bc  call    MSCryptGetHashProperty
0x18007d5c1  mov     ebx, eax
0x18007d5c3  test    eax, eax
0x18007d5c5  jz      short loc_18007D5D4
0x18007d5c7  mov     r9d, 43Ch
0x18007d5cd  mov     ecx, eax
0x18007d5cf  jmp     loc_18007D7DD
0x18007d5d4  mov     eax, [rbp+47h+var_54]
0x18007d5d7  lea     r8, [rbp+47h+var_5C]
0x18007d5db  add     eax, 7
0x18007d5de  mov     [rsp+0C0h+var_98], r12d
0x18007d5e3  shr     eax, 3
0x18007d5e6  xor     edx, edx
0x18007d5e8  mov     dword ptr [rbp+47h+Size], eax
0x18007d5eb  mov     r9d, edi
0x18007d5ee  dec     eax
0x18007d5f0  mov     rcx, rsi
0x18007d5f3  add     eax, [rbp+47h+arg_8]
0x18007d5f6  div     [rbp+47h+arg_8]
0x18007d5f9  lea     rdx, aObjectlength; "ObjectLength"
0x18007d600  mov     r15d, eax
0x18007d603  lea     rax, [rbp+47h+var_60]
0x18007d607  mov     [rsp+0C0h+var_A0], rax
0x18007d60c  call    MSCryptGetHashProperty
0x18007d611  mov     ebx, eax
0x18007d613  test    eax, eax
0x18007d615  jns     short loc_18007D61F
0x18007d617  mov     r9d, 44Fh
0x18007d61d  jmp     short loc_18007D5CD
0x18007d61f  mov     ecx, [rbp+47h+arg_8]
0x18007d622  call    MSCryptAlloc
0x18007d627  mov     ecx, [rbp+47h+var_5C]
0x18007d62a  mov     r12, rax
0x18007d62d  call    MSCryptAlloc
0x18007d632  mov     ecx, r15d
0x18007d635  mov     r14, rax
0x18007d638  imul    ecx, [rbp+47h+arg_8]
0x18007d63c  call    MSCryptAlloc
0x18007d641  mov     rdi, rax
0x18007d644  test    r12, r12
0x18007d647  jz      loc_18007D71A
0x18007d64d  test    r14, r14
0x18007d650  jz      loc_18007D71A
0x18007d656  test    rax, rax
0x18007d659  jz      loc_18007D71A
0x18007d65f  xor     eax, eax
0x18007d661  cmp     eax, r15d
0x18007d664  jnb     short loc_18007D6E3
0x18007d666  mov     ecx, [rbp+47h+arg_8]
0x18007d669  lea     edx, [rax+1]
0x18007d66c  mov     r9, [rbp+47h+var_40]
0x18007d670  mov     [rsp+58h], ecx
0x18007d674  imul    eax, ecx
0x18007d677  mov     rcx, rsi
0x18007d67a  mov     [rbp+47h+var_60], edx
0x18007d67d  add     rax, rdi
0x18007d680  mov     qword ptr [rsp+0C0h+var_70], rax
0x18007d685  mov     eax, [rbp+47h+var_5C]
0x18007d688  mov     [rsp+0C0h+var_78], r12
0x18007d68d  mov     dword ptr [rsp+0C0h+var_80], eax
0x18007d691  mov     rax, [rbp+47h+var_38]
0x18007d695  mov     qword ptr [rsp+0C0h+var_88], r14
0x18007d69a  mov     dword ptr [rsp+0C0h+var_90], edx
0x18007d69e  mov     qword ptr [rsp+0C0h+var_98], rax
0x18007d6a3  mov     eax, [rbp+47h+var_58]
0x18007d6a6  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18007d6aa  mov     rax, [rbp+47h+arg_0]
0x18007d6ae  mov     r8d, [rax+10h]
0x18007d6b2  mov     rdx, [rax+18h]
0x18007d6b6  call    _PBKDF2
0x18007d6bb  mov     ebx, eax
0x18007d6bd  test    eax, eax
0x18007d6bf  jnz     short loc_18007D6C6
0x18007d6c1  mov     eax, [rbp+47h+var_60]
0x18007d6c4  jmp     short loc_18007D661
0x18007d6c6  mov     r9d, 471h
0x18007d6cc  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d6d3  lea     rdx, aStatus; "Status"
0x18007d6da  mov     ecx, eax
0x18007d6dc  call    DebugTraceError
0x18007d6e1  jmp     short loc_18007D742
0x18007d6e3  mov     ebx, dword ptr [rbp+47h+Size]
0x18007d6e6  mov     rdx, rdi; Src
0x18007d6e9  mov     rcx, [rbp+47h+arg_10]; void *
0x18007d6ed  mov     r8d, ebx; Size
0x18007d6f0  call    memmove
0x18007d6f5  lea     ecx, ds:0[rbx*8]
0x18007d6fc  mov     eax, 0FFh
0x18007d701  sub     ecx, [rbp+47h+var_54]
0x18007d704  lea     edx, [rbx-1]
0x18007d707  shl     al, cl
0x18007d709  mov     rcx, [rbp+47h+arg_10]
0x18007d70d  and     [rdx+rcx], al
0x18007d710  mov     rax, [rbp+47h+arg_20]
0x18007d714  mov     [rax], ebx
0x18007d716  xor     ebx, ebx
0x18007d718  jmp     short loc_18007D742
0x18007d71a  mov     r9d, 45Ch
0x18007d720  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007d727  lea     rdx, aStatus; "Status"
0x18007d72e  mov     ecx, 0C0000017h
0x18007d733  call    DebugTraceError
0x18007d738  mov     ebx, 0C0000017h
0x18007d73d  test    rdi, rdi
0x18007d740  jz      short loc_18007D766
0x18007d742  imul    r15d, [rbp+47h+arg_8]
0x18007d747  mov     rax, rdi
0x18007d74a  mov     ecx, r15d
0x18007d74d  test    r15d, r15d
0x18007d750  jz      short loc_18007D75E
0x18007d752  mov     byte ptr [rax], 0
0x18007d755  inc     rax
0x18007d758  sub     rcx, 1
0x18007d75c  jnz     short loc_18007D752
0x18007d75e  mov     rcx, rdi; P
0x18007d761  call    MSCryptFree
0x18007d766  test    r14, r14
0x18007d769  jz      short loc_18007D78A
0x18007d76b  mov     eax, [rbp+47h+var_5C]
0x18007d76e  mov     rcx, r14
0x18007d771  test    rax, rax
0x18007d774  jz      short loc_18007D782
0x18007d776  mov     byte ptr [rcx], 0
0x18007d779  inc     rcx
0x18007d77c  sub     rax, 1
0x18007d780  jnz     short loc_18007D776
  ... truncated ...
```
