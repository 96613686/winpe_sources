# WfpNlShimInspectvSwitchForwardDatagram

- ea: `0x14016e378`
- end: `0x14016eb54`
- name: `WfpNlShimInspectvSwitchForwardDatagram`
- size: `2012`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x140122b24`

## callees

- `0x14008b610`
- `0x1400ca530`
- `0x1400ca6a0`
- `0x1400efdc0`
- `0x14016d888`
- `0x14016d8e0`
- `0x14016da8c`
- `0x14016db60`
- `0x14016de1c`
- `0x14016e1ac`
- `0x14016e2f4`
- `0x14016e378`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `NETIO!NetioDereferenceNetBufferList` at `0x14016eac2`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016eaf4`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016eac2`
- `NETIO!NetioDereferenceNetBufferList` at `0x14016eaf4`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e4ff`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e516`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e4ff`
- `NETIO!NetioReferenceNetBufferList` at `0x14016e516`
- `NETIO!NetioFlowRemoveContext` at `0x14016e6fd`
- `NETIO!NetioFlowRemoveContext` at `0x14016e6fd`
- `NETIO!NetioFlowRetrieveContext` at `0x14016e60e`
- `NETIO!NetioFlowRetrieveContext` at `0x14016e60e`
- `NETIO!KfdReleaseCachedFilters` at `0x14016e90a`
- `NETIO!KfdReleaseCachedFilters` at `0x14016e90a`
- `NETIO!KfdClassify` at `0x14016e854`
- `NETIO!KfdClassify` at `0x14016e854`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14016e638`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14016e638`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e5b1`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e9c2`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e5b1`
- `fwpkclnt!FwppvSwitchGetDestinationInterface` at `0x14016e9c2`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016eaa8`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016eae2`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016eaa8`
- `fwpkclnt!FwppDereferencevSwitchNblContext` at `0x14016eae2`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e4de`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e4f0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e525`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e4de`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e4f0`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14016e525`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e47c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016ea72`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016e47c`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x14016ea72`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016e4c6`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x14016e4c6`

## pseudocode

