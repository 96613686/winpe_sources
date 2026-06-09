# Smb2Negotiate_Start

- ea: `0x140052540`
- end: `0x140053044`
- name: `Smb2Negotiate_Start`
- size: `2820`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e700`
- `0x1400297a8`
- `0x1400297fc`
- `0x140029840`
- `0x14002ba84`
- `0x1400372c0`
- `0x140052540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400527ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400527ce`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140052faf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140052faf`
- `rdbss!RxFreeMdl` at `0x140053024`
- `rdbss!RxFreeMdl` at `0x140053024`
- `rdbss!RxAllocateMdl2` at `0x140052f89`
- `rdbss!RxAllocateMdl2` at `0x140052f89`
- `ksecdd!BCryptGenRandom` at `0x140052a55`
- `ksecdd!BCryptGenRandom` at `0x140052a55`
- `mrxsmb!MRxSmbIsRdmaUsageAllowedByLicense` at `0x140052e9f`
- `mrxsmb!MRxSmbIsRdmaUsageAllowedByLicense` at `0x140052e9f`
- `mrxsmb!SubRdrBuildDialectRevisionNegotiateList` at `0x1400526e2`
- `mrxsmb!SubRdrBuildDialectRevisionNegotiateList` at `0x1400526e2`
- `mrxsmb!VctReferenceEndpoint` at `0x14005260f`
- `mrxsmb!VctReferenceEndpoint` at `0x14005260f`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400525f1`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400525f1`
- `mrxsmb!MRxSmbCopyCipherSuiteInfoFromGlobalConfig` at `0x1400525be`
- `mrxsmb!MRxSmbCopyCipherSuiteInfoFromGlobalConfig` at `0x1400525be`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400528b6`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400528b6`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140052565`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140052565`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005295c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005299d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052c1e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052c3f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052d03`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052dae`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052dd7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052df8`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005295c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005299d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052c1e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052c3f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052d03`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052dae`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052dd7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140052df8`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14005300a`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14005300a`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140052fed`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140052fed`

## pseudocode

