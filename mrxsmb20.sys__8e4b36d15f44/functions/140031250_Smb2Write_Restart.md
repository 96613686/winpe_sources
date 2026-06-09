# Smb2Write_Restart

- ea: `0x140031250`
- end: `0x14003241a`
- name: `Smb2Write_Restart`
- size: `4554`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000e700`
- `0x140013b30`
- `0x140028950`
- `0x1400297fc`
- `0x140029cb0`
- `0x14002a1dc`
- `0x14002a6a8`
- `0x14002e258`
- `0x140031250`
- `0x140033234`
- `0x140036ab4`
- `0x140036bac`
- `0x1400372c0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400313db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032317`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400313db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032317`
- `ntoskrnl!MmMdlPageContentsState` at `0x14003152b`
- `ntoskrnl!MmMdlPageContentsState` at `0x14003152b`
- `ntoskrnl!ExAllocatePool2` at `0x140031bb4`
- `ntoskrnl!ExAllocatePool2` at `0x140031bb4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400315c1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032055`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003208a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400315c1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032055`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003208a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031edb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031f73`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031edb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031f73`
- `ntoskrnl!IoBuildPartialMdl` at `0x140031fab`
- `ntoskrnl!IoBuildPartialMdl` at `0x140031fab`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x1400313c2`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x1400322f7`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x1400313c2`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x1400322f7`
- `rdbss!RxFreeMdl` at `0x1400322c6`
- `rdbss!RxFreeMdl` at `0x1400322da`
- `rdbss!RxFreeMdl` at `0x1400322c6`
- `rdbss!RxFreeMdl` at `0x1400322da`
- `rdbss!RxAllocateMdl2` at `0x140031eb8`
- `rdbss!RxAllocateMdl2` at `0x140031f42`
- `rdbss!RxAllocateMdl2` at `0x140031eb8`
- `rdbss!RxAllocateMdl2` at `0x140031f42`
- `rdbss!RxLowIoGetBufferAddress` at `0x14003162a`
- `rdbss!RxLowIoGetBufferAddress` at `0x14003162a`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x1400312b7`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x1400319b6`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x1400312b7`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x1400319b6`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14003167a`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14003167a`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x1400314b5`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x1400314b5`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x140031b53`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x140031b53`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400313aa`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400313aa`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140031404`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140031438`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400319cc`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400319d8`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140031404`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140031438`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400319cc`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400319d8`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14003234c`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14003234c`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140031ff6`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400321d2`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140031ff6`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400321d2`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140031785`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140031785`
- `mrxsmb!SmbCryptoGetCryptoKeyAuthTagSize` at `0x140031aa8`
- `mrxsmb!SmbCryptoGetCryptoKeyAuthTagSize` at `0x140031aa8`
- `mrxsmb!SmbCryptoEncryptRdmaPayload` at `0x1400320d2`
- `mrxsmb!SmbCryptoEncryptRdmaPayload` at `0x1400320d2`
- `mrxsmb!SmbCryptoGetCryptoKeyNonceSize` at `0x140031a87`
- `mrxsmb!SmbCryptoGetCryptoKeyNonceSize` at `0x140031a87`

## pseudocode

```c
__int64 __fastcall Smb2Write_Restart(__int64 a1)
{
  __int64 v1; // r13
  __int64 *v3; // rbx
  _QWORD *v4; // rbp
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r12
  __int64 v8; // r8
  char v9; // r14
  unsigned __int64 v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  _QWORD *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 ConfigurationBlock; // rax
  __int64 v19; // r8
  unsigned int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // rbx
  bool v24; // r15
  __int64 v25; // r12
  unsigned int v26; // edx
  unsigned int i; // ecx
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // r15d
  __int64 v32; // rcx
  char *v33; // rbx
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  int v36; // ebx
  char *BufferAddress; // r14
  __int64 v38; // rsi
  __int64 SmbBuffer; // rax
  char *v40; // rsi
  unsigned int v41; // ebx
  bool v42; // zf
  BOOL v43; // esi
  __int64 v44; // r10
  unsigned int v45; // r12d
  unsigned int v46; // eax
  unsigned int v47; // r9d
  int v48; // edx
  int v49; // esi
  ULONG v50; // r8d
  ULONG v51; // r14d
  int v52; // ecx
  unsigned __int64 v53; // rax
  __int64 v54; // rbp
  unsigned __int64 v55; // rax
  __int64 v56; // rbp
  unsigned int v57; // eax
  char v58; // r13
  __int64 v59; // rsi
  __int64 v60; // rcx
  __int64 v61; // rcx
  char v62; // bp
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // r8
  unsigned int v66; // ebx
  int v67; // ecx
  unsigned int v68; // r12d
  unsigned __int16 v69; // dx
  __int64 v70; // rbp
  unsigned int CryptoKeyNonceSize; // eax
  unsigned __int16 v72; // r15
  unsigned int CryptoKeyAuthTagSize; // ecx
  int v74; // ebp
  __int64 v75; // rsi
  __int64 v76; // rdx
  __int64 ImplicitExchangeBuffer; // rax
  __int64 Pool2; // rax
  unsigned int v79; // ecx
  __int64 v80; // r12
  __int64 v81; // rbx
  unsigned __int16 v82; // cx
  unsigned __int16 v83; // cx
  bool v84; // cf
  unsigned __int16 v85; // ax
  unsigned __int16 v86; // r15
  unsigned __int16 v87; // ax
  unsigned __int16 v88; // cx
  __int64 v89; // rax
  ULONG v90; // ecx
  __int64 v91; // rax
  ULONG v92; // edx
  int v93; // eax
  unsigned int v94; // r13d
  __int64 v95; // rax
  struct _MDL *Mdl2; // rax
  struct _MDL *v97; // rbx
  unsigned int v98; // edx
  char *v99; // rcx
  struct _MDL *v100; // rax
  struct _MDL *v101; // r13
  unsigned int v102; // ecx
  int v103; // eax
  int v104; // eax
  PVOID MappedSystemVa; // rbx
  PVOID v106; // rax
  PDEVICE_OBJECT v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // r9
  int v110; // r8d
  int v111; // esi
  ULONG Priority[2]; // [rsp+28h] [rbp-120h]
  __int64 v114; // [rsp+38h] [rbp-110h]
  int v115; // [rsp+40h] [rbp-108h]
  unsigned __int16 v116[2]; // [rsp+50h] [rbp-F8h] BYREF
  int v117; // [rsp+54h] [rbp-F4h]
  ULONG v118; // [rsp+58h] [rbp-F0h]
  unsigned int v119; // [rsp+5Ch] [rbp-ECh]
  unsigned int v120; // [rsp+60h] [rbp-E8h]
  int v121; // [rsp+64h] [rbp-E4h]
  unsigned int v122; // [rsp+68h] [rbp-E0h]
  unsigned int v123; // [rsp+6Ch] [rbp-DCh]
  unsigned __int16 v124; // [rsp+70h] [rbp-D8h]
  int v125; // [rsp+74h] [rbp-D4h]
  BOOL v126; // [rsp+78h] [rbp-D0h]
  int v127; // [rsp+7Ch] [rbp-CCh] BYREF
  int v128; // [rsp+80h] [rbp-C8h]
  int v129; // [rsp+84h] [rbp-C4h]
  struct _MDL *v130; // [rsp+88h] [rbp-C0h]
  __int64 v131; // [rsp+90h] [rbp-B8h]
  __int64 v132; // [rsp+98h] [rbp-B0h]
  __int64 v133; // [rsp+A0h] [rbp-A8h]
  PMDL SourceMdl; // [rsp+A8h] [rbp-A0h]
  __int64 v135; // [rsp+B0h] [rbp-98h]
  struct _MDL *v136; // [rsp+B8h] [rbp-90h]
  __int64 v137; // [rsp+C0h] [rbp-88h]
  __int64 v138; // [rsp+C8h] [rbp-80h]
  __int64 v139; // [rsp+D0h] [rbp-78h]
  __int64 v140; // [rsp+D8h] [rbp-70h]
  __int128 v141; // [rsp+E8h] [rbp-60h]
  bool v142; // [rsp+150h] [rbp+8h]
  char v143; // [rsp+158h] [rbp+10h]
  char v144; // [rsp+160h] [rbp+18h]
  unsigned __int16 v145; // [rsp+168h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 48);
  v3 = *(__int64 **)(a1 + 2496);
  LODWORD(v4) = 0;
  v141 = 0;
  v139 = *(_QWORD *)(*(_QWORD *)(v1 + 72) + 48LL);
  v5 = *(_QWORD *)(a1 + 96);
  v6 = *(_QWORD *)(a1 + 88);
  v7 = *(_QWORD *)(v5 + 392);
  v127 = 0;
  v116[0] = 0;
  v9 = MRxSmbDetermineDdpSecurity(*(_QWORD *)(v6 + 424));
  v10 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
      v1,
      a1,
      *(_QWORD *)(v1 + 56) + 360LL);
  }
  if ( v3 )
  {
    v11 = *(_DWORD *)(a1 + 2520);
    v8 = 0;
    v119 = 0;
    v10 = 0;
    if ( v11 )
    {
      do
      {
        v12 = (unsigned int)v10;
        v10 = (unsigned int)(v10 + 1);
        v8 = (unsigned int)(HIDWORD(v3[2 * v12 + 1]) + v8);
      }
      while ( (unsigned int)v10 < v11 );
      v119 = v8;
    }
    v13 = *v3;
  }
  else
  {
    v119 = *(_DWORD *)(v1 + 568);
    v13 = *(_QWORD *)(v1 + 560);
  }
  v138 = v13;
  v14 = *(_QWORD *)(a1 + 160);
  if ( v14 != a1 + 160 )
  {
    v15 = (_QWORD *)(v14 - 8);
    if ( v15 )
    {
      do
      {
        v16 = v15[1];
        v4 = 0;
        if ( v16 != a1 + 160 )
          v4 = (_QWORD *)(v16 - 8);
        ProcessChunkAndUpdateBlockState(a1, v15, v8);
        SmbCseFinalizeBufferContext(v15);
        v10 = v15[175];
        if ( v10 )
          RxUnlockAndFreeMdlChain();
        if ( v15 == (_QWORD *)(a1 + 1064) )
          *(_BYTE *)(a1 + 1056) = 0;
        else
          ExFreePoolWithTag(v15, 0x6D536357u);
        v15 = v4;
      }
      while ( v4 );
    }
  }
  if ( *(_DWORD *)(MRxSmbGetConfigurationBlock(v10) + 4) )
  {
    if ( (unsigned int)(*(_DWORD *)(v7 + 320) - 2) <= 1 )
    {
      ConfigurationBlock = MRxSmbGetConfigurationBlock(v17);
      v20 = v119;
      if ( v119 >= *(_DWORD *)(ConfigurationBlock + 4) )
      {
        if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 && v9 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 748LL) & 1) == 0 )
            goto LABEL_34;
          v20 = v119;
        }
        if ( ((*(_DWORD *)(a1 + 68) & 0x800) == 0 || !v9) && !*(_QWORD *)(a1 + 56) )
        {
          v21 = v20;
          if ( v20 > 0x10000 )
            v21 = 0x10000;
          LOBYTE(v19) = (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0;
          SmbCseEstimateMemoryDescriptorSize(v7, v21, v19, 0, v116, &v127);
        }
      }
    }
  }