```c
__int64 __fastcall WfpNlShimInspectvSwitchForwardDatagram(
        int a1,
        __int64 a2,
        int a3,
        int a4,
        __int16 a5,
        __int16 a6,
        __int64 a7,
        __int64 a8)
{
  int v8; // r13d
  unsigned int v9; // ebx
  bool v10; // zf
  int v12; // eax
  unsigned __int16 v13; // r12
  _QWORD *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rdx
  bool v17; // al
  unsigned int *v18; // r15
  __int64 DestinationInterface; // r13
  unsigned int v20; // esi
  int v21; // r10d
  unsigned int v22; // r9d
  char v23; // r12
  int v24; // ecx
  char v25; // al
  __int64 v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // r9
  unsigned int v29; // eax
  char v30; // al
  int v31; // r9d
  __int64 v32; // r8
  int v33; // edx
  unsigned int i; // esi
  unsigned int v35; // eax
  int v36; // r8d
  _QWORD *v37; // rsi
  int v38; // r15d
  _QWORD *v39; // r14
  __int64 v40; // rax
  int v41; // ecx
  bool v43; // [rsp+80h] [rbp-80h]
  char v44; // [rsp+81h] [rbp-7Fh]
  char StorageForClassifyValues; // [rsp+82h] [rbp-7Eh]
  char v46; // [rsp+83h] [rbp-7Dh] BYREF
  _BYTE v47[4]; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h]
  unsigned int v49; // [rsp+8Ch] [rbp-74h] BYREF
  int v50; // [rsp+90h] [rbp-70h]
  void *v51; // [rsp+98h] [rbp-68h] BYREF
  int v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D4h] [rbp-2Ch]
  int v60; // [rsp+D8h] [rbp-28h]
  __int128 v61; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-10h] BYREF
  int v63; // [rsp+F8h] [rbp-8h]
  __int64 v64; // [rsp+100h] [rbp+0h] BYREF
  int v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h] BYREF
  int v67; // [rsp+118h] [rbp+18h]
  __int64 v68; // [rsp+120h] [rbp+20h] BYREF
  int v69; // [rsp+128h] [rbp+28h]
  _DWORD v70[4]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v71; // [rsp+140h] [rbp+40h] BYREF
  __int128 v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+160h] [rbp+60h]

  LOBYTE(v8) = 0;
  v54 = a8;
  v58 = a4;
  v9 = 1;
  v10 = *(_BYTE *)(a7 + 73) == 0;
  v69 = 0;
  v67 = 0;
  v65 = 0;
  v63 = 0;
  memset(v70, 0, 12);
  v68 = 0;
  v66 = 0;
  v64 = 0;
  v62 = 0;
  v56 = 0;
  LODWORD(v57) = 0;
  WORD2(v57) = 0;
  v55 = 0;
  v51 = 0;
  StorageForClassifyValues = 0;
  LODWORD(v73) = 0;
  v12 = 1;
  v59 = a3;
  v60 = a1;
  v49 = 1;
  v48 = v8;
  v61 = 0;
  v46 = 0;
  v47[0] = 0;
  v71 = 0;
  v72 = 0;
  if ( v10 )
    v12 = *(_DWORD *)(a7 + 12);
  v50 = v12;
  if ( a1 )
  {
    v13 = 75;
    if ( v12 != 1 )
      v13 = 77;
  }
  else
  {
    v13 = 74;
    if ( v12 != 1 )
      v13 = 76;
  }
  v14 = *(_QWORD **)(a2 + 64);
  if ( *(_BYTE *)(a2 + 72) )
  {
    while ( 1 )
    {
      if ( !v14 )
        goto LABEL_16;
      v15 = FwppGetvSwitchNblContext(v14);
      if ( !v15 )
      {
        if ( FwppNetBufferListAssociateContext(
               1,
               v14,
               0xFFFF,
               a7,
               2,
               0,
               0,
               0,
               NlShimvSwitchNetBufferListEventNotifyFn,
               0) )
        {
          v23 = 1;
          goto LABEL_93;
        }
        FwppReferencevSwitchNblContext(a7);
        v15 = a7;
      }
      FwppReferencevSwitchNblContext(v15);
      NetioReferenceNetBufferList(v14);
      v14 = (_QWORD *)*v14;
    }
  }
  NetioReferenceNetBufferList(*(_QWORD *)(a2 + 64));
  FwppReferencevSwitchNblContext(a7);
LABEL_16:
  v16 = *(_QWORD *)(a7 + 56);
  v17 = 0;
  v18 = 0;
  v43 = 0;
  DestinationInterface = 0;
  v20 = 0;
  if ( v16 && !*(_BYTE *)(a7 + 73) )
  {
    v21 = *(_DWORD *)(v16 + 12);
    v22 = *(_DWORD *)(v16 + 8);
    v43 = v21 == 1;
    if ( v22 )
    {
      do
      {
        if ( (*(_BYTE *)(v20 * *(_DWORD *)(v16 + 4) + *(_QWORD *)(v16 + 16) + 6LL) & 1) == 0 )
          break;
        ++v20;
      }
      while ( v20 < v22 );
    }
    if ( v20 == v21 )
    {
      LOBYTE(v8) = v48;
      v9 = 0;
      *(_DWORD *)(a7 + 68) = 0;
      v23 = 1;
      goto LABEL_93;
    }
    v18 = (unsigned int *)(*(_QWORD *)(v16 + 16) + *(_DWORD *)(v16 + 4) * v20);
    DestinationInterface = FwppvSwitchGetDestinationInterface(
                             *(_QWORD *)(a7 + 136),
                             *v18,
                             *((unsigned __int16 *)v18 + 2));
    v17 = v43;
  }
  if ( *(_BYTE *)(a2 + 72)
    || v50 != 1 && !v17
    || !v54
    || !*(_QWORD *)(v54 + 200)
    || (v53 = 0, (unsigned int)NetioFlowRetrieveContext(v54, 1, NlShimReferenceFwLayerCache, &v53))
    || !v53 )
  {
LABEL_46:
    StorageForClassifyValues = WfpShimGetStorageForClassifyValues(&v55, &v51, v47, &v46);
    if ( !StorageForClassifyValues )
    {
      LOBYTE(v8) = v48;
      v23 = 1;
      v9 = 1;
      goto LABEL_93;
    }
    v49 = 0;
    v44 = 0;
    while ( 1 )
    {
      HIDWORD(v56) = NlShimMarshalvSwitchFwLayerFields(
                       v60,
                       a2,
                       v59,
                       v58,
                       a5,
                       a6,
                       a7,
                       DestinationInterface,
                       v50,
                       (__int64)v70,
                       (__int64)&v68,
                       (__int64)&v66,
                       (__int64)&v64,
                       (__int64)&v62,
                       v55);
      v57 = v55;
      LOWORD(v56) = v13;
      memset(v51, 0, 0x2A8u);
      LOBYTE(v26) = v44;
      v27 = (char *)v51 + 624;
      *((_QWORD *)v51 + 79) = (char *)v51 + 624;
      *v27 = v27;
      NlShimSetvSwitchLayerMetadata(a7, DestinationInterface, v26);
      if ( !*(_BYTE *)(a2 + 72) && v54 && (v50 == 1 || v43) )
      {
        *((_QWORD *)&v61 + 1) = &v61;
        *(_QWORD *)&v61 = &v61;
        *(_QWORD *)(v28 + 512) = &v61;
      }
      if ( (unsigned int)KfdClassify(v13, &v56, v51, *(_QWORD *)(a2 + 64), 0, &v71) )
      {
        v71 = 0;
        LODWORD(v71) = 4097;
        v72 = 0;
        v73 = 0;
      }
      else
      {
        v29 = WfpShimClassifyOutToIpFilterAction(&v71);
        WfpNlShimCheckIfPacketAbsorbed(v29, *(_QWORD *)(a2 + 64));
        if ( (_DWORD)v71 == 4097 )
        {
          v30 = v48;
          if ( (BYTE12(v72) & 1) == 0 )
            v30 = 1;
          LOBYTE(v48) = v30;
        }
        if ( !*(_BYTE *)(a2 + 72) && v54 && *((_DWORD *)v51 + 134) && (v50 == 1 || v43) )
        {
          v31 = DestinationInterface ? *(_DWORD *)(DestinationInterface + 1040) : 0;
          if ( (int)NlShimCacheMatchedFwLayerFilterList(
                      v54,
                      *((_DWORD *)v51 + 132),
                      0,
                      v31,
                      *((_QWORD *)v51 + 64),
                      (__int64)&v56,
                      1) < 0 )
            KfdReleaseCachedFilters(&v61);
        }
      }
      if ( *(_QWORD *)(a7 + 56) )
      {
        if ( (_DWORD)v71 == 4097 )
        {
          if ( (BYTE12(v72) & 1) == 0 )
            *(_BYTE *)(a7 + 64) = 1;
          if ( (unsigned int)NlShimExcludeDestinationForNblChain(a7, *(_QWORD *)(a2 + 64), v20) )
          {
LABEL_91:
            LOBYTE(v8) = v48;
            v23 = 1;
            goto LABEL_93;
          }
        }
        else
        {
          ++v49;
        }
        v32 = *(_QWORD *)(a7 + 56);
        v33 = -1;
        for ( i = v20 + 1; i < *(_DWORD *)(v32 + 8); ++i )
        {
          if ( (*(_BYTE *)(*(_DWORD *)(v32 + 4) * i + *(_QWORD *)(v32 + 16) + 6LL) & 1) == 0 )
          {
            v33 = i;
            break;
          }
        }
        v20 = v33;
        if ( v33 == -1 )
        {
          v18 = 0;
        }
        else
        {
          v18 = (unsigned int *)(*(_QWORD *)(v32 + 16) + (unsigned int)(*(_DWORD *)(v32 + 4) * v33));
          DestinationInterface = FwppvSwitchGetDestinationInterface(
                                   *(_QWORD *)(a7 + 136),
                                   *v18,
                                   *((unsigned __int16 *)v18 + 2));
          v44 = 1;
        }
      }
      v35 = WfpShimClassifyOutToIpFilterAction(&v71);
      v9 = v35;
      if ( v35 )
      {
        if ( v49 )
        {
          v9 = 0;
        }
        else if ( v35 == 1 )
        {
          v36 = (int)v51;
          *((_QWORD *)v51 + 64) = 0;
          ShimIndicateDiscardNoClassify(v13, (unsigned int)&v56, v36, *(_QWORD *)(a2 + 64), 0, v72, 0);
        }
      }
      if ( !v18 )
        goto LABEL_91;
    }
  }
  v52 = 0;
  KfdGetLayerCacheEpoch(v13, &v52);
  if ( *(_DWORD *)(v53 + 88) != v52 )
  {
    *(_DWORD *)(v53 + 88) = v52;
LABEL_45:
    NetioFlowRemoveContext(v54, 1);
    NLShimDereferenceFwLayerCache(&v53);
    goto LABEL_46;
  }
  if ( DestinationInterface )
    v24 = *(_DWORD *)(DestinationInterface + 1040);
  else
    v24 = 0;
  if ( *(_DWORD *)(v53 + 24) != v24 )
    goto LABEL_45;
  v25 = NlShimFwLayerDirectClassify((unsigned int)&v49, v13, v53, a2, 0, a7, DestinationInterface, (__int64)&v49);
  v9 = v49;
  if ( !v25 )
    goto LABEL_45;
  WfpNlShimCheckIfPacketAbsorbed(v49, *(_QWORD *)(a2 + 64));
  v23 = 1;
  v8 = (unsigned __int8)v48;
  if ( v9 == 1 )
    v8 = 1;
  v48 = v8;
  if ( v18 && v9 )
  {
    *(_BYTE *)(a7 + 64) = 1;
    NlShimExcludeDestinationForNblChain(a7, *(_QWORD *)(a2 + 64), v20);
  }
  NLShimDereferenceFwLayerCache(&v53);
LABEL_93:
  if ( *(_BYTE *)(a2 + 72) )
  {
    v37 = *(_QWORD **)(a2 + 64);
    v38 = v9;
    v39 = v37;
    if ( v37 )
    {
      do
      {
        v37 = (_QWORD *)*v37;
        v40 = FwppGetvSwitchNblContext(v39);
        if ( v9 != 3 )
        {
          *v39 = 0;
          v10 = v23 == 0;
          v41 = v9;
          v23 = 0;
          if ( v10 )
            v41 = v38;
          v38 = v41;
          if ( v41 != v9 )
          {
            v9 = 1;
            v38 = 1;
          }
        }
        FwppDereferencevSwitchNblContext(v40);
        *((_DWORD *)v39 + 34) &= ~0x800000u;
        NetioDereferenceNetBufferList(v39, 0);
        v39 = v37;
      }
      while ( v37 );
      LOBYTE(v8) = v48;
    }
    v9 = v38;
  }
  else
  {
    FwppDereferencevSwitchNblContext(a7);
    NetioDereferenceNetBufferList(*(_QWORD *)(a2 + 64), 0);
  }
  if ( StorageForClassifyValues )
    WfpShimReturnStorageForClassifyValues(&v55, &v51, v47, &v46);
  if ( v9 == 1 )
    *(_DWORD *)(a7 + 68) = (_BYTE)v8 != 0 ? -1073741790 : -1073741670;
  return v9;
}

```

