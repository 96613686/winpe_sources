# DeriveKeySP800108_CTR_HMAC

- ea: `0x180004820`
- end: `0x1800051cd`
- name: `DeriveKeySP800108_CTR_HMAC`
- size: `2477`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180039de0`

## callees

- `0x180002530`
- `0x180003f70`
- `0x180004320`
- `0x180004820`
- `0x1800051d4`
- `0x180005590`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180011ac0`
- `0x180031270`
- `0x18003a150`
- `0x18003b970`
- `0x180040308`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x180004b7b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004d1a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004dd1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004e19`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004e7b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004ed0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004f2a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004f87`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180004fbe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800050b9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000510b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000512e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18000517e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800051a6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

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
  int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  unsigned int v28; // ecx
  char *v29; // rax
  char *v30; // rdi
  unsigned int v31; // r14d
  char *v32; // rdi
  void *v33; // rcx
  unsigned int v34; // ebx
  void *v35; // rdx
  __int64 v36; // rcx
  size_t v37; // rbx
  char *v38; // rcx
  char *v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  void *v45; // rdx
  unsigned int v46; // r13d
  int v47; // edx
  unsigned int v48; // r12d
  unsigned int i; // r15d
  __int64 v50; // r9
  __int64 v51; // rax
  _BYTE *v52; // rcx
  __int64 v53; // rax
  _BYTE *v54; // rcx
  __int64 v55; // rcx
  _BYTE *v56; // rax
  unsigned int *v58; // rdx
  char *j; // rcx
  int v60; // edx
  int v61; // edx
  unsigned int v62; // ebx
  unsigned int v63; // edi
  size_t v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rbx
  unsigned int v67; // eax
  unsigned __int64 v68; // r15
  size_t v69; // r14
  int v70; // edx
  int v71; // edx
  int v72; // edx
  __int64 v73; // rax
  void *v74; // rax
  size_t v75; // [rsp+38h] [rbp-59h]
  PVOID v76; // [rsp+48h] [rbp-49h]
  PVOID P; // [rsp+50h] [rbp-41h]
  PVOID v78; // [rsp+58h] [rbp-39h] BYREF
  int v79[2]; // [rsp+60h] [rbp-31h] BYREF
  size_t v80; // [rsp+68h] [rbp-29h] BYREF
  int v81; // [rsp+70h] [rbp-21h] BYREF
  unsigned int Size; // [rsp+74h] [rbp-1Dh]
  unsigned int Size_4; // [rsp+78h] [rbp-19h]
  int v84; // [rsp+7Ch] [rbp-15h]
  int v85; // [rsp+80h] [rbp-11h]
  int v86[2]; // [rsp+88h] [rbp-9h] BYREF
  PVOID v87; // [rsp+90h] [rbp-1h]
  void *Src; // [rsp+98h] [rbp+7h]
  void *v89; // [rsp+A0h] [rbp+Fh]

  v7 = 0;
  v8 = 0;
  *(_QWORD *)v79 = 0;
  v9 = 0;
  *(_QWORD *)v86 = 0;
  v10 = 0;
  v81 = 0;
  v11 = 0;
  P = 0;
  v80 = 0;
  LODWORD(v78) = 0;
  v87 = 0;
  if ( !a6 )
  {
    *a5 = 0;
    v85 = *(_DWORD *)(a1 + 32);
    KeyBitLength = GetKeyBitLength(a2, a4, (char *)&v80 + 4);
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
    v84 = ParameterList;
    if ( ParameterList >= 0 )
    {
      v73 = *(_QWORD *)(a2 + 8);
      v8 = *(void **)(v73 + 16 * v15 + 8);
      a6 = *(_DWORD *)(v73 + 16 * v15);
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
      v40 = v16;
      v41 = *(_QWORD *)(a2 + 8);
      v40 *= 2;
      v42 = *(void **)(v41 + 8 * v40 + 8);
      LODWORD(v41) = *(_DWORD *)(v41 + 8 * v40);
      Src = v42;
      Size = v41;
    }
    v89 = 0;
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
      v43 = v18;
      v44 = *(_QWORD *)(a2 + 8);
      v43 *= 2;
      v45 = *(void **)(v44 + 8 * v43 + 8);
      LODWORD(v44) = *(_DWORD *)(v44 + 8 * v43);
      v89 = v45;
      Size_4 = v44;
    }
    v20 = QueryParameterList(a2, 0, 0);
    if ( v20 >= 0 )
    {
      _mm_lfence();
      v65 = *(_QWORD *)(a2 + 8);
      v66 = 2LL * v20;
      v67 = *(_DWORD *)(v65 + 16LL * v20);
      if ( (v67 & 1) != 0 || v67 < 2 )
      {
        HashProperty = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v65,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            12);
        goto LABEL_94;
      }
      v21 = *(const wchar_t **)(v65 + 8 * v66 + 8);
      v68 = (unsigned __int64)v67 >> 1;
      v69 = v67;
      if ( v21[v68 - 1] )
      {
        v74 = (void *)MSCryptAlloc(v67 + 2LL);
        v87 = v74;
        if ( !v74 )
        {
          HashProperty = -1073741801;
          DebugTraceError(
            3221225495LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
            283);
          goto LABEL_104;
        }
        memmove(v74, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v66 + 8), v69);
        v21 = (const wchar_t *)v87;
        *((_WORD *)v87 + v68) = 0;
      }
      LODWORD(v15) = v84;
    }
    else
    {
      v21 = L"SHA256";
    }
    v22 = v85 != 0;
    v85 = -v85;
    HashProperty = MSCryptOpenHashProvider(v79, v21, (unsigned int)v22 + 40);
    if ( !HashProperty )
    {
      v7 = *(_QWORD *)v79;
      HashProperty = MSCryptGetHashProperty(*(_QWORD *)v79, L"ObjectLength", &v81, 4, &v78, 0);
      if ( !HashProperty )
      {
        v76 = (PVOID)MSCryptAlloc((unsigned int)v81);
        if ( v76 )
        {
          v25 = MSCryptGetHashProperty(v7, L"HashDigestLength", &v80, 4, &v78, 0);
          HashProperty = v25;
          if ( !v25 )
          {
            P = (PVOID)MSCryptAlloc((unsigned int)v80);
            if ( !P )
            {
              HashProperty = -1073741801;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_85;
              v71 = *((_DWORD *)WPP_GLOBAL_Control + 11);
              if ( (v71 & 1) == 0 )
                goto LABEL_85;
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v71,
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
              v50 = 381;
            }
            else
            {
              v27 = Size + 8;
              if ( Size >= 0xFFFFFFF8 )
              {
                v50 = 393;
              }
              else
              {
                v28 = v27 + Size_4;
                if ( v27 + Size_4 >= v27 )
                {
                  v10 = v28 + 1;
                  if ( v28 + 1 >= v28 )
                  {
LABEL_18:
                    v29 = (char *)MSCryptAlloc(v10);
                    v78 = v29;
                    v30 = v29;
                    if ( v29 )
                    {
                      v31 = (unsigned int)(HIDWORD(v80) + 7) >> 3;
                      memset(v29, 0, v10);
                      v32 = v30 + 4;
                      v33 = v32;
                      if ( (int)v15 >= 0 )
                      {
                        v37 = a6;
                        v35 = v8;
                      }
                      else
                      {
                        v34 = Size;
                        memmove(v32, Src, Size);
                        v35 = v89;
                        v36 = v34 + 1;
                        v37 = Size_4;
                        v32 += v36;
                        v33 = v32;
                      }
                      memmove(v33, v35, v37);
                      v38 = &v32[v37 + 3];
                      v39 = (char *)&v80 + 4;
                      while ( v38 >= &v32[v37] )
                        *v38-- = *v39++;
                      v8 = v76;
                      v46 = (v31 + (_DWORD)v80 - 1) / (unsigned int)v80;
                      LODWORD(v75) = *(_DWORD *)(a1 + 16);
                      HashProperty = MSCryptCreateMultiHash(
                                       v79[0],
                                       (int)v86,
                                       0,
                                       (int)v76,
                                       v81,
                                       *(void **)(a1 + 24),
                                       v75,
                                       0);
                      if ( HashProperty )
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            v47,
                            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                            (unsigned int)"Status",
                            HashProperty,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                            237);
                        }
                        v7 = *(_QWORD *)v79;
                        v9 = v78;
                        goto LABEL_86;
                      }
                      v48 = 0;
                      for ( i = 1; ; ++i )
                      {
                        a6 = i;
                        if ( i > v46 )
                        {
                          v9 = v78;
                          *(_BYTE *)(v31 - 1 + a3) &= -1 << (8 * v31 - BYTE4(v80));
                          HashProperty = 0;
                          *a5 = v31;
                          goto LABEL_32;
                        }
                        v30 = (char *)v78;
                        v58 = &a6;
                        for ( j = (char *)v78 + 3; j >= v30; --j )
                        {
                          *j = *(_BYTE *)v58;
                          v58 = (unsigned int *)((char *)v58 + 1);
                        }
                        HashProperty = MSCryptHashData(*(_QWORD *)v86, v30, v10, 0);
                        if ( HashProperty )
                          break;
                        HashProperty = MSCryptFinishHash(*(_QWORD *)v86, P, (unsigned int)v80, 0);
                        if ( HashProperty )
                        {
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
                              17);
                            goto LABEL_79;
                          }
                          goto LABEL_83;
                        }
                        v62 = v80;
                        v63 = v31 - v48;
                        v64 = v31 - v48;
                        if ( (unsigned int)v80 < v31 - v48 )
                          v64 = (unsigned int)v80;
                        memmove((void *)(a3 + v48), P, v64);
                        if ( v62 < v63 )
                          v63 = v62;
                        v48 += v63;
                      }
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v60,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                          (unsigned int)"Status",
                          HashProperty,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                          5);
LABEL_79:
                        v9 = v30;
LABEL_32:
                        v7 = *(_QWORD *)v79;
                        goto LABEL_35;
                      }
LABEL_83:
                      v7 = *(_QWORD *)v79;
                      goto LABEL_84;
                    }
                    HashProperty = -1073741801;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (v70 = *((_DWORD *)WPP_GLOBAL_Control + 11), (v70 & 1) == 0) )
                    {
LABEL_84:
                      v9 = v30;
LABEL_85:
                      v8 = v76;
LABEL_86:
                      v11 = P;
                      goto LABEL_37;
                    }
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v70,
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
                    v26,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                    (unsigned int)"Status",
                    13,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                    157);