LABEL_34:
  v22 = *(_QWORD *)(a1 + 48);
  v23 = *(_QWORD *)(a1 + 2488);
  v24 = v116[0] != 0;
  v25 = *(_QWORD *)(*(_QWORD *)(v22 + 64) + 56LL);
  if ( v23 )
  {
    v26 = *(_DWORD *)(a1 + 2520);
    if ( v26 )
    {
      for ( i = 0; i < v26; ++i )
      {
        v28 = i;
        LODWORD(v4) = *(_DWORD *)(16 * v28 + *(_QWORD *)(a1 + 2496) + 12) + (_DWORD)v4;
      }
    }
  }
  else
  {
    v23 = *(_QWORD *)(v22 + 544);
    LODWORD(v4) = *(_DWORD *)(v22 + 568);
  }
  v29 = MmMdlPageContentsState(v23, 2);
  v30 = v29;
  if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 && v9 && (v24 || v29 != 1) )
  {
    v31 = 0;
    goto LABEL_50;
  }
  v31 = 0;
  if ( (*(_DWORD *)(a1 + 68) & 0x800) != 0 && v9 && v29 != 1 || (unsigned int)(*(_DWORD *)(v25 + 48) - 1) <= 1 )
  {
LABEL_50:
    v32 = *(_QWORD *)(a1 + 2488);
    v33 = 0;
    if ( v32
      && (_DWORD)v4
      && ((*(_BYTE *)(v32 + 10) & 5) == 0
        ? (v33 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v32, 0, MmCached, 0, 0, 0x40000010u))
        : (v33 = *(char **)(v32 + 24)),
          !v33) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)-1073741670;
      }
      v35 = 14;
    }
    else
    {
      BufferAddress = 0;
      if ( *(_QWORD *)(a1 + 2488)
        || !(_DWORD)v4
        || (BufferAddress = (char *)RxLowIoGetBufferAddress((PRX_CONTEXT)v22)) != 0 )
      {
        v38 = *(_QWORD *)(a1 + 1040);
        if ( v38
          || (SmbBuffer = SmbMmAllocateSmbBuffer((unsigned int)v4, 1834185559),
              *(_QWORD *)(a1 + 1040) = SmbBuffer,
              (v38 = SmbBuffer) != 0) )
        {
          v40 = (char *)(v38 & 0xFFFFFFFFFFFFFFF8uLL);
          *(_QWORD *)(a1 + 1024) = 0;
          *(_QWORD *)(a1 + 1032) = v40;
          if ( *(_QWORD *)(a1 + 2488) )
            BufferAddress = &v33[*(unsigned int *)(*(_QWORD *)(a1 + 2496) + 8LL)];
          if ( *(_DWORD *)(v25 + 48) == 2 )
          {
            if ( (_DWORD)v4 )
            {
              do
              {
                v41 = (_DWORD)v4 - v31;
                if ( (unsigned int)v4 - v31 > 0x100000 )
                  v41 = 0x100000;
                HviEnterKernelAperture(v32, v30);
                memmove(&v40[v31], &BufferAddress[v31], v41);
                HviLeaveKernelAperture();
                v31 += 0x100000;
              }
              while ( v31 < (unsigned int)v4 );
            }
            LOWORD(v31) = 0;
          }
          else
          {
            memmove(v40, BufferAddress, (unsigned int)v4);
          }
          goto LABEL_84;
        }
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return (unsigned int)-1073741670;
        }
        v35 = 16;
      }
      else
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return (unsigned int)-1073741670;
        }
        v35 = 15;
      }
    }
    WPP_SF_q(v34->AttachedDevice, v35, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, a1);
    return (unsigned int)-1073741670;
  }
  *(_QWORD *)(a1 + 1032) = 0;
  *(_QWORD *)(a1 + 1024) = v23;
