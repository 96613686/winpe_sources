# ParseKeyFile

- ea: `0x180011678`
- end: `0x1800121db`
- name: `ParseKeyFile`
- size: `2915`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e1d4`
- `0x1800115b0`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18000bdd0`
- `0x18000d3d0`
- `0x18000def0`
- `0x180011678`
- `0x180016218`
- `0x18001c894`
- `0x18001ec8c`
- `0x180027068`
- `0x180029004`
- `0x1800398b0`
- `0x180050540`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x180011d1a`
- `bcrypt!BCryptImportKeyPair` at `0x180011e4a`
- `bcrypt!BCryptImportKeyPair` at `0x180011d1a`
- `bcrypt!BCryptImportKeyPair` at `0x180011e4a`
- `bcrypt!BCryptDestroyKey` at `0x180012194`
- `bcrypt!BCryptDestroyKey` at `0x1800121a9`
- `bcrypt!BCryptDestroyKey` at `0x180012194`
- `bcrypt!BCryptDestroyKey` at `0x1800121a9`

## string_xrefs

- `0x1800118fd`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180011a78`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180012178`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180011c83`: `COMPMLKEMPUBLICBLOB`

## pseudocode

```c
__int64 __fastcall ParseKeyFile(__int64 a1)
{
  unsigned int *v1; // rsi
  __int64 v3; // r9
  unsigned int v4; // ecx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  char *v8; // r8
  bool v9; // zf
  int *v10; // rcx
  _DWORD *v11; // r13
  __int64 v12; // rax
  size_t v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r15
  char *v16; // r9
  size_t v17; // r12
  char *v18; // r12
  int v19; // r14d
  __int64 v20; // rcx
  size_t v21; // r13
  unsigned int v22; // eax
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // r15
  unsigned __int16 *v25; // rax
  int v26; // edx
  int v27; // r8d
  void *v28; // rax
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r8
  char *v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r8
  _QWORD *v36; // rdx
  void *v37; // r15
  void *v38; // rcx
  unsigned int v39; // r13d
  void *v40; // rax
  rsize_t *p_SourceSize; // rsi
  int v42; // r12d
  unsigned int MsbBitLength; // eax
  __int64 v44; // r9
  __int64 v45; // rcx
  _BYTE *v46; // r15
  unsigned int v47; // eax
  __int64 v48; // rdx
  _BYTE *v49; // rax
  size_t v50; // rbx
  void *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // r8
  _QWORD *v54; // rdx
  __int64 v55; // rax
  UCHAR *pbInput; // r13
  const WCHAR *v57; // r15
  int v58; // eax
  unsigned __int64 v59; // r14
  __int64 v60; // rdx
  unsigned __int64 v61; // rcx
  __int64 v62; // rcx
  unsigned __int64 v63; // rcx
  void *v64; // rsp
  void *v65; // rsp
  rsize_t *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rdx
  _QWORD *v69; // r8
  size_t v70; // rbx
  void *v71; // rax
  void *v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  _QWORD *v75; // rdx
  BOOL v76; // eax
  void *v77; // rcx
  _DWORD *v78; // rbx
  rsize_t v79; // r14
  void *v80; // rax
  void *v81; // r15
  __int64 v82; // rcx
  __int64 v84; // [rsp+0h] [rbp-50h] BYREF
  rsize_t SourceSize; // [rsp+50h] [rbp+0h] BYREF
  __int64 v86; // [rsp+58h] [rbp+8h] BYREF
  void *Source; // [rsp+60h] [rbp+10h] BYREF
  unsigned int v88; // [rsp+68h] [rbp+18h] BYREF
  void *v89; // [rsp+70h] [rbp+20h] BYREF
  size_t cbInput; // [rsp+78h] [rbp+28h] BYREF
  size_t v91; // [rsp+80h] [rbp+30h] BYREF
  void *v92; // [rsp+88h] [rbp+38h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp+40h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+98h] [rbp+48h] BYREF
  size_t Size; // [rsp+A0h] [rbp+50h]
  _BYTE *v96; // [rsp+A8h] [rbp+58h] BYREF
  PUCHAR v97; // [rsp+B0h] [rbp+60h] BYREF
  __int64 v98; // [rsp+B8h] [rbp+68h]
  char *v99; // [rsp+C0h] [rbp+70h]
  _DWORD *v100; // [rsp+C8h] [rbp+78h] BYREF
  void *Src; // [rsp+D0h] [rbp+80h]
  __int64 v102; // [rsp+D8h] [rbp+88h] BYREF
  void *v103; // [rsp+E0h] [rbp+90h] BYREF
  void *v104; // [rsp+E8h] [rbp+98h]

  v1 = *(unsigned int **)(a1 + 224);
  Source = 0;
  LODWORD(SourceSize) = 0;
  v103 = 0;
  v91 = 0;
  v92 = 0;
  cbInput = 0;
  LODWORD(v89) = 0;
  v100 = 0;
  phKey = 0;
  hKey = 0;
  v97 = 0;
  v102 = 0;
  v86 = 0;
  if ( !v1 )
  {
    v3 = 167;
LABEL_174:
    v5 = -2146893811;
    v6 = 2148073485LL;
    goto LABEL_175;
  }
  v4 = v1[3];
  if ( v4 - 196612 <= 7 && *(_DWORD *)(a1 + 24) )
  {
    v5 = -2146893785;
    v3 = 187;
    v6 = 2148073511LL;
LABEL_175:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v3);
    goto LABEL_176;
  }
  v7 = *(_DWORD *)(a1 + 24);
  v8 = (char *)v1 + v1[2] + 44;
  v99 = v8;
  if ( v7 )
  {
    v10 = (int *)(v1 + 7);
  }
  else
  {
    v9 = v4 == 0;
    v10 = (int *)(v1 + 7);
    if ( v9 && (*v10 == 196611 || (v10 = (int *)(v1 + 7), v1[7] == 196609)) || !v1[3] && *v10 == 196620 )
    {
      *(_DWORD *)(a1 + 24) = 2;
      v7 = 2;
    }
    else
    {
      v7 = 0;
    }
  }
  v11 = v1 + 6;
  if ( v7 == 2 )
  {
    v12 = *v11 + v1[4] + v1[5];
    v11 = v1 + 10;
    v13 = v1[9];
    v8 += v12;
    v14 = v1[8];
    v99 = v8;
    LODWORD(v15) = v14;
    Size = v13;
    v16 = &v8[v14];
    v17 = v14 + v13;
  }
  else
  {
    v15 = v1[4];
    v10 = (int *)(v1 + 3);
    v14 = v15;
    LODWORD(Size) = v1[5];
    v17 = v15 + (unsigned int)Size;
    v16 = &v8[v15];
  }
  v88 = v14;
  v96 = v8;
  v18 = &v8[v17];
  v19 = *v10;
  v20 = (unsigned int)*v10;
  v21 = (unsigned int)*v11;
  Src = v16;
  v98 = v14;
  v22 = FinishNewKeyObject(v20, a1);
  v5 = v22;
  if ( v22 )
  {
    v3 = 260;
    v6 = v22;
    goto LABEL_175;
  }
  if ( !(_DWORD)v15 || !(_DWORD)v21 )
  {
    v3 = 278;
    goto LABEL_174;
  }
  v23 = (unsigned __int16 *)SafeAllocaAllocateFromHeap(v1[2] + 2LL);
  v104 = v23;
  v24 = v23;
  if ( !v23 )
  {
    v5 = -2146893810;
    v3 = 297;
    v6 = 2148073486LL;
    goto LABEL_175;
  }
  memcpy_0(v23, v1 + 11, v1[2]);
  v24[(unsigned __int64)v1[2] >> 1] = 0;
  v25 = v24;
  do
  {
    v26 = *(unsigned __int16 *)((char *)v25 + *(_QWORD *)(a1 + 8) - (_QWORD)v24);
    v27 = *v25 - v26;
    if ( v27 )
      break;
    ++v25;
  }
  while ( v26 );
  if ( v27 )
  {
    MSCryptFree(*(_QWORD *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = v24;
    v104 = 0;
  }
  v28 = (void *)SafeAllocaAllocateFromHeap(v21);
  *(_QWORD *)(a1 + 240) = v28;
  if ( v28 )
  {
    memcpy_0(v28, v18, v21);
    v31 = (unsigned int)v98;
    v32 = v99;
    *(_DWORD *)(a1 + 248) = v21;
    v33 = DeserializeProperties(a1, v32, v31, 0);
    v5 = v33;
    if ( v33 )
    {
      v29 = 341;
      v30 = v33;
      goto LABEL_32;
    }
    if ( !(unsigned int)LookupKeyPropertyByNumber(a1, 27, (unsigned int)&v86, (unsigned int)&v100, (__int64)&v89) )
    {
      if ( (_DWORD)v89 != 4 )
      {
        v5 = -2146893798;
        v29 = 360;
        v30 = 2148073498LL;
        goto LABEL_32;
      }
      *(_DWORD *)(a1 + 564) = *v100;
      v34 = v86;
      v35 = *(_QWORD *)(v86 + 152);
      if ( *(_QWORD *)(v35 + 8) != v86 + 152 )
        goto LABEL_137;
      v36 = *(_QWORD **)(v86 + 160);
      if ( *v36 != v86 + 152 )
        goto LABEL_137;
      *v36 = v35;
      *(_QWORD *)(v35 + 8) = v36;
      MSCryptFree(v34);
      v86 = 0;
    }
    v37 = Src;
    v38 = 0;
    v39 = Size;
    v89 = 0;
    if ( ((unsigned __int8)Src & 0xF) != 0 )
    {
      v40 = (void *)SafeAllocaAllocateFromHeap((unsigned int)Size);
      v89 = v40;
      if ( !v40 )
      {
        v29 = 377;
        goto LABEL_31;
      }
      memcpy_0(v40, v37, v39);
      v38 = v89;
    }
    p_SourceSize = 0;
    v42 = 1;
    if ( v38 )
      LODWORD(v37) = (_DWORD)v38;
    MsbBitLength = DecryptPrivateKey(
                     (_DWORD)v37,
                     v39,
                     (unsigned int)&v96,
                     (unsigned int)&v88,
                     *(_DWORD *)(a1 + 32),
                     0,
                     *(_DWORD *)(a1 + 564) & 1,
                     0,
                     0,
                     (__int64)&v91 + 4);
    v5 = MsbBitLength;
    if ( MsbBitLength )
    {
      v44 = 403;
LABEL_49:
      v45 = MsbBitLength;
LABEL_50:
      DebugTraceError(v45, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v44);
LABEL_166:
      if ( v89 )
        MSCryptFree(v89);
      if ( p_SourceSize && *((_DWORD *)p_SourceSize - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_171;
    }
    v46 = v96;
    v47 = DeserializeProperties(a1, v96, v88, 1);
    v48 = v88;
    v5 = v47;
    v49 = v46;
    if ( v88 )
    {
      do
      {
        *v49++ = 0;
        --v48;
      }
      while ( v48 );
    }
    MSCryptFree(v46);
    if ( v5 )
    {
      v44 = 419;
LABEL_55:
      v45 = v5;
      goto LABEL_50;
    }
    if ( !(unsigned int)LookupKeyPropertyByNumber(a1, 25, (unsigned int)&v86, (unsigned int)&v92, (__int64)&cbInput)
      && (_DWORD)cbInput )
    {
      v50 = (unsigned int)cbInput;
      v51 = (void *)SafeAllocaAllocateFromHeap((unsigned int)cbInput);
      *(_QWORD *)(a1 + 544) = v51;
      if ( !v51 )
      {
        v44 = 440;
LABEL_60:
        v5 = -2146893810;
        v45 = 2148073486LL;
        goto LABEL_50;
      }
      memcpy_0(v51, v92, v50);
      v52 = v86;
      v53 = *(_QWORD *)(v86 + 152);
      if ( *(_QWORD *)(v53 + 8) != v86 + 152 )
        goto LABEL_137;
      v54 = *(_QWORD **)(v86 + 160);
      if ( *v54 != v86 + 152 )
        goto LABEL_137;
      *v54 = v53;
      *(_QWORD *)(v53 + 8) = v54;
      MSCryptFree(v52);
      v86 = 0;
    }
    v55 = *(_QWORD *)(a1 + 64);
    if ( *(_DWORD *)(v55 + 8) == 1 || *(_DWORD *)(v55 + 8) == 7 )
      goto LABEL_123;
    MsbBitLength = LookupKeyPropertyByNumber(a1, 10, (unsigned int)&v102, (unsigned int)&v97, (__int64)&cbInput + 4);
    v5 = MsbBitLength;
    if ( MsbBitLength )
    {
      v44 = 470;
      goto LABEL_49;
    }
    pbInput = v97;
    v92 = 0;
    switch ( v19 )
    {
      case 196609:
        v57 = L"RSAPUBLICBLOB";
        *(_DWORD *)(a1 + 28) = *((_DWORD *)v97 + 1);
LABEL_95:
        v59 = HIDWORD(cbInput);
        MsbBitLength = BCryptImportKeyPair(
                         *(BCRYPT_ALG_HANDLE *)(a1 + 88),
                         0,
                         v57,
                         &phKey,
                         pbInput,
                         HIDWORD(cbInput),
                         0);
        v5 = MsbBitLength;
        if ( MsbBitLength )
        {
          v44 = 625;
          goto LABEL_49;
        }
        if ( v92 )
        {
          if ( !(_DWORD)v59 )
            goto LABEL_183;
          if ( v59 > g_ulMaxStackAllocSize )
            goto LABEL_183;
          v61 = v59 + g_ulAdditionalProbeSize + 8;
          if ( v61 < v59 || !(unsigned int)VerifyStackAvailable(v61, v60) )
            goto LABEL_183;
          v62 = v59 + 23;
          if ( v59 + 23 <= v59 + 8 )
            v62 = 0xFFFFFFFFFFFFFF0LL;
          v63 = v62 & 0xFFFFFFFFFFFFFFF0uLL;
          v64 = alloca(v63);
          v65 = alloca(v63);
          p_SourceSize = &SourceSize;
          if ( &v84 == (__int64 *)-80LL || (LODWORD(SourceSize) = 1801679955, (p_SourceSize = (rsize_t *)&v86) == 0) )
          {
LABEL_183:
            if ( v59 + 8 >= v59 )
            {
              v66 = (rsize_t *)((__int64 (*)(void))g_pfnAllocate)();
              p_SourceSize = v66;
              if ( v66 )
              {
                *(_DWORD *)v66 = 1885431112;
                p_SourceSize = v66 + 1;
              }
            }
          }
          if ( !p_SourceSize )
          {
            v5 = 8;
            v44 = 642;
            goto LABEL_55;
          }
          memcpy_0(p_SourceSize, pbInput, v59);
          switch ( *(_DWORD *)p_SourceSize )
          {
            case 0x314B4345:
              *(_DWORD *)p_SourceSize = 827540293;
              break;
            case 0x334B4345:
              *(_DWORD *)p_SourceSize = 861094725;
              break;
            case 0x354B4345:
              *(_DWORD *)p_SourceSize = 894649157;
              break;
            default:
              v44 = 668;
              goto LABEL_87;
          }
          MsbBitLength = BCryptImportKeyPair(
                           *(BCRYPT_ALG_HANDLE *)(a1 + 120),
                           0,
                           v57,
                           &hKey,
                           (PUCHAR)p_SourceSize,
                           v59,
                           0);
          v5 = MsbBitLength;
          if ( MsbBitLength )
          {
            v44 = 685;
            goto LABEL_49;
          }
        }
        v67 = v102;
        v68 = *(_QWORD *)(v102 + 152);
        if ( *(_QWORD *)(v68 + 8) != v102 + 152 )
          goto LABEL_137;
        v69 = *(_QWORD **)(v102 + 160);
        if ( *v69 != v102 + 152 )
          goto LABEL_137;
        *v69 = v68;
        *(_QWORD *)(v68 + 8) = v69;
        MSCryptFree(v67);
LABEL_123:
        if ( (unsigned int)LookupKeyPropertyByNumber(a1, 24, (unsigned int)&v86, (unsigned int)&v103, (__int64)&v91)
          || (v70 = (unsigned int)v91, !(_DWORD)v91) )
        {
LABEL_130:
          if ( !(unsigned int)LookupKeyPropertyByNumber(
                                a1,
                                29,
                                (unsigned int)&v86,
                                (unsigned int)&Source,
                                (__int64)&SourceSize)
            && (_DWORD)SourceSize == 4
            && *(_DWORD *)Source )
          {
            v76 = !(unsigned int)LookupKeyPropertyByNumber(
                                   a1,
                                   30,
                                   (unsigned int)&v86,
                                   (unsigned int)&Source,
                                   (__int64)&SourceSize)
               && (_DWORD)SourceSize == 4
               && *(_DWORD *)Source;
            *(_DWORD *)(a1 + 144) = 1;
            *(_DWORD *)(a1 + 148) = v76;
          }
          else
          {
            v42 = 0;
          }
          *(_DWORD *)(a1 + 48) = v42;
          if ( !(unsigned int)LookupKeyPropertyByNumber(
                                a1,
                                3,
                                (unsigned int)&v86,
                                (unsigned int)&Source,
                                (__int64)&SourceSize)
            && (_DWORD)SourceSize == 4 )
          {
            *(_DWORD *)(a1 + 36) = *(_DWORD *)Source;
          }
          if ( !(unsigned int)LookupKeyPropertyByNumber(
                                a1,
                                5,
                                (unsigned int)&v86,
                                (unsigned int)&Source,
                                (__int64)&SourceSize)
            && (_DWORD)SourceSize == 4 )
          {
            *(_DWORD *)(a1 + 40) = *(_DWORD *)Source;
          }
          if ( !(unsigned int)LookupKeyPropertyByNumber(
                                a1,
                                12,
                                (unsigned int)&v86,
                                (unsigned int)&Source,
                                (__int64)&SourceSize) )
          {
            v77 = *(void **)(a1 + 416);
            v78 = (_DWORD *)(a1 + 424);
            v79 = (unsigned int)SourceSize;
            if ( v77 && *v78 >= (unsigned int)SourceSize )
            {
              if ( memcpy_s(v77, (unsigned int)*v78, Source, (unsigned int)SourceSize) )
              {
LABEL_151:
                v5 = -2147418113;
                goto LABEL_166;
              }
            }
            else
            {
              v80 = (void *)SafeAllocaAllocateFromHeap((unsigned int)SourceSize);
              v81 = v80;
              if ( !v80 )
              {
                v5 = 8;
                goto LABEL_166;
              }
              if ( memcpy_s(v80, v79, Source, v79) )
                goto LABEL_151;
              v82 = *(_QWORD *)(a1 + 416);
              if ( v82 && *v78 < (unsigned int)v79 )
                MSCryptFree(v82);
              *(_QWORD *)(a1 + 416) = v81;
            }
            *v78 = v79;
          }
          if ( !(unsigned int)LookupKeyPropertyByNumber(
                                a1,
                                18,
                                (unsigned int)&v86,
                                (unsigned int)&Source,
                                (__int64)&SourceSize)
            && (_DWORD)SourceSize == 4 )
          {
            *(_DWORD *)(a1 + 428) |= *(_DWORD *)Source;
          }
          v9 = (v91 & 0x800000000LL) == 0;
          *(_QWORD *)(a1 + 104) = phKey;
          *(_QWORD *)(a1 + 128) = hKey;
          phKey = 0;
          hKey = 0;
          if ( !v9 )
            WriteKeyToStore(a1, 0, 2);
          v5 = 0;
          goto LABEL_166;
        }
        v71 = (void *)SafeAllocaAllocateFromHeap((unsigned int)v91);
        *(_QWORD *)(a1 + 512) = v71;
        if ( !v71 )
        {
          v44 = 716;
          goto LABEL_60;
        }
        v72 = v103;
        *(_DWORD *)(a1 + 520) = v70;
        memcpy_0(v71, v72, v70);
        v73 = v86;
        v74 = *(_QWORD *)(v86 + 152);
        if ( *(_QWORD *)(v74 + 8) == v86 + 152 )
        {
          v75 = *(_QWORD **)(v86 + 160);
          if ( *v75 == v86 + 152 )
          {
            *v75 = v74;
            *(_QWORD *)(v74 + 8) = v75;
            MSCryptFree(v73);
            goto LABEL_130;
          }
        }
LABEL_137:
        __fastfail(3u);
      case 196611:
        v57 = L"DSAPUBLICBLOB";
        *(_DWORD *)(a1 + 28) = 8 * *((_DWORD *)v97 + 1);
        goto LABEL_95;
      case 196610:
        v57 = L"DHPUBLICBLOB";
        *(_DWORD *)(a1 + 28) = 8 * *((_DWORD *)v97 + 1);
        goto LABEL_95;
    }
    if ( (unsigned int)(v19 - 196612) > 1 )
    {
      if ( v19 == 196614 )
      {
LABEL_91:
        v58 = 521;
        goto LABEL_93;
      }
      if ( (unsigned int)(v19 - 196615) > 1 )
      {
        if ( v19 != 196617 )
        {
          if ( (unsigned int)(v19 - 196618) <= 1 )
          {
            MsbBitLength = GetMsbBitLength(v97 + 32, *((unsigned int *)v97 + 4), a1 + 28);
            v5 = MsbBitLength;
            if ( MsbBitLength )
            {
              v44 = 558;
              goto LABEL_49;
            }
            v57 = L"ECCFULLPUBLICBLOB";
          }
          else
          {
            switch ( v19 )
            {
              case 196620:
                v57 = L"PQDSAPUBLICBLOB";
                break;
              case 458753:
                v57 = L"MLKEMPUBLICBLOB";
                break;
              case 458754:
                v57 = L"COMPMLKEMPUBLICBLOB";
                break;
              default:
                v44 = 609;
LABEL_87:
                v5 = -2146893783;
                v45 = 2148073513LL;
                goto LABEL_50;
            }
            *(_DWORD *)(a1 + 28) = 0;
          }
          goto LABEL_95;
        }
        goto LABEL_91;
      }
    }
    v58 = 8 * *((_DWORD *)v97 + 1);
LABEL_93:
    *(_DWORD *)(a1 + 28) = v58;
    v57 = L"ECCPUBLICBLOB";
    if ( (unsigned int)(v19 - 196615) <= 2 )
      v92 = *(void **)(a1 + 120);
    goto LABEL_95;
  }
  v29 = 321;
LABEL_31:
  v5 = -2146893810;
  v30 = 2148073486LL;
LABEL_32:
  DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v29);
LABEL_171:
  if ( v104 )
    MSCryptFree(v104);
LABEL_176:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( hKey )
    BCryptDestroyKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180011678  push    rbp
0x18001167a  push    rbx
0x18001167b  push    rsi
0x18001167c  push    rdi
0x18001167d  push    r12
0x18001167f  push    r13
0x180011681  push    r14
0x180011683  push    r15
0x180011685  sub     rsp, 108h
0x18001168c  lea     rbp, [rsp+50h]
0x180011691  mov     rax, cs:__security_cookie
0x180011698  xor     rax, rbp
0x18001169b  mov     [rbp+0F0h+var_50], rax
0x1800116a2  mov     rsi, [rcx+0E0h]
0x1800116a9  mov     rdi, rcx
0x1800116ac  mov     [rbp+0F0h+Source], 0
0x1800116b4  mov     dword ptr [rbp+0F0h+SourceSize], 0
0x1800116bb  mov     [rbp+0F0h+var_60], 0
0x1800116c6  mov     dword ptr [rbp+0F0h+var_C0], 0
0x1800116cd  mov     [rbp+0F0h+var_B8], 0
0x1800116d5  mov     dword ptr [rbp+0F0h+var_C8], 0
0x1800116dc  mov     dword ptr [rbp+0F0h+var_D0], 0
0x1800116e3  mov     [rbp+0F0h+var_78], 0
0x1800116eb  mov     [rbp+0F0h+phKey], 0
0x1800116f3  mov     [rbp+0F0h+hKey], 0
0x1800116fb  mov     [rbp+0F0h+var_90], 0
0x180011703  mov     dword ptr [rbp+0F0h+var_C8+4], 0
0x18001170a  mov     [rbp+0F0h+var_68], 0
0x180011715  mov     [rbp+0F0h+var_E8], 0
0x18001171d  mov     dword ptr [rbp+0F0h+var_C0+4], 0
0x180011724  test    rsi, rsi
0x180011727  jnz     short loc_180011734
0x180011729  mov     r9d, 0A7h
0x18001172f  jmp     loc_18001216E
0x180011734  lea     rdx, [rsi+0Ch]
0x180011738  mov     ecx, [rdx]
0x18001173a  lea     eax, [rcx-30004h]
0x180011740  cmp     eax, 7
0x180011743  ja      short loc_180011760
0x180011745  cmp     dword ptr [rdi+18h], 0
0x180011749  jz      short loc_180011760
0x18001174b  mov     ebx, 80090027h
0x180011750  mov     r9d, 0BBh
0x180011756  mov     ecx, 80090027h
0x18001175b  jmp     loc_180012178
0x180011760  mov     r8d, [rsi+8]
0x180011764  mov     r9d, 2
0x18001176a  mov     eax, [rdi+18h]
0x18001176d  add     r8, 2Ch ; ','
0x180011771  add     r8, rsi
0x180011774  mov     [rbp+0F0h+var_80], r8
0x180011778  test    eax, eax
0x18001177a  jnz     short loc_1800117B2
0x18001177c  test    ecx, ecx
0x18001177e  lea     rcx, [rsi+1Ch]
0x180011782  jnz     short loc_1800117A1
0x180011784  cmp     dword ptr [rcx], 30003h
0x18001178a  jz      short loc_180011798
0x18001178c  lea     rcx, [rsi+1Ch]
0x180011790  cmp     dword ptr [rcx], 30001h
0x180011796  jnz     short loc_1800117A1
0x180011798  mov     [rdi+18h], r9d
0x18001179c  mov     eax, r9d
0x18001179f  jmp     short loc_1800117B6
0x1800117a1  cmp     dword ptr [rdx], 0
0x1800117a4  jnz     short loc_1800117AE
0x1800117a6  cmp     dword ptr [rcx], 3000Ch
0x1800117ac  jz      short loc_180011798
0x1800117ae  xor     eax, eax
0x1800117b0  jmp     short loc_1800117B6
0x1800117b2  lea     rcx, [rsi+1Ch]
0x1800117b6  lea     r13, [rsi+18h]
0x1800117ba  cmp     eax, r9d
0x1800117bd  jnz     short loc_1800117EB
0x1800117bf  mov     eax, [rsi+14h]
0x1800117c2  add     eax, [rsi+10h]
0x1800117c5  add     eax, [r13+0]
0x1800117c9  lea     r13, [rsi+28h]
0x1800117cd  mov     edx, [rsi+24h]
0x1800117d0  add     r8, rax
0x1800117d3  mov     eax, [rsi+20h]
0x1800117d6  mov     [rbp+0F0h+var_80], r8
0x1800117da  mov     r15d, eax
0x1800117dd  mov     [rbp+0F0h+Size], rdx
0x1800117e1  lea     r9, [rax+r8]
0x1800117e5  lea     r12, [rax+rdx]
0x1800117e9  jmp     short loc_180011804
0x1800117eb  mov     r15d, [rsi+10h]
0x1800117ef  mov     rcx, rdx
0x1800117f2  mov     r12d, [rsi+14h]
0x1800117f6  mov     eax, r15d
0x1800117f9  mov     dword ptr [rbp+0F0h+Size], r12d
0x1800117fd  add     r12, r15
0x180011800  lea     r9, [r15+r8]
0x180011804  mov     [rbp+0F0h+var_D8], eax
0x180011807  mov     rdx, rdi
0x18001180a  mov     [rbp+0F0h+var_98], r8
0x18001180e  add     r12, r8
0x180011811  mov     r14d, [rcx]
0x180011814  mov     ecx, r14d
0x180011817  mov     r13d, [r13+0]
0x18001181b  mov     [rbp+0F0h+Src], r9
0x180011822  mov     [rbp+0F0h+var_88], rax
0x180011826  call    FinishNewKeyObject
0x18001182b  mov     ebx, eax
0x18001182d  test    eax, eax
0x18001182f  jz      short loc_18001183E
0x180011831  mov     r9d, 104h
0x180011837  mov     ecx, eax
0x180011839  jmp     loc_180012178
0x18001183e  test    r15d, r15d
0x180011841  jz      loc_180012168
0x180011847  test    r13d, r13d
0x18001184a  jz      loc_180012168
0x180011850  mov     ecx, [rsi+8]
0x180011853  add     rcx, 2
0x180011857  call    SafeAllocaAllocateFromHeap
0x18001185c  mov     [rbp+0F0h+var_58], rax
0x180011863  mov     r15, rax
0x180011866  test    rax, rax
0x180011869  jnz     short loc_180011880
0x18001186b  mov     ebx, 8009000Eh
0x180011870  mov     r9d, 129h
0x180011876  mov     ecx, 8009000Eh
0x18001187b  jmp     loc_180012178
0x180011880  mov     r8d, [rsi+8]; Size
0x180011884  lea     rdx, [rsi+2Ch]; Src
0x180011888  mov     rcx, r15; void *
0x18001188b  call    memcpy_0
0x180011890  mov     ecx, [rsi+8]
0x180011893  xor     eax, eax
0x180011895  shr     rcx, 1
0x180011898  mov     [r15+rcx*2], ax
0x18001189d  mov     rax, r15
0x1800118a0  mov     rcx, [rdi+8]
0x1800118a4  mov     r9, rcx
0x1800118a7  sub     r9, r15
0x1800118aa  movzx   r8d, word ptr [rax]
0x1800118ae  movzx   edx, word ptr [rax+r9]
0x1800118b3  sub     r8d, edx
0x1800118b6  jnz     short loc_1800118C0
0x1800118b8  add     rax, 2
0x1800118bc  test    edx, edx
0x1800118be  jnz     short loc_1800118AA
0x1800118c0  test    r8d, r8d
0x1800118c3  jz      short loc_1800118D9
0x1800118c5  call    MSCryptFree
0x1800118ca  mov     [rdi+8], r15
0x1800118ce  mov     [rbp+0F0h+var_58], 0
0x1800118d9  mov     rcx, r13
0x1800118dc  call    SafeAllocaAllocateFromHeap
0x1800118e1  mov     [rdi+0F0h], rax
0x1800118e8  test    rax, rax
0x1800118eb  jnz     short loc_180011915
0x1800118ed  mov     r9d, 141h
0x1800118f3  mov     ebx, 8009000Eh
0x1800118f8  mov     ecx, 8009000Eh
0x1800118fd  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011904  lea     rdx, aStatus; "Status"
0x18001190b  call    DebugTraceError
0x180011910  jmp     loc_180012152
0x180011915  mov     r8, r13; Size
0x180011918  mov     rdx, r12; Src
0x18001191b  mov     rcx, rax; void *
0x18001191e  call    memcpy_0
0x180011923  mov     r8d, dword ptr [rbp+0F0h+var_88]
0x180011927  xor     r9d, r9d
0x18001192a  mov     rdx, [rbp+0F0h+var_80]
0x18001192e  mov     rcx, rdi
0x180011931  mov     [rdi+0F8h], r13d
0x180011938  call    DeserializeProperties
0x18001193d  mov     ebx, eax
0x18001193f  test    eax, eax
0x180011941  jz      short loc_18001194D
0x180011943  mov     r9d, 155h
0x180011949  mov     ecx, eax
0x18001194b  jmp     short loc_1800118FD
0x18001194d  lea     rax, [rbp+0F0h+var_D0]
0x180011951  mov     edx, 1Bh
0x180011956  lea     r9, [rbp+0F0h+var_78]
0x18001195a  mov     [rsp+140h+pbInput], rax
0x18001195f  lea     r8, [rbp+0F0h+var_E8]
0x180011963  mov     rcx, rdi
0x180011966  call    LookupKeyPropertyByNumber
0x18001196b  test    eax, eax
0x18001196d  jnz     short loc_1800119CF
0x18001196f  cmp     dword ptr [rbp+0F0h+var_D0], 4
0x180011973  jz      short loc_18001198A
0x180011975  mov     ebx, 8009001Ah
0x18001197a  mov     r9d, 168h
0x180011980  mov     ecx, 8009001Ah
0x180011985  jmp     loc_1800118FD
0x18001198a  mov     rax, [rbp+0F0h+var_78]
0x18001198e  mov     ecx, [rax]
0x180011990  mov     [rdi+234h], ecx
0x180011996  mov     rcx, [rbp+0F0h+var_E8]
0x18001199a  lea     rax, [rcx+98h]
0x1800119a1  mov     r8, [rax]
0x1800119a4  cmp     [r8+8], rax
0x1800119a8  jnz     loc_180011F8D
0x1800119ae  mov     rdx, [rax+8]
0x1800119b2  cmp     [rdx], rax
0x1800119b5  jnz     loc_180011F8D
0x1800119bb  mov     [rdx], r8
0x1800119be  mov     [r8+8], rdx
0x1800119c2  call    MSCryptFree
0x1800119c7  mov     [rbp+0F0h+var_E8], 0
0x1800119cf  mov     r15, [rbp+0F0h+Src]
0x1800119d6  xor     ecx, ecx
0x1800119d8  mov     r13, [rbp+0F0h+Size]
0x1800119dc  mov     [rbp+0F0h+var_D0], rcx
0x1800119e0  test    r15b, 0Fh
0x1800119e4  jz      short loc_180011A17
0x1800119e6  mov     ecx, r13d
0x1800119e9  mov     ebx, r13d
0x1800119ec  call    SafeAllocaAllocateFromHeap
0x1800119f1  mov     [rbp+0F0h+var_D0], rax
0x1800119f5  test    rax, rax
0x1800119f8  jnz     short loc_180011A05
0x1800119fa  mov     r9d, 179h
0x180011a00  jmp     loc_1800118F3
0x180011a05  mov     r8, rbx; Size
0x180011a08  mov     rdx, r15; Src
0x180011a0b  mov     rcx, rax; void *
0x180011a0e  call    memcpy_0
0x180011a13  mov     rcx, [rbp+0F0h+var_D0]
0x180011a17  mov     eax, [rdi+234h]
0x180011a1d  lea     r9, [rbp+0F0h+var_D8]
0x180011a21  xor     edx, edx
0x180011a23  lea     r8, [rbp+0F0h+var_98]
0x180011a27  mov     esi, edx
0x180011a29  lea     r12d, [rdx+1]
0x180011a2d  and     eax, r12d
0x180011a30  test    rcx, rcx
0x180011a33  cmovnz  r15, rcx
0x180011a37  lea     rcx, [rbp+0F0h+var_C0+4]
0x180011a3b  mov     [rsp+140h+var_F8], rcx
0x180011a40  mov     rcx, r15
0x180011a43  mov     [rsp+140h+var_100], edx
0x180011a47  mov     [rsp+140h+var_108], rdx
0x180011a4c  mov     [rsp+140h+dwFlags], eax
0x180011a50  mov     eax, [rdi+20h]
0x180011a53  mov     [rsp+140h+cbInput], edx
0x180011a57  mov     edx, r13d
0x180011a5a  mov     dword ptr [rsp+140h+pbInput], eax
0x180011a5e  call    DecryptPrivateKey
0x180011a63  mov     ebx, eax
0x180011a65  test    eax, eax
0x180011a67  jz      short loc_180011A89
0x180011a69  mov     r9d, 193h
0x180011a6f  mov     ecx, eax
0x180011a71  lea     rdx, aStatus; "Status"
0x180011a78  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011a7f  call    DebugTraceError
0x180011a84  jmp     loc_180012127
0x180011a89  mov     r15, [rbp+0F0h+var_98]
0x180011a8d  mov     r9d, r12d
0x180011a90  mov     r8d, [rbp+0F0h+var_D8]
0x180011a94  mov     rdx, r15
0x180011a97  mov     rcx, rdi
0x180011a9a  call    DeserializeProperties
0x180011a9f  mov     edx, [rbp+0F0h+var_D8]
0x180011aa2  mov     ebx, eax
0x180011aa4  mov     rax, r15
0x180011aa7  test    rdx, rdx
0x180011aaa  jz      short loc_180011AB7
0x180011aac  mov     [rax], sil
0x180011aaf  add     rax, r12
0x180011ab2  sub     rdx, r12
0x180011ab5  jnz     short loc_180011AAC
0x180011ab7  mov     rcx, r15
0x180011aba  call    MSCryptFree
0x180011abf  test    ebx, ebx
0x180011ac1  jz      short loc_180011ACD
0x180011ac3  mov     r9d, 1A3h
0x180011ac9  mov     ecx, ebx
0x180011acb  jmp     short loc_180011A71
0x180011acd  lea     rax, [rbp+0F0h+var_C8]
0x180011ad1  mov     edx, 19h
0x180011ad6  lea     r9, [rbp+0F0h+var_B8]
0x180011ada  mov     [rsp+140h+pbInput], rax
0x180011adf  lea     r8, [rbp+0F0h+var_E8]
0x180011ae3  mov     rcx, rdi
0x180011ae6  call    LookupKeyPropertyByNumber
0x180011aeb  test    eax, eax
0x180011aed  jnz     short loc_180011B64
0x180011aef  mov     eax, dword ptr [rbp+0F0h+var_C8]
0x180011af2  test    eax, eax
0x180011af4  jz      short loc_180011B64
0x180011af6  mov     ecx, eax
0x180011af8  mov     ebx, eax
0x180011afa  call    SafeAllocaAllocateFromHeap
0x180011aff  mov     [rdi+220h], rax
0x180011b06  test    rax, rax
0x180011b09  jnz     short loc_180011B20
0x180011b0b  mov     r9d, 1B8h
0x180011b11  mov     ebx, 8009000Eh
0x180011b16  mov     ecx, 8009000Eh
0x180011b1b  jmp     loc_180011A71
0x180011b20  mov     rdx, [rbp+0F0h+var_B8]; Src
  ... truncated ...
```