LABEL_35:
                  v11 = P;
LABEL_36:
                  v8 = v76;
                  goto LABEL_37;
                }
                v50 = 403;
              }
            }
            v10 = -1;
            HashProperty = -1073741811;
            DebugTraceError(
              3221225485LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
              v50);
            goto LABEL_35;
          }
          DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 352);
        }
        else
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
    v7 = *(_QWORD *)v79;
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
  if ( *(_QWORD *)v86 )
    MSCryptDestroyHash();
  if ( v7 )
    MSCryptCloseHashProvider(v7, 0);
  if ( v11 )
  {
    v51 = (unsigned int)v80;
    v52 = v11;
    if ( (_DWORD)v80 )
    {
      do
      {
        *v52++ = 0;
        --v51;
      }
      while ( v51 );
    }
    MSCryptFree(v11);
  }
  if ( v8 )
  {
    v53 = (unsigned int)v81;
    v54 = v8;
    if ( v81 )
    {
      do
      {
        *v54++ = 0;
        --v53;
      }
      while ( v53 );
    }
    MSCryptFree(v8);
  }
  if ( v9 )
  {
    v55 = v10;
    v56 = v9;
    if ( v10 )
    {
      do
      {
        *v56++ = 0;
        --v55;
      }
      while ( v55 );
    }
    MSCryptFree(v9);
  }
  if ( v87 )
    MSCryptFree(v87);
  return HashProperty;
}

