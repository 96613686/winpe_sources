# DeriveKeySP800108_CTR_HMAC

- ea: `0x18000e940`
- end: `0x18000f2ed`
- name: `DeriveKeySP800108_CTR_HMAC`
- size: `2477`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180043e70`

## callees

- `0x18000c650`
- `0x18000e090`
- `0x18000e440`
- `0x18000e940`
- `0x18000f2f4`
- `0x18000f6b0`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x18001bba0`
- `0x18003b290`
- `0x1800441e0`
- `0x180045a00`
- `0x18004a2c8`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x18000ec9b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000ee3a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000eef1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000ef39`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000ef9b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000eff0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f04a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f0a7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f0de`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f1d9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f22b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f24e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f29e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000f2c6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeySP800108_CTR_HMAC(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  __int64 v7; // r14
  void *v8; // r12
  _BYTE *v9; // r13
  unsigned int v10; // esi
  _BYTE *v11; // r15
  int KeyBitLength; // eax
  unsigned int HashProperty; // ebx
  int ParameterList; // eax
  __int64 v15; // r15
  int v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  int v20; // eax
  const wchar_t *v21; // rdx
  bool v22; // cf
  int v23; // edx
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // ecx
  char *v30; // rax
  char *v31; // rdi
  unsigned int v32; // r14d
  char *v33; // rdi
  void *v34; // rcx
  unsigned int v35; // ebx
  void *v36; // rdx
  __int64 v37; // rcx
  size_t v38; // rbx
  char *v39; // rcx
  char *v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  void *v46; // rdx
  unsigned int v47; // r13d
  int v48; // edx
  unsigned int v49; // r12d
  unsigned int i; // r15d
  __int64 v51; // r9
  __int64 v52; // rax
  _BYTE *v53; // rcx
  __int64 v54; // rax
  _BYTE *v55; // rcx
  __int64 v56; // rcx
  _BYTE *v57; // rax
  unsigned int *v59; // rdx
  char *j; // rcx
  int v61; // edx
  int v62; // edx
  unsigned int v63; // ebx
  unsigned int v64; // edi
  size_t v65; // r8
  __int64 v66; // rdx
  __int64 v67; // rbx
  unsigned int v68; // eax
  unsigned __int64 v69; // r15
  size_t v70; // r14
  int v71; // edx
  int v72; // edx
  int v73; // edx
  __int64 v74; // rax
  void *v75; // rax
  size_t v76; // [rsp+38h] [rbp-59h]
  PVOID v77; // [rsp+48h] [rbp-49h]
  PVOID P; // [rsp+50h] [rbp-41h]
  PVOID v79; // [rsp+58h] [rbp-39h] BYREF
  int v80[2]; // [rsp+60h] [rbp-31h] BYREF
  size_t v81; // [rsp+68h] [rbp-29h] BYREF
  int v82; // [rsp+70h] [rbp-21h] BYREF
  unsigned int Size; // [rsp+74h] [rbp-1Dh]
  unsigned int Size_4; // [rsp+78h] [rbp-19h]
  int v85; // [rsp+7Ch] [rbp-15h]
  int v86; // [rsp+80h] [rbp-11h]
  int v87[2]; // [rsp+88h] [rbp-9h] BYREF
  PVOID v88; // [rsp+90h] [rbp-1h]
  void *Src; // [rsp+98h] [rbp+7h]
  void *v90; // [rsp+A0h] [rbp+Fh]

  v7 = 0;
  v8 = 0;
  *(_QWORD *)v80 = 0;
  v9 = 0;
  *(_QWORD *)v87 = 0;
  v10 = 0;
  v82 = 0;
  v11 = 0;
  P = 0;
  v81 = 0;
  LODWORD(v79) = 0;
  v88 = 0;
  if ( !a6 )
  {
    *a5 = 0;
    v86 = *(_DWORD *)(a1 + 32);
    KeyBitLength = GetKeyBitLength(a2, a4, (char *)&v81 + 4);
    HashProperty = KeyBitLength;
    if ( KeyBitLength < 0 )
    {
      DebugTraceError(
        (unsigned int)KeyBitLength,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        176);
      goto LABEL_37;
    }
    Src = 0;
    Size = 0;
    a6 = 0;
    ParameterList = QueryParameterList(a2, 17, 0);
    v15 = ParameterList;
    v85 = ParameterList;
    if ( ParameterList >= 0 )
    {
      v74 = *(_QWORD *)(a2 + 8);
      v8 = *(void **)(v74 + 16 * v15 + 8);
      a6 = *(_DWORD *)(v74 + 16 * v15);
    }
    v16 = QueryParameterList(a2, 13, 0);
    if ( v16 >= 0 )
    {
      if ( v8 )
      {
        HashProperty = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v17,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            212);
        goto LABEL_94;
      }
      v41 = v16;
      v42 = *(_QWORD *)(a2 + 8);
      v41 *= 2;
      v43 = *(void **)(v42 + 8 * v41 + 8);
      LODWORD(v42) = *(_DWORD *)(v42 + 8 * v41);
      Src = v43;
      Size = v42;
    }
    v90 = 0;
    Size_4 = 0;
    v18 = QueryParameterList(a2, 14, 0);
    if ( v18 >= 0 )
    {
      if ( v8 )
      {
        HashProperty = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v19,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            236);
        goto LABEL_94;
      }
      v44 = v18;
      v45 = *(_QWORD *)(a2 + 8);
      v44 *= 2;
      v46 = *(void **)(v45 + 8 * v44 + 8);
      LODWORD(v45) = *(_DWORD *)(v45 + 8 * v44);
      v90 = v46;
      Size_4 = v45;
    }
    v20 = QueryParameterList(a2, 0, 0);
    if ( v20 >= 0 )
    {
      _mm_lfence();
      v66 = *(_QWORD *)(a2 + 8);
      v67 = 2LL * v20;
      v68 = *(_DWORD *)(v66 + 16LL * v20);
      if ( (v68 & 1) != 0 || v68 < 2 )
      {
        HashProperty = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v66,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            12);
        goto LABEL_94;
      }
      v21 = *(const wchar_t **)(v66 + 8 * v67 + 8);
      v69 = (unsigned __int64)v68 >> 1;
      v70 = v68;
      if ( v21[v69 - 1] )
      {
        v75 = (void *)MSCryptAlloc(v68 + 2LL, v21);
        v88 = v75;
        if ( !v75 )
        {
          HashProperty = -1073741801;
          DebugTraceError(
            3221225495LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            283);
          goto LABEL_104;
        }
        memmove(v75, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v67 + 8), v70);
        v21 = (const wchar_t *)v88;
        *((_WORD *)v88 + v69) = 0;
      }
      LODWORD(v15) = v85;
    }
    else
    {
      v21 = L"SHA256";
    }
    v22 = v86 != 0;
    v86 = -v86;
    HashProperty = MSCryptOpenHashProvider(v80, v21, (unsigned int)v22 + 40);
    if ( !HashProperty )
    {
      v7 = *(_QWORD *)v80;
      HashProperty = MSCryptGetHashProperty(*(_QWORD *)v80, L"ObjectLength", &v82, 4, &v79, 0);
      if ( !HashProperty )
      {
        v77 = (PVOID)MSCryptAlloc((unsigned int)v82, v24);
        if ( v77 )
        {
          v25 = MSCryptGetHashProperty(v7, L"HashDigestLength", &v81, 4, &v79, 0);
          HashProperty = v25;
          if ( !v25 )
          {
            P = (PVOID)MSCryptAlloc((unsigned int)v81, v26);
            if ( !P )
            {
              HashProperty = -1073741801;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_85;
              v72 = *((_DWORD *)WPP_GLOBAL_Control + 11);
              if ( (v72 & 1) == 0 )
                goto LABEL_85;
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v72,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                107);
              goto LABEL_35;
            }
            if ( (int)v15 >= 0 )
            {
              v10 = a6 + 8;
              if ( a6 < 0xFFFFFFF8 )
                goto LABEL_18;
              v51 = 381;
            }
            else
            {
              v28 = Size + 8;
              if ( Size >= 0xFFFFFFF8 )
              {
                v51 = 393;
              }
              else
              {
                v29 = v28 + Size_4;
                if ( v28 + Size_4 >= v28 )
                {
                  v10 = v29 + 1;
                  if ( v29 + 1 >= v29 )
                  {
LABEL_18:
                    v30 = (char *)MSCryptAlloc(v10, v27);
                    v79 = v30;
                    v31 = v30;
                    if ( v30 )
                    {
                      v32 = (unsigned int)(HIDWORD(v81) + 7) >> 3;
                      memset(v30, 0, v10);
                      v33 = v31 + 4;
                      v34 = v33;
                      if ( (int)v15 >= 0 )
                      {
                        v38 = a6;
                        v36 = v8;
                      }
                      else
                      {
                        v35 = Size;
                        memmove(v33, Src, Size);
                        v36 = v90;
                        v37 = v35 + 1;
                        v38 = Size_4;
                        v33 += v37;
                        v34 = v33;
                      }
                      memmove(v34, v36, v38);
                      v39 = &v33[v38 + 3];
                      v40 = (char *)&v81 + 4;
                      while ( v39 >= &v33[v38] )
                        *v39-- = *v40++;
                      v8 = v77;
                      v47 = (v32 + (_DWORD)v81 - 1) / (unsigned int)v81;
                      LODWORD(v76) = *(_DWORD *)(a1 + 16);
                      HashProperty = MSCryptCreateMultiHash(
                                       v80[0],
                                       (int)v87,
                                       0,
                                       (int)v77,
                                       v82,
                                       *(void **)(a1 + 24),
                                       v76,
                                       0);
                      if ( HashProperty )
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            v48,
                            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                            (unsigned int)"Status",
                            HashProperty,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                            237);
                        }
                        v7 = *(_QWORD *)v80;
                        v9 = v79;
                        goto LABEL_86;
                      }
                      v49 = 0;
                      for ( i = 1; ; ++i )
                      {
                        a6 = i;
                        if ( i > v47 )
                        {
                          v9 = v79;
                          *(_BYTE *)(v32 - 1 + a3) &= -1 << (8 * v32 - BYTE4(v81));
                          HashProperty = 0;
                          *a5 = v32;
                          goto LABEL_32;
                        }
                        v31 = (char *)v79;
                        v59 = &a6;
                        for ( j = (char *)v79 + 3; j >= v31; --j )
                        {
                          *j = *(_BYTE *)v59;
                          v59 = (unsigned int *)((char *)v59 + 1);
                        }
                        HashProperty = MSCryptHashData(*(_QWORD *)v87, v31, v10, 0);
                        if ( HashProperty )
                          break;
                        HashProperty = MSCryptFinishHash(*(_QWORD *)v87, P, (unsigned int)v81, 0);
                        if ( HashProperty )
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                          {
                            WPP_SF_sDsd(
                              *((_QWORD *)WPP_GLOBAL_Control + 3),
                              v62,
                              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                              (unsigned int)"Status",
                              HashProperty,
                              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                              17);
                            goto LABEL_79;
                          }
                          goto LABEL_83;
                        }
                        v63 = v81;
                        v64 = v32 - v49;
                        v65 = v32 - v49;
                        if ( (unsigned int)v81 < v32 - v49 )
                          v65 = (unsigned int)v81;
                        memmove((void *)(a3 + v49), P, v65);
                        if ( v63 < v64 )
                          v64 = v63;
                        v49 += v64;
                      }
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v61,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                          (unsigned int)"Status",
                          HashProperty,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                          5);
LABEL_79:
                        v9 = v31;
LABEL_32:
                        v7 = *(_QWORD *)v80;
                        goto LABEL_35;
                      }
LABEL_83:
                      v7 = *(_QWORD *)v80;
                      goto LABEL_84;
                    }
                    HashProperty = -1073741801;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (v71 = *((_DWORD *)WPP_GLOBAL_Control + 11), (v71 & 1) == 0) )
                    {
LABEL_84:
                      v9 = v31;
LABEL_85:
                      v8 = v77;
LABEL_86:
                      v11 = P;
                      goto LABEL_37;
                    }
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v71,
                      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                      (unsigned int)"Status",
                      23,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                      170);
                    v9 = 0;
                    goto LABEL_35;
                  }
                  v10 = -1;
                  HashProperty = -1073741811;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                  {
                    goto LABEL_85;
                  }
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v27,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                    (unsigned int)"Status",
                    13,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                    157);
