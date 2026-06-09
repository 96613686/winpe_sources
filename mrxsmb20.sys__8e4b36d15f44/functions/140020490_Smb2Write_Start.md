# Smb2Write_Start

- ea: `0x140020490`
- end: `0x1400218ce`
- name: `Smb2Write_Start`
- size: `5182`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b940`
- `0x14000e700`
- `0x14001fd00`
- `0x140020490`
- `0x140028950`
- `0x1400297fc`
- `0x14002a1dc`
- `0x14002a6a8`
- `0x14002e258`
- `0x140030d24`
- `0x140030d4c`
- `0x140033234`
- `0x140036880`
- `0x140036ab4`
- `0x140036bac`
- `0x1400372c0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021733`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021733`
- `ntoskrnl!MmMdlPageContentsState` at `0x140020768`
- `ntoskrnl!MmMdlPageContentsState` at `0x140020768`
- `ntoskrnl!ExAllocatePool2` at `0x140020ec4`
- `ntoskrnl!ExAllocatePool2` at `0x140020ec4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002080d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140021488`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400214c2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002080d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140021488`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400214c2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400212dd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140021389`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400212dd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140021389`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400213be`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400213be`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x14002170c`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x14002170c`
- `rdbss!RxFreeMdl` at `0x140020faa`
- `rdbss!RxFreeMdl` at `0x140020fb8`
- `rdbss!RxFreeMdl` at `0x1400212ba`
- `rdbss!RxFreeMdl` at `0x1400212c9`
- `rdbss!RxFreeMdl` at `0x1400216df`
- `rdbss!RxFreeMdl` at `0x1400216ee`
- `rdbss!RxFreeMdl` at `0x140020faa`
- `rdbss!RxFreeMdl` at `0x140020fb8`
- `rdbss!RxFreeMdl` at `0x1400212ba`
- `rdbss!RxFreeMdl` at `0x1400212c9`
- `rdbss!RxFreeMdl` at `0x1400216df`
- `rdbss!RxFreeMdl` at `0x1400216ee`
- `rdbss!RxAllocateMdl2` at `0x14002129f`
- `rdbss!RxAllocateMdl2` at `0x140021335`
- `rdbss!RxAllocateMdl2` at `0x14002135d`
- `rdbss!RxAllocateMdl2` at `0x14002129f`
- `rdbss!RxAllocateMdl2` at `0x140021335`
- `rdbss!RxAllocateMdl2` at `0x14002135d`
- `rdbss!RxLowIoGetBufferAddress` at `0x14002087d`
- `rdbss!RxLowIoGetBufferAddress` at `0x14002087d`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x140020509`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x140020be9`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x140020509`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x140020be9`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x1400208d9`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x1400208d9`
- `mrxsmb!RDR_PERF_INIT` at `0x14002176e`
- `mrxsmb!RDR_PERF_INIT` at `0x14002176e`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x140020a73`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x140020a73`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x140020e63`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x140020e63`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x1400209dc`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x1400209dc`
- `mrxsmb!RDR_PERF_ENTER` at `0x140020522`
- `mrxsmb!RDR_PERF_ENTER` at `0x140020b8a`
- `mrxsmb!RDR_PERF_ENTER` at `0x140020522`
- `mrxsmb!RDR_PERF_ENTER` at `0x140020b8a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400205dd`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400205f3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140020c07`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140020c1a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400205dd`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400205f3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140020c07`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140020c1a`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140021812`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140021812`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140021428`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140021605`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140021428`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140021605`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140020ad7`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140020b1a`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140020ad7`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140020b1a`
- `mrxsmb!SmbCryptoGetCryptoKeyAuthTagSize` at `0x140020da6`
- `mrxsmb!SmbCryptoGetCryptoKeyAuthTagSize` at `0x140020da6`
- `mrxsmb!SmbCryptoEncryptRdmaPayload` at `0x140021506`
- `mrxsmb!SmbCryptoEncryptRdmaPayload` at `0x140021506`
- `mrxsmb!SmbCseSubmitRdmaDirectWrite` at `0x1400217bf`
- `mrxsmb!SmbCseSubmitRdmaDirectWrite` at `0x1400217bf`
- `mrxsmb!SmbCryptoGetCryptoKeyNonceSize` at `0x140020d7d`
- `mrxsmb!SmbCryptoGetCryptoKeyNonceSize` at `0x140020d7d`

## pseudocode

```c
__int64 __fastcall Smb2Write_Start(__int64 a1)
{
  __int64 v1; // r13
  unsigned int v2; // r15d
  __int64 v3; // rdi
  __int64 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  _DWORD *v9; // r12
  __int64 v10; // rcx
  char v11; // al
  __int64 v12; // rdx
  char v13; // r14
  __int64 v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned int *v18; // r9
  _QWORD *v19; // r8
  _QWORD *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // r8
  _DWORD *v24; // rcx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  __int64 v27; // rsi
  __int64 v28; // r15
  __int64 v29; // rbx
  unsigned int v30; // edx
  unsigned int v31; // edi
  unsigned int i; // ecx
  __int64 v33; // rax
  unsigned int v34; // eax
  _QWORD *v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rcx
  char *v38; // rbx
  char *v39; // rax
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  _QWORD *v42; // r9
  char *BufferAddress; // r15
  __int64 v45; // r14
  __int64 SmbBuffer; // rax
  char *v47; // r14
  bool v48; // zf
  __int64 j; // rsi
  unsigned int v50; // ebx
  _QWORD *v51; // r15
  char v52; // cl
  unsigned int v53; // eax
  ULONG v54; // r12d
  unsigned int v55; // eax
  _QWORD *v56; // rdi
  int v57; // esi
  int v58; // ebx
  char v59; // al
  __int64 v60; // rdx
  int v61; // ecx
  ULONG v62; // ebx
  USHORT v63; // bx
  struct _MDL *v64; // r14
  __int64 v65; // r13
  struct _MDL *v66; // rax
  char v67; // r15
  __int64 v68; // rcx
  __int64 v69; // rsi
  __int64 v70; // rcx
  unsigned int v71; // r12d
  __int64 v72; // rcx
  __int64 ConfigurationBlock; // rax
  __int64 v74; // rdx
  unsigned int v75; // edi
  __int64 v76; // r8
  int v77; // ecx
  ULONG v78; // ebx
  ULONG v79; // r15d
  __int64 v80; // rsi
  ULONG v81; // eax
  unsigned int v82; // edi
  __int64 v83; // r12
  ULONG CryptoKeyNonceSize; // eax
  NTSTATUS v85; // ebx
  ULONG CryptoKeyAuthTagSize; // ecx
  int v87; // esi
  __int64 v88; // rbx
  __int64 ImplicitExchangeBuffer; // rax
  char *v90; // r13
  __int64 Pool2; // rax
  struct _MDL *v92; // rdi
  char *v93; // rbx
  ULONG v94; // r13d
  unsigned int v95; // r14d
  __int64 v96; // rax
  char *v97; // rdi
  __int64 v98; // rsi
  unsigned __int16 v99; // cx
  char *v100; // rdi
  USHORT v101; // dx
  __int16 v102; // cx
  USHORT v103; // cx
  __int16 v104; // ax
  __int64 v105; // r15
  unsigned int v106; // r8d
  unsigned int v107; // r10d
  int v108; // edi
  __int64 v109; // r12
  int v110; // r11d
  __int64 v111; // r13
  __int64 v112; // rax
  unsigned int v113; // r9d
  __int64 *v114; // rdx
  int v115; // ecx
  __int64 v116; // rax
  int v117; // edx
  unsigned int v118; // edx
  int v119; // ecx
  __int64 v120; // rax
  unsigned int v121; // ecx
  int v122; // eax
  struct _MDL *Mdl2; // rax
  struct _MDL *v124; // rcx
  _DWORD *v125; // rbx
  __int64 v126; // rcx
  struct _MDL *v127; // rax
  unsigned int v128; // ecx
  __int64 v129; // r9
  int v130; // eax
  PVOID MappedSystemVa; // rbx
  PVOID v132; // rax
  PDEVICE_OBJECT v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // r8
  __int64 v136; // r14
  __int64 v137; // rcx
  int v138; // edi
  char v139; // si
  ULONG Priority[2]; // [rsp+28h] [rbp-D8h]
  __int64 v141; // [rsp+38h] [rbp-C8h]
  int v142; // [rsp+40h] [rbp-C0h]
  USHORT v143; // [rsp+50h] [rbp-B0h]
  USHORT v144; // [rsp+54h] [rbp-ACh] BYREF
  USHORT pusResult[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v146; // [rsp+5Ch] [rbp-A4h]
  USHORT v147[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v148; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG Length; // [rsp+68h] [rbp-98h]
  unsigned int v150; // [rsp+6Ch] [rbp-94h]
  USHORT v151[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v152; // [rsp+74h] [rbp-8Ch]
  int v153; // [rsp+78h] [rbp-88h]
  unsigned int v154; // [rsp+7Ch] [rbp-84h]
  int v155; // [rsp+80h] [rbp-80h]
  int v156; // [rsp+84h] [rbp-7Ch]
  char *v157; // [rsp+88h] [rbp-78h]
  int v158; // [rsp+90h] [rbp-70h]
  __int64 v159; // [rsp+98h] [rbp-68h]
  char *v160; // [rsp+A0h] [rbp-60h]
  int v161; // [rsp+A8h] [rbp-58h]
  int v162; // [rsp+ACh] [rbp-54h] BYREF
  ULONG pulResult; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v164; // [rsp+B4h] [rbp-4Ch]
  __int64 v165; // [rsp+B8h] [rbp-48h]
  __int64 SrvRdmaRegistrationForIo; // [rsp+C0h] [rbp-40h]
  int v167; // [rsp+C8h] [rbp-38h]
  int v168; // [rsp+CCh] [rbp-34h]
  __int64 v169; // [rsp+D0h] [rbp-30h]
  PMDL SourceMdl; // [rsp+D8h] [rbp-28h]
  __int64 v171; // [rsp+E0h] [rbp-20h]
  __int64 v172; // [rsp+E8h] [rbp-18h]
  __int64 v173; // [rsp+F0h] [rbp-10h]
  __int64 v174; // [rsp+F8h] [rbp-8h]
  __int64 v175; // [rsp+100h] [rbp+0h]
  __int64 v176; // [rsp+108h] [rbp+8h]
  __int128 v177; // [rsp+118h] [rbp+18h]
  char v179; // [rsp+188h] [rbp+88h]
  char v180; // [rsp+188h] [rbp+88h]
  __int64 v181; // [rsp+190h] [rbp+90h]
  bool v182; // [rsp+190h] [rbp+90h]
  char v183; // [rsp+198h] [rbp+98h]

  v1 = *(_QWORD *)(a1 + 48);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 96);
  v5 = *(__int64 **)(a1 + 2496);
  v6 = *(_QWORD *)(a1 + 88);
  v7 = *(_QWORD *)(v1 + 72);
  v179 = 0;
  SrvRdmaRegistrationForIo = 0;
  v8 = *(_QWORD *)(v7 + 48);
  v148 = 0;
  v9 = *(_DWORD **)(v3 + 392);
  v162 = 0;
  v151[0] = 0;
  v10 = *(_QWORD *)(v6 + 424);
  v174 = v8;
  v177 = 0;
  v11 = MRxSmbDetermineDdpSecurity(v10);
  LOBYTE(v12) = 15;
  v13 = v11;
  RDR_PERF_ENTER(a1 + 512, v12);
  if ( v5 )
  {
    v15 = *(_DWORD *)(a1 + 2520);
    v16 = 0;
    v150 = 0;
    if ( v15 )
    {
      do
      {
        v17 = v16++;
        v2 += HIDWORD(v5[2 * v17 + 1]);
      }
      while ( v16 < v15 );
      v150 = v2;
    }
    v14 = *v5;
    v18 = (unsigned int *)(v1 + 568);
    v172 = *v5;
    v19 = (_QWORD *)(v1 + 560);
  }
  else
  {
    v19 = (_QWORD *)(v1 + 560);
    v18 = (unsigned int *)(v1 + 568);
    v2 = *(_DWORD *)(v1 + 568);
    v172 = *(_QWORD *)(v1 + 560);
    v150 = v2;
  }
  v20 = (_QWORD *)(a1 + 56);
  if ( ((unsigned int)(v9[80] - 2) > 1
     || *v20
     || (*(_DWORD *)(a1 + 68) & 0x1000800) != 0
     || (SrvRdmaRegistrationForIo = Smb2FindSrvRdmaRegistrationForIo(v174, v3, *v19, *v18)) == 0)
    && *(_DWORD *)(MRxSmbGetConfigurationBlock(v14) + 4)
    && v2 >= *(_DWORD *)(MRxSmbGetConfigurationBlock(v21) + 4)
    && (unsigned int)(v9[80] - 2) <= 1
    && !*v20 )
  {
    v22 = *(_QWORD *)(a1 + 72);
    v23 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL);
    v24 = (_DWORD *)(v22 + 748);
    if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 && (*v24 & 1) == 0 && v13 )
    {
      v25 = *(_DWORD *)(v22 + 584);
      if ( v25 != 144 * (v25 / 0x90) )
        goto LABEL_29;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
      {
        McTemplateK0hzr0_EtwWriteTransfer(
          v25,
          (unsigned int)RdmaWithEncryption,
          v23,
          *(_WORD *)(v23 + 96) >> 1,
          *(_QWORD *)(v23 + 104));
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 584));
        goto LABEL_29;
      }
LABEL_27:
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 584));
      goto LABEL_29;
    }
    if ( (*(_DWORD *)(a1 + 68) & 0x800) != 0 && (*v24 & 2) == 0 && v13 )
    {
      v26 = *(_DWORD *)(v22 + 584);
      if ( v26 != 144 * (v26 / 0x90) )
        goto LABEL_29;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
        McTemplateK0hzr0_EtwWriteTransfer(
          v26,
          (unsigned int)RdmaWithSigning,
          v23,
          *(_WORD *)(v23 + 96) >> 1,
          *(_QWORD *)(v23 + 104));
      goto LABEL_27;
    }
    v179 = 1;
  }
