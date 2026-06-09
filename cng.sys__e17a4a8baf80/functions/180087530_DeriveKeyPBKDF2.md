# DeriveKeyPBKDF2

- ea: `0x180087530`
- end: `0x180087a2a`
- name: `DeriveKeyPBKDF2`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043e70`

## callees

- `0x18000c650`
- `0x18000e090`
- `0x18000e440`
- `0x18000f2f4`
- `0x18000f6b0`
- `0x180010590`
- `0x18001155c`
- `0x18004a2c8`
- `0x180087530`
- `0x180087e94`
- `0x1800a45c0`

## string_xrefs

- `0x1800875b7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180087740`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800878cc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180087920`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800879e4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

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
  __int64 v34; // rdx
  _BYTE *v35; // r12
  __int64 v36; // rdx
  _BYTE *v37; // r14
  __int64 v38; // rdx
  __int64 v39; // rax
  char *v40; // rdi
  unsigned int i; // eax
  unsigned int v42; // eax
  int v43; // ebx
  unsigned int v44; // r15d
  _BYTE *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  _BYTE *v48; // rcx
  __int64 v49; // rax
  _BYTE *v50; // rcx
  unsigned int v52; // [rsp+68h] [rbp-19h] BYREF
  __int64 v53; // [rsp+6Ch] [rbp-15h] BYREF
  int v54; // [rsp+74h] [rbp-Dh] BYREF
  __int64 v55; // [rsp+78h] [rbp-9h] BYREF
  size_t Size; // [rsp+80h] [rbp-1h] BYREF
  __int64 v57; // [rsp+88h] [rbp+7h]
  __int64 v58; // [rsp+90h] [rbp+Fh]
  __int64 v60; // [rsp+E0h] [rbp+5Fh] BYREF
  void *v61; // [rsp+E8h] [rbp+67h]

  v61 = a3;
  Size = 0;
  LODWORD(v55) = 0;
  v7 = 0;
  LODWORD(v53) = 0;
  v8 = 0;
  LODWORD(v60) = 0;
  v52 = 0;
  v54 = 0;
  if ( !a2 || a6 )
  {
    v11 = -1073741811;
    v31 = 881;
    v32 = 3221225485LL;
    goto LABEL_62;
  }
  *a5 = 0;
  v9 = *(_DWORD *)(a1 + 32);
  KeyBitLength = GetKeyBitLength(a2, a4, &v54);
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
    v57 = *(_QWORD *)(v18 + 8 * v19 + 8);
    HIDWORD(v53) = *(_DWORD *)(v18 + 8 * v19);
    goto LABEL_15;
  }
  HIDWORD(v53) = 0;
  v57 = 0;