LABEL_84:
  v42 = (*(_DWORD *)(v1 + 120) & 0x1000000) == 0;
  v36 = 0;
  v144 = 0;
  v43 = 0;
  v126 = 0;
  v131 = 0;
  if ( !v42 )
  {
    v43 = (unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(a1 + 72), 3, 0, 2) != 0;
    v126 = v43;
  }
  if ( (*(_DWORD *)(v1 + 120) & 0x40000000) != 0 )
  {
    v129 = 2;
  }
  else
  {
    v129 = 0;
    v126 = v43;
  }
  v44 = *(_QWORD *)(a1 + 2496);
  v45 = 0;
  v46 = v119;
  v47 = 0;
  v132 = v44;
  v120 = 0;
  v123 = 0;
  if ( !v119 )
    return (unsigned int)v36;
  v48 = DWORD2(v141);
  v49 = DWORD1(v141);
  v50 = v141;
  v117 = DWORD2(v141);
  v121 = DWORD1(v141);
  v118 = v141;
  while ( 1 )
  {
    v51 = v46;
    if ( v46 > 0x10000 )
      v51 = 0x10000;
    v52 = *(_DWORD *)(a1 + 8LL * v47 + 2528);
    if ( v52 != -1 )
    {
      v53 = (unsigned int)(v52 + 1073741667);
      if ( (unsigned int)v53 > 0x2F || (v54 = 0x900281000001LL, !_bittest64(&v54, v53)) )
      {
        v55 = (unsigned int)(v52 + 1073741309);
        if ( (unsigned int)v55 > 0x3E || (v56 = 0x4208040000000601LL, !_bittest64(&v56, v55)) )
        {
          if ( v52 != -1073740964
            && v52 != -1073741507
            && (unsigned int)(v52 + 1073740698) > 1
            && v52 != -1073740672
            && v52 != -2146893022
            && v52 != -1073741073
            && v52 != -2147483631
            && v52 != -1073741810
            && v52 != -1073741202
            && v52 != -1069481983 )
          {
            if ( *(_QWORD *)(a1 + 2496) )
            {
              v57 = *(_DWORD *)(v44 + 12);
              if ( v50 + v51 >= v57 )
              {
                v118 = 0;
                v51 = v57 - v50;
                v50 = 0;
                v48 = 0;
                v49 += ((v57 - 1) >> 16) + 2;
                v44 += 16;
                v121 = v49;
                v132 = v44;
              }
              else
              {
                v118 = v50 + v51;
                v48 += ((v51 - 1) >> 16) + 1;
                v50 += v51;
              }
              v117 = v48;
              v47 = v49 + v48;
            }
            else
            {
              v47 += ((v51 - 1) >> 16) + 1;
            }
            goto LABEL_240;
          }
        }
      }
    }
    v58 = 0;
    v59 = *(_QWORD *)(a1 + 96);
    v145 = v116[0];
    v124 = v116[0];
    v60 = *(_QWORD *)(a1 + 88);
    v128 = v127;
    v140 = *(_QWORD *)(a1 + 1032);
    v61 = *(_QWORD *)(v60 + 424);
    SourceMdl = *(PMDL *)(a1 + 1024);
    v136 = 0;
    v130 = 0;
    v125 = 0;
    v62 = MRxSmbDetermineDdpSecurity(v61);
    v143 = v62;
    MRxSmbGetConfigurationBlock(v63);
    MRxSmbGetConfigurationBlock(v64);
    v66 = ((v51 - 1) >> 16) + 1;
    if ( v132 )
    {
      v67 = *(_DWORD *)(v132 + 12);
      v65 = v118;
      v68 = v117 + v121;
      v137 = v132;
      v122 = v118;
      if ( v67 - v118 <= v51 )
      {
        v51 = v67 - v118;
        v66 = ((unsigned int)(v67 - 1) >> 16) - v117 + 2;
      }
    }
    else
    {
      v137 = 0;
      v68 = HIWORD(v45);
      v122 = 0;
    }
    v69 = v145;
    if ( !v145 || (*(_DWORD *)(a1 + 68) & 0x1000800) == 0 || !v62 )
      goto LABEL_129;
    v70 = 0;
    if ( (*(_DWORD *)(a1 + 68) & 0x1000000) == 0 )
    {
      CryptoKeyAuthTagSize = *(_DWORD *)(v59 + 516);
      if ( CryptoKeyAuthTagSize <= 0xFFFF )
      {
        v74 = *(unsigned __int16 *)(v59 + 520);
        goto LABEL_128;
      }
      v36 = -1073741675;
LABEL_230:
      v101 = v130;
      goto LABEL_231;
    }
    CryptoKeyNonceSize = SmbCryptoGetCryptoKeyNonceSize(*(_QWORD *)(v59 + 528), v145, v65);
    v72 = CryptoKeyNonceSize;
    if ( CryptoKeyNonceSize > 0xFFFF
      || (CryptoKeyAuthTagSize = SmbCryptoGetCryptoKeyAuthTagSize(*(_QWORD *)(v59 + 528)), CryptoKeyAuthTagSize > 0xFFFF) )
    {
      v36 = -1073741675;
      goto LABEL_230;
    }
    v69 = v145;
    v74 = v72;
LABEL_128:
    v125 = v74;
    v58 = 1;
    LOWORD(v31) = CryptoKeyAuthTagSize;
    v69 += ((v74 + CryptoKeyAuthTagSize + 7) & 0xFFF8) + 25;
    v145 = v69;
LABEL_129:
    v75 = 0;
    v76 = (unsigned int)v69 + 112;
    v131 = 0;
    v133 = v76;
    v142 = 0;
    if ( !*(_BYTE *)(a1 + 1056) )
    {
      ImplicitExchangeBuffer = 0;
      if ( !(_DWORD)v76 )
        goto LABEL_133;
      ImplicitExchangeBuffer = SmbCeAllocateImplicitExchangeBuffer(a1, (unsigned int)(v76 + 32));
      if ( ImplicitExchangeBuffer )
      {
        LODWORD(v76) = v133;
LABEL_133:
        *(_BYTE *)(a1 + 1056) = 1;
        v142 = ImplicitExchangeBuffer != 0;
        v70 = a1 + 1064;
        v75 = (ImplicitExchangeBuffer + 32) & -(__int64)(ImplicitExchangeBuffer != 0);
        if ( a1 != -1064 )
          goto LABEL_139;
      }
    }
    Pool2 = ExAllocatePool2(66, ((unsigned int)v133 + 1431LL) & 0xFFFFFFFFFFFFFFF8uLL, 1834181463);
    v70 = Pool2;
    if ( !Pool2 )
    {
      v70 = 0;
LABEL_229:
      v36 = -1073741670;
      goto LABEL_230;
    }
    LODWORD(v76) = v133;
    if ( (_DWORD)v133 )
      v75 = Pool2 + 1424;
LABEL_139:
    memset((void *)v75, 0, (unsigned int)v76);
    if ( !v70 || !v75 )
      goto LABEL_229;
    v79 = v120;
    *(_DWORD *)(v70 + 1384) = v68;
    v80 = v137;
    *(_DWORD *)(v70 + 1388) = v66;
    v81 = v122;
    *(_DWORD *)(v70 + 1392) = v79;
    *(_QWORD *)(v70 + 1408) = v80;
    *(_DWORD *)(v70 + 1416) = v81;
    v135 = 0;
    *(_DWORD *)(v70 + 1396) = v51;
    *(_QWORD *)(v70 + 1400) = 0;
    *(_DWORD *)(v70 + 1420) = 1;
    SmbCeBuildSmb2Header(a1, v75, 64);
    *(_WORD *)(v75 + 12) = 9;
    if ( v145 )
    {
      *(_WORD *)(v75 + 104) = 112;
      if ( !v58 )
      {
        *(_DWORD *)(v75 + 96) = v128;
        *(_WORD *)(v75 + 106) = v145;
LABEL_160:
        v31 = v133;
        *(_DWORD *)(v75 + 100) = v51;
        goto LABEL_162;
      }
      *(_DWORD *)(v75 + 96) = 3;
      if ( (((_BYTE)v75 + 112) & 7) != 0 )
        __int2c();
      *(_WORD *)(v75 + 114) = v124;
      *(_DWORD *)(v75 + 116) = v128;
      *(_WORD *)(v75 + 120) = 0;
      v82 = *(_WORD *)(v75 + 106);
      if ( (unsigned __int16)(v82 + 16) < v82 )
      {
        *(_WORD *)(v75 + 106) = -1;
        __int2c();
      }
      else
      {
        *(_WORD *)(v75 + 106) = v82 + 16;
      }
      v83 = v125;
      v84 = (*(_DWORD *)(a1 + 68) & 0x1000000) != 0;
      v135 = v75 + 128;
      *(_WORD *)(v75 + 128) = 2 - v84;
      *(_WORD *)(v75 + 130) = v31;
      *(_DWORD *)(v75 + 132) = v83;
      v85 = *(_WORD *)(v75 + 106);
      v86 = v85 + ((v83 + v31 + 7) & 0xFFF8) + 8;
      if ( v86 < v85 )
      {
        *(_WORD *)(v75 + 106) = -1;
        __int2c();
      }
      else
      {
        *(_WORD *)(v75 + 106) = v86;
      }
      ++*(_WORD *)(v75 + 120);
      v87 = *(_WORD *)(v75 + 106);
      if ( (v87 & 7) != 0 )
      {
        if ( (unsigned __int16)(v87 + 7) < v87 )
        {
          __int2c();
LABEL_156:
          v88 = *(_WORD *)(v75 + 106);
          if ( (unsigned __int16)(v145 + v88) < v88 )
          {
            *(_WORD *)(v75 + 106) = -1;
            __int2c();
          }
          else
          {
            *(_WORD *)(v75 + 106) = v145 + v88;
          }
          goto LABEL_160;
        }
        v87 = (v87 + 7) & 0xFFF8;
      }
      *(_WORD *)(v75 + 112) = v87;
      goto LABEL_156;
    }
    *(_DWORD *)(v75 + 68) = v51;
    v31 = 112;
    *(_WORD *)(v75 + 66) = 112;
LABEL_162:
    v89 = v139;
    *(_WORD *)(v75 + 64) = 49;
    *(_OWORD *)(v75 + 80) = *(_OWORD *)(v89 + 28);
    if ( v126 )
      *(_DWORD *)(v75 + 108) |= 2u;
    if ( v129 )
      *(_DWORD *)(v75 + 108) |= 1u;
    if ( v80 )
    {
      *(_QWORD *)(v75 + 72) = *(_QWORD *)v80 + v81;
      if ( v51 >= *(_DWORD *)(v80 + 12) - (int)v81 )
        v90 = *(_DWORD *)(v80 + 12) - v81;
      else
        v90 = v51;
      v91 = v132;
      v92 = v90 + v118;
      *(_DWORD *)(v75 + 68) = v90;
      v118 = v92;
      v93 = *(_DWORD *)(v91 + 12);
      if ( v92 == v93 )
      {
        v118 = 0;
        v121 += ((unsigned int)(v93 - 1) >> 16) + 2;
        v132 = v80 + 16;
        v117 = 0;
      }
      else
      {
        v117 += ((v90 - 1) >> 16) + 1;
      }
      v94 = v120;
    }
    else
    {
      v94 = v120;
      v90 = v51;
      v95 = v120;
      *(_DWORD *)(v75 + 68) = v51;
      *(_QWORD *)(v75 + 72) = v138 + v95;
    }
    if ( v145 )
    {
      *(_DWORD *)(v75 + 100) = v90;
      *(_DWORD *)(v75 + 68) = 0;
    }
    Mdl2 = (struct _MDL *)RxAllocateMdl2(v75, v31, 0, 0, 0);
    v136 = Mdl2;
    v97 = Mdl2;
    if ( !Mdl2 )
      goto LABEL_229;
    MmBuildMdlForNonPagedPool(Mdl2);
    if ( v142 )
      v97->MdlFlags |= 0x1000u;
    if ( SourceMdl )
    {
      if ( v80 )
        v98 = *(_DWORD *)(v80 + 8) + v122;
      else
        v98 = v94;
      v99 = (char *)SourceMdl->StartVa + v98 + (unsigned __int64)SourceMdl->ByteOffset;
    }
    else
    {
      v99 = (char *)(v140 + v94);
    }
    v100 = (struct _MDL *)RxAllocateMdl2(v99, v51, 0, 0, 0);
    v101 = v100;
    if ( !v100 )
    {
      v36 = -1073741670;
      goto LABEL_231;
    }
    if ( SourceMdl )
    {
      if ( v80 )
        v102 = *(_DWORD *)(v80 + 8) + v122;
      else
        v102 = v120;
      IoBuildPartialMdl(
        SourceMdl,
        v100,
        (char *)SourceMdl->StartVa + v102 + (unsigned __int64)SourceMdl->ByteOffset,
        v51);
    }
    else
    {
      MmBuildMdlForNonPagedPool(v100);
    }
    if ( !v145 )
    {
      v109 = v31 + v51;
      LOWORD(v115) = 0;
      LOWORD(v31) = 0;
      LODWORD(v114) = 0;
      Priority[0] = v51;
      v97->Next = v101;
      v36 = SmbCseInitializeBufferContextWithMemoryRegistration(
              v70,
              a1,
              v97,
              v109,
              0,
              *(_QWORD *)Priority,
              0,
              v114,
              v115,
              4);
LABEL_219:
      if ( v36 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, a1, v70);
        }
        goto LABEL_231;
      }
      goto LABEL_224;
    }
    LOWORD(v115) = v145;
    LODWORD(v114) = v51;
    Priority[0] = 0;
    v103 = SmbCseInitializeBufferContextWithMemoryRegistration(
             v70,
             a1,
             v97,
             v31,
             0,
             *(_QWORD *)Priority,
             v101,
             v114,
             v115,
             16388);
    LOWORD(v31) = 0;
    v36 = v103;
    v104 = *(_DWORD *)(v70 + 4);
    if ( (v104 & 0x8000) != 0 && v143 )
    {
      if ( SourceMdl )
        __int2c();
      if ( (v101->MdlFlags & 5) != 0 )
        MappedSystemVa = v101->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v101, 0, MmCached, 0, 0, 0x40000010u);
      if ( (v101->MdlFlags & 5) != 0 )
        v106 = v101->MappedSystemVa;
      else
        v106 = MmMapLockedPagesSpecifyCache(v101, 0, MmCached, 0, 0, 0x40000010u);
      v36 = SmbCryptoEncryptRdmaPayload(
              *(_QWORD *)(*(_QWORD *)(a1 + 96) + 528LL),
              v135 + 8,
              *(unsigned __int16 *)(v135 + 2),
              *(unsigned __int16 *)(v135 + 2) + v135 + 8,
              *(unsigned __int16 *)(v135 + 4),
              v106,
              v51,
              MappedSystemVa);
      if ( v36 < 0 )
      {
        v107 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v108 = 10;
          goto LABEL_210;
        }
        goto LABEL_231;
      }
    }
    else
    {
      if ( (v104 & 0x1000) == 0 || !v143 )
        goto LABEL_219;
      v36 = Smb2ComputeOutgoingSignatureForRdmaBuffer(v70, v135);
      if ( v36 < 0 )
      {
        v107 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v108 = 11;
LABEL_210:
          WPP_SF_qqD(v107->AttachedDevice, v108, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, a1, v70, v36);
        }
LABEL_231:
        RxFreeMdl(v101);
        RxFreeMdl(v136);
        if ( v70 )
        {
          if ( *(_QWORD *)(v70 + 1400) )
            RxUnlockAndFreeMdlChain();
          if ( v70 == a1 + 1064 )
            *(_BYTE *)(a1 + 1056) = 0;
          else
            ExFreePoolWithTag((PVOID)v70, 0x6D536357u);
        }
        goto LABEL_246;
      }
    }