LABEL_29:
  v27 = *(_QWORD *)(a1 + 48);
  v28 = *(_QWORD *)(*(_QWORD *)(v27 + 64) + 56LL);
  v181 = v28;
  v29 = *(_QWORD *)(a1 + 2488);
  if ( v29 )
  {
    v30 = *(_DWORD *)(a1 + 2520);
    v31 = 0;
    if ( v30 )
    {
      for ( i = 0; i < v30; ++i )
      {
        v33 = i;
        v31 += *(_DWORD *)(16 * v33 + *(_QWORD *)(a1 + 2496) + 12);
      }
    }
  }
  else
  {
    v31 = *(_DWORD *)(v27 + 568);
    v29 = *(_QWORD *)(v27 + 544);
  }
  v34 = MmMdlPageContentsState(v29, 2);
  v35 = (_QWORD *)a1;
  v36 = v34;
  if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 && v13 && (v179 || v34 != 1)
    || (*(_DWORD *)(a1 + 68) & 0x800) != 0 && v13 && v34 != 1
    || (unsigned int)(*(_DWORD *)(v28 + 48) - 1) <= 1 )
  {
    v37 = *(_QWORD *)(a1 + 2488);
    v38 = 0;
    if ( v37
      && v31
      && ((*(_BYTE *)(v37 + 10) & 5) == 0
        ? (v39 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v37, 0, MmCached, 0, 0, 0x40000010u),
           v35 = (_QWORD *)a1,
           v38 = v39)
        : (v38 = *(char **)(v37 + 24)),
          !v38) )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 3221225626LL;
      }
      v41 = 14;
    }
    else
    {
      BufferAddress = 0;
      if ( !v35[311] && v31 )
      {
        BufferAddress = (char *)RxLowIoGetBufferAddress((PRX_CONTEXT)v27);
        if ( !BufferAddress )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return 3221225626LL;
          }
          v42 = (_QWORD *)a1;
          v41 = 15;
          goto LABEL_55;
        }
        v35 = (_QWORD *)a1;
      }
      v45 = v35[130];
      if ( v45
        || (SmbBuffer = SmbMmAllocateSmbBuffer(v31, 1834185559),
            v35 = (_QWORD *)a1,
            v45 = SmbBuffer,
            (*(_QWORD *)(a1 + 1040) = SmbBuffer) != 0) )
      {
        v47 = (char *)(v45 & 0xFFFFFFFFFFFFFFF8uLL);
        v35[128] = 0;
        v48 = v35[311] == 0;
        v35[129] = v47;
        if ( !v48 )
          BufferAddress = &v38[*(unsigned int *)(v35[312] + 8LL)];
        if ( *(_DWORD *)(v181 + 48) == 2 )
        {
          for ( j = 0; (unsigned int)j < v31; j = (unsigned int)(j + 0x100000) )
          {
            v50 = v31 - j;
            if ( v31 - (unsigned int)j > 0x100000 )
              v50 = 0x100000;
            HviEnterKernelAperture(v37, v36);
            memmove(&v47[j], &BufferAddress[j], v50);
            HviLeaveKernelAperture();
          }
        }
        else
        {
          memmove(v47, BufferAddress, v31);
        }
        goto LABEL_80;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 3221225626LL;
      }
      v41 = 16;
    }
    v42 = v35;