## disassembly

```asm
0x14016e378  push    rbp
0x14016e37a  push    rbx
0x14016e37b  push    rsi
0x14016e37c  push    rdi
0x14016e37d  push    r12
0x14016e37f  push    r13
0x14016e381  push    r14
0x14016e383  push    r15
0x14016e385  lea     rbp, [rsp-78h]
0x14016e38a  sub     rsp, 178h
0x14016e391  mov     rax, cs:__security_cookie
0x14016e398  xor     rax, rsp
0x14016e39b  mov     [rbp+0B0h+var_48], rax
0x14016e39f  mov     rax, [rbp+0B0h+arg_38]
0x14016e3a6  xor     r13b, r13b
0x14016e3a9  mov     rdi, [rbp+0B0h+arg_30]
0x14016e3b0  xorps   xmm0, xmm0
0x14016e3b3  mov     [rbp+0B0h+var_100], rax
0x14016e3b7  mov     r15d, 1
0x14016e3bd  xor     eax, eax
0x14016e3bf  mov     [rbp+0B0h+var_E0], r9d
0x14016e3c3  mov     [rbp+0B0h+var_7C], rax
0x14016e3c7  mov     ebx, r15d
0x14016e3ca  cmp     [rdi+49h], al
0x14016e3cd  mov     r14, rdx
0x14016e3d0  mov     [rbp+0B0h+var_8C], rax
0x14016e3d4  mov     [rbp+0B0h+var_9C], rax
0x14016e3d8  mov     [rbp+0B0h+var_AC], rax
0x14016e3dc  mov     [rbp+0B0h+var_BC], rax
0x14016e3e0  mov     [rbp+30h], rax
0x14016e3e4  mov     [rbp+20h], rax
0x14016e3e8  mov     [rbp+10h], rax
0x14016e3ec  mov     [rbp+0], rax
0x14016e3f0  mov     [rbp-10h], rax
0x14016e3f4  mov     [rbp+0B0h+var_F0], rax
0x14016e3f8  mov     dword ptr [rbp+0B0h+var_E8], eax
0x14016e3fb  mov     word ptr [rbp+0B0h+var_E8+4], ax
0x14016e3ff  mov     [rbp+0B0h+var_F8], rax
0x14016e403  mov     [rbp+0B0h+var_118], rax
0x14016e407  mov     [rbp+0B0h+var_12E], al
0x14016e40a  mov     dword ptr [rbp+0B0h+var_50], eax
0x14016e40d  mov     eax, r15d
0x14016e410  mov     [rbp+0B0h+var_DC], r8d
0x14016e414  mov     [rbp+0B0h+var_D8], ecx
0x14016e417  mov     [rbp+0B0h+var_124], ebx
0x14016e41a  mov     [rbp+0B0h+var_128], r13d
0x14016e41e  movups  [rbp+0B0h+var_D0], xmm0
0x14016e422  mov     [rbp+0B0h+var_12D], r13b
0x14016e426  mov     [rbp+0B0h+var_12C], r13b
0x14016e42a  movups  [rbp+0B0h+var_70], xmm0
0x14016e42e  movups  [rbp+0B0h+var_60], xmm0
0x14016e432  jnz     short loc_14016E437
0x14016e434  mov     eax, [rdi+0Ch]
0x14016e437  mov     [rbp+0B0h+var_120], eax
0x14016e43a  test    ecx, ecx
0x14016e43c  jnz     short loc_14016E451
0x14016e43e  mov     ecx, 4Ch ; 'L'
0x14016e443  cmp     eax, r15d
0x14016e446  lea     r12d, [rcx-2]
0x14016e44a  cmovnz  r12w, cx
0x14016e44f  jmp     short loc_14016E462
0x14016e451  mov     r12d, 4Bh ; 'K'
0x14016e457  cmp     eax, r15d
0x14016e45a  jz      short loc_14016E462
0x14016e45c  mov     r12d, 4Dh ; 'M'
0x14016e462  cmp     byte ptr [rdx+48h], 0
0x14016e466  mov     rsi, [rdx+40h]
0x14016e46a  jz      loc_14016E513
0x14016e470  test    rsi, rsi
0x14016e473  jz      loc_14016E531
0x14016e479  mov     rcx, rsi
0x14016e47c  call    cs:__imp_FwppGetvSwitchNblContext
0x14016e483  nop     dword ptr [rax+rax+00h]
0x14016e488  xor     ecx, ecx
0x14016e48a  test    rax, rax
0x14016e48d  jnz     short loc_14016E4ED
0x14016e48f  mov     dword ptr [rsp+1B0h+var_168], ecx
0x14016e493  lea     rax, NlShimvSwitchNetBufferListEventNotifyFn
0x14016e49a  mov     [rsp+1B0h+var_170], rax
0x14016e49f  mov     r8d, 0FFFFh
0x14016e4a5  mov     [rsp+1B0h+var_178], rcx
0x14016e4aa  mov     r9, rdi
0x14016e4ad  mov     [rsp+1B0h+var_180], rcx
0x14016e4b2  mov     rdx, rsi
0x14016e4b5  mov     [rsp+1B0h+var_188], rcx
0x14016e4ba  mov     ecx, r15d
0x14016e4bd  mov     [rsp+1B0h+var_190], 2
0x14016e4c6  call    cs:__imp_FwppNetBufferListAssociateContext
0x14016e4cd  nop     dword ptr [rax+rax+00h]
0x14016e4d2  test    rax, rax
0x14016e4d5  jnz     loc_14016EA49
0x14016e4db  mov     rcx, rdi
0x14016e4de  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e4e5  nop     dword ptr [rax+rax+00h]
0x14016e4ea  mov     rax, rdi
0x14016e4ed  mov     rcx, rax
0x14016e4f0  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e4f7  nop     dword ptr [rax+rax+00h]
0x14016e4fc  mov     rcx, rsi
0x14016e4ff  call    cs:__imp_NetioReferenceNetBufferList
0x14016e506  nop     dword ptr [rax+rax+00h]
0x14016e50b  mov     rsi, [rsi]
0x14016e50e  jmp     loc_14016E470
0x14016e513  mov     rcx, rsi
0x14016e516  call    cs:__imp_NetioReferenceNetBufferList
0x14016e51d  nop     dword ptr [rax+rax+00h]
0x14016e522  mov     rcx, rdi
0x14016e525  call    cs:__imp_FwppReferencevSwitchNblContext
0x14016e52c  nop     dword ptr [rax+rax+00h]
0x14016e531  mov     rdx, [rdi+38h]
0x14016e535  xor     al, al
0x14016e537  xor     r15d, r15d
0x14016e53a  mov     [rbp+0B0h+var_130], al
0x14016e53d  xor     r13d, r13d
0x14016e540  xor     esi, esi
0x14016e542  test    rdx, rdx
0x14016e545  jz      short loc_14016E5C3
0x14016e547  cmp     [rdi+49h], al
0x14016e54a  jnz     short loc_14016E5C3
0x14016e54c  mov     r10d, [rdx+0Ch]
0x14016e550  mov     r15d, ebx
0x14016e553  mov     r9d, [rdx+8]
0x14016e557  cmp     r10d, ebx
0x14016e55a  setz    [rbp+0B0h+var_130]
0x14016e55e  test    r9d, r9d
0x14016e561  jz      short loc_14016E580
0x14016e563  mov     r11d, [rdx+4]
0x14016e567  mov     r8, [rdx+10h]
0x14016e56b  mov     eax, r11d
0x14016e56e  imul    eax, esi
0x14016e571  test    [rax+r8+6], r15b
0x14016e576  jz      short loc_14016E580
0x14016e578  add     esi, r15d
0x14016e57b  cmp     esi, r9d
0x14016e57e  jb      short loc_14016E56B
0x14016e580  cmp     esi, r10d
0x14016e583  jnz     short loc_14016E596
0x14016e585  mov     r13d, [rbp+0B0h+var_128]
0x14016e589  xor     ebx, ebx
0x14016e58b  mov     [rdi+44h], ebx
0x14016e58e  mov     r12d, r15d
0x14016e591  jmp     loc_14016EA4C
0x14016e596  mov     rcx, [rdi+88h]
0x14016e59d  mov     r15d, esi
0x14016e5a0  imul    r15d, [rdx+4]
0x14016e5a5  add     r15, [rdx+10h]
0x14016e5a9  movzx   r8d, word ptr [r15+4]
0x14016e5ae  mov     edx, [r15]
0x14016e5b1  call    cs:__imp_FwppvSwitchGetDestinationInterface
0x14016e5b8  nop     dword ptr [rax+rax+00h]
0x14016e5bd  mov     r13, rax
0x14016e5c0  mov     al, [rbp+0B0h+var_130]
0x14016e5c3  cmp     byte ptr [r14+48h], 0
0x14016e5c8  jnz     loc_14016E712
0x14016e5ce  cmp     [rbp+0B0h+var_120], ebx
0x14016e5d1  jz      short loc_14016E5DB
0x14016e5d3  test    al, al
0x14016e5d5  jz      loc_14016E712
0x14016e5db  mov     rax, [rbp+0B0h+var_100]
0x14016e5df  test    rax, rax
0x14016e5e2  jz      loc_14016E712
0x14016e5e8  cmp     qword ptr [rax+0C8h], 0
0x14016e5f0  jz      loc_14016E712
0x14016e5f6  lea     r9, [rbp+0B0h+var_108]
0x14016e5fa  mov     [rbp+0B0h+var_108], 0
0x14016e602  lea     r8, NlShimReferenceFwLayerCache
0x14016e609  mov     edx, ebx
0x14016e60b  mov     rcx, rax
0x14016e60e  call    cs:__imp_NetioFlowRetrieveContext
0x14016e615  nop     dword ptr [rax+rax+00h]
0x14016e61a  test    eax, eax
0x14016e61c  jnz     loc_14016E712
0x14016e622  cmp     [rbp+0B0h+var_108], 0
0x14016e627  jz      loc_14016E712
0x14016e62d  lea     rdx, [rbp+0B0h+var_110]
0x14016e631  mov     [rbp+0B0h+var_110], eax
0x14016e634  movzx   ecx, r12w
0x14016e638  call    cs:__imp_KfdGetLayerCacheEpoch
0x14016e63f  nop     dword ptr [rax+rax+00h]
0x14016e644  mov     rax, [rbp+0B0h+var_108]
0x14016e648  mov     ecx, [rbp+0B0h+var_110]
0x14016e64b  cmp     [rax+58h], ecx
0x14016e64e  jnz     loc_14016E6F4
0x14016e654  test    r13, r13
0x14016e657  jz      short loc_14016E662
0x14016e659  mov     ecx, [r13+410h]
0x14016e660  jmp     short loc_14016E664
0x14016e662  xor     ecx, ecx
0x14016e664  cmp     [rax+18h], ecx
0x14016e667  jnz     loc_14016E6ED
0x14016e66d  lea     rcx, [rbp+0B0h+var_124]
0x14016e671  mov     r9, r14
0x14016e674  mov     [rsp+1B0h+var_178], rcx
0x14016e679  mov     r8, rax
0x14016e67c  mov     [rsp+1B0h+var_180], r13
0x14016e681  movzx   edx, r12w
0x14016e685  mov     [rsp+1B0h+var_188], rdi
0x14016e68a  mov     [rsp+1B0h+var_190], 0
0x14016e693  call    NlShimFwLayerDirectClassify
0x14016e698  mov     ebx, [rbp+0B0h+var_124]
0x14016e69b  test    al, al
0x14016e69d  jz      short loc_14016E6ED
0x14016e69f  mov     rdx, [r14+40h]
0x14016e6a3  mov     ecx, ebx
0x14016e6a5  call    WfpNlShimCheckIfPacketAbsorbed
0x14016e6aa  mov     r13d, [rbp+0B0h+var_128]
0x14016e6ae  mov     r12d, 1
0x14016e6b4  cmp     ebx, r12d
0x14016e6b7  movzx   r13d, r13b
0x14016e6bb  cmovz   r13d, r12d
0x14016e6bf  mov     [rbp+0B0h+var_128], r13d
0x14016e6c3  test    r15, r15
0x14016e6c6  jz      short loc_14016E6DF
0x14016e6c8  test    ebx, ebx
0x14016e6ca  jz      short loc_14016E6DF
0x14016e6cc  mov     [rdi+40h], r12b
0x14016e6d0  mov     r8d, esi
0x14016e6d3  mov     rdx, [r14+40h]
0x14016e6d7  mov     rcx, rdi
0x14016e6da  call    NlShimExcludeDestinationForNblChain
0x14016e6df  lea     rcx, [rbp+0B0h+var_108]
0x14016e6e3  call    NLShimDereferenceFwLayerCache
0x14016e6e8  jmp     loc_14016EA4C
0x14016e6ed  mov     edx, 1
0x14016e6f2  jmp     short loc_14016E6F9
0x14016e6f4  mov     [rax+58h], ecx
0x14016e6f7  mov     edx, ebx
0x14016e6f9  mov     rcx, [rbp+0B0h+var_100]
0x14016e6fd  call    cs:__imp_NetioFlowRemoveContext
0x14016e704  nop     dword ptr [rax+rax+00h]
0x14016e709  lea     rcx, [rbp+0B0h+var_108]
0x14016e70d  call    NLShimDereferenceFwLayerCache
0x14016e712  lea     r9, [rbp+0B0h+var_12D]
0x14016e716  lea     r8, [rbp+0B0h+var_12C]
0x14016e71a  lea     rdx, [rbp+0B0h+var_118]
0x14016e71e  lea     rcx, [rbp+0B0h+var_F8]
0x14016e722  call    WfpShimGetStorageForClassifyValues
0x14016e727  mov     [rbp+0B0h+var_12E], al
0x14016e72a  test    al, al
0x14016e72c  jnz     short loc_14016E740
0x14016e72e  mov     r13d, [rbp+0B0h+var_128]
0x14016e732  mov     r12d, 1
0x14016e738  mov     ebx, r12d
0x14016e73b  jmp     loc_14016EA4C
0x14016e740  mov     [rbp+0B0h+var_124], 0
0x14016e747  mov     [rbp+0B0h+var_12F], 0
0x14016e74b  mov     rax, [rbp+0B0h+var_F8]
0x14016e74f  mov     rdx, r14
0x14016e752  mov     r9d, [rbp+0B0h+var_E0]
0x14016e756  mov     r8d, [rbp+0B0h+var_DC]
0x14016e75a  mov     ecx, [rbp+0B0h+var_D8]
0x14016e75d  mov     [rsp+1B0h+var_140], rax
0x14016e762  lea     rax, [rbp+0B0h+var_C0]
0x14016e766  mov     [rsp+1B0h+var_148], rax
0x14016e76b  lea     rax, [rbp+0B0h+var_B0]
0x14016e76f  mov     [rsp+1B0h+var_150], rax
0x14016e774  lea     rax, [rbp+0B0h+var_A0]
0x14016e778  mov     [rsp+1B0h+var_158], rax
0x14016e77d  lea     rax, [rbp+0B0h+var_90]
0x14016e781  mov     [rsp+1B0h+var_160], rax
0x14016e786  lea     rax, [rbp+0B0h+var_80]
0x14016e78a  mov     [rsp+1B0h+var_168], rax
0x14016e78f  mov     eax, [rbp+0B0h+var_120]
0x14016e792  mov     dword ptr [rsp+1B0h+var_170], eax
0x14016e796  movzx   eax, [rbp+0B0h+arg_28]
0x14016e79d  mov     [rsp+1B0h+var_178], r13
0x14016e7a2  mov     [rsp+1B0h+var_180], rdi
0x14016e7a7  mov     word ptr [rsp+1B0h+var_188], ax
0x14016e7ac  movzx   eax, [rbp+0B0h+arg_20]
0x14016e7b3  mov     word ptr [rsp+1B0h+var_190], ax
0x14016e7b8  call    NlShimMarshalvSwitchFwLayerFields
0x14016e7bd  mov     rcx, [rbp+0B0h+var_118]; void *
0x14016e7c1  xor     edx, edx; Val
0x14016e7c3  mov     dword ptr [rbp+0B0h+var_F0+4], eax
0x14016e7c6  mov     r8d, 2A8h; Size
0x14016e7cc  mov     rax, [rbp+0B0h+var_F8]
0x14016e7d0  mov     [rbp+0B0h+var_E8], rax
0x14016e7d4  mov     word ptr [rbp+0B0h+var_F0], r12w
0x14016e7d9  call    memset
0x14016e7de  mov     r9, [rbp+0B0h+var_118]
0x14016e7e2  mov     rdx, r13
0x14016e7e5  mov     r8b, [rbp+0B0h+var_12F]
0x14016e7e9  mov     rcx, rdi
0x14016e7ec  lea     rax, [r9+270h]
0x14016e7f3  mov     [r9+278h], rax
0x14016e7fa  mov     [rax], rax
0x14016e7fd  call    NlShimSetvSwitchLayerMetadata
0x14016e802  xor     ecx, ecx
0x14016e804  cmp     [r14+48h], cl
0x14016e808  jnz     short loc_14016E836
0x14016e80a  cmp     [rbp+0B0h+var_100], rcx
0x14016e80e  jz      short loc_14016E836
0x14016e810  cmp     [rbp+0B0h+var_120], 1
0x14016e814  jz      short loc_14016E81B
0x14016e816  cmp     [rbp+0B0h+var_130], cl
0x14016e819  jz      short loc_14016E836
0x14016e81b  lea     rax, [rbp+0B0h+var_D0]
0x14016e81f  mov     qword ptr [rbp+0B0h+var_D0+8], rax
0x14016e823  lea     rax, [rbp+0B0h+var_D0]
0x14016e827  mov     qword ptr [rbp+0B0h+var_D0], rax
  ... truncated ...
```