LABEL_224:
    v110 = *(_DWORD *)(v70 + 1388);
    *(_DWORD *)(v70 + 80) = v110;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
        v70,
        *(_DWORD *)(v70 + 1384),
        v110);
    }
    *(_QWORD *)(v70 + 88) = v75;
    v131 = v70;
    v51 = *(_DWORD *)(v70 + 1396);
    v111 = *(_DWORD *)(v70 + 1388);
    v36 = SmbCseSubmitBufferContext(v70);
    if ( v36 < 0 )
      break;
    v45 = v120;
    v47 = v111 + v123;
    v49 = v121;
    v48 = v117;
    v50 = v118;
    v44 = v132;
    v144 = 1;
LABEL_240:
    v45 += v51;
    v46 = v119 - v51;
    v123 = v47;
    v119 = v46;
    v120 = v45;
    if ( !v46 )
      goto LABEL_246;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_DiqD(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      (unsigned int)WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
      v51,
      v120,
      v70,
      v36);
  }
LABEL_246:
  if ( v144 == 1 )
    return 259;
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x140031250  push    rbx
0x140031252  push    rbp
0x140031253  push    rsi
0x140031254  push    rdi
0x140031255  push    r12
0x140031257  push    r13
0x140031259  push    r14
0x14003125b  push    r15
0x14003125d  sub     rsp, 108h
0x140031264  mov     r13, [rcx+30h]
0x140031268  mov     rdi, rcx
0x14003126b  mov     rbx, [rcx+9C0h]
0x140031272  xor     ebp, ebp
0x140031274  xorps   xmm0, xmm0
0x140031277  mov     [rsp+148h+arg_0], r13
0x14003127f  movdqu  [rsp+148h+var_60], xmm0
0x140031288  mov     rax, [r13+48h]
0x14003128c  mov     rax, [rax+30h]
0x140031290  mov     [rsp+148h+var_78], rax
0x140031298  mov     rax, [rcx+60h]
0x14003129c  mov     rcx, [rcx+58h]
0x1400312a0  mov     r12, [rax+188h]
0x1400312a7  mov     [rsp+148h+var_CC], ebp
0x1400312ab  mov     [rsp+148h+var_F8], bp
0x1400312b0  mov     rcx, [rcx+1A8h]
0x1400312b7  call    cs:__imp_MRxSmbDetermineDdpSecurity
0x1400312be  nop     dword ptr [rax+rax+00h]
0x1400312c3  mov     r14b, al
0x1400312c6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400312cd  lea     rax, WPP_GLOBAL_Control
0x1400312d4  lea     r15d, [rbp+1]
0x1400312d8  cmp     rcx, rax
0x1400312db  jz      short loc_140031315
0x1400312dd  mov     edx, [rcx+2Ch]
0x1400312e0  test    r15b, dl
0x1400312e3  jz      short loc_140031315
0x1400312e5  cmp     [rcx+29h], r15b
0x1400312e9  jb      short loc_140031315
0x1400312eb  mov     rax, [r13+38h]
0x1400312ef  lea     edx, [rbp+14h]
0x1400312f2  mov     rcx, [rcx+18h]
0x1400312f6  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x1400312fd  add     rax, 168h
0x140031303  mov     r9, r13
0x140031306  mov     qword ptr [rsp+148h+Priority], rax
0x14003130b  mov     qword ptr [rsp+148h+BugCheckOnFailure], rdi
0x140031310  call    WPP_SF_qqZ
0x140031315  test    rbx, rbx
0x140031318  jz      short loc_140031349
0x14003131a  mov     edx, [rdi+9D8h]
0x140031320  mov     r8d, ebp
0x140031323  mov     [rsp+148h+var_EC], ebp
0x140031327  mov     ecx, ebp
0x140031329  test    edx, edx
0x14003132b  jz      short loc_140031344
0x14003132d  mov     eax, ecx
0x14003132f  add     ecx, r15d
0x140031332  shl     rax, 4
0x140031336  add     r8d, [rax+rbx+0Ch]
0x14003133b  cmp     ecx, edx
0x14003133d  jb      short loc_14003132D
0x14003133f  mov     [rsp+148h+var_EC], r8d
0x140031344  mov     rax, [rbx]
0x140031347  jmp     short loc_14003135B
0x140031349  mov     eax, [r13+238h]
0x140031350  mov     [rsp+148h+var_EC], eax
0x140031354  mov     rax, [r13+230h]
0x14003135b  lea     rsi, [rdi+0A0h]
0x140031362  mov     [rsp+148h+var_80], rax
0x14003136a  mov     rbx, [rsi]
0x14003136d  cmp     rbx, rsi
0x140031370  jz      loc_140031404
0x140031376  add     rbx, 0FFFFFFFFFFFFFFF8h
0x14003137a  jz      loc_140031404
0x140031380  lea     r15, [rdi+428h]
0x140031387  xor     r13d, r13d
0x14003138a  mov     rcx, [rbx+8]
0x14003138e  mov     rbp, r13
0x140031391  cmp     rcx, rsi
0x140031394  mov     rdx, rbx
0x140031397  lea     rax, [rcx-8]
0x14003139b  mov     rcx, rdi
0x14003139e  cmovnz  rbp, rax
0x1400313a2  call    ProcessChunkAndUpdateBlockState
0x1400313a7  mov     rcx, rbx
0x1400313aa  call    cs:__imp_SmbCseFinalizeBufferContext
0x1400313b1  nop     dword ptr [rax+rax+00h]
0x1400313b6  mov     rcx, [rbx+578h]
0x1400313bd  test    rcx, rcx
0x1400313c0  jz      short loc_1400313CE
0x1400313c2  call    cs:__imp_RxUnlockAndFreeMdlChain
0x1400313c9  nop     dword ptr [rax+rax+00h]
0x1400313ce  cmp     rbx, r15
0x1400313d1  jz      short loc_1400313E9
0x1400313d3  mov     edx, 6D536357h; Tag
0x1400313d8  mov     rcx, rbx; P
0x1400313db  call    cs:__imp_ExFreePoolWithTag
0x1400313e2  nop     dword ptr [rax+rax+00h]
0x1400313e7  jmp     short loc_1400313F0
0x1400313e9  mov     [rdi+420h], r13b
0x1400313f0  mov     rbx, rbp
0x1400313f3  test    rbp, rbp
0x1400313f6  jnz     short loc_14003138A
0x1400313f8  mov     r13, [rsp+148h+arg_0]
0x140031400  lea     r15d, [rbp+1]
0x140031404  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14003140b  nop     dword ptr [rax+rax+00h]
0x140031410  mov     ebx, 10000h
0x140031415  mov     r9d, 2
0x14003141b  cmp     [rax+4], ebp
0x14003141e  jbe     loc_1400314C7
0x140031424  mov     eax, [r12+140h]
0x14003142c  sub     eax, r9d
0x14003142f  cmp     eax, r15d
0x140031432  ja      loc_1400314C7
0x140031438  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14003143f  nop     dword ptr [rax+rax+00h]
0x140031444  mov     ecx, [rsp+148h+var_EC]
0x140031448  cmp     ecx, [rax+4]
0x14003144b  jb      short loc_1400314C1
0x14003144d  mov     eax, [rdi+44h]
0x140031450  bt      eax, 18h
0x140031454  jnb     short loc_14003146E
0x140031456  test    r14b, r14b
0x140031459  jz      short loc_14003146E
0x14003145b  mov     rax, [rdi+48h]
0x14003145f  mov     ecx, [rax+2ECh]
0x140031465  test    r15b, cl
0x140031468  jz      short loc_1400314C1
0x14003146a  mov     ecx, [rsp+148h+var_EC]
0x14003146e  mov     eax, [rdi+44h]
0x140031471  bt      eax, 0Bh
0x140031475  jnb     short loc_14003147C
0x140031477  test    r14b, r14b
0x14003147a  jnz     short loc_1400314C1
0x14003147c  cmp     [rdi+38h], rbp
0x140031480  jnz     short loc_1400314C1
0x140031482  mov     rax, [rdi+48h]
0x140031486  cmp     ecx, ebx
0x140031488  mov     edx, ecx
0x14003148a  mov     rcx, r12
0x14003148d  cmova   edx, ebx
0x140031490  xor     r9d, r9d
0x140031493  mov     r8b, [rax+2E0h]
0x14003149a  lea     rax, [rsp+148h+var_CC]
0x14003149f  mov     qword ptr [rsp+148h+Priority], rax
0x1400314a4  lea     rax, [rsp+148h+var_F8]
0x1400314a9  shr     r8b, 6
0x1400314ad  and     r8b, r15b
0x1400314b0  mov     qword ptr [rsp+148h+BugCheckOnFailure], rax
0x1400314b5  call    cs:__imp_SmbCseEstimateMemoryDescriptorSize
0x1400314bc  nop     dword ptr [rax+rax+00h]
0x1400314c1  mov     r9d, 2
0x1400314c7  cmp     [rsp+148h+var_F8], bp
0x1400314cc  mov     rsi, [rdi+30h]
0x1400314d0  mov     rbx, [rdi+9B8h]
0x1400314d7  setnz   r15b
0x1400314db  mov     rax, [rsi+40h]
0x1400314df  mov     r12, [rax+38h]
0x1400314e3  test    rbx, rbx
0x1400314e6  jz      short loc_140031518
0x1400314e8  mov     edx, [rdi+9D8h]
0x1400314ee  xor     eax, eax
0x1400314f0  test    edx, edx
0x1400314f2  jz      short loc_140031525
0x1400314f4  mov     r8, [rdi+9C0h]
0x1400314fb  mov     ecx, eax
0x1400314fd  mov     eax, ecx
0x1400314ff  inc     ecx
0x140031501  shl     rax, 4
0x140031505  add     ebp, [rax+r8+0Ch]
0x14003150a  cmp     ecx, edx
0x14003150c  jb      short loc_1400314FD
0x14003150e  mov     r13, [rsp+148h+arg_0]
0x140031516  jmp     short loc_140031525
0x140031518  mov     rbx, [rsi+220h]
0x14003151f  mov     ebp, [rsi+238h]
0x140031525  mov     edx, r9d
0x140031528  mov     rcx, rbx
0x14003152b  call    cs:__imp_MmMdlPageContentsState
0x140031532  nop     dword ptr [rax+rax+00h]
0x140031537  mov     ecx, [rdi+44h]
0x14003153a  mov     r8d, 1; CacheType
0x140031540  mov     edx, eax
0x140031542  bt      ecx, 18h
0x140031546  jnb     short loc_140031557
0x140031548  test    r14b, r14b
0x14003154b  jz      short loc_140031557
0x14003154d  test    r15b, r15b
0x140031550  jnz     short loc_14003158D
0x140031552  cmp     eax, r8d
0x140031555  jnz     short loc_14003158D
0x140031557  mov     eax, [rdi+44h]
0x14003155a  xor     r15d, r15d
0x14003155d  bt      eax, 0Bh
0x140031561  jnb     short loc_14003156D
0x140031563  test    r14b, r14b
0x140031566  jz      short loc_14003156D
0x140031568  cmp     edx, r8d
0x14003156b  jnz     short loc_140031590
0x14003156d  mov     eax, [r12+30h]
0x140031572  sub     eax, r8d
0x140031575  cmp     eax, r8d
0x140031578  jbe     short loc_140031590
0x14003157a  mov     [rdi+408h], r15
0x140031581  mov     [rdi+400h], rbx
0x140031588  jmp     loc_14003174A
0x14003158d  xor     r15d, r15d
0x140031590  mov     rcx, [rdi+9B8h]; MemoryDescriptorList
0x140031597  mov     rbx, r15
0x14003159a  test    rcx, rcx
0x14003159d  jz      short loc_140031617
0x14003159f  test    ebp, ebp
0x1400315a1  jz      short loc_140031617
0x1400315a3  test    byte ptr [rcx+0Ah], 5
0x1400315a7  jz      short loc_1400315AF
0x1400315a9  mov     rbx, [rcx+18h]
0x1400315ad  jmp     short loc_1400315D0
0x1400315af  mov     [rsp+148h+Priority], 40000010h; Priority
0x1400315b7  xor     r9d, r9d; RequestedAddress
0x1400315ba  xor     edx, edx; AccessMode
0x1400315bc  mov     [rsp+148h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x1400315c1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400315c8  nop     dword ptr [rax+rax+00h]
0x1400315cd  mov     rbx, rax
0x1400315d0  test    rbx, rbx
0x1400315d3  jnz     short loc_140031617
0x1400315d5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400315dc  lea     rax, WPP_GLOBAL_Control
0x1400315e3  cmp     rcx, rax
0x1400315e6  jz      short loc_14003160D
0x1400315e8  mov     eax, [rcx+2Ch]
0x1400315eb  lea     edx, [rbx+1]
0x1400315ee  test    dl, al
0x1400315f0  jz      short loc_14003160D
0x1400315f2  cmp     [rcx+29h], dl
0x1400315f5  jb      short loc_14003160D
0x1400315f7  lea     edx, [rbx+0Eh]
0x1400315fa  mov     rcx, [rcx+18h]
0x1400315fe  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x140031605  mov     r9, rdi
0x140031608  call    WPP_SF_q
0x14003160d  mov     ebx, 0C000009Ah
0x140031612  jmp     loc_140032403
0x140031617  mov     r14, r15
0x14003161a  cmp     [rdi+9B8h], r15
0x140031621  jnz     short loc_140031667
0x140031623  test    ebp, ebp
0x140031625  jz      short loc_140031667
0x140031627  mov     rcx, rsi; RxContext
0x14003162a  call    cs:__imp_RxLowIoGetBufferAddress
0x140031631  nop     dword ptr [rax+rax+00h]
0x140031636  mov     r14, rax
0x140031639  test    rax, rax
0x14003163c  jnz     short loc_140031667
0x14003163e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140031645  lea     rax, WPP_GLOBAL_Control
0x14003164c  cmp     rcx, rax
0x14003164f  jz      short loc_14003160D
0x140031651  mov     eax, [rcx+2Ch]
0x140031654  lea     edx, [r14+1]
0x140031658  test    dl, al
0x14003165a  jz      short loc_14003160D
0x14003165c  cmp     [rcx+29h], dl
0x14003165f  jb      short loc_14003160D
0x140031661  lea     edx, [r14+0Fh]
0x140031665  jmp     short loc_1400315FA
0x140031667  mov     rsi, [rdi+410h]
0x14003166e  test    rsi, rsi
0x140031671  jnz     short loc_1400316CB
0x140031673  mov     edx, 6D537357h
0x140031678  mov     ecx, ebp
0x14003167a  call    cs:__imp_SmbMmAllocateSmbBuffer
0x140031681  nop     dword ptr [rax+rax+00h]
0x140031686  mov     [rdi+410h], rax
0x14003168d  mov     rsi, rax
0x140031690  test    rax, rax
0x140031693  jnz     short loc_1400316CB
0x140031695  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003169c  lea     rax, WPP_GLOBAL_Control
0x1400316a3  cmp     rcx, rax
0x1400316a6  jz      loc_14003160D
0x1400316ac  mov     eax, [rcx+2Ch]
0x1400316af  lea     edx, [rsi+1]
0x1400316b2  test    dl, al
0x1400316b4  jz      loc_14003160D
0x1400316ba  cmp     [rcx+29h], dl
0x1400316bd  jb      loc_14003160D
0x1400316c3  lea     edx, [rsi+10h]
0x1400316c6  jmp     loc_1400315FA
0x1400316cb  and     rsi, 0FFFFFFFFFFFFFFF8h
0x1400316cf  mov     [rdi+400h], r15
0x1400316d6  mov     [rdi+408h], rsi
0x1400316dd  cmp     [rdi+9B8h], r15
0x1400316e4  jz      short loc_1400316F4
0x1400316e6  mov     rax, [rdi+9C0h]
0x1400316ed  mov     r14d, [rax+8]
0x1400316f1  add     r14, rbx
0x1400316f4  cmp     dword ptr [r12+30h], 2
0x1400316fa  jnz     short loc_14003173C
  ... truncated ...
```