LABEL_55:
    WPP_SF_q(v40->AttachedDevice, v41, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, v42);
    return 3221225626LL;
  }
  *(_QWORD *)(a1 + 1032) = 0;
  *(_QWORD *)(a1 + 1024) = v29;
LABEL_80:
  v51 = (_QWORD *)a1;
  SmbCeQueryOptimalBufferSize(*(_QWORD *)(a1 + 96), &v148, 0, 0);
  v52 = v179;
  if ( v179 || v9[80] != 2 )
  {
    v53 = v148;
  }
  else
  {
    v53 = v148;
    if ( v148 >= v9[28] )
    {
      v53 = v9[28];
      v148 = v53;
    }
    v52 = 0;
  }
  if ( v53 < 0x10000 )
  {
    v53 = 0x10000;
    v148 = 0x10000;
  }
  if ( SrvRdmaRegistrationForIo )
  {
    v53 = v9[29];
  }
  else if ( v52 )
  {
    SmbCseEstimateMemoryDescriptorSize(
      v9,
      v150,
      (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0,
      &v148,
      v151,
      &v162);
    v53 = v148;
  }
  v54 = v150;
  v55 = v53 & 0xFFFF0000;
  v48 = *(_BYTE *)(a1 + 1048) == 1;
  v148 = v55;
  if ( v48 && v150 > v55 )
    return 3221225485LL;
  v56 = (_QWORD *)(a1 + 72);
  v57 = 0;
  v183 = 0;
  v48 = (*(_DWORD *)(v1 + 120) & 0x1000000) == 0;
  v146 = 0;
  if ( !v48 )
    v57 = (unsigned __int8)SmbCeCheckServerEntryDialect(*v56, 3, 0, 2) != 0;
  if ( (*(_DWORD *)(v1 + 120) & 0x40000000) != 0 )
    v57 |= 2u;
  v58 = v57 | 4;
  if ( !SrvRdmaRegistrationForIo )
    v58 = v57;
  v59 = SmbCeCheckServerEntryDialect(*v56, 3, 1, 2);
  v61 = v58 | 8;
  v169 = *(_QWORD *)(a1 + 2496);
  if ( !v59 )
    v61 = v58;
  v167 = v61;
  if ( !v54 )
    return 0;
  v156 = v61 & 4;
  v168 = v61 & 8;
  v155 = DWORD2(v177);
  v158 = DWORD1(v177);
  v154 = v177;
  do
  {
    v62 = v54;
    LOBYTE(v60) = 16;
    if ( v148 < v54 )
      v62 = v148;
    Length = v62;
    RDR_PERF_ENTER(v51 + 64, v60);
    v63 = v151[0];
    v64 = 0;
    v65 = v51[12];
    v161 = v162;
    v176 = v51[129];
    v66 = (struct _MDL *)v51[128];
    v67 = 0;
    SourceMdl = v66;
    pusResult[0] = 0;
    v144 = 0;
    v143 = v151[0];
    v68 = *(_QWORD *)(a1 + 88);
    v147[0] = v151[0];
    v69 = 1;
    v180 = MRxSmbDetermineDdpSecurity(*(_QWORD *)(v68 + 424));
    v153 = 1;
    pulResult = 0;
    v71 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v70) + 420);
    ConfigurationBlock = MRxSmbGetConfigurationBlock(v72);
    v74 = Length;
    v75 = ((Length - 1) >> 16) + 1;
    if ( !v169 )
    {
      v76 = 0;
      v74 = HIWORD(v146);
      v164 = HIWORD(v146);
      v159 = 0;
      v152 = 0;
      goto LABEL_126;
    }
    v76 = v169;
    v159 = v169;
    v152 = v154;
    v164 = v155 + v158;
    v77 = *(_DWORD *)(v169 + 12);
    v78 = v77 - v154;
    if ( v77 - v154 > Length )
      goto LABEL_125;
    v75 = ((unsigned int)(v77 - 1) >> 16) - v155 + 2;
    if ( !v143 || !v168 || v156 )
    {
      Length = v77 - v154;
LABEL_125:
      v63 = v143;
LABEL_126:
      v173 = v76;
      if ( !v63 )
        goto LABEL_136;
      goto LABEL_127;
    }
    v79 = *(_DWORD *)(ConfigurationBlock + 424);
    if ( v78 < Length )
    {
      while ( (unsigned int)v69 < v71 )
      {
        v80 = v76 + 16 * v69;
        if ( RtlULongAdd(v78, *(_DWORD *)(v80 + 12), &pulResult) < 0 || pulResult > v79 )
        {
          LODWORD(v69) = v153;
          v76 = v159;
          break;
        }
        v74 = Length;
        if ( pulResult > Length )
        {
          v81 = Length - v78;
          v82 = v75 + 1;
        }
        else
        {
          v81 = *(_DWORD *)(v80 + 12);
          v82 = v75 + 2;
        }
        v76 = v159;
        v69 = (unsigned int)(v153 + 1);
        v78 = pulResult;
        v75 = ((v81 - 1) >> 16) + v82;
        ++v153;
        if ( pulResult >= Length )
        {
          v63 = v143;
          v67 = 0;
          v173 = v159;
          goto LABEL_127;
        }
      }
      Length = v78;
    }
    v63 = v143;
    v67 = 0;
    v173 = v76;