LABEL_35:
                  v11 = P;
LABEL_36:
                  v8 = v77;
                  goto LABEL_37;
                }
                v51 = 403;
              }
            }
            v10 = -1;
            HashProperty = -1073741811;
            DebugTraceError(
              3221225485LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
              v51);
            goto LABEL_35;
          }
          DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 352);
        }
        else
        {
          HashProperty = -1073741801;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_85;
          v73 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v73 & 1) == 0 )
            goto LABEL_85;
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v73,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            79);
        }
        v11 = 0;
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      {
        v8 = 0;
        goto LABEL_86;
      }
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v24,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        (unsigned int)"Status",
        HashProperty,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        68);
LABEL_94:
      v11 = 0;
      v8 = 0;
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v23,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        (unsigned int)"Status",
        HashProperty,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        51);
LABEL_104:
    v7 = *(_QWORD *)v80;
    goto LABEL_94;
  }
  HashProperty = -1073741811;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
    return HashProperty;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 3),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
    (unsigned int)"Status",
    13,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
    153);
LABEL_37:
  if ( *(_QWORD *)v87 )
    MSCryptDestroyHash();
  if ( v7 )
    MSCryptCloseHashProvider(v7, 0);
  if ( v11 )
  {
    v52 = (unsigned int)v81;
    v53 = v11;
    if ( (_DWORD)v81 )
    {
      do
      {
        *v53++ = 0;
        --v52;
      }
      while ( v52 );
    }
    MSCryptFree(v11);
  }
  if ( v8 )
  {
    v54 = (unsigned int)v82;
    v55 = v8;
    if ( v82 )
    {
      do
      {
        *v55++ = 0;
        --v54;
      }
      while ( v54 );
    }
    MSCryptFree(v8);
  }
  if ( v9 )
  {
    v56 = v10;
    v57 = v9;
    if ( v10 )
    {
      do
      {
        *v57++ = 0;
        --v56;
      }
      while ( v56 );
    }
    MSCryptFree(v9);
  }
  if ( v88 )
    MSCryptFree(v88);
  return HashProperty;
}