LABEL_15:
  v20 = QueryParameterList(a2, 16, 0);
  v21 = (_QWORD *)(a2 + 8);
  if ( v20 < 0 )
  {
    v58 = 10000;
  }
  else
  {
    if ( *(_DWORD *)(*v21 + 16LL * v20) != 8 )
    {
      v12 = 968;
      goto LABEL_9;
    }
    _mm_lfence();
    v58 = **(_QWORD **)(*v21 + 16LL * v20 + 8);
    if ( !v58 )
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
    v28 = (_WORD *)MSCryptAlloc(v24 + 2, v25);
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
    v7 = (_DWORD *)Size;
    if ( (unsigned int)MSCryptGetHashProperty((_DWORD *)Size, L"IsKeyedHash", &v55, 4u, &v52, 0) || !(_DWORD)v55 )
    {
      v11 = -1073741816;
      v31 = 1071;
      v32 = 3221225480LL;
      goto LABEL_62;
    }
    HashProperty = MSCryptGetHashProperty(v7, L"HashDigestLength", &v60, 4u, &v52, 0);
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
    LODWORD(Size) = (unsigned int)(v54 + 7) >> 3;
    v33 = ((int)v60 + (int)Size - 1) / (unsigned int)v60;
    HashProperty = MSCryptGetHashProperty(v7, L"ObjectLength", &v53, 4u, &v52, 0);
    v11 = HashProperty;
    if ( HashProperty < 0 )
    {
      v31 = 1103;
      goto LABEL_35;
    }
    v35 = (_BYTE *)MSCryptAlloc((unsigned int)v60, v34);
    v37 = (_BYTE *)MSCryptAlloc((unsigned int)v53, v36);
    v39 = MSCryptAlloc((unsigned int)v60 * v33, v38);
    v40 = (char *)v39;
    if ( v35 && v37 && v39 )
    {
      for ( i = 0; i < v33; i = v52 )
      {
        v52 = i + 1;
        v42 = PBKDF2(
                v7,
                *(_QWORD *)(a1 + 24),
                *(unsigned int *)(a1 + 16),
                v57,
                HIDWORD(v53),
                v58,
                i + 1,
                v37,
                v53,
                v35,
                &v40[(unsigned int)v60 * i],
                v60);
        v11 = v42;
        if ( v42 )
        {
          DebugTraceError(
            v42,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            1137);
          goto LABEL_48;
        }
      }
      v43 = Size;
      memmove(v61, v40, (unsigned int)Size);
      *((_BYTE *)v61 + (unsigned int)(v43 - 1)) &= -1 << (8 * v43 - v54);
      *a5 = v43;
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
      if ( !v40 )
      {
LABEL_51:
        if ( v37 )
        {
          v47 = (unsigned int)v53;
          v48 = v37;
          if ( (_DWORD)v53 )
          {
            do
            {
              *v48++ = 0;
              --v47;
            }
            while ( v47 );
          }
          MSCryptFree(v37);
        }
        if ( v35 )
        {
          v49 = (unsigned int)v60;
          v50 = v35;
          if ( (_DWORD)v60 )
          {
            do
            {
              *v50++ = 0;
              --v49;
            }
            while ( v49 );
          }
          MSCryptFree(v35);
        }
        goto LABEL_63;
      }
    }
LABEL_48:
    v44 = v60 * v33;
    v45 = v40;
    v46 = v44;
    if ( v44 )
    {
      do
      {
        *v45++ = 0;
        --v46;
      }
      while ( v46 );
    }
    MSCryptFree(v40);
    goto LABEL_51;
  }
  DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1055);
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
0x180087530  mov     rax, rsp
0x180087533  mov     [rax+20h], rbx
0x180087537  mov     [rax+18h], r8
0x18008753b  mov     [rax+8], rcx
0x18008753f  push    rbp
0x180087540  push    rsi
0x180087541  push    rdi
0x180087542  push    r12
0x180087544  push    r13
0x180087546  push    r14
0x180087548  push    r15
0x18008754a  lea     rbp, [rax-4Fh]
0x18008754e  sub     rsp, 90h
0x180087555  xor     r12d, r12d
0x180087558  mov     rdi, rdx
0x18008755b  mov     [rbp+47h+Size], r12
0x18008755f  mov     rax, rcx
0x180087562  mov     dword ptr [rbp+47h+var_50], r12d
0x180087566  mov     esi, r12d
0x180087569  mov     [rbp+47h+var_5C], r12d
0x18008756d  mov     r13d, r12d
0x180087570  mov     dword ptr [rbp+47h+arg_8], r12d
0x180087574  mov     [rbp+47h+var_60], r12d
0x180087578  mov     [rbp+47h+var_54], r12d
0x18008757c  test    rdx, rdx
0x18008757f  jz      loc_1800879CD
0x180087585  cmp     [rbp+47h+arg_28], r12d
0x180087589  jnz     loc_1800879CD
0x18008758f  mov     rcx, [rbp+47h+arg_20]
0x180087593  lea     r8, [rbp+47h+var_54]
0x180087597  mov     edx, r9d
0x18008759a  mov     [rcx], r12d
0x18008759d  mov     rcx, rdi
0x1800875a0  mov     r15d, [rax+20h]
0x1800875a4  call    GetKeyBitLength
0x1800875a9  mov     ebx, eax
0x1800875ab  test    eax, eax
0x1800875ad  jns     short loc_1800875CF
0x1800875af  mov     r9d, 38Dh
0x1800875b5  mov     ecx, eax
0x1800875b7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800875be  lea     rdx, aStatus; "Status"
0x1800875c5  call    DebugTraceError
0x1800875ca  jmp     loc_180087A0C
0x1800875cf  xor     r8d, r8d
0x1800875d2  mov     rcx, rdi
0x1800875d5  lea     edx, [r8+11h]
0x1800875d9  call    QueryParameterList
0x1800875de  xor     r8d, r8d
0x1800875e1  movsxd  rbx, eax
0x1800875e4  lea     edx, [r8+0Fh]
0x1800875e8  call    QueryParameterList
0x1800875ed  test    eax, eax
0x1800875ef  js      short loc_180087622
0x1800875f1  test    ebx, ebx
0x1800875f3  js      short loc_180087607
0x1800875f5  mov     r9d, 3AAh
0x1800875fb  mov     ebx, 0C000000Dh
0x180087600  mov     ecx, 0C000000Dh
0x180087605  jmp     short loc_1800875B7
0x180087607  movsxd  rcx, eax
0x18008760a  mov     rax, [rdi+8]
0x18008760e  add     rcx, rcx
0x180087611  mov     rsi, [rax+rcx*8+8]
0x180087616  mov     [rbp+47h+var_40], rsi
0x18008761a  mov     esi, [rax+rcx*8]
0x18008761d  mov     [rbp+47h+var_58], esi
0x180087620  jmp     short loc_180087633
0x180087622  test    ebx, ebx
0x180087624  js      short loc_18008762B
0x180087626  mov     rcx, rbx
0x180087629  jmp     short loc_18008760A
0x18008762b  mov     [rbp+47h+var_58], r12d
0x18008762f  mov     [rbp+47h+var_40], r12
0x180087633  xor     r8d, r8d
0x180087636  mov     rcx, rdi
0x180087639  lea     edx, [r8+10h]
0x18008763d  call    QueryParameterList
0x180087642  lea     rbx, [rdi+8]
0x180087646  test    eax, eax
0x180087648  js      short loc_180087683
0x18008764a  movsxd  rcx, eax
0x18008764d  mov     rax, [rbx]
0x180087650  add     rcx, rcx
0x180087653  cmp     dword ptr [rax+rcx*8], 8
0x180087657  jz      short loc_180087661
0x180087659  mov     r9d, 3C8h
0x18008765f  jmp     short loc_1800875FB
0x180087661  lfence
0x180087664  mov     rax, [rbx]
0x180087667  mov     rcx, [rax+rcx*8+8]
0x18008766c  mov     rsi, [rcx]
0x18008766f  mov     [rbp+47h+var_38], rsi
0x180087673  test    rsi, rsi
0x180087676  jnz     short loc_18008768B
0x180087678  mov     r9d, 3D2h
0x18008767e  jmp     loc_1800875FB
0x180087683  mov     [rbp+47h+var_38], 2710h
0x18008768b  xor     r8d, r8d
0x18008768e  xor     edx, edx
0x180087690  mov     rcx, rdi
0x180087693  call    QueryParameterList
0x180087698  test    eax, eax
0x18008769a  jns     short loc_1800876A7
0x18008769c  mov     r9d, 3ECh
0x1800876a2  jmp     loc_1800875FB
0x1800876a7  lfence
0x1800876aa  mov     rdx, [rbx]
0x1800876ad  movsxd  rdi, eax
0x1800876b0  add     rdi, rdi
0x1800876b3  mov     eax, [rdx+rdi*8]
0x1800876b6  test    al, 1
0x1800876b8  jnz     loc_1800879C2
0x1800876be  cmp     eax, 2
0x1800876c1  jb      loc_1800879C2
0x1800876c7  mov     rdx, [rdx+rdi*8+8]
0x1800876cc  mov     esi, eax
0x1800876ce  shr     rsi, 1
0x1800876d1  mov     r14d, eax
0x1800876d4  cmp     r12w, [rdx+rsi*2-2]
0x1800876da  jz      short loc_18008771E
0x1800876dc  lea     rcx, [rax+2]
0x1800876e0  call    MSCryptAlloc
0x1800876e5  mov     r13, rax
0x1800876e8  test    rax, rax
0x1800876eb  jnz     short loc_180087702
0x1800876ed  mov     ebx, 0C0000017h
0x1800876f2  mov     r9d, 406h
0x1800876f8  mov     ecx, 0C0000017h
0x1800876fd  jmp     loc_1800875B7
0x180087702  mov     rdx, [rbx]
0x180087705  mov     r8, r14; Size
0x180087708  mov     rcx, r13; void *
0x18008770b  mov     rdx, [rdx+rdi*8+8]; Src
0x180087710  call    memmove
0x180087715  mov     rdx, r13
0x180087718  mov     [r13+rsi*2+0], r12w
0x18008771e  neg     r15d
0x180087721  lea     rcx, [rbp+47h+Size]
0x180087725  sbb     r8d, r8d
0x180087728  neg     r8d
0x18008772b  add     r8d, 28h ; '('
0x18008772f  call    MSCryptOpenHashProvider
0x180087734  mov     ebx, eax
0x180087736  test    eax, eax
0x180087738  jz      short loc_18008775E
0x18008773a  mov     r9d, 41Fh
0x180087740  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180087747  lea     rdx, aStatus; "Status"
0x18008774e  mov     ecx, eax
0x180087750  call    DebugTraceError
0x180087755  mov     rsi, [rbp+47h+Size]
0x180087759  jmp     loc_1800879F0
0x18008775e  mov     rsi, [rbp+47h+Size]
0x180087762  lea     rax, [rbp+47h+var_60]
0x180087766  mov     edi, 4
0x18008776b  mov     [rsp+0C0h+var_98], r12d
0x180087770  mov     r9d, edi
0x180087773  mov     [rsp+0C0h+var_A0], rax
0x180087778  mov     rcx, rsi
0x18008777b  lea     r8, [rbp+47h+var_50]
0x18008777f  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x180087786  call    MSCryptGetHashProperty
0x18008778b  test    eax, eax
0x18008778d  jnz     loc_1800879B0
0x180087793  cmp     dword ptr [rbp+47h+var_50], r12d
0x180087797  jz      loc_1800879B0
0x18008779d  lea     rax, [rbp+47h+var_60]
0x1800877a1  mov     [rsp+0C0h+var_98], r12d
0x1800877a6  mov     r9d, edi
0x1800877a9  mov     [rsp+0C0h+var_A0], rax
0x1800877ae  lea     r8, [rbp+47h+arg_8]
0x1800877b2  mov     rcx, rsi
0x1800877b5  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800877bc  call    MSCryptGetHashProperty
0x1800877c1  mov     ebx, eax
0x1800877c3  test    eax, eax
0x1800877c5  jz      short loc_1800877D4
0x1800877c7  mov     r9d, 43Ch
0x1800877cd  mov     ecx, eax
0x1800877cf  jmp     loc_1800879DD
0x1800877d4  mov     eax, [rbp+47h+var_54]
0x1800877d7  lea     r8, [rbp+47h+var_5C]
0x1800877db  add     eax, 7
0x1800877de  mov     [rsp+0C0h+var_98], r12d
0x1800877e3  shr     eax, 3
0x1800877e6  xor     edx, edx
0x1800877e8  mov     dword ptr [rbp+47h+Size], eax
0x1800877eb  mov     r9d, edi
0x1800877ee  dec     eax
0x1800877f0  mov     rcx, rsi
0x1800877f3  add     eax, dword ptr [rbp+47h+arg_8]
0x1800877f6  div     dword ptr [rbp+47h+arg_8]
0x1800877f9  lea     rdx, aObjectlength; "ObjectLength"
0x180087800  mov     r15d, eax
0x180087803  lea     rax, [rbp+47h+var_60]
0x180087807  mov     [rsp+0C0h+var_A0], rax
0x18008780c  call    MSCryptGetHashProperty
0x180087811  mov     ebx, eax
0x180087813  test    eax, eax
0x180087815  jns     short loc_18008781F
0x180087817  mov     r9d, 44Fh
0x18008781d  jmp     short loc_1800877CD
0x18008781f  mov     ecx, dword ptr [rbp+47h+arg_8]
0x180087822  call    MSCryptAlloc
0x180087827  mov     ecx, [rbp+47h+var_5C]
0x18008782a  mov     r12, rax
0x18008782d  call    MSCryptAlloc
0x180087832  mov     ecx, r15d
0x180087835  mov     r14, rax
0x180087838  imul    ecx, dword ptr [rbp+47h+arg_8]
0x18008783c  call    MSCryptAlloc
0x180087841  mov     rdi, rax
0x180087844  test    r12, r12
0x180087847  jz      loc_18008791A
0x18008784d  test    r14, r14
0x180087850  jz      loc_18008791A
0x180087856  test    rax, rax
0x180087859  jz      loc_18008791A
0x18008785f  xor     eax, eax
0x180087861  cmp     eax, r15d
0x180087864  jnb     short loc_1800878E3
0x180087866  mov     ecx, dword ptr [rbp+47h+arg_8]
0x180087869  lea     edx, [rax+1]
0x18008786c  mov     r9, [rbp+47h+var_40]
0x180087870  mov     [rsp+58h], ecx
0x180087874  imul    eax, ecx
0x180087877  mov     rcx, rsi
0x18008787a  mov     [rbp+47h+var_60], edx
0x18008787d  add     rax, rdi
0x180087880  mov     qword ptr [rsp+0C0h+var_70], rax
0x180087885  mov     eax, [rbp+47h+var_5C]
0x180087888  mov     [rsp+0C0h+var_78], r12
0x18008788d  mov     dword ptr [rsp+0C0h+var_80], eax
0x180087891  mov     rax, [rbp+47h+var_38]
0x180087895  mov     qword ptr [rsp+0C0h+var_88], r14
0x18008789a  mov     dword ptr [rsp+0C0h+var_90], edx
0x18008789e  mov     qword ptr [rsp+0C0h+var_98], rax
0x1800878a3  mov     eax, [rbp+47h+var_58]
0x1800878a6  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800878aa  mov     rax, [rbp+47h+arg_0]
0x1800878ae  mov     r8d, [rax+10h]
0x1800878b2  mov     rdx, [rax+18h]
0x1800878b6  call    _PBKDF2
0x1800878bb  mov     ebx, eax
0x1800878bd  test    eax, eax
0x1800878bf  jnz     short loc_1800878C6
0x1800878c1  mov     eax, [rbp+47h+var_60]
0x1800878c4  jmp     short loc_180087861
0x1800878c6  mov     r9d, 471h
0x1800878cc  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800878d3  lea     rdx, aStatus; "Status"
0x1800878da  mov     ecx, eax
0x1800878dc  call    DebugTraceError
0x1800878e1  jmp     short loc_180087942
0x1800878e3  mov     ebx, dword ptr [rbp+47h+Size]
0x1800878e6  mov     rdx, rdi; Src
0x1800878e9  mov     rcx, [rbp+47h+arg_10]; void *
0x1800878ed  mov     r8d, ebx; Size
0x1800878f0  call    memmove
0x1800878f5  lea     ecx, ds:0[rbx*8]
0x1800878fc  mov     eax, 0FFh
0x180087901  sub     ecx, [rbp+47h+var_54]
0x180087904  lea     edx, [rbx-1]
0x180087907  shl     al, cl
0x180087909  mov     rcx, [rbp+47h+arg_10]
0x18008790d  and     [rdx+rcx], al
0x180087910  mov     rax, [rbp+47h+arg_20]
0x180087914  mov     [rax], ebx
0x180087916  xor     ebx, ebx
0x180087918  jmp     short loc_180087942
0x18008791a  mov     r9d, 45Ch
0x180087920  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180087927  lea     rdx, aStatus; "Status"
0x18008792e  mov     ecx, 0C0000017h
0x180087933  call    DebugTraceError
0x180087938  mov     ebx, 0C0000017h
0x18008793d  test    rdi, rdi
0x180087940  jz      short loc_180087966
0x180087942  imul    r15d, dword ptr [rbp+47h+arg_8]
0x180087947  mov     rax, rdi
0x18008794a  mov     ecx, r15d
0x18008794d  test    r15d, r15d
0x180087950  jz      short loc_18008795E
0x180087952  mov     byte ptr [rax], 0
0x180087955  inc     rax
0x180087958  sub     rcx, 1
0x18008795c  jnz     short loc_180087952
0x18008795e  mov     rcx, rdi; P
0x180087961  call    MSCryptFree
0x180087966  test    r14, r14
0x180087969  jz      short loc_18008798A
0x18008796b  mov     eax, [rbp+47h+var_5C]
0x18008796e  mov     rcx, r14
0x180087971  test    rax, rax
0x180087974  jz      short loc_180087982
0x180087976  mov     byte ptr [rcx], 0
0x180087979  inc     rcx
0x18008797c  sub     rax, 1
0x180087980  jnz     short loc_180087976
  ... truncated ...
```