LABEL_127:
    if ( (*(_DWORD *)(a1 + 68) & 0x1000800) != 0 && v180 )
    {
      v83 = 0;
      v171 = 0;
      if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 )
      {
        CryptoKeyNonceSize = SmbCryptoGetCryptoKeyNonceSize(*(_QWORD *)(v65 + 528), v74, v76);
        v85 = RtlULongToUShort(CryptoKeyNonceSize, pusResult);
        if ( v85 < 0 )
          goto LABEL_257;
        CryptoKeyAuthTagSize = SmbCryptoGetCryptoKeyAuthTagSize(*(_QWORD *)(v65 + 528));
      }
      else
      {
        pusResult[0] = *(_WORD *)(v65 + 520);
        CryptoKeyAuthTagSize = *(_DWORD *)(v65 + 516);
      }
      v85 = RtlULongToUShort(CryptoKeyAuthTagSize, &v144);
      if ( v85 < 0 )
      {
LABEL_257:
        v92 = 0;
        goto LABEL_258;
      }
      v67 = 1;
      v63 = ((pusResult[0] + v144 + 7) & 0xFFF8) + 25 + v143;
      v143 = v63;
    }
LABEL_136:
    v87 = 48 * v69;
    v171 = 0;
    v160 = 0;
    v182 = 0;
    v88 = (unsigned int)v63 + v87 + 64;
    v165 = v88;
    if ( *(_BYTE *)(a1 + 1056)
      || (ImplicitExchangeBuffer = 0, (_DWORD)v88)
      && (ImplicitExchangeBuffer = SmbCeAllocateImplicitExchangeBuffer(a1, (unsigned int)(v88 + 32))) == 0 )
    {
      v90 = 0;
    }
    else
    {
      v83 = a1 + 1064;
      *(_BYTE *)(a1 + 1056) = 1;
      v175 = a1 + 1064;
      v90 = (char *)(ImplicitExchangeBuffer + 32);
      v182 = ImplicitExchangeBuffer != 0;
      if ( !ImplicitExchangeBuffer )
        v90 = 0;
      v160 = v90;
      if ( a1 != -1064 )
        goto LABEL_148;
    }
    Pool2 = ExAllocatePool2(66, ((unsigned int)v88 + 1431LL) & 0xFFFFFFFFFFFFFFF8uLL, 1834181463);
    v175 = Pool2;
    v83 = Pool2;
    if ( !Pool2 )
      goto LABEL_145;
    if ( (_DWORD)v88 )
    {
      v90 = (char *)(Pool2 + 1424);
      v160 = (char *)(Pool2 + 1424);
    }