```c
__int64 __fastcall Smb2Negotiate_Start(__int64 a1)
{
  __int64 CompressionConfigBlock; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  _DWORD *v6; // rcx
  __int64 v7; // r13
  __int64 v8; // r12
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _WORD *v12; // r15
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // rbx
  unsigned int v19; // ecx
  unsigned int i; // r8d
  __int64 v21; // rdx
  bool v22; // r14
  __int64 v23; // rax
  PDEVICE_OBJECT v24; // rcx
  unsigned __int16 v25; // dx
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rsi
  __int64 v30; // r8
  unsigned __int16 v31; // dx
  __int64 v32; // r10
  unsigned __int16 v33; // r8
  _DWORD *v34; // rdx
  unsigned __int16 *v35; // r14
  unsigned __int16 v36; // bp
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // rsi
  __int64 v40; // rsi
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // r12
  unsigned __int16 *v44; // r14
  unsigned __int16 v45; // bp
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // r15
  __int64 ConfigurationBlock; // rax
  int v50; // edx
  __int16 v51; // ax
  int v52; // r8d
  unsigned __int16 v53; // dx
  struct _MDL *Mdl2; // rax
  struct _MDL *v55; // r12
  void *Src; // [rsp+50h] [rbp-58h]
  unsigned __int16 v58; // [rsp+B0h] [rbp+8h]
  unsigned int v59; // [rsp+B8h] [rbp+10h] BYREF
  struct _MDL *v60; // [rsp+C0h] [rbp+18h]
  __int64 v61; // [rsp+C8h] [rbp+20h]

  v59 = 0;
  v60 = 0;
  CompressionConfigBlock = MRxSmbGetCompressionConfigBlock();
  v6 = (_DWORD *)(a1 + 2424);
  v7 = *(_QWORD *)(a1 + 72);
  v61 = CompressionConfigBlock;
  v8 = *(_QWORD *)(v7 + 24);
  v58 = *(_WORD *)(v7 + 128);
  Src = *(void **)(v7 + 136);
  if ( *(_BYTE *)(a1 + 2408) )
  {
    if ( (int)MRxSmbCopyCipherSuiteInfoFromGlobalConfig(v6, 4, a1 + 2440) < 0 )
    {
LABEL_3:
      v9 = -1073741595;
LABEL_116:
      RxFreeMdl(v60);
      return (unsigned int)v9;
    }
  }
  else
  {
    *(_WORD *)(a1 + 2440) = 1;
    *v6 = *(unsigned __int16 *)(v7 + 742);
  }
  v10 = *(_QWORD *)(a1 + 2448);
  if ( v10 )
    VctDereferenceEndpoint(v10);
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL);
  *(_QWORD *)(a1 + 2448) = v11;
  VctReferenceEndpoint(v11, v3, v4, v5);
  SmbCeBuildSmb2Header(a1, a1 + 2488, 64);
  v12 = (_WORD *)(a1 + 2588);
  *(_WORD *)(a1 + 2500) = 0;
  *(_WORD *)(a1 + 2552) = 36;
  *(_BYTE *)(a1 + 2559) = 0;
  if ( *(_BYTE *)(a1 + 2408) )
  {
    if ( *(_WORD *)(v7 + 740) )
    {
      v59 = 1;
      *v12 = *(_WORD *)(v7 + 740);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v14 = *(unsigned __int16 *)(v7 + 740);
        v15 = 26;
LABEL_22:
        WPP_SF_dq(v13->AttachedDevice, v15, WPP_48214901e2dc3d654588515547715784_Traceguids, v14, v7);
      }
    }
    else
    {
      v16 = *(_QWORD *)(a1 + 72);
      v59 = 16;
      v9 = SubRdrBuildDialectRevisionNegotiateList(*(_QWORD *)(v16 + 24), a1 + 2588, &v59);
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_48214901e2dc3d654588515547715784_Traceguids, a1, v9);
        }
        goto LABEL_116;
      }
    }
  }
  else
  {
    v59 = 1;
    v17 = *(unsigned __int16 *)(*(_QWORD *)(v7 + 64) + 8LL);
    *v12 = v17;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v14 = v17;
      v15 = 28;
      goto LABEL_22;
    }
  }
  if ( !*(_WORD *)(v7 + 740) )
  {
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 2448) + 616LL) )
      __int2c();
    v18 = *(_QWORD *)(a1 + 2448);
    *(_QWORD *)(v18 + 616) = ExAllocatePool2(66, 2LL * v59, 1834182478);
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 2448) + 616LL) )
    {
      v9 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
      }
      goto LABEL_116;
    }
    v19 = v59;
    for ( i = 0; i < v59; v19 = v59 )
    {
      v21 = i++;
      *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 2448) + 616LL) + 2 * v21) = *(_WORD *)(a1 + 2 * v21 + 2588);
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 2448) + 624LL) = v19;
  }
  v22 = 1;
  if ( v59 == 1 )
    v22 = *v12 >= 0x311u;
  *(_WORD *)(a1 + 2554) = v59;
  if ( *(_BYTE *)(MRxSmbGetInstanceConfigurationBlock(v8) + 56) )
  {
    v23 = *(_QWORD *)(a1 + 2448);
    *(_WORD *)(a1 + 2556) = 2;
    *(_BYTE *)(v23 + 607) = 1;
  }
  else
  {
    *(_WORD *)(a1 + 2556) = 1;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      WPP_48214901e2dc3d654588515547715784_Traceguids,
      *(unsigned __int8 *)(v8 + 1312),
      *(unsigned __int8 *)(*(_QWORD *)(a1 + 2448) + 607LL));
  }
  *(_OWORD *)(a1 + 2564) = *(_OWORD *)(*(_QWORD *)(a1 + 72) + 684LL);
  if ( *(_BYTE *)(a1 + 2408) )
  {
    *(_DWORD *)(a1 + 2560) = 255;
    if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v24) + 432) )
      *(_DWORD *)(a1 + 2560) &= ~0x80u;
    v25 = *(_WORD *)(a1 + 2440);
    v26 = 0;
    if ( v25 )
    {
      while ( *(_DWORD *)(a1 + 4LL * (unsigned __int16)v26 + 2424) != 1 )
      {
        LOWORD(v26) = v26 + 1;
        if ( (unsigned __int16)v26 >= v25 )
          goto LABEL_49;
      }
    }
    else
    {
LABEL_49:
      if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v26) + 474) )
        *(_DWORD *)(a1 + 2560) &= ~0x40u;
    }
    *(_DWORD *)(v7 + 680) = *(_DWORD *)(a1 + 2560);
  }
  else
  {
    *(_DWORD *)(a1 + 2560) = *(_DWORD *)(v7 + 680);
  }
  *(_BYTE *)(a1 + 2558) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL) + 1312LL);
  v27 = 2 * (unsigned int)*(unsigned __int16 *)(a1 + 2554) + 100;
  if ( v22 )
  {
    if ( ((2 * (unsigned __int8)*(_WORD *)(a1 + 2554) + 100) & 7) != 0 )
    {
      if ( (int)v27 + 7 < (unsigned int)v27 )
        goto LABEL_3;
      v27 = (2 * *(unsigned __int16 *)(a1 + 2554) + 107) & 0xFFFFFFF8;
    }
    *(_DWORD *)(v27 + a1 + 2496) = 2097153;
    *(_WORD *)(v27 + a1 + 2500) = 1;
    if ( BCryptGenRandom(0, (PUCHAR)((unsigned int)v27 + a1 + 2502), 0x20u, 2u) < 0 )
      goto LABEL_3;
    *(_DWORD *)(v27 + a1 + 2488) = 2490369;
    ++*(_WORD *)(a1 + 2584);
    *(_DWORD *)(a1 + 2580) = v27;
    v29 = (unsigned int)v27 + *(unsigned __int16 *)(v27 + a1 + 2490) + 8;
    if ( *(_BYTE *)(a1 + 2408) || *(_WORD *)(v7 + 742) )
    {
      if ( (((_BYTE)v27 + (unsigned __int8)*(_WORD *)(v27 + a1 + 2490) + 8) & 7) != 0 )
      {
        if ( (int)v29 + 7 < (unsigned int)v29 )
          goto LABEL_3;
        v29 = ((_DWORD)v29 + 7) & 0xFFFFFFF8;
      }
      v28 = *(unsigned __int16 *)(a1 + 2440);
      v30 = v29 + a1;
      *(_WORD *)(v29 + a1 + 2496) = v28;
      v31 = 0;
      if ( (_WORD)v28 )
      {
        do
        {
          v28 = v31++;
          *(_WORD *)(v30 + 2 * v28 + 2498) = *(_WORD *)(a1 + 4 * v28 + 2424);
        }
        while ( v31 < *(_WORD *)(v30 + 2496) );
      }
      *(_WORD *)(v29 + a1 + 2488) = 2;
      *(_WORD *)(v29 + a1 + 2490) = 2 * (*(_WORD *)(v30 + 2496) + 1);
      ++*(_WORD *)(a1 + 2584);
      v29 = (unsigned int)*(unsigned __int16 *)(v29 + a1 + 2490) + (_DWORD)v29 + 8;
    }
    v32 = v61;
    if ( (*(_BYTE *)(v61 + 26) & 2) != 0 )
    {
      *(_BYTE *)(*(_QWORD *)(a1 + 2448) + 605LL) = 0;
    }
    else
    {
      if ( (v29 & 7) != 0 )
      {
        if ( (int)v29 + 7 < (unsigned int)v29 )
          goto LABEL_3;
        v29 = ((_DWORD)v29 + 7) & 0xFFFFFFF8;
      }
      v28 = *(unsigned __int16 *)(v61 + 24);
      v33 = 0;
      v34 = (_DWORD *)((unsigned int)v29 + a1 + 2496);
      *v34 = (unsigned __int16)v28;
      v34[1] = 1;
      if ( (_WORD)v28 )
      {
        do
        {
          v28 = v33++;
          *((_WORD *)v34 + v28 + 4) = *(_WORD *)(v32 + 4 * v28);
        }
        while ( v33 < *(_WORD *)v34 );
      }
      *(_WORD *)(v29 + a1 + 2488) = 3;
      *(_WORD *)(v29 + a1 + 2490) = 2 * (*(_WORD *)v34 + 4);
      ++*(_WORD *)(a1 + 2584);
      v29 = *(unsigned __int16 *)(v29 + a1 + 2490) + 8 + (unsigned int)v29;
      *(_BYTE *)(*(_QWORD *)(a1 + 2448) + 605LL) = 1;
    }
    if ( (v29 & 7) != 0 )
    {
      if ( (int)v29 + 7 < (unsigned int)v29 )
        goto LABEL_3;
      v29 = ((_DWORD)v29 + 7) & 0xFFFFFFF8;
    }
    v35 = (unsigned __int16 *)((unsigned int)v29 + a1 + 2496);
    if ( *(_BYTE *)(a1 + 2408) )
    {
      v36 = 0;
      v37 = *(unsigned __int16 *)(MRxSmbGetConfigurationBlock(v28) + 372);
      *v35 = v37;
      if ( (_WORD)v37 )
      {
        do
        {
          v38 = v36++;
          LOWORD(v37) = *(_WORD *)(MRxSmbGetConfigurationBlock(v37) + 4 * v38 + 360);
          v35[v38 + 1] = v37;
        }
        while ( v36 < *v35 );
      }
    }
    else
    {
      *v35 = 1;
      v35[1] = *(_WORD *)(v7 + 744);
    }
    *(_WORD *)(v29 + a1 + 2488) = 8;
    *(_WORD *)(v29 + a1 + 2490) = 2 * (*v35 + 1);
    ++*(_WORD *)(a1 + 2584);
    v39 = *(unsigned __int16 *)(v29 + a1 + 2490) + 8 + (unsigned int)v29;
    if ( (v39 & 7) != 0 )
    {
      if ( (int)v39 + 7 < (unsigned int)v39 )
        goto LABEL_3;
      v39 = ((_DWORD)v39 + 7) & 0xFFFFFFF8;
    }
    memmove((void *)((unsigned int)v39 + a1 + 2496), Src, v58);
    *(_WORD *)(v39 + a1 + 2490) = v58;
    *(_WORD *)(v39 + a1 + 2488) = 5;
    ++*(_WORD *)(a1 + 2584);
    v40 = *(unsigned __int16 *)(v39 + a1 + 2490) + 8 + (unsigned int)v39;
    if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(v41) + 396) && *(_DWORD *)(*(_QWORD *)(a1 + 2448) + 320LL) == 4 )
    {
      if ( (v40 & 7) != 0 )
      {
        if ( (int)v40 + 7 < (unsigned int)v40 )
          goto LABEL_3;
        v40 = ((_DWORD)v40 + 7) & 0xFFFFFFF8;
      }
      *(_DWORD *)(v40 + a1 + 2496) = 1;
      *(_DWORD *)(v40 + a1 + 2488) = 262150;
      ++*(_WORD *)(a1 + 2584);
      LODWORD(v40) = *(unsigned __int16 *)(v40 + a1 + 2490) + v40 + 8;
    }
    if ( (v40 & 7) != 0 )
    {
      if ( (int)v40 + 7 < (unsigned int)v40 )
        goto LABEL_3;
      LODWORD(v40) = (v40 + 7) & 0xFFFFFFF8;
    }
    v43 = (unsigned int)v40;
    v44 = (unsigned __int16 *)((unsigned int)v40 + a1 + 2496);
    *(_DWORD *)(*(_QWORD *)(a1 + 2448) + 612LL) = 0;
    if ( *(_BYTE *)(a1 + 2408) )
    {
      v45 = 0;
      v46 = *(unsigned __int16 *)(MRxSmbGetConfigurationBlock(v42) + 384);
      *v44 = v46;
      if ( (_WORD)v46 )
      {
        do
        {
          v47 = *(unsigned __int16 *)(MRxSmbGetConfigurationBlock(v46) + 4LL * v45 + 376);
          v44[v45 + 4] = v47;
          v48 = *(_QWORD *)(a1 + 2448);
          ConfigurationBlock = MRxSmbGetConfigurationBlock(v47);
          v50 = *(_DWORD *)(v48 + 612);
          v46 = *(unsigned __int16 *)(ConfigurationBlock + 4LL * v45 + 376);
          if ( (v50 & (unsigned int)v46) == 0 )
          {
            v46 = (unsigned int)(v46 - 1);
            *(_DWORD *)(v48 + 612) = v50 | (1 << v46);
          }
          ++v45;
        }
        while ( v45 < *v44 );
        v43 = (unsigned int)v40;
      }
    }
    else
    {
      *v44 = 0;
      v51 = 0;
      do
      {
        v52 = *(_DWORD *)(v7 + 748);
        v53 = v51 + 1;
        if ( _bittest(&v52, (unsigned __int8)v51) )
        {
          v44[(*v44)++ + 4] = v53;
          v52 = *(_DWORD *)(v7 + 748);
        }
        ++v51;
      }
      while ( v53 < 2u );
      *(_DWORD *)(*(_QWORD *)(a1 + 2448) + 612LL) = v52;
    }
    *(_WORD *)(v43 + a1 + 2488) = 7;
    *(_WORD *)(v43 + a1 + 2490) = 2 * (*v44 + 4);
    ++*(_WORD *)(a1 + 2584);
    v27 = (unsigned int)v40 + *(unsigned __int16 *)(v43 + a1 + 2490) + 8;
    if ( *(_WORD *)(a1 + 2LL * *(unsigned __int16 *)(a1 + 2554) + 2586) >= 0x312u
      && *(_BYTE *)(a1 + 2408)
      && (unsigned int)MRxSmbIsRdmaUsageAllowedByLicense() )
    {
      if ( (v27 & 7) != 0 )
      {
        if ( (int)v27 + 7 < (unsigned int)v27 )
          goto LABEL_3;
        v27 = ((_DWORD)v27 + 7) & 0xFFFFFFF8;
      }
      *(_OWORD *)(v27 + a1 + 2496) = 0;
      *(_DWORD *)(v27 + a1 + 2496) = 1;
      *(_DWORD *)(v27 + a1 + 2488) = 1048585;
      ++*(_WORD *)(a1 + 2584);
      LODWORD(v27) = *(unsigned __int16 *)(v27 + a1 + 2490) + v27 + 8;
    }
  }
  Mdl2 = (struct _MDL *)RxAllocateMdl2(a1 + 2488, (unsigned int)v27, 0, 0, 0);
  v60 = Mdl2;
  v55 = Mdl2;
  if ( !Mdl2 )
  {
    v9 = -1073741670;
    goto LABEL_116;
  }
  MmBuildMdlForNonPagedPool(Mdl2);
  v9 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, v55, (unsigned int)v27, 0, 0, 0, 0, 0, 4);
  if ( !v9 )
  {
    v60 = 0;
    v9 = SmbCseSubmitBufferContext(a1 + 1024);
  }
  if ( v9 < 0 )
    goto LABEL_116;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140052540  mov     rax, rsp
0x140052543  push    rbx
0x140052544  push    rbp
0x140052545  push    rsi
0x140052546  push    rdi
0x140052547  push    r12
0x140052549  push    r13
0x14005254b  push    r14
0x14005254d  push    r15
0x14005254f  sub     rsp, 68h
0x140052553  xor     r14d, r14d
0x140052556  mov     rdi, rcx
0x140052559  mov     [rax+10h], r14d
0x14005255d  mov     [rsp+0A8h+arg_10], r14
0x140052565  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x14005256c  nop     dword ptr [rax+rax+00h]
0x140052571  lea     rcx, [rdi+978h]
0x140052578  mov     r13, [rdi+48h]
0x14005257c  lea     ebx, [r14+1]
0x140052580  mov     [rsp+0A8h+arg_18], rax
0x140052588  movzx   eax, word ptr [r13+80h]
0x140052590  mov     r12, [r13+18h]
0x140052594  mov     [rsp+0A8h+arg_0], ax
0x14005259c  mov     rax, [r13+88h]
0x1400525a3  mov     [rsp+0A8h+Src], rax
0x1400525a8  lea     rax, [rdi+988h]
0x1400525af  cmp     [rdi+968h], r14b
0x1400525b6  jz      short loc_1400525D8
0x1400525b8  lea     edx, [rbx+3]
0x1400525bb  mov     r8, rax
0x1400525be  call    cs:__imp_MRxSmbCopyCipherSuiteInfoFromGlobalConfig
0x1400525c5  nop     dword ptr [rax+rax+00h]
0x1400525ca  test    eax, eax
0x1400525cc  jns     short loc_1400525E5
0x1400525ce  mov     ebx, 0C00000E5h
0x1400525d3  jmp     loc_14005301C
0x1400525d8  mov     [rax], bx
0x1400525db  movzx   eax, word ptr [r13+2E6h]
0x1400525e3  mov     [rcx], eax
0x1400525e5  mov     rcx, [rdi+990h]
0x1400525ec  test    rcx, rcx
0x1400525ef  jz      short loc_1400525FD
0x1400525f1  call    cs:__imp_VctDereferenceEndpoint
0x1400525f8  nop     dword ptr [rax+rax+00h]
0x1400525fd  mov     rax, [rdi+60h]
0x140052601  mov     rcx, [rax+188h]
0x140052608  mov     [rdi+990h], rcx
0x14005260f  call    cs:__imp_VctReferenceEndpoint
0x140052616  nop     dword ptr [rax+rax+00h]
0x14005261b  lea     rdx, [rdi+9B8h]
0x140052622  mov     r8d, 40h ; '@'
0x140052628  mov     rcx, rdi
0x14005262b  call    SmbCeBuildSmb2Header
0x140052630  lea     r15, [rdi+0A1Ch]
0x140052637  mov     [rdi+9C4h], r14w
0x14005263f  lea     rbp, WPP_48214901e2dc3d654588515547715784_Traceguids
0x140052646  mov     word ptr [rdi+9F8h], 24h ; '$'
0x14005264f  lea     rsi, WPP_GLOBAL_Control
0x140052656  mov     [rdi+9FFh], r14b
0x14005265d  cmp     [rdi+968h], r14b
0x140052664  jz      loc_140052747
0x14005266a  cmp     [r13+2E4h], r14w
0x140052672  jz      short loc_1400526C4
0x140052674  mov     [rsp+0A8h+arg_8], ebx
0x14005267b  movzx   eax, word ptr [r13+2E4h]
0x140052683  mov     [r15], ax
0x140052687  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005268e  cmp     rcx, rsi
0x140052691  jz      loc_140052792
0x140052697  mov     eax, [rcx+2Ch]
0x14005269a  mov     r8d, 4
0x1400526a0  test    r8b, al
0x1400526a3  jz      loc_140052792
0x1400526a9  cmp     [rcx+29h], r8b
0x1400526ad  jb      loc_140052792
0x1400526b3  movzx   r9d, word ptr [r13+2E4h]
0x1400526bb  lea     edx, [r8+16h]
0x1400526bf  jmp     loc_140052781
0x1400526c4  mov     rcx, [rdi+48h]
0x1400526c8  lea     r8, [rsp+0A8h+arg_8]
0x1400526d0  mov     [rsp+0A8h+arg_8], 10h
0x1400526db  mov     rdx, r15
0x1400526de  mov     rcx, [rcx+18h]
0x1400526e2  call    cs:__imp_SubRdrBuildDialectRevisionNegotiateList
0x1400526e9  nop     dword ptr [rax+rax+00h]
0x1400526ee  mov     ebx, eax
0x1400526f0  test    eax, eax
0x1400526f2  jns     loc_140052792
0x1400526f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400526ff  lea     rsi, WPP_GLOBAL_Control
0x140052706  cmp     rcx, rsi
0x140052709  jz      loc_14005301C
0x14005270f  mov     edx, [rcx+2Ch]
0x140052712  mov     eax, 1
0x140052717  test    al, dl
0x140052719  jz      loc_14005301C
0x14005271f  cmp     [rcx+29h], al
0x140052722  jb      loc_14005301C
0x140052728  mov     rcx, [rcx+18h]
0x14005272c  lea     edx, [rax+1Ah]
0x14005272f  mov     r9, rdi
0x140052732  mov     dword ptr [rsp+0A8h+var_88], ebx
0x140052736  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14005273d  call    WPP_SF_qD
0x140052742  jmp     loc_14005301C
0x140052747  mov     [rsp+0A8h+arg_8], ebx
0x14005274e  mov     rax, [r13+40h]
0x140052752  movzx   edx, word ptr [rax+8]
0x140052756  mov     [r15], dx
0x14005275a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052761  cmp     rcx, rsi
0x140052764  jz      short loc_140052792
0x140052766  mov     eax, [rcx+2Ch]
0x140052769  mov     r8d, 4
0x14005276f  test    r8b, al
0x140052772  jz      short loc_140052792
0x140052774  cmp     [rcx+29h], r8b
0x140052778  jb      short loc_140052792
0x14005277a  mov     r9d, edx
0x14005277d  lea     edx, [r8+18h]
0x140052781  mov     rcx, [rcx+18h]
0x140052785  mov     r8, rbp
0x140052788  mov     [rsp+0A8h+var_88], r13
0x14005278d  call    WPP_SF_dq
0x140052792  cmp     r14w, [r13+2E4h]
0x14005279a  jnz     loc_14005287F
0x1400527a0  mov     rax, [rdi+990h]
0x1400527a7  cmp     [rax+268h], r14
0x1400527ae  jz      short loc_1400527B2
0x1400527b0  int     2Ch; Windows NT - assertion failure
0x1400527b2  mov     edx, [rsp+0A8h+arg_8]
0x1400527b9  mov     ecx, 42h ; 'B'
0x1400527be  mov     rbx, [rdi+990h]
0x1400527c5  add     rdx, rdx
0x1400527c8  mov     r8d, 6D53674Eh
0x1400527ce  call    cs:__imp_ExAllocatePool2
0x1400527d5  nop     dword ptr [rax+rax+00h]
0x1400527da  mov     [rbx+268h], rax
0x1400527e1  mov     rax, [rdi+990h]
0x1400527e8  cmp     [rax+268h], r14
0x1400527ef  jnz     short loc_140052838
0x1400527f1  mov     ebx, 0C000009Ah
0x1400527f6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400527fd  cmp     rcx, rsi
0x140052800  jz      loc_14005301C
0x140052806  mov     eax, [rcx+2Ch]
0x140052809  test    al, 1
0x14005280b  jz      loc_14005301C
0x140052811  mov     edx, 4
0x140052816  cmp     [rcx+29h], dl
0x140052819  jb      loc_14005301C
0x14005281f  mov     rcx, [rcx+18h]
0x140052823  mov     edx, 1Dh
0x140052828  mov     r9, rdi
0x14005282b  mov     r8, rbp
0x14005282e  call    WPP_SF_q
0x140052833  jmp     loc_14005301C
0x140052838  mov     ecx, [rsp+0A8h+arg_8]
0x14005283f  mov     r8d, r14d
0x140052842  test    ecx, ecx
0x140052844  jz      short loc_140052872
0x140052846  mov     rax, [rdi+990h]
0x14005284d  mov     edx, r8d
0x140052850  inc     r8d
0x140052853  mov     rcx, [rax+268h]
0x14005285a  movzx   eax, word ptr [rdi+rdx*2+0A1Ch]
0x140052862  mov     [rcx+rdx*2], ax
0x140052866  mov     ecx, [rsp+0A8h+arg_8]
0x14005286d  cmp     r8d, ecx
0x140052870  jb      short loc_140052846
0x140052872  mov     rax, [rdi+990h]
0x140052879  mov     [rax+270h], ecx
0x14005287f  mov     ebx, 1
0x140052884  mov     r14d, ebx
0x140052887  cmp     [rsp+0A8h+arg_8], ebx
0x14005288e  jnz     short loc_1400528A4
0x140052890  xor     ebx, ebx
0x140052892  mov     ecx, 311h
0x140052897  cmp     [r15], cx
0x14005289b  cmovb   r14d, ebx
0x14005289f  mov     ebx, 1
0x1400528a4  movzx   eax, word ptr [rsp+0A8h+arg_8]
0x1400528ac  mov     rcx, r12
0x1400528af  mov     [rdi+9FAh], ax
0x1400528b6  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x1400528bd  nop     dword ptr [rax+rax+00h]
0x1400528c2  xor     r15d, r15d
0x1400528c5  mov     cl, [rax+38h]
0x1400528c8  test    cl, cl
0x1400528ca  jz      short loc_1400528E4
0x1400528cc  mov     rax, [rdi+990h]
0x1400528d3  mov     word ptr [rdi+9FCh], 2
0x1400528dc  mov     [rax+25Fh], bl
0x1400528e2  jmp     short loc_1400528EB
0x1400528e4  mov     [rdi+9FCh], bx
0x1400528eb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400528f2  cmp     rcx, rsi
0x1400528f5  jz      short loc_140052936
0x1400528f7  mov     eax, [rcx+2Ch]
0x1400528fa  mov     edx, 4
0x1400528ff  test    dl, al
0x140052901  jz      short loc_140052936
0x140052903  cmp     [rcx+29h], dl
0x140052906  jb      short loc_140052936
0x140052908  mov     rax, [rdi+990h]
0x14005290f  mov     edx, 1Eh
0x140052914  movzx   r9d, byte ptr [r12+520h]
0x14005291d  mov     rcx, [rcx+18h]
0x140052921  movzx   r8d, byte ptr [rax+25Fh]
0x140052929  mov     dword ptr [rsp+0A8h+var_88], r8d
0x14005292e  mov     r8, rbp
0x140052931  call    WPP_SF_DD
0x140052936  mov     rax, [rdi+48h]
0x14005293a  movups  xmm0, xmmword ptr [rax+2ACh]
0x140052941  movdqu  xmmword ptr [rdi+0A04h], xmm0
0x140052949  cmp     [rdi+968h], r15b
0x140052950  jz      short loc_1400529C8
0x140052952  mov     dword ptr [rdi+0A00h], 0FFh
0x14005295c  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140052963  nop     dword ptr [rax+rax+00h]
0x140052968  cmp     [rax+1B0h], r15b
0x14005296f  jz      short loc_140052979
0x140052971  btr     dword ptr [rdi+0A00h], 7
0x140052979  movzx   edx, word ptr [rdi+988h]
0x140052980  mov     ecx, r15d
0x140052983  cmp     r15w, dx
0x140052987  jnb     short loc_14005299D
0x140052989  movzx   eax, cx
0x14005298c  cmp     [rdi+rax*4+978h], ebx
0x140052993  jz      short loc_1400529B9
0x140052995  add     cx, bx
0x140052998  cmp     cx, dx
0x14005299b  jb      short loc_140052989
0x14005299d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400529a4  nop     dword ptr [rax+rax+00h]
0x1400529a9  cmp     [rax+1DAh], r15b
0x1400529b0  jz      short loc_1400529B9
0x1400529b2  and     dword ptr [rdi+0A00h], 0FFFFFFBFh
0x1400529b9  mov     eax, [rdi+0A00h]
0x1400529bf  mov     [r13+2A8h], eax
0x1400529c6  jmp     short loc_1400529D5
0x1400529c8  mov     eax, [r13+2A8h]
0x1400529cf  mov     [rdi+0A00h], eax
0x1400529d5  mov     rax, [rdi+48h]
0x1400529d9  mov     rcx, [rax+18h]
0x1400529dd  mov     al, [rcx+520h]
0x1400529e3  mov     [rdi+9FEh], al
0x1400529e9  movzx   eax, word ptr [rdi+9FAh]
0x1400529f0  lea     ebx, ds:64h[rax*2]
0x1400529f7  test    r14b, r14b
0x1400529fa  jz      loc_140052F6F
0x140052a00  mov     eax, ebx
0x140052a02  mov     r14d, 7
0x140052a08  and     eax, r14d
0x140052a0b  mov     ebp, 0FFFFFFF8h
0x140052a10  test    al, al
0x140052a12  jz      short loc_140052A23
0x140052a14  lea     eax, [rbx+7]
0x140052a17  cmp     eax, ebx
0x140052a19  jb      loc_1400525CE
0x140052a1f  mov     ebx, eax
0x140052a21  and     ebx, ebp
0x140052a23  mov     r12d, 1
0x140052a29  mov     dword ptr [rbx+rdi+9C0h], 200001h
0x140052a34  mov     esi, ebx
0x140052a36  lea     rdx, [rdi+9C6h]
0x140052a3d  add     rdx, rsi; pbBuffer
0x140052a40  mov     [rbx+rdi+9C4h], r12w
0x140052a49  xor     ecx, ecx; hAlgorithm
0x140052a4b  lea     r8d, [r12+1Fh]; cbBuffer
0x140052a50  lea     r9d, [r12+1]; dwFlags
0x140052a55  call    cs:__imp_BCryptGenRandom
0x140052a5c  nop     dword ptr [rax+rax+00h]
0x140052a61  test    eax, eax
0x140052a63  js      loc_1400525CE
0x140052a69  mov     dword ptr [rbx+rdi+9B8h], 260001h
0x140052a74  add     [rdi+0A18h], r12w
0x140052a7c  mov     [rdi+0A14h], ebx
0x140052a82  movzx   esi, word ptr [rbx+rdi+9BAh]
0x140052a8a  add     esi, 8
0x140052a8d  add     esi, ebx
0x140052a8f  cmp     [rdi+968h], r15b
0x140052a96  jnz     short loc_140052AA6
0x140052a98  cmp     [r13+2E6h], r15w
0x140052aa0  jz      loc_140052B32
0x140052aa6  mov     eax, esi
0x140052aa8  and     eax, r14d
0x140052aab  test    al, al
0x140052aad  jz      short loc_140052ABE
0x140052aaf  lea     eax, [rsi+7]
0x140052ab2  cmp     eax, esi
0x140052ab4  jb      loc_1400525CE
0x140052aba  mov     esi, eax
0x140052abc  and     esi, ebp
0x140052abe  movzx   ecx, word ptr [rdi+988h]
0x140052ac5  lea     r8, [rsi+rdi]
0x140052ac9  mov     [r8+9C0h], cx
0x140052ad1  mov     edx, r15d
0x140052ad4  cmp     r15w, cx
0x140052ad8  jnb     short loc_140052AFC
  ... truncated ...
```