```

## disassembly

```asm
0x18000e940  mov     rax, rsp
0x18000e943  mov     [rax+10h], rbx
0x18000e947  mov     [rax+18h], r8
0x18000e94b  mov     [rax+8], rcx
0x18000e94f  push    rbp
0x18000e950  push    rsi
0x18000e951  push    rdi
0x18000e952  push    r12
0x18000e954  push    r13
0x18000e956  push    r14
0x18000e958  push    r15
0x18000e95a  lea     rbp, [rax-4Fh]
0x18000e95e  sub     rsp, 0A0h
0x18000e965  xor     r8d, r8d
0x18000e968  mov     rdi, rdx
0x18000e96b  mov     rax, rcx
0x18000e96e  mov     r14d, r8d
0x18000e971  mov     r12d, r8d
0x18000e974  mov     qword ptr [rbp+47h+var_78], r8
0x18000e978  mov     r13d, r8d
0x18000e97b  mov     qword ptr [rbp+47h+var_50], r8
0x18000e97f  mov     esi, r8d
0x18000e982  mov     [rbp+47h+var_68], r8d
0x18000e986  mov     r15d, r8d
0x18000e989  mov     [rbp+47h+P], r8
0x18000e98d  mov     dword ptr [rbp+47h+var_70], r8d
0x18000e991  mov     dword ptr [rbp+47h+var_80], r8d
0x18000e995  mov     [rbp+47h+var_48], r8
0x18000e999  mov     dword ptr [rbp+47h+var_70+4], r8d
0x18000e99d  cmp     [rbp+47h+arg_28], r8d
0x18000e9a1  jnz     loc_18000F01F
0x18000e9a7  mov     rcx, [rbp+47h+arg_20]
0x18000e9ab  mov     edx, r9d
0x18000e9ae  mov     [rcx], r8d
0x18000e9b1  lea     r8, [rbp+47h+var_70+4]
0x18000e9b5  mov     eax, [rax+20h]
0x18000e9b8  mov     rcx, rdi
0x18000e9bb  mov     [rbp+47h+var_58], eax
0x18000e9be  call    GetKeyBitLength
0x18000e9c3  mov     ebx, eax
0x18000e9c5  test    eax, eax
0x18000e9c7  js      loc_18000F248
0x18000e9cd  xor     ebx, ebx
0x18000e9cf  xor     r8d, r8d
0x18000e9d2  mov     rcx, rdi
0x18000e9d5  mov     [rbp+47h+Src], rbx
0x18000e9d9  mov     dword ptr [rbp+47h+Size], ebx
0x18000e9dc  mov     [rbp+47h+arg_28], ebx
0x18000e9df  lea     edx, [rbx+11h]
0x18000e9e2  call    QueryParameterList
0x18000e9e7  movsxd  r15, eax
0x18000e9ea  mov     [rbp+47h+var_5C], r15d
0x18000e9ee  test    eax, eax
0x18000e9f0  jns     loc_18000F268
0x18000e9f6  xor     r8d, r8d
0x18000e9f9  mov     rcx, rdi
0x18000e9fc  lea     edx, [r8+0Dh]
0x18000ea00  call    QueryParameterList
0x18000ea05  test    eax, eax
0x18000ea07  jns     loc_18000EB99
0x18000ea0d  xor     r8d, r8d
0x18000ea10  mov     [rbp+47h+var_38], rbx
0x18000ea14  mov     rcx, rdi
0x18000ea17  mov     dword ptr [rbp+47h+Size+4], ebx
0x18000ea1a  lea     edx, [r8+0Eh]
0x18000ea1e  call    QueryParameterList
0x18000ea23  test    eax, eax
0x18000ea25  jns     loc_18000EBC0
0x18000ea2b  xor     r8d, r8d
0x18000ea2e  xor     edx, edx
0x18000ea30  mov     rcx, rdi
0x18000ea33  call    QueryParameterList
0x18000ea38  test    eax, eax
0x18000ea3a  jns     loc_18000EE63
0x18000ea40  lea     rdx, aSha256; "SHA256"
0x18000ea47  neg     [rbp+47h+var_58]
0x18000ea4a  lea     rcx, [rbp+47h+var_78]
0x18000ea4e  sbb     r8d, r8d
0x18000ea51  neg     r8d
0x18000ea54  add     r8d, 28h ; '('
0x18000ea58  call    MSCryptOpenHashProvider
0x18000ea5d  mov     ebx, eax
0x18000ea5f  test    eax, eax
0x18000ea61  jnz     loc_18000F0C0
0x18000ea67  mov     r14, qword ptr [rbp+47h+var_78]
0x18000ea6b  lea     rax, [rbp+47h+var_80]
0x18000ea6f  lea     edi, [rbx+4]
0x18000ea72  mov     dword ptr [rsp+0D0h+var_A8], esi
0x18000ea76  mov     r9d, edi
0x18000ea79  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000ea7e  mov     rcx, r14
0x18000ea81  lea     r8, [rbp+47h+var_68]
0x18000ea85  lea     rdx, aObjectlength; "ObjectLength"
0x18000ea8c  call    MSCryptGetHashProperty
0x18000ea91  mov     ebx, eax
0x18000ea93  test    eax, eax
0x18000ea95  jnz     loc_18000F209
0x18000ea9b  mov     ecx, [rbp+47h+var_68]
0x18000ea9e  call    MSCryptAlloc
0x18000eaa3  mov     [rbp+47h+var_90], rax
0x18000eaa7  test    rax, rax
0x18000eaaa  jz      loc_18000F1AD
0x18000eab0  lea     rax, [rbp+47h+var_80]
0x18000eab4  mov     dword ptr [rsp+0D0h+var_A8], esi
0x18000eab8  mov     r9d, edi
0x18000eabb  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000eac0  lea     r8, [rbp+47h+var_70]
0x18000eac4  mov     rcx, r14
0x18000eac7  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000eace  call    MSCryptGetHashProperty
0x18000ead3  mov     ebx, eax
0x18000ead5  test    eax, eax
0x18000ead7  jnz     loc_18000F2C0
0x18000eadd  mov     ecx, dword ptr [rbp+47h+var_70]
0x18000eae0  call    MSCryptAlloc
0x18000eae5  mov     [rbp+47h+P], rax
0x18000eae9  test    rax, rax
0x18000eaec  jz      loc_18000F077
0x18000eaf2  test    r15d, r15d
0x18000eaf5  jns     loc_18000EEA9
0x18000eafb  mov     eax, dword ptr [rbp+47h+Size]
0x18000eafe  add     eax, 8
0x18000eb01  cmp     eax, 8
0x18000eb04  jb      loc_18000EDFD
0x18000eb0a  mov     ecx, dword ptr [rbp+47h+Size+4]
0x18000eb0d  add     ecx, eax
0x18000eb0f  cmp     ecx, eax
0x18000eb11  jb      loc_18000EC92
0x18000eb17  lea     esi, [rcx+1]
0x18000eb1a  cmp     esi, ecx
0x18000eb1c  jb      loc_18000EE08
0x18000eb22  mov     ecx, esi
0x18000eb24  mov     ebx, esi
0x18000eb26  call    MSCryptAlloc
0x18000eb2b  mov     [rbp+47h+var_80], rax
0x18000eb2f  mov     rdi, rax
0x18000eb32  test    rax, rax
0x18000eb35  jz      loc_18000EF15
0x18000eb3b  mov     r14d, dword ptr [rbp+47h+var_70+4]
0x18000eb3f  mov     r8d, ebx; Size
0x18000eb42  add     r14d, 7
0x18000eb46  xor     edx, edx; Val
0x18000eb48  mov     rcx, rax; void *
0x18000eb4b  shr     r14d, 3
0x18000eb4f  call    memset
0x18000eb54  add     rdi, 4
0x18000eb58  mov     rcx, rdi; void *
0x18000eb5b  test    r15d, r15d
0x18000eb5e  jns     loc_18000F16E
0x18000eb64  mov     ebx, dword ptr [rbp+47h+Size]
0x18000eb67  mov     rdx, [rbp+47h+Src]; Src
0x18000eb6b  mov     r8d, ebx; Size
0x18000eb6e  call    memmove
0x18000eb73  mov     rdx, [rbp+47h+var_38]; Src
0x18000eb77  lea     ecx, [rbx+1]
0x18000eb7a  mov     ebx, dword ptr [rbp+47h+Size+4]
0x18000eb7d  add     rdi, rcx
0x18000eb80  mov     rcx, rdi; void *
0x18000eb83  mov     r8, rbx; Size
0x18000eb86  call    memmove
0x18000eb8b  lea     rdx, [rbx+rdi]
0x18000eb8f  lea     rcx, [rdx+3]
0x18000eb93  lea     r8, [rbp+47h+var_70+4]
0x18000eb97  jmp     short loc_18000EBF2
0x18000eb99  test    r12, r12
0x18000eb9c  jnz     loc_18000F13A
0x18000eba2  movsxd  rcx, eax
0x18000eba5  mov     rax, [rdi+8]
0x18000eba9  add     rcx, rcx
0x18000ebac  mov     rdx, [rax+rcx*8+8]
0x18000ebb1  mov     eax, [rax+rcx*8]
0x18000ebb4  mov     [rbp+47h+Src], rdx
0x18000ebb8  mov     dword ptr [rbp+47h+Size], eax
0x18000ebbb  jmp     loc_18000EA0D
0x18000ebc0  test    r12, r12
0x18000ebc3  jnz     loc_18000EFC9
0x18000ebc9  movsxd  rcx, eax
0x18000ebcc  mov     rax, [rdi+8]
0x18000ebd0  add     rcx, rcx
0x18000ebd3  mov     rdx, [rax+rcx*8+8]
0x18000ebd8  mov     eax, [rax+rcx*8]
0x18000ebdb  mov     [rbp+47h+var_38], rdx
0x18000ebdf  mov     dword ptr [rbp+47h+Size+4], eax
0x18000ebe2  jmp     loc_18000EA2B
0x18000ebe7  mov     al, [r8]
0x18000ebea  mov     [rcx], al
0x18000ebec  dec     rcx
0x18000ebef  inc     r8
0x18000ebf2  cmp     rcx, rdx
0x18000ebf5  jnb     short loc_18000EBE7
0x18000ebf7  mov     ecx, dword ptr [rbp+47h+var_70]
0x18000ebfa  xor     edx, edx
0x18000ebfc  mov     r12, [rbp+47h+var_90]
0x18000ec00  xor     r8d, r8d; int
0x18000ec03  mov     dword ptr [rsp+38h], 0; int
0x18000ec0b  mov     r9, r12; int
0x18000ec0e  lea     eax, [rcx-1]
0x18000ec11  add     eax, r14d
0x18000ec14  div     ecx
0x18000ec16  mov     edx, [rbp+47h+var_68]
0x18000ec19  mov     r13d, eax
0x18000ec1c  mov     rax, [rbp+47h+arg_0]
0x18000ec20  mov     ecx, [rax+10h]
0x18000ec23  mov     dword ptr [rsp+0D0h+var_A0], ecx; Size
0x18000ec27  mov     rcx, [rax+18h]
0x18000ec2b  mov     [rsp+0D0h+var_A8], rcx; Src
0x18000ec30  mov     rcx, qword ptr [rbp+47h+var_78]; int
0x18000ec34  mov     [rsp+0D0h+var_B0], edx; int
0x18000ec38  lea     rdx, [rbp+47h+var_50]; int
0x18000ec3c  call    MSCryptCreateMultiHash
0x18000ec41  mov     ebx, eax
0x18000ec43  test    eax, eax
0x18000ec45  jnz     loc_18000EF7D
0x18000ec4b  xor     r12d, r12d
0x18000ec4e  lea     r15d, [rax+1]
0x18000ec52  mov     eax, r15d
0x18000ec55  mov     [rbp+47h+arg_28], r15d
0x18000ec59  cmp     eax, r13d
0x18000ec5c  jbe     loc_18000ED74
0x18000ec62  mov     r13, [rbp+47h+var_80]
0x18000ec66  lea     ecx, ds:0[r14*8]
0x18000ec6e  sub     ecx, dword ptr [rbp+47h+var_70+4]
0x18000ec71  lea     edx, [r14-1]
0x18000ec75  mov     eax, 0FFh
0x18000ec7a  shl     al, cl
0x18000ec7c  mov     rcx, [rbp+47h+arg_10]
0x18000ec80  and     [rdx+rcx], al
0x18000ec83  mov     rax, [rbp+47h+arg_20]
0x18000ec87  xor     ebx, ebx
0x18000ec89  mov     [rax], r14d
0x18000ec8c  mov     r14, qword ptr [rbp+47h+var_78]
0x18000ec90  jmp     short loc_18000ECB8
0x18000ec92  mov     r9d, 193h
0x18000ec98  or      esi, 0FFFFFFFFh
0x18000ec9b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eca2  lea     rdx, aStatus; "Status"
0x18000eca9  mov     ecx, 0C000000Dh
0x18000ecae  mov     ebx, 0C000000Dh
0x18000ecb3  call    DebugTraceError
0x18000ecb8  mov     r15, [rbp+47h+P]
0x18000ecbc  mov     r12, [rbp+47h+var_90]
0x18000ecc0  mov     rcx, qword ptr [rbp+47h+var_50]
0x18000ecc4  xor     edi, edi
0x18000ecc6  test    rcx, rcx
0x18000ecc9  jz      short loc_18000ECD0
0x18000eccb  call    MSCryptDestroyHash
0x18000ecd0  test    r14, r14
0x18000ecd3  jz      short loc_18000ECDF
0x18000ecd5  xor     edx, edx
0x18000ecd7  mov     rcx, r14
0x18000ecda  call    MSCryptCloseHashProvider
0x18000ecdf  test    r15, r15
0x18000ece2  jz      short loc_18000ED03
0x18000ece4  mov     eax, dword ptr [rbp+47h+var_70]
0x18000ece7  mov     rcx, r15
0x18000ecea  test    rax, rax
0x18000eced  jz      short loc_18000ECFB
0x18000ecef  mov     [rcx], dil
0x18000ecf2  inc     rcx
0x18000ecf5  sub     rax, 1
0x18000ecf9  jnz     short loc_18000ECEF
0x18000ecfb  mov     rcx, r15; P
0x18000ecfe  call    MSCryptFree
0x18000ed03  test    r12, r12
0x18000ed06  jz      short loc_18000ED27
0x18000ed08  mov     eax, [rbp+47h+var_68]
0x18000ed0b  mov     rcx, r12
0x18000ed0e  test    rax, rax
0x18000ed11  jz      short loc_18000ED1F
0x18000ed13  mov     [rcx], dil
0x18000ed16  inc     rcx
0x18000ed19  sub     rax, 1
0x18000ed1d  jnz     short loc_18000ED13
0x18000ed1f  mov     rcx, r12; P
0x18000ed22  call    MSCryptFree
0x18000ed27  test    r13, r13
0x18000ed2a  jz      short loc_18000ED49
0x18000ed2c  mov     ecx, esi
0x18000ed2e  mov     rax, r13
0x18000ed31  test    esi, esi
0x18000ed33  jz      short loc_18000ED41
0x18000ed35  mov     [rax], dil
0x18000ed38  inc     rax
0x18000ed3b  sub     rcx, 1
0x18000ed3f  jnz     short loc_18000ED35
0x18000ed41  mov     rcx, r13; P
0x18000ed44  call    MSCryptFree
0x18000ed49  mov     rax, [rbp+47h+var_48]
0x18000ed4d  test    rax, rax
0x18000ed50  jnz     loc_18000F2E0
0x18000ed56  mov     eax, ebx
0x18000ed58  mov     rbx, [rsp+0D0h+arg_8]
0x18000ed60  add     rsp, 0A0h
0x18000ed67  pop     r15
0x18000ed69  pop     r14
0x18000ed6b  pop     r13
0x18000ed6d  pop     r12
0x18000ed6f  pop     rdi
0x18000ed70  pop     rsi
0x18000ed71  pop     rbp
  ... truncated ...
```