LABEL_148:
    memset(v90, 0, (unsigned int)v88);
    if ( !v83 || !v90 )
    {
LABEL_145:
      v85 = -1073741670;
      v92 = 0;
      goto LABEL_258;
    }
    v93 = v90 + 64;
    v94 = Length;
    v95 = v153;
    *(_DWORD *)(v83 + 1392) = v146;
    *(_DWORD *)(v83 + 1384) = v164;
    v96 = v159;
    *(_DWORD *)(v83 + 1388) = v75;
    v97 = v160;
    *(_QWORD *)(v83 + 1408) = v96;
    LODWORD(v96) = v152;
    v157 = 0;
    *(_QWORD *)(v83 + 1400) = 0;
    *(_DWORD *)(v83 + 1416) = v96;
    *(_DWORD *)(v83 + 1396) = v94;
    *(_DWORD *)(v83 + 1420) = v95;
    SmbCeBuildSmb2Header(a1, v97, 64);
    v48 = v156 == 0;
    *((_WORD *)v97 + 6) = 9;
    if ( !v48 )
    {
      if ( v67 )
      {
        v85 = -1073741637;
        RxFreeMdl(0);
        RxFreeMdl(0);
        goto LABEL_259;
      }
      v98 = (unsigned int)(v87 + 64);
      *((_DWORD *)v93 + 9) = v94;
      *((_WORD *)v93 + 1) = v98;
      goto LABEL_172;
    }
    if ( v143 )
    {
      v99 = 48 * v95 + 64;
      *((_WORD *)v93 + 20) = v99;
      if ( v67 )
      {
        v100 = &v97[v99];
        *((_DWORD *)v93 + 8) = 3;
        if ( ((unsigned __int8)v100 & 7) != 0 )
          __int2c();
        *((_WORD *)v100 + 1) = v147[0];
        *((_WORD *)v100 + 4) = 0;
        *((_DWORD *)v100 + 1) = v161;
        if ( RtlUShortAdd(*((_WORD *)v93 + 21), 0x10u, (USHORT *)v93 + 21) < 0 )
          __int2c();
        v157 = v100 + 16;
        *((_WORD *)v100 + 8) = 2 - ((*(_DWORD *)(a1 + 68) & 0x1000000) != 0);
        *((_WORD *)v100 + 9) = v144;
        v101 = v144;
        *((_WORD *)v100 + 10) = pusResult[0];
        v102 = pusResult[0] + 7;
        *((_WORD *)v100 + 11) = 0;
        if ( RtlUShortAdd(*((_WORD *)v93 + 21), ((v102 + v101) & 0xFFF8) + 8, (USHORT *)v93 + 21) < 0 )
          __int2c();
        ++*((_WORD *)v100 + 4);
        v103 = *((_WORD *)v93 + 21);
        v147[0] = 0;
        if ( (v103 & 7) != 0 )
        {
          if ( RtlUShortAdd(v103, 7u, v147) < 0 )
          {
            __int2c();
LABEL_167:
            if ( RtlUShortAdd(*((_WORD *)v93 + 21), v143, (USHORT *)v93 + 21) < 0 )
            {
              __int2c();
              LODWORD(v98) = v165;
              *((_DWORD *)v93 + 9) = v94;
              goto LABEL_173;
            }
LABEL_170:
            LODWORD(v98) = v165;
            *((_DWORD *)v93 + 9) = v94;
            goto LABEL_173;
          }
          v103 = v147[0] & 0xFFF8;
        }
        *(_WORD *)v100 = v103;
        goto LABEL_167;
      }
      *((_DWORD *)v93 + 8) = v161;
      *((_WORD *)v93 + 21) = v143;
      goto LABEL_170;
    }
    v104 = v87 + 64;
    *((_DWORD *)v93 + 1) = v94;
    v98 = (unsigned int)(v87 + 64);
    *((_WORD *)v93 + 1) = v104;
LABEL_172:
    v165 = v98;
LABEL_173:
    v105 = v159;
    v106 = 0;
    v107 = v94;
    if ( v95 )
    {
      v108 = v167 & 1;
      v109 = v173;
      v110 = v167 & 2;
      v111 = v152;
      do
      {
        v112 = v174;
        *(_WORD *)v93 = 49;
        *((_OWORD *)v93 + 1) = *(_OWORD *)(v112 + 28);
        if ( v108 )
          *((_DWORD *)v93 + 11) |= 2u;
        if ( v110 )
          *((_DWORD *)v93 + 11) |= 1u;
        v113 = v106 + 1;
        if ( v106 + 1 < v95 )
          *((_DWORD *)v93 + 11) |= 4u;
        if ( v105 )
        {
          v114 = (__int64 *)(v109 + 16LL * v106);
          if ( v106 )
          {
            v116 = *v114;
            v115 = 0;
          }
          else
          {
            v115 = v111;
            v116 = *v114 + v111;
          }
          *((_QWORD *)v93 + 1) = v116;
          v117 = *((_DWORD *)v114 + 3);
          if ( v107 >= v117 - v115 )
          {
            v119 = v111;
            if ( v106 )
              v119 = 0;
            v118 = v117 - v119;
          }
          else
          {
            v118 = v107;
          }
          v120 = v169;
          v121 = v118 + v154;
          *((_DWORD *)v93 + 1) = v118;
          v154 = v121;
          v122 = *(_DWORD *)(v120 + 12);
          if ( v121 == v122 )
          {
            v154 = 0;
            v158 += ((unsigned int)(v122 - 1) >> 16) + 2;
            v169 = v105 + 16LL * v113;
            v155 = 0;
          }
          else
          {
            v155 += ((v118 - 1) >> 16) + 1;
          }
        }
        else
        {
          v118 = v107;
          *((_QWORD *)v93 + 1) = v172 + v146;
          *((_DWORD *)v93 + 1) = v107;
        }
        v107 -= v118;
        if ( v156 || v143 )
        {
          *((_DWORD *)v93 + 9) = v118;
          *((_DWORD *)v93 + 1) = 0;
        }
        v93 += 48;
        ++v106;
      }
      while ( v113 < v95 );
      v83 = v175;
      v94 = Length;
      LODWORD(v98) = v165;
    }
    Mdl2 = (struct _MDL *)RxAllocateMdl2(v160, (unsigned int)v98, 0, 0, 0);
    v92 = Mdl2;
    if ( !Mdl2 )
    {
      v124 = 0;
      goto LABEL_201;
    }
    MmBuildMdlForNonPagedPool(Mdl2);
    if ( v182 )
      v92->MdlFlags |= 0x1000u;
    if ( SourceMdl )
    {
      v125 = (_DWORD *)(v105 + 8);
      if ( v105 )
        v126 = *v125 + v152;
      else
        v126 = v146;
      v127 = (struct _MDL *)RxAllocateMdl2((char *)SourceMdl->StartVa + SourceMdl->ByteOffset + v126, v94, 0, 0, 0);
    }
    else
    {
      v127 = (struct _MDL *)RxAllocateMdl2(v176 + v146, v94, 0, 0, 0);
      v125 = (_DWORD *)(v105 + 8);
    }
    v64 = v127;
    if ( !v127 )
    {
      v124 = 0;
LABEL_201:
      v85 = -1073741670;
LABEL_202:
      RxFreeMdl(v124);
      RxFreeMdl(v92);
LABEL_259:
      if ( *(_QWORD *)(v83 + 1400) )
        RxUnlockAndFreeMdlChain();
      if ( v83 == a1 + 1064 )
        *(_BYTE *)(a1 + 1056) = 0;
      else
        ExFreePoolWithTag((PVOID)v83, 0x6D536357u);
LABEL_281:
      if ( v183 )
        return 259;
      return (unsigned int)v85;
    }
    if ( SourceMdl )
    {
      if ( v105 )
        v128 = *v125 + v152;
      else
        v128 = v146;
      IoBuildPartialMdl(
        SourceMdl,
        v127,
        (char *)SourceMdl->StartVa + v128 + (unsigned __int64)SourceMdl->ByteOffset,
        v94);
    }
    else
    {
      MmBuildMdlForNonPagedPool(v127);
    }
    if ( v156 )
    {
      *(_QWORD *)(v83 + 1400) = v64;
      v64 = 0;
      v129 = (unsigned int)v98;
LABEL_246:
      v51 = (_QWORD *)a1;
      LOWORD(v142) = 0;
      LODWORD(v141) = 0;
      Priority[0] = v94;
      v85 = SmbCseInitializeBufferContextWithMemoryRegistration(
              v83,
              a1,
              v92,
              v129,
              0,
              *(_QWORD *)Priority,
              0,
              v141,
              v142,
              4);
      goto LABEL_247;
    }
    if ( !v143 )
    {
      v92->Next = v64;
      v129 = (unsigned int)v98 + v94;
      goto LABEL_246;
    }
    v51 = (_QWORD *)a1;
    LOWORD(v142) = v143;
    LODWORD(v141) = v94;
    Priority[0] = 0;
    v85 = SmbCseInitializeBufferContextWithMemoryRegistration(
            v83,
            a1,
            v92,
            (unsigned int)v98,
            0,
            *(_QWORD *)Priority,
            v64,
            v141,
            v142,
            16388);
    v130 = *(_DWORD *)(v83 + 4);
    if ( (v130 & 0x8000) != 0 && v180 )
    {
      if ( SourceMdl )
        __int2c();
      if ( (v64->MdlFlags & 5) != 0 )
        MappedSystemVa = v64->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v64, 0, MmCached, 0, 0, 0x40000010u);
      if ( (v64->MdlFlags & 5) != 0 )
        v132 = v64->MappedSystemVa;
      else
        v132 = MmMapLockedPagesSpecifyCache(v64, 0, MmCached, 0, 0, 0x40000010u);
      v85 = SmbCryptoEncryptRdmaPayload(
              *(_QWORD *)(*(_QWORD *)(a1 + 96) + 528LL),
              v157 + 8,
              *((unsigned __int16 *)v157 + 1),
              &v157[*((unsigned __int16 *)v157 + 1) + 8],
              *((unsigned __int16 *)v157 + 2),
              v132,
              v94,
              MappedSystemVa);
      if ( v85 >= 0 )
        goto LABEL_252;
      v133 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_258;
      }
      v134 = 10;