```

## disassembly

```asm
0x180004820  mov     rax, rsp
0x180004823  mov     [rax+10h], rbx
0x180004827  mov     [rax+18h], r8
0x18000482b  mov     [rax+8], rcx
0x18000482f  push    rbp
0x180004830  push    rsi
0x180004831  push    rdi
0x180004832  push    r12
0x180004834  push    r13
0x180004836  push    r14
0x180004838  push    r15
0x18000483a  lea     rbp, [rax-4Fh]
0x18000483e  sub     rsp, 0A0h
0x180004845  xor     r8d, r8d
0x180004848  mov     rdi, rdx
0x18000484b  mov     rax, rcx
0x18000484e  mov     r14d, r8d
0x180004851  mov     r12d, r8d
0x180004854  mov     qword ptr [rbp+47h+var_78], r8
0x180004858  mov     r13d, r8d
0x18000485b  mov     qword ptr [rbp+47h+var_50], r8
0x18000485f  mov     esi, r8d
0x180004862  mov     [rbp+47h+var_68], r8d
0x180004866  mov     r15d, r8d
0x180004869  mov     [rbp+47h+P], r8
0x18000486d  mov     dword ptr [rbp+47h+var_70], r8d
0x180004871  mov     dword ptr [rbp+47h+var_80], r8d
0x180004875  mov     [rbp+47h+var_48], r8
0x180004879  mov     dword ptr [rbp+47h+var_70+4], r8d
0x18000487d  cmp     [rbp+47h+arg_28], r8d
0x180004881  jnz     loc_180004EFF
0x180004887  mov     rcx, [rbp+47h+arg_20]
0x18000488b  mov     edx, r9d
0x18000488e  mov     [rcx], r8d
0x180004891  lea     r8, [rbp+47h+var_70+4]
0x180004895  mov     eax, [rax+20h]
0x180004898  mov     rcx, rdi
0x18000489b  mov     [rbp+47h+var_58], eax
0x18000489e  call    GetKeyBitLength
0x1800048a3  mov     ebx, eax
0x1800048a5  test    eax, eax
0x1800048a7  js      loc_180005128
0x1800048ad  xor     ebx, ebx
0x1800048af  xor     r8d, r8d
0x1800048b2  mov     rcx, rdi
0x1800048b5  mov     [rbp+47h+Src], rbx
0x1800048b9  mov     dword ptr [rbp+47h+Size], ebx
0x1800048bc  mov     [rbp+47h+arg_28], ebx
0x1800048bf  lea     edx, [rbx+11h]
0x1800048c2  call    QueryParameterList
0x1800048c7  movsxd  r15, eax
0x1800048ca  mov     [rbp+47h+var_5C], r15d
0x1800048ce  test    eax, eax
0x1800048d0  jns     loc_180005148
0x1800048d6  xor     r8d, r8d
0x1800048d9  mov     rcx, rdi
0x1800048dc  lea     edx, [r8+0Dh]
0x1800048e0  call    QueryParameterList
0x1800048e5  test    eax, eax
0x1800048e7  jns     loc_180004A79
0x1800048ed  xor     r8d, r8d
0x1800048f0  mov     [rbp+47h+var_38], rbx
0x1800048f4  mov     rcx, rdi
0x1800048f7  mov     dword ptr [rbp+47h+Size+4], ebx
0x1800048fa  lea     edx, [r8+0Eh]
0x1800048fe  call    QueryParameterList
0x180004903  test    eax, eax
0x180004905  jns     loc_180004AA0
0x18000490b  xor     r8d, r8d
0x18000490e  xor     edx, edx
0x180004910  mov     rcx, rdi
0x180004913  call    QueryParameterList
0x180004918  test    eax, eax
0x18000491a  jns     loc_180004D43
0x180004920  lea     rdx, aSha256; "SHA256"
0x180004927  neg     [rbp+47h+var_58]
0x18000492a  lea     rcx, [rbp+47h+var_78]
0x18000492e  sbb     r8d, r8d
0x180004931  neg     r8d
0x180004934  add     r8d, 28h ; '('
0x180004938  call    MSCryptOpenHashProvider
0x18000493d  mov     ebx, eax
0x18000493f  test    eax, eax
0x180004941  jnz     loc_180004FA0
0x180004947  mov     r14, qword ptr [rbp+47h+var_78]
0x18000494b  lea     rax, [rbp+47h+var_80]
0x18000494f  lea     edi, [rbx+4]
0x180004952  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180004956  mov     r9d, edi
0x180004959  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000495e  mov     rcx, r14
0x180004961  lea     r8, [rbp+47h+var_68]
0x180004965  lea     rdx, aObjectlength; "ObjectLength"
0x18000496c  call    MSCryptGetHashProperty
0x180004971  mov     ebx, eax
0x180004973  test    eax, eax
0x180004975  jnz     loc_1800050E9
0x18000497b  mov     ecx, [rbp+47h+var_68]
0x18000497e  call    MSCryptAlloc
0x180004983  mov     [rbp+47h+var_90], rax
0x180004987  test    rax, rax
0x18000498a  jz      loc_18000508D
0x180004990  lea     rax, [rbp+47h+var_80]
0x180004994  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180004998  mov     r9d, edi
0x18000499b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800049a0  lea     r8, [rbp+47h+var_70]
0x1800049a4  mov     rcx, r14
0x1800049a7  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800049ae  call    MSCryptGetHashProperty
0x1800049b3  mov     ebx, eax
0x1800049b5  test    eax, eax
0x1800049b7  jnz     loc_1800051A0
0x1800049bd  mov     ecx, dword ptr [rbp+47h+var_70]
0x1800049c0  call    MSCryptAlloc
0x1800049c5  mov     [rbp+47h+P], rax
0x1800049c9  test    rax, rax
0x1800049cc  jz      loc_180004F57
0x1800049d2  test    r15d, r15d
0x1800049d5  jns     loc_180004D89
0x1800049db  mov     eax, dword ptr [rbp+47h+Size]
0x1800049de  add     eax, 8
0x1800049e1  cmp     eax, 8
0x1800049e4  jb      loc_180004CDD
0x1800049ea  mov     ecx, dword ptr [rbp+47h+Size+4]
0x1800049ed  add     ecx, eax
0x1800049ef  cmp     ecx, eax
0x1800049f1  jb      loc_180004B72
0x1800049f7  lea     esi, [rcx+1]
0x1800049fa  cmp     esi, ecx
0x1800049fc  jb      loc_180004CE8
0x180004a02  mov     ecx, esi
0x180004a04  mov     ebx, esi
0x180004a06  call    MSCryptAlloc
0x180004a0b  mov     [rbp+47h+var_80], rax
0x180004a0f  mov     rdi, rax
0x180004a12  test    rax, rax
0x180004a15  jz      loc_180004DF5
0x180004a1b  mov     r14d, dword ptr [rbp+47h+var_70+4]
0x180004a1f  mov     r8d, ebx; Size
0x180004a22  add     r14d, 7
0x180004a26  xor     edx, edx; Val
0x180004a28  mov     rcx, rax; void *
0x180004a2b  shr     r14d, 3
0x180004a2f  call    memset
0x180004a34  add     rdi, 4
0x180004a38  mov     rcx, rdi; void *
0x180004a3b  test    r15d, r15d
0x180004a3e  jns     loc_18000504E
0x180004a44  mov     ebx, dword ptr [rbp+47h+Size]
0x180004a47  mov     rdx, [rbp+47h+Src]; Src
0x180004a4b  mov     r8d, ebx; Size
0x180004a4e  call    memmove
0x180004a53  mov     rdx, [rbp+47h+var_38]; Src
0x180004a57  lea     ecx, [rbx+1]
0x180004a5a  mov     ebx, dword ptr [rbp+47h+Size+4]
0x180004a5d  add     rdi, rcx
0x180004a60  mov     rcx, rdi; void *
0x180004a63  mov     r8, rbx; Size
0x180004a66  call    memmove
0x180004a6b  lea     rdx, [rbx+rdi]
0x180004a6f  lea     rcx, [rdx+3]
0x180004a73  lea     r8, [rbp+47h+var_70+4]
0x180004a77  jmp     short loc_180004AD2
0x180004a79  test    r12, r12
0x180004a7c  jnz     loc_18000501A
0x180004a82  movsxd  rcx, eax
0x180004a85  mov     rax, [rdi+8]
0x180004a89  add     rcx, rcx
0x180004a8c  mov     rdx, [rax+rcx*8+8]
0x180004a91  mov     eax, [rax+rcx*8]
0x180004a94  mov     [rbp+47h+Src], rdx
0x180004a98  mov     dword ptr [rbp+47h+Size], eax
0x180004a9b  jmp     loc_1800048ED
0x180004aa0  test    r12, r12
0x180004aa3  jnz     loc_180004EA9
0x180004aa9  movsxd  rcx, eax
0x180004aac  mov     rax, [rdi+8]
0x180004ab0  add     rcx, rcx
0x180004ab3  mov     rdx, [rax+rcx*8+8]
0x180004ab8  mov     eax, [rax+rcx*8]
0x180004abb  mov     [rbp+47h+var_38], rdx
0x180004abf  mov     dword ptr [rbp+47h+Size+4], eax
0x180004ac2  jmp     loc_18000490B
0x180004ac7  mov     al, [r8]
0x180004aca  mov     [rcx], al
0x180004acc  dec     rcx
0x180004acf  inc     r8
0x180004ad2  cmp     rcx, rdx
0x180004ad5  jnb     short loc_180004AC7
0x180004ad7  mov     ecx, dword ptr [rbp+47h+var_70]
0x180004ada  xor     edx, edx
0x180004adc  mov     r12, [rbp+47h+var_90]
0x180004ae0  xor     r8d, r8d; int
0x180004ae3  mov     dword ptr [rsp+38h], 0; int
0x180004aeb  mov     r9, r12; int
0x180004aee  lea     eax, [rcx-1]
0x180004af1  add     eax, r14d
0x180004af4  div     ecx
0x180004af6  mov     edx, [rbp+47h+var_68]
0x180004af9  mov     r13d, eax
0x180004afc  mov     rax, [rbp+47h+arg_0]
0x180004b00  mov     ecx, [rax+10h]
0x180004b03  mov     dword ptr [rsp+0D0h+var_A0], ecx; Size
0x180004b07  mov     rcx, [rax+18h]
0x180004b0b  mov     [rsp+0D0h+var_A8], rcx; Src
0x180004b10  mov     rcx, qword ptr [rbp+47h+var_78]; int
0x180004b14  mov     [rsp+0D0h+var_B0], edx; int
0x180004b18  lea     rdx, [rbp+47h+var_50]; int
0x180004b1c  call    MSCryptCreateMultiHash
0x180004b21  mov     ebx, eax
0x180004b23  test    eax, eax
0x180004b25  jnz     loc_180004E5D
0x180004b2b  xor     r12d, r12d
0x180004b2e  lea     r15d, [rax+1]
0x180004b32  mov     eax, r15d
0x180004b35  mov     [rbp+47h+arg_28], r15d
0x180004b39  cmp     eax, r13d
0x180004b3c  jbe     loc_180004C54
0x180004b42  mov     r13, [rbp+47h+var_80]
0x180004b46  lea     ecx, ds:0[r14*8]
0x180004b4e  sub     ecx, dword ptr [rbp+47h+var_70+4]
0x180004b51  lea     edx, [r14-1]
0x180004b55  mov     eax, 0FFh
0x180004b5a  shl     al, cl
0x180004b5c  mov     rcx, [rbp+47h+arg_10]
0x180004b60  and     [rdx+rcx], al
0x180004b63  mov     rax, [rbp+47h+arg_20]
0x180004b67  xor     ebx, ebx
0x180004b69  mov     [rax], r14d
0x180004b6c  mov     r14, qword ptr [rbp+47h+var_78]
0x180004b70  jmp     short loc_180004B98
0x180004b72  mov     r9d, 193h
0x180004b78  or      esi, 0FFFFFFFFh
0x180004b7b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004b82  lea     rdx, aStatus; "Status"
0x180004b89  mov     ecx, 0C000000Dh
0x180004b8e  mov     ebx, 0C000000Dh
0x180004b93  call    DebugTraceError
0x180004b98  mov     r15, [rbp+47h+P]
0x180004b9c  mov     r12, [rbp+47h+var_90]
0x180004ba0  mov     rcx, qword ptr [rbp+47h+var_50]
0x180004ba4  xor     edi, edi
0x180004ba6  test    rcx, rcx
0x180004ba9  jz      short loc_180004BB0
0x180004bab  call    MSCryptDestroyHash
0x180004bb0  test    r14, r14
0x180004bb3  jz      short loc_180004BBF
0x180004bb5  xor     edx, edx
0x180004bb7  mov     rcx, r14
0x180004bba  call    MSCryptCloseHashProvider
0x180004bbf  test    r15, r15
0x180004bc2  jz      short loc_180004BE3
0x180004bc4  mov     eax, dword ptr [rbp+47h+var_70]
0x180004bc7  mov     rcx, r15
0x180004bca  test    rax, rax
0x180004bcd  jz      short loc_180004BDB
0x180004bcf  mov     [rcx], dil
0x180004bd2  inc     rcx
0x180004bd5  sub     rax, 1
0x180004bd9  jnz     short loc_180004BCF
0x180004bdb  mov     rcx, r15; P
0x180004bde  call    MSCryptFree
0x180004be3  test    r12, r12
0x180004be6  jz      short loc_180004C07
0x180004be8  mov     eax, [rbp+47h+var_68]
0x180004beb  mov     rcx, r12
0x180004bee  test    rax, rax
0x180004bf1  jz      short loc_180004BFF
0x180004bf3  mov     [rcx], dil
0x180004bf6  inc     rcx
0x180004bf9  sub     rax, 1
0x180004bfd  jnz     short loc_180004BF3
0x180004bff  mov     rcx, r12; P
0x180004c02  call    MSCryptFree
0x180004c07  test    r13, r13
0x180004c0a  jz      short loc_180004C29
0x180004c0c  mov     ecx, esi
0x180004c0e  mov     rax, r13
0x180004c11  test    esi, esi
0x180004c13  jz      short loc_180004C21
0x180004c15  mov     [rax], dil
0x180004c18  inc     rax
0x180004c1b  sub     rcx, 1
0x180004c1f  jnz     short loc_180004C15
0x180004c21  mov     rcx, r13; P
0x180004c24  call    MSCryptFree
0x180004c29  mov     rax, [rbp+47h+var_48]
0x180004c2d  test    rax, rax
0x180004c30  jnz     loc_1800051C0
0x180004c36  mov     eax, ebx
0x180004c38  mov     rbx, [rsp+0D0h+arg_8]
0x180004c40  add     rsp, 0A0h
0x180004c47  pop     r15
0x180004c49  pop     r14
0x180004c4b  pop     r13
0x180004c4d  pop     r12
0x180004c4f  pop     rdi
0x180004c50  pop     rsi
0x180004c51  pop     rbp
  ... truncated ...
```