LABEL_244:
      WPP_SF_qqD(v133->AttachedDevice, v134, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, a1, v83, v85);
      v124 = v64;
      goto LABEL_202;
    }
    if ( (v130 & 0x1000) != 0 && v180 )
    {
      v85 = Smb2ComputeOutgoingSignatureForRdmaBuffer(v83, v157);
      if ( v85 >= 0 )
        goto LABEL_252;
      v133 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_258;
      }
      v134 = 11;
      goto LABEL_244;
    }
LABEL_247:
    if ( v85 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, v51, v83);
        v124 = v64;
        goto LABEL_202;
      }
LABEL_258:
      RxFreeMdl(v64);
      RxFreeMdl(v92);
      if ( v83 )
        goto LABEL_259;
      goto LABEL_281;
    }
LABEL_252:
    v135 = *(unsigned int *)(v83 + 1388);
    *(_DWORD *)(v83 + 80) = v135;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
        v83,
        *(_DWORD *)(v83 + 1384),
        v135);
    }
    *(_QWORD *)(v83 + 88) = v160;
    v171 = v83;
    v136 = v171;
    LOBYTE(v135) = 24;
    v137 = v171;
    v138 = *(_DWORD *)(v171 + 1396);
    *(_WORD *)(v171 + 2) = 9;
    RDR_PERF_INIT(v137, 58144, v135);
    if ( SrvRdmaRegistrationForIo )
    {
      v139 = v146;
      v85 = SmbCseSubmitRdmaDirectWrite(
              v136,
              SrvRdmaRegistrationForIo + 48,
              *(unsigned __int16 *)(SrvRdmaRegistrationForIo + 46),
              v146 + v172,
              *(_QWORD *)(v136 + 1400),
              v138,
              v136,
              Smb2Write_RdmaDirectWriteComplete);
      if ( v85 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_DiqD(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            (unsigned int)WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
            v138,
            v139,
            v136,
            v85);
        }
        goto LABEL_281;
      }
    }
    else
    {
      v85 = SmbCseSubmitBufferContext(v136);
      if ( v85 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_DiqD(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            (unsigned int)WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
            v138,
            v146,
            v136,
            v85);
        }
        goto LABEL_281;
      }
      v183 = 1;
    }
    v146 += v138;
    v54 = v150 - v138;
    v150 = v54;
  }
  while ( v54 );
  if ( v183 )
    return 259;
  return (unsigned int)v85;
}

```

## disassembly

```asm
0x140020490  mov     [rsp-8+arg_0], rcx
0x140020495  push    rbp
0x140020496  push    rbx
0x140020497  push    rsi
0x140020498  push    rdi
0x140020499  push    r12
0x14002049b  push    r13
0x14002049d  push    r14
0x14002049f  push    r15
0x1400204a1  lea     rbp, [rsp-38h]
0x1400204a6  sub     rsp, 138h
0x1400204ad  mov     r13, [rcx+30h]
0x1400204b1  xor     r15d, r15d
0x1400204b4  mov     rdi, [rcx+60h]
0x1400204b8  mov     rsi, rcx
0x1400204bb  mov     rbx, [rcx+9C0h]
0x1400204c2  xorps   xmm0, xmm0
0x1400204c5  mov     rcx, [rcx+58h]
0x1400204c9  mov     rax, [r13+48h]
0x1400204cd  mov     [rbp+70h+arg_18], r13
0x1400204d4  mov     [rbp+70h+arg_8], r15b
0x1400204db  mov     [rbp+70h+var_B0], r15
0x1400204df  mov     rax, [rax+30h]
0x1400204e3  mov     [rsp+170h+var_10C], r15d
0x1400204e8  mov     r12, [rdi+188h]
0x1400204ef  mov     [rbp+70h+var_C4], r15d
0x1400204f3  mov     [rsp+170h+var_100], r15w
0x1400204f9  mov     rcx, [rcx+1A8h]
0x140020500  mov     [rbp+70h+var_78], rax
0x140020504  movdqu  [rbp+70h+var_58], xmm0
0x140020509  call    cs:__imp_MRxSmbDetermineDdpSecurity
0x140020510  nop     dword ptr [rax+rax+00h]
0x140020515  lea     rcx, [rsi+200h]
0x14002051c  mov     dl, 0Fh
0x14002051e  movzx   r14d, al
0x140020522  call    cs:__imp_RDR_PERF_ENTER
0x140020529  nop     dword ptr [rax+rax+00h]
0x14002052e  test    rbx, rbx
0x140020531  jz      short loc_14002057D
0x140020533  mov     edx, [rsi+9D8h]
0x140020539  xor     ecx, ecx
0x14002053b  mov     [rsp+170h+var_104], r15d
0x140020540  test    edx, edx
0x140020542  jz      short loc_140020566
0x140020544  nop     dword ptr [rax+00h]
0x140020548  nop     dword ptr [rax+rax+00000000h]
0x140020550  mov     eax, ecx
0x140020552  inc     ecx
0x140020554  shl     rax, 4
0x140020558  add     r15d, [rax+rbx+0Ch]
0x14002055d  cmp     ecx, edx
0x14002055f  jb      short loc_140020550
0x140020561  mov     [rsp+170h+var_104], r15d
0x140020566  mov     rcx, [rbx]
0x140020569  lea     r9, [r13+238h]
0x140020570  mov     [rbp+70h+var_88], rcx
0x140020574  lea     r8, [r13+230h]
0x14002057b  jmp     short loc_14002059A
0x14002057d  lea     r8, [r13+230h]
0x140020584  mov     rax, [r8]
0x140020587  lea     r9, [r13+238h]
0x14002058e  mov     r15d, [r9]
0x140020591  mov     [rbp+70h+var_88], rax
0x140020595  mov     [rsp+170h+var_104], r15d
0x14002059a  mov     eax, [r12+140h]
0x1400205a2  lea     rbx, [rsi+38h]
0x1400205a6  sub     eax, 2
0x1400205a9  cmp     eax, 1
0x1400205ac  ja      short loc_1400205DD
0x1400205ae  cmp     qword ptr [rbx], 0
0x1400205b2  jnz     short loc_1400205DD
0x1400205b4  mov     eax, [rsi+44h]
0x1400205b7  test    eax, 1000800h
0x1400205bc  jnz     short loc_1400205DD
0x1400205be  mov     r9d, [r9]
0x1400205c1  mov     rdx, rdi
0x1400205c4  mov     r8, [r8]
0x1400205c7  mov     rcx, [rbp+70h+var_78]
0x1400205cb  call    Smb2FindSrvRdmaRegistrationForIo
0x1400205d0  mov     [rbp+70h+var_B0], rax
0x1400205d4  test    rax, rax
0x1400205d7  jnz     loc_140020704
0x1400205dd  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400205e4  nop     dword ptr [rax+rax+00h]
0x1400205e9  cmp     dword ptr [rax+4], 0
0x1400205ed  jbe     loc_140020704
0x1400205f3  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400205fa  nop     dword ptr [rax+rax+00h]
0x1400205ff  cmp     r15d, [rax+4]
0x140020603  jb      loc_140020704
0x140020609  mov     eax, [r12+140h]
0x140020611  sub     eax, 2
0x140020614  cmp     eax, 1
0x140020617  ja      loc_140020704
0x14002061d  cmp     qword ptr [rbx], 0
0x140020621  jnz     loc_140020704
0x140020627  mov     rax, [rsi+58h]
0x14002062b  mov     rbx, [rsi+48h]
0x14002062f  mov     r8, [rax+1A8h]
0x140020636  mov     eax, [rsi+44h]
0x140020639  lea     rcx, [rbx+2ECh]
0x140020640  bt      eax, 18h
0x140020644  jnb     short loc_14002069F
0x140020646  mov     eax, [rcx]
0x140020648  test    al, 1
0x14002064a  jnz     short loc_14002069F
0x14002064c  test    r14b, r14b
0x14002064f  jz      short loc_14002069F
0x140020651  mov     ecx, [rbx+248h]
0x140020657  mov     eax, 38E38E39h
0x14002065c  mul     ecx
0x14002065e  shr     edx, 5
0x140020661  lea     eax, [rdx+rdx*8]
0x140020664  shl     eax, 4
0x140020667  cmp     ecx, eax
0x140020669  jnz     loc_140020704
0x14002066f  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x140020676  jz      short loc_1400206F4
0x140020678  movzx   r9d, word ptr [r8+60h]
0x14002067d  lea     rdx, RdmaWithEncryption
0x140020684  mov     rax, [r8+68h]
0x140020688  shr     r9w, 1
0x14002068c  mov     qword ptr [rsp+170h+BugCheckOnFailure], rax
0x140020691  call    McTemplateK0hzr0_EtwWriteTransfer
0x140020696  lock inc dword ptr [rbx+248h]
0x14002069d  jmp     short loc_140020704
0x14002069f  mov     eax, [rsi+44h]
0x1400206a2  bt      eax, 0Bh
0x1400206a6  jnb     short loc_1400206FD
0x1400206a8  mov     eax, [rcx]
0x1400206aa  test    al, 2
0x1400206ac  jnz     short loc_1400206FD
0x1400206ae  test    r14b, r14b
0x1400206b1  jz      short loc_1400206FD
0x1400206b3  mov     ecx, [rbx+248h]
0x1400206b9  mov     eax, 38E38E39h
0x1400206be  mul     ecx
0x1400206c0  shr     edx, 5
0x1400206c3  lea     eax, [rdx+rdx*8]
0x1400206c6  shl     eax, 4
0x1400206c9  cmp     ecx, eax
0x1400206cb  jnz     short loc_140020704
0x1400206cd  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x1400206d4  jz      short loc_1400206F4
0x1400206d6  movzx   r9d, word ptr [r8+60h]
0x1400206db  lea     rdx, RdmaWithSigning
0x1400206e2  mov     rax, [r8+68h]
0x1400206e6  shr     r9w, 1
0x1400206ea  mov     qword ptr [rsp+170h+BugCheckOnFailure], rax
0x1400206ef  call    McTemplateK0hzr0_EtwWriteTransfer
0x1400206f4  lock inc dword ptr [rbx+248h]
0x1400206fb  jmp     short loc_140020704
0x1400206fd  mov     [rbp+70h+arg_8], 1
0x140020704  mov     rsi, [rsi+30h]
0x140020708  mov     rax, [rsi+40h]
0x14002070c  mov     r15, [rax+38h]
0x140020710  mov     rax, [rbp+70h+arg_0]
0x140020717  mov     [rbp+70h+arg_10], r15
0x14002071e  mov     rbx, [rax+9B8h]
0x140020725  test    rbx, rbx
0x140020728  jz      short loc_140020753
0x14002072a  mov     edx, [rax+9D8h]
0x140020730  xor     edi, edi
0x140020732  test    edx, edx
0x140020734  jz      short loc_140020760
0x140020736  mov     r8, [rax+9C0h]
0x14002073d  xor     ecx, ecx
0x14002073f  nop
0x140020740  mov     eax, ecx
0x140020742  inc     ecx
0x140020744  shl     rax, 4
0x140020748  add     edi, [rax+r8+0Ch]
0x14002074d  cmp     ecx, edx
0x14002074f  jb      short loc_140020740
0x140020751  jmp     short loc_140020760
0x140020753  mov     edi, [rsi+238h]
0x140020759  mov     rbx, [rsi+220h]
0x140020760  mov     edx, 2
0x140020765  mov     rcx, rbx
0x140020768  call    cs:__imp_MmMdlPageContentsState
0x14002076f  nop     dword ptr [rax+rax+00h]
0x140020774  mov     r8, [rbp+70h+arg_0]
0x14002077b  mov     edx, eax
0x14002077d  mov     ecx, [r8+44h]
0x140020781  bt      ecx, 18h
0x140020785  jnb     short loc_14002079A
0x140020787  test    r14b, r14b
0x14002078a  jz      short loc_14002079A
0x14002078c  cmp     [rbp+70h+arg_8], 0
0x140020793  jnz     short loc_1400207D0
0x140020795  cmp     eax, 1
0x140020798  jnz     short loc_1400207D0
0x14002079a  mov     eax, [r8+44h]
0x14002079e  bt      eax, 0Bh
0x1400207a2  jnb     short loc_1400207AE
0x1400207a4  test    r14b, r14b
0x1400207a7  jz      short loc_1400207AE
0x1400207a9  cmp     edx, 1
0x1400207ac  jnz     short loc_1400207D0
0x1400207ae  mov     eax, [r15+30h]
0x1400207b2  dec     eax
0x1400207b4  cmp     eax, 1
0x1400207b7  jbe     short loc_1400207D0
0x1400207b9  mov     qword ptr [r8+408h], 0
0x1400207c4  mov     [r8+400h], rbx
0x1400207cb  jmp     loc_1400209C3
0x1400207d0  mov     rcx, [r8+9B8h]; MemoryDescriptorList
0x1400207d7  xor     ebx, ebx
0x1400207d9  test    rcx, rcx
0x1400207dc  jz      loc_14002086A
0x1400207e2  test    edi, edi
0x1400207e4  jz      loc_14002086A
0x1400207ea  test    byte ptr [rcx+0Ah], 5
0x1400207ee  jz      short loc_1400207F6
0x1400207f0  mov     rbx, [rcx+18h]
0x1400207f4  jmp     short loc_140020823
0x1400207f6  mov     [rsp+170h+Priority], 40000010h; Priority
0x1400207fe  xor     r9d, r9d; RequestedAddress
0x140020801  xor     edx, edx; AccessMode
0x140020803  mov     [rsp+170h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140020807  mov     r8d, 1; CacheType
0x14002080d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140020814  nop     dword ptr [rax+rax+00h]
0x140020819  mov     r8, [rbp+70h+arg_0]
0x140020820  mov     rbx, rax
0x140020823  test    rbx, rbx
0x140020826  jnz     short loc_14002086A
0x140020828  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002082f  lea     rax, WPP_GLOBAL_Control
0x140020836  cmp     rcx, rax
0x140020839  jz      short loc_140020860
0x14002083b  mov     eax, [rcx+2Ch]
0x14002083e  test    al, 1
0x140020840  jz      short loc_140020860
0x140020842  cmp     byte ptr [rcx+29h], 1
0x140020846  jb      short loc_140020860
0x140020848  mov     edx, 0Eh
0x14002084d  mov     r9, r8
0x140020850  mov     rcx, [rcx+18h]
0x140020854  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x14002085b  call    WPP_SF_q
0x140020860  mov     eax, 0C000009Ah
0x140020865  jmp     loc_1400218B9
0x14002086a  xor     r15d, r15d
0x14002086d  cmp     [r8+9B8h], r15
0x140020874  jnz     short loc_1400208C6
0x140020876  test    edi, edi
0x140020878  jz      short loc_1400208C6
0x14002087a  mov     rcx, rsi; RxContext
0x14002087d  call    cs:__imp_RxLowIoGetBufferAddress
0x140020884  nop     dword ptr [rax+rax+00h]
0x140020889  mov     r15, rax
0x14002088c  test    rax, rax
0x14002088f  jnz     short loc_1400208BF
0x140020891  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140020898  lea     rax, WPP_GLOBAL_Control
0x14002089f  cmp     rcx, rax
0x1400208a2  jz      short loc_140020860
0x1400208a4  mov     eax, [rcx+2Ch]
0x1400208a7  test    al, 1
0x1400208a9  jz      short loc_140020860
0x1400208ab  cmp     byte ptr [rcx+29h], 1
0x1400208af  jb      short loc_140020860
0x1400208b1  mov     r9, [rbp+70h+arg_0]
0x1400208b8  mov     edx, 0Fh
0x1400208bd  jmp     short loc_140020850
0x1400208bf  mov     r8, [rbp+70h+arg_0]
0x1400208c6  mov     r14, [r8+410h]
0x1400208cd  test    r14, r14
0x1400208d0  jnz     short loc_140020931
0x1400208d2  mov     edx, 6D537357h
0x1400208d7  mov     ecx, edi
0x1400208d9  call    cs:__imp_SmbMmAllocateSmbBuffer
0x1400208e0  nop     dword ptr [rax+rax+00h]
0x1400208e5  mov     r8, [rbp+70h+arg_0]
0x1400208ec  mov     r14, rax
0x1400208ef  mov     [r8+410h], rax
0x1400208f6  test    rax, rax
0x1400208f9  jnz     short loc_140020931
0x1400208fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140020902  lea     rax, WPP_GLOBAL_Control
0x140020909  cmp     rcx, rax
0x14002090c  jz      loc_140020860
0x140020912  mov     eax, [rcx+2Ch]
0x140020915  test    al, 1
0x140020917  jz      loc_140020860
0x14002091d  cmp     byte ptr [rcx+29h], 1
0x140020921  jb      loc_140020860
0x140020927  mov     edx, 10h
0x14002092c  jmp     loc_14002084D
0x140020931  and     r14, 0FFFFFFFFFFFFFFF8h
0x140020935  mov     qword ptr [r8+400h], 0
0x140020940  cmp     qword ptr [r8+9B8h], 0
0x140020948  mov     [r8+408h], r14
0x14002094f  jz      short loc_14002095F
0x140020951  mov     rax, [r8+9C0h]
0x140020958  mov     r15d, [rax+8]
0x14002095c  add     r15, rbx
0x14002095f  mov     rax, [rbp+70h+arg_10]
0x140020966  cmp     dword ptr [rax+30h], 2
  ... truncated ...
```
