# NtfsEncryptDecryptOnline

- ea: `0x1400cc78c`
- end: `0x1400ceb84`
- name: `NtfsEncryptDecryptOnline`
- size: `9208`
- prototype: ``
- caller_count: `1`
- callee_count: `67`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027af58`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14000e220`
- `0x1400100b0`
- `0x140010be0`
- `0x140012e70`
- `0x140015b90`
- `0x14001d8f0`
- `0x14001e2f0`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x140024070`
- `0x140025bd0`
- `0x140025c10`
- `0x1400286d0`
- `0x14002b680`
- `0x14002bc00`
- `0x140030850`
- `0x140031410`
- `0x14003e5b4`
- `0x14004062c`
- `0x1400410a8`
- `0x14004608c`
- `0x1400593e0`
- `0x140059740`
- `0x1400cc78c`
- `0x140125100`
- `0x140126220`
- `0x140128da0`
- `0x14012be50`
- `0x14013ce30`
- `0x1401403d0`
- `0x140158b40`
- `0x1401597b8`
- `0x14015a5c0`
- `0x140160c30`
- `0x140160ee0`
- `0x140162110`
- `0x1401623c0`
- `0x140163fc8`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0bf1`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0bf1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ccced`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ccced`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ccd01`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ccd01`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400ccb32`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400cd6fb`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400ccb32`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400cd6fb`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdb55`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdcb7`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdb55`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdcb7`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdb6d`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdccf`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdb6d`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdccf`
- `ntoskrnl!KeClearEvent` at `0x1400cceda`
- `ntoskrnl!KeClearEvent` at `0x1400cceda`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ccf22`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ccf22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccd17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce926`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0c02`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccd17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce926`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0c02`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07fe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c0818`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c0818`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`

## pseudocode

```c
__int64 __fastcall NtfsEncryptDecryptOnline(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r15
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 v11; // r9
  char v12; // di
  __int64 v13; // rdx
  unsigned __int64 m; // rcx
  __int64 v15; // r8
  unsigned __int8 v16; // di
  int v17; // r12d
  char v18; // r9
  int v19; // r15d
  __int64 v20; // r9
  __int64 v21; // r11
  unsigned __int16 v22; // ax
  __int64 v23; // r8
  _DWORD *v24; // r12
  __int64 v25; // r8
  __int64 v26; // r9
  char v27; // r15
  int v28; // r10d
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  ULONG v32; // r12d
  PVOID PoolWithTag; // r15
  PVOID v34; // rax
  struct _MDL *v35; // rax
  struct _MDL *v36; // r12
  unsigned int v37; // r12d
  unsigned __int8 v38; // r15
  __int64 v39; // rcx
  char v40; // r15
  __int16 *Scb; // r12
  char v42; // r15
  __int64 v43; // r8
  char v44; // di
  LONGLONG *v45; // rbx
  int v46; // ecx
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  char v55; // di
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rbx
  int v60; // eax
  int v61; // edx
  __int64 v62; // rbx
  char v63; // r15
  __int64 v64; // rcx
  char v65; // di
  __int64 v66; // rcx
  __int64 v67; // rcx
  char v68; // r15
  __int64 v69; // rax
  char v70; // di
  __int64 v71; // rdx
  bool v72; // zf
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // r8
  int v76; // r12d
  int v77; // eax
  unsigned int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rcx
  char v82; // di
  char v83; // cl
  LONGLONG v84; // r12
  LONGLONG v85; // rdx
  int v86; // ebx
  unsigned int v87; // ebx
  int *v88; // rdx
  char v89; // di
  __int16 *v90; // rbx
  int v91; // eax
  char v92; // al
  int v93; // r9d
  int v94; // r8d
  __int64 v95; // rcx
  __int64 v96; // r9
  __int64 v97; // rax
  unsigned int v98; // eax
  __int64 v99; // rdx
  __int64 v100; // r9
  int v101; // eax
  __int64 v102; // r9
  int v103; // eax
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  unsigned int i; // eax
  __int64 v108; // rcx
  char v109; // al
  __int64 v110; // rcx
  unsigned int v111; // r8d
  __int64 v112; // rdx
  unsigned int k; // eax
  __int64 v114; // rax
  __int64 v115; // rcx
  PVOID v116; // r15
  unsigned int v117; // eax
  __int64 v118; // rdx
  __int64 n; // rcx
  int SectorCountFromStartingLbn; // [rsp+C0h] [rbp-2B0h]
  int Index; // [rsp+C8h] [rbp-2A8h]
  int Indexb; // [rsp+C8h] [rbp-2A8h]
  int Indexa; // [rsp+C8h] [rbp-2A8h]
  int Indexc; // [rsp+C8h] [rbp-2A8h]
  size_t Size; // [rsp+D0h] [rbp-2A0h]
  __int64 v127; // [rsp+118h] [rbp-258h] BYREF
  int v128; // [rsp+120h] [rbp-250h]
  int v129; // [rsp+124h] [rbp-24Ch]
  int v130; // [rsp+128h] [rbp-248h]
  char v131; // [rsp+12Ch] [rbp-244h]
  int v132; // [rsp+130h] [rbp-240h]
  PVOID P; // [rsp+138h] [rbp-238h] BYREF
  PMDL Mdl; // [rsp+140h] [rbp-230h] BYREF
  int v135; // [rsp+148h] [rbp-228h]
  __int64 SectorCountFromLbn; // [rsp+150h] [rbp-220h] BYREF
  int v137; // [rsp+158h] [rbp-218h]
  unsigned int v138; // [rsp+15Ch] [rbp-214h]
  int v139; // [rsp+160h] [rbp-210h]
  __int16 *v140; // [rsp+168h] [rbp-208h]
  signed int v141; // [rsp+170h] [rbp-200h]
  __int64 v142; // [rsp+178h] [rbp-1F8h]
  int *v143; // [rsp+180h] [rbp-1F0h]
  __int16 v144; // [rsp+188h] [rbp-1E8h]
  LONGLONG v145; // [rsp+190h] [rbp-1E0h]
  __int64 v146; // [rsp+198h] [rbp-1D8h] BYREF
  _DWORD *v147; // [rsp+1A0h] [rbp-1D0h]
  __int64 v148; // [rsp+1A8h] [rbp-1C8h]
  unsigned int v149; // [rsp+1B0h] [rbp-1C0h]
  __int64 v150[2]; // [rsp+1B8h] [rbp-1B8h] BYREF
  int v151; // [rsp+1C8h] [rbp-1A8h] BYREF
  __int64 Lbn; // [rsp+1D0h] [rbp-1A0h] BYREF
  __int64 v153; // [rsp+1D8h] [rbp-198h] BYREF
  __int64 v154; // [rsp+1E0h] [rbp-190h] BYREF
  __int64 v155; // [rsp+1E8h] [rbp-188h]
  LONGLONG v156; // [rsp+1F0h] [rbp-180h] BYREF
  LONGLONG j; // [rsp+1F8h] [rbp-178h]
  __int64 v158; // [rsp+200h] [rbp-170h]
  __int128 v159; // [rsp+208h] [rbp-168h] BYREF
  __int128 v160; // [rsp+218h] [rbp-158h]
  __int64 v161[12]; // [rsp+228h] [rbp-148h] BYREF
  LONGLONG v162; // [rsp+288h] [rbp-E8h]
  _OWORD v163[3]; // [rsp+298h] [rbp-D8h] BYREF
  __int64 v164; // [rsp+2C8h] [rbp-A8h]
  _DWORD v165[38]; // [rsp+2D8h] [rbp-98h] BYREF

  v5 = a4;
  LODWORD(v8) = 0;
  memset(v161, 0, 0x58u);
  v9 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 96LL);
  v150[1] = v9;
  Mdl = 0;
  BYTE5(v127) = 0;
  P = 0;
  v129 = 0;
  v135 = 0;
  memset(v165, 0, 0x5Cu);
  v159 = 0;
  v160 = 0;
  v146 = 0;
  v139 = 0;
  SectorCountFromLbn = 0;
  Lbn = 0;
  LOBYTE(v128) = 0;
  v140 = 0;
  LODWORD(v127) = 128;
  *(_QWORD *)(a1 + 16) |= 0x80000000uLL;
  BYTE4(v127) = 1;
  v12 = 0x80;
  if ( *(_QWORD *)(a3 + 16) )
  {
    if ( (a5 & 0x2000000) != 0 || (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v10, v11);
      v12 = -126;
    }
    else
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingShared(a1, a3, v10, 0);
      v12 = -124;
    }
    LOBYTE(v127) = v12;
  }
  NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
  v16 = v12 | 1;
  LOBYTE(v127) = v16;
  v17 = *(_DWORD *)(a3 + 512);
  v18 = 2;
  if ( (v17 & 2) != 0 )
  {
    v13 = 0;
    if ( v5 )
    {
      v19 = *(_DWORD *)(v5 + 4);
      if ( (v19 & 0x8000000) == 0 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v20 = *(_QWORD *)(a3 + 192);
          v21 = *(_QWORD *)(v20 + 248);
          v22 = *(_WORD *)(v21 + 6);
          if ( v22 > 0x40u || (v22 & 1) != 0 )
          {
            v22 = 0;
            v132 = 0;
          }
          else
          {
            v132 = *(unsigned __int16 *)(v21 + 6);
          }
          LOWORD(j) = v22;
          v158 = v21 + 32;
          McTemplateU0ppwwpipdzdd_EtwWriteTransfer(
            *(_QWORD *)(a3 + 184),
            v22 >> 1,
            (unsigned int)KeGetCurrentThread(),
            v20,
            *(_WORD *)(v20 + 7872) >> 1,
            *(_QWORD *)(v20 + 7880),
            v22 >> 1,
            v21 + 32,
            *(_QWORD *)(a3 + 184),
            *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
            a3,
            *(_DWORD *)(a3 + 256),
            *(_QWORD *)(a3 + 272),
            v17,
            v19);
        }
        LODWORD(v8) = -1073741790;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_276;
        v23 = 809897;
LABEL_19:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)v8, v23);
        goto LABEL_276;
      }
      v5 = a4;
    }
  }
  if ( (v16 & 4) != 0 )
  {
    v24 = (_DWORD *)(v5 + 8);
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      NtfsReleasePagingResourcePriv(m, a3);
      LOBYTE(v127) = v16 & 0xFB;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      LOBYTE(v127) = v16 & 0xFA;
      LOBYTE(v25) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v25, v26);
      LOBYTE(v127) = v16 & 0xF8 | 2;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v16 = v16 & 0xF8 | 3;
      LOBYTE(v127) = v16;
      v18 = 2;
    }
  }
  else
  {
    v24 = (_DWORD *)(a4 + 8);
  }
  v27 = v16;
  if ( (*v24 & 0x100) == 0 )
  {
    SetFlagInterlocked(v24, 256);
    *(_DWORD *)(a3 + 448) += v28;
  }
  m = a3 + 200;
  v143 = (int *)(a3 + 200);
  if ( (v16 & (unsigned __int8)v18) != 0 )
  {
    if ( (*(_DWORD *)m & 0x2000000) != 0 )
    {
      v143 = (int *)(a3 + 200);
    }
    else
    {
      ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
      v16 = v16 & 0xF9 | 4;
      LOBYTE(v127) = v27 & 0xF9 | 4;
      v27 = v127;
      m = a3 + 200;
    }
  }
  v29 = *(_DWORD *)(a3 + 512);
  if ( (v29 & 0x10000) != 0 )
  {
    LODWORD(v8) = -1073741202;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_276;
    v23 = 809978;
    goto LABEL_19;
  }
  if ( (v29 & 0x4000000) != 0 )
  {
    LODWORD(v8) = -1073741431;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_276;
    v23 = 809988;
    goto LABEL_19;
  }
  if ( (*(_DWORD *)m & 0x20) == 0 )
  {
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *(_QWORD *)(a3 + 184),
                             *(_QWORD *)(a3 + 184) + 8LL,
                             *(unsigned int *)(a3 + 256),
                             a3 + 264,
                             0,
                             0,
                             0,
                             0,
                             v161) )
    {
      LODWORD(v8) = 0;
      goto LABEL_276;
    }
    NtfsUpdateScbFromAttribute(a1, a3, v161[0]);
    NtfsCleanupAttributeContext(v30, v161);
    BYTE4(v127) = 0;
  }
  NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  v16 = v27 & 0xFE;
  LOBYTE(v127) = v27 & 0xFE;
  NtfsCleanupAttributeContext(v31, v161);
  BYTE4(v127) = 0;
  v32 = *(_DWORD *)(v9 + 356);
  if ( v32 < 0x200000 )
    v32 = 0x200000;
  v141 = v32;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v32, 0x4446744Eu);
  P = PoolWithTag;
  v34 = 0;
  if ( PoolWithTag )
  {
    v35 = IoAllocateMdl(PoolWithTag, v32, 0, 0, 0);
    v36 = v35;
    Mdl = v35;
    if ( v35 )
    {
      MmBuildMdlForNonPagedPool(v35);
      MmMdlPageContentsState(v36, 1);
      v34 = PoolWithTag;
    }
    else
    {
      ExFreePoolWithTag(PoolWithTag, 0);
      v34 = 0;
      P = 0;
    }
  }
  if ( v34 )
  {
    v38 = v16;
  }
  else
  {
    v16 |= 0x40u;
    LOBYTE(v127) = v16;
    if ( (*(_DWORD *)(a3 + 512) & 8) != 0 )
      v37 = *(_DWORD *)(*(_QWORD *)(v9 + 5512) + 144LL);
    else
      v37 = dword_140095988;
    v141 = v37;
    v38 = v16;
    if ( v37 < *(_DWORD *)(v9 + 356) )
      v141 = *(_DWORD *)(v9 + 356);
  }
  NtfsInitializeIoContext(a1, v165, 0);
  if ( (v38 & 6) != 0 )
  {
    NtfsReleasePagingResourcePriv(v39, a3);
    v16 = v38 & 0xF9;
    LOBYTE(v127) = v38 & 0xF9;
  }
  v40 = BYTE1(v127);
  Scb = v140;
  while ( 1 )
  {
    if ( (_BYTE)v128 )
      goto LABEL_246;
    v145 = 0;
    v154 = 0;
    v150[0] = 0;
    NtfsPurgeFileRecordCache(a1);
    if ( (v16 & 0x20) != 0 )
    {
      memset(v163, 0, sizeof(v163));
      v164 = 0;
      BYTE6(v127) = 0;
      v42 = v40 & 0xF7;
      BYTE1(v127) = v42;
      NtfsAcquireCheckpointSynchronization(a1, v9, 18);
      HIBYTE(v127) = 0;
      LOBYTE(v43) = 1;
      NtfsAcquireSharedVcb(a1, v9, v43);
      v44 = v16 & 0xD7 | 8;
      LOBYTE(v127) = v44;
      v45 = (LONGLONG *)(a1 + 104);
      v46 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL);
      if ( (v46 & 1) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 810202);
        NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 810202);
LABEL_300:
        v8 = 3221225865LL;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225865LL, 810211);
        NtfsRaiseStatusInternal(a1, -1073741431, 0, 0, 810211);
LABEL_303:
        if ( NtfsStatusDebugFlags
          && (unsigned int)v8 < 0xFFFFFFED
          && (_DWORD)v8 != -1073741802
          && (unsigned int)(v8 + 2147483643) > 1
          && (_DWORD)v8 != -1073741807
          && (_DWORD)v8 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v8, 810996);
        }
        NtfsRaiseStatusInternal(a1, v8, 0, 0, 810996);
LABEL_311:
        NtfsAttachCorruption_BadOrOrphanFRS(
          a1,
          v94 + 2,
          811006,
          v93,
          *(_QWORD *)(v8 + 184) + 8LL,
          *(_QWORD *)(v8 + 184),
          v94);
        NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9000C5FFELL);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 811006);
        v101 = NtfsRaiseStatusInternal(
                 a1,
                 -1073741566,
                 (unsigned int)*(_QWORD *)(v8 + 184) + 8,
                 *(_QWORD *)(v8 + 184),
                 811006);
LABEL_314:
        if ( NtfsStatusDebugFlags
          && (unsigned int)v101 < 0xFFFFFFED
          && v101 != -1073741802
          && (unsigned int)(v101 + 2147483643) > 1
          && (_DWORD)v8 != -1073741807
          && (_DWORD)v8 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v8, 811172);
        }
        NtfsRaiseStatusInternal(a1, v8, 0, 0, 811172);
        __debugbreak();
        JUMPOUT(0x1400CEB84LL);
      }
      if ( (v46 & 0x20) != 0 )
        goto LABEL_300;
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 1;
      if ( *(_WORD *)(*(_QWORD *)(v9 + 1272) + 4LL) )
      {
        KeClearEvent((PRKEVENT)(v9 + 1400));
        HIBYTE(v127) = 1;
        v45 = (LONGLONG *)(a1 + 104);
      }
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      if ( HIBYTE(v127) )
        KeWaitForSingleObject((PVOID)(v9 + 1400), Executive, 0, 0, 0);
      else
        v45 = (LONGLONG *)(a1 + 104);
      NtfsCheckpointVolume((_DWORD *)a1, v9, 1, 0, 0, 0, *(_QWORD *)(a1 + 200));
      LfsFlushToLsn(*(_QWORD *)(*v45 + 232), NtfsLargeMax);
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v47, deviosup_c23811, v9);
      }
      NtfsFreeRecentlyDeallocated((int *)a1, *v45, &NtfsLargeMax, 1);
      NtfsMarkUnusedContextPreTrimProcessing(a1, v48, v49, v50);
      NtfsPrepareToWaitForDeallocatedClustersToDrain(a1, v163);
      v40 = v42 | 8;
      BYTE1(v127) = v40;
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v51, deviosup_c23826, v9);
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 0;
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      NtfsReleaseCheckpointSynchronization(v52, v9, 18);
      BYTE6(v127) = (v44 & 8) != 0;
      NtfsWaitForDeallocatedClustersToDrainAfterPrepare(a1, v163, (char *)&v127 + 6);
      if ( BYTE6(v127) )
        NtfsReleaseVcb(a1, v9);
      v16 = v44 & 0xF7;
      LOBYTE(v127) = v16;
    }
    while ( 1 )
    {
      NtfsReleaseQuotaControlIfOwned(a1);
      LOBYTE(v53) = 1;
      NtfsAcquireSharedVcb(a1, v9, v53);
      v55 = v16 | 8;
      LOBYTE(v127) = v55;
      LOBYTE(v56) = 1;
      if ( (v40 & 4) != 0 )
      {
        NtfsAcquirePagingResourceExclusive(a1, a3, v56, v54);
        v16 = v55 | 2;
      }
      else
      {
        NtfsAcquirePagingShared(a1, a3, v56, 0);
        v16 = v55 | 4;
      }
      LOBYTE(v127) = v16;
      LODWORD(v142) = *(_DWORD *)(a3 + 512);
      if ( (v142 & 0x10000) != 0 )
      {
        LODWORD(v8) = -1073741202;
        if ( NtfsStatusDebugFlags )
        {
          v57 = 810330;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v142 & 0x4000000) != 0 )
      {
        LODWORD(v8) = -1073741431;
        if ( NtfsStatusDebugFlags )
        {
          v57 = 810340;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v142 & 0x40) != 0 )
      {
        LODWORD(v8) = -1073741533;
        if ( NtfsStatusDebugFlags )
        {
          v57 = 810350;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v142 & 2) != 0 )
      {
        if ( a4 )
        {
          v132 = *(_DWORD *)(a4 + 4);
          if ( (v132 & 0x8000000) == 0 )
          {
            if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
            {
              v58 = *(_QWORD *)(a3 + 192);
              v59 = *(_QWORD *)(v58 + 248);
              v60 = *(unsigned __int16 *)(v59 + 6);
              if ( (unsigned __int16)v60 > 0x40u || (v60 & 1) != 0 )
                v60 = 0;
              v139 = v60;
              LOWORD(v147) = v60;
              v148 = v59 + 32;
              McTemplateU0ppwwpipdwdd_EtwWriteTransfer(
                *(unsigned __int16 *)(a3 + 264) >> 1,
                (unsigned int)deviosup_c23931,
                (unsigned int)KeGetCurrentThread(),
                v58,
                *(_WORD *)(v58 + 7872) >> 1,
                *(_QWORD *)(v58 + 7880),
                (unsigned __int16)v60 >> 1,
                v59 + 32,
                *(_QWORD *)(a3 + 184),
                *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
                a3,
                *(_DWORD *)(a3 + 256),
                *(_WORD *)(a3 + 264) >> 1,
                *(_QWORD *)(a3 + 272),
                v142,
                v132,
                v127);
            }
            LODWORD(v8) = -1073741790;
            if ( NtfsStatusDebugFlags )
            {
              v57 = 810381;
              goto LABEL_81;
            }
            goto LABEL_82;
          }
        }
      }
      if ( *(_DWORD *)(a3 + 516) == 3 && *(_DWORD *)(a3 + 256) == 128 )
      {
        LODWORD(v8) = -1073740637;
        if ( NtfsStatusDebugFlags )
        {
          v57 = 810391;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      v61 = v141;
      v129 = v141;
      v135 = v141;
      if ( *(_QWORD *)(a3 + 632) + v141 >= *(__int64 *)(a3 + 40) )
      {
        v61 = -*(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL)
            & (*(_DWORD *)(a3 + 40) + *(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL) + ~*(_DWORD *)(a3 + 632));
        v135 = v61;
        if ( v61 > v141 )
          v61 = v141;
        v129 = v61;
        v135 = v61;
      }
      v62 = v61;
      j = v61;
      if ( (v16 & 4) == 0 )
        break;
      NtfsLockFsRtlHeader(a1, a3);
      v63 = v40 | 2;
      BYTE1(v127) = v63;
      v64 = v62 + *(_QWORD *)(a3 + 632);
      if ( v64 < *(_QWORD *)(a3 + 40) )
      {
        if ( (a5 & 0x2000000) != 0 )
        {
          memset(v161, 0, 0x58u);
          BYTE4(v127) = 1;
          NtfsAcquireSharedFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v65 = v16 | 1;
          LOBYTE(v127) = v65;
          LOBYTE(Index) = 0;
          if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                   a1,
                                   *(_QWORD *)(a3 + 184),
                                   *(_QWORD *)(a3 + 184) + 8LL,
                                   128,
                                   &NtfsEfsBackupName,
                                   0,
                                   Index,
                                   0,
                                   0,
                                   v161) )
          {
            NtfsReleasePagingResourcePriv(v66, a3);
            v65 &= ~4u;
            LOBYTE(v127) = v65;
            v63 |= 0x14u;
            BYTE1(v127) = v63;
          }
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v16 = v65 & 0xFE;
          LOBYTE(v127) = v16;
          NtfsCleanupAttributeContext(v67, v161);
          BYTE4(v127) = 0;
        }
      }
      else
      {
        NtfsReleasePagingResourcePriv(v64, a3);
        v16 &= ~4u;
        LOBYTE(v127) = v16;
        v63 |= 4u;
        BYTE1(v127) = v63;
      }
      NtfsUnlockFsRtlHeader(a1, a3);
      v40 = v63 & 0xFD;
      BYTE1(v127) = v40;
      if ( (v40 & 4) == 0 )
        break;
      if ( (v16 & 8) != 0 )
      {
        NtfsReleaseVcb(a1, v9);
        v16 &= ~8u;
        LOBYTE(v127) = v16;
      }
    }
    v68 = v40 & 0xFB;
    BYTE1(v127) = v68;
    LODWORD(v69) = a5 & 0x2000000;
    v132 = a5 & 0x2000000;
    if ( (a5 & 0x2000000) != 0 )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v70 = v16 | 1;
      LOBYTE(v127) = v70;
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
      v140 = Scb;
      *((_DWORD *)Scb + 128) |= 0x800000u;
      NtfsCreateInternalAttributeStream(a1, (__int64)Scb, 0, 0, 0, 0);
      memset(v161, 0, 0x58u);
      BYTE4(v127) = 1;
      v71 = *((_QWORD *)Scb + 23);
      v147 = Scb + 256;
      LOBYTE(Indexb) = 0;
      v72 = (unsigned __int8)NtfsLookupInFileRecord(
                               a1,
                               v71,
                               v71 + 8,
                               *((unsigned int *)Scb + 64),
                               Scb + 132,
                               0,
                               Indexb,
                               0,
                               0,
                               v161) == 0;
      v73 = *((_DWORD *)Scb + 128);
      if ( v72 )
      {
        *v147 = v73 & 0xFFFFFF7F;
        NtfsCreateAttribute(a1, 0, 0, 0, 1, 0, 0);
        *((_DWORD *)Scb + 128) &= ~0x40u;
      }
      else
      {
        *v147 = v73 | 0x80;
        NtfsUpdateScbFromAttribute(a1, Scb, v161[0]);
        NtfsSnapshotScb(a1, Scb);
        *(_QWORD *)(*((_QWORD *)Scb + 62) + 96LL) = a1;
        if ( *(_BYTE *)(v161[0] + 8) )
          NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
      }
      NtfsCheckpointCurrentTransaction(a1);
      NtfsCleanupAttributeContext(v74, v161);
      BYTE4(v127) = 0;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v16 = v70 & 0xFE;
      LOBYTE(v127) = v16;
      v69 = NtfsReleaseQuotaControlIfOwned(a1);
    }
    if ( (v68 & 0x10) != 0 )
    {
      v69 = *(_QWORD *)(a3 + 632) + v129;
      if ( v69 < *(_QWORD *)(a3 + 40) )
      {
        ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
        v16 = v16 & 0xF9 | 4;
        LOBYTE(v127) = v16;
      }
    }
    v40 = v68 & 0xEF;
    BYTE1(v127) = v40;
    v8 = *(_QWORD *)(a3 + 40);
    v142 = v8;
    v75 = *(_QWORD *)(a3 + 632);
    if ( v75 < v8 )
      break;
    v155 = v8;
    LOBYTE(v69) = 1;
    v128 = v69;
    v131 = 1;
LABEL_203:
    NtfsReleaseQuotaControlIfOwned(a1);
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
    v16 |= 1u;
    LOBYTE(v127) = v16;
    if ( (_BYTE)v128 )
      v8 = -1;
    v100 = (unsigned __int8)v128;
    if ( !v132 )
      v100 = 0;
    v101 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))&xmmword_1400957A0 + 1))(
             a1,
             *(_QWORD *)(a3 + 184),
             a3 + 264,
             v100,
             v8);
    LODWORD(v8) = v101;
    v130 = v101;
    if ( v101 < 0 )
      goto LABEL_314;
    LOBYTE(v102) = 1;
    NtfsPersistDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL, v102);
    BYTE5(v127) = 0;
    if ( (_BYTE)v128 )
    {
      v103 = a5;
      if ( (a5 & 0x4000000) != 0 )
      {
        NtfsDeleteEncryptionContext(a3);
        *(_QWORD *)(a3 + 632) = -1;
        v103 = a5;
      }
      else
      {
        *(_QWORD *)(a3 + 632) = 0;
      }
      *v143 &= ~v103;
    }
    else
    {
      *(_QWORD *)(a3 + 632) = v142;
    }
    *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
    if ( (v40 & 2) != 0 )
    {
      NtfsUnlockFsRtlHeader(a1, a3);
      v40 &= ~2u;
      BYTE1(v127) = v40;
    }
    NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
    if ( P && (v16 & 0x40) != 0 )
    {
      NtfsDeleteMdlAndBuffer(v9, Mdl, P);
      v104 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      P = 0;
      Mdl = 0;
    }
    if ( (v40 & 1) != 0 )
    {
      NtfsReleaseRangeInternal(&v159);
      v40 &= ~1u;
      BYTE1(v127) = v40;
    }
    if ( Scb )
    {
      NtfsDeleteInternalAttributeStream(a1, (__int64)Scb, 1, 0);
      Scb = 0;
      v140 = 0;
    }
    if ( (v16 & 6) != 0 )
    {
      NtfsReleasePagingResourcePriv(v104, a3);
      v16 &= 0xF9u;
      LOBYTE(v127) = v16;
    }
    if ( (v16 & 1) != 0 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v16 &= ~1u;
      LOBYTE(v127) = v16;
    }
    if ( v132 )
    {
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
      if ( !(_BYTE)v128 )
        goto LABEL_243;
      NtfsReleaseQuotaControlIfOwned(a1);
      memset(v161, 0, 0x58u);
      BYTE4(v127) = 1;
      LOBYTE(v105) = 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v105, v106);
      v149 = 0;
      for ( i = 0; ; ++i )
      {
        v149 = i;
        if ( i >= 2 )
          break;
        v108 = *(_QWORD *)(a1 + 8LL * i + 48);
        if ( !v108 || v108 == *(_QWORD *)(a3 + 184) )
        {
          *(_QWORD *)(a1 + 8LL * i + 48) = *(_QWORD *)(a3 + 184);
          break;
        }
      }
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
      v140 = Scb;
      *((_DWORD *)Scb + 128) |= 0x800000u;
      *((_DWORD *)Scb + 128) |= 0x80u;
      LOBYTE(Indexc) = 0;
      v109 = NtfsLookupInFileRecord(
               a1,
               *(_QWORD *)(a3 + 184),
               *(_QWORD *)(a3 + 184) + 8LL,
               128,
               &NtfsEfsBackupName,
               0,
               Indexc,
               0,
               0,
               v161);
      while ( v109 )
      {
        NtfsDeleteAttributeRecord(a1, *(_QWORD *)(a3 + 184), 7, v161);
        v111 = *((_DWORD *)Scb + 64);
        v112 = *((_QWORD *)Scb + 23);
        if ( v161[5] )
        {
          LODWORD(Size) = 0;
          v109 = NtfsLookupExternalAttribute(
                   a1,
                   v112,
                   v111,
                   (PCUNICODE_STRING)(Scb + 132),
                   0,
                   0,
                   0,
                   Size,
                   (__int64)v161);
        }
        else
        {
          LOBYTE(Index) = 0;
          v109 = NtfsLookupInFileRecord(a1, v112, 0, v111, Scb + 132, 0, Index, 0, 0, v161);
        }
      }
      NtfsCleanupAttributeContext(v110, v161);
      BYTE4(v127) = 0;
      NtfsCheckpointCurrentTransaction(a1);
      *((_DWORD *)Scb + 128) |= 0x40u;
      NtfsTeardownStructures(a1, (int)Scb, 0);
      *(_DWORD *)(a1 + 4) |= 0x40400u;
      NtfsExtendedCompleteRequestInternal(a1, 0, 0, 0, 1);
    }
    if ( (_BYTE)v128 )
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
LABEL_243:
    if ( (v16 & 8) != 0 )
    {
      NtfsReleaseVcb(a1, v9);
      v16 &= ~8u;
      LOBYTE(v127) = v16;
    }
  }
  if ( (v16 & 4) != 0 )
  {
    NtfsAcquireRange(a1, a3, v75, j, 0, (__int64)&v159);
    v40 |= 1u;
    BYTE1(v127) = v40;
  }
  if ( (*v143 & a5) == 0 )
    *v143 |= a5;
  *(_QWORD *)(a1 + 16) |= 0x40000uLL;
  v8 = *(_QWORD *)(a3 + 632);
  v142 = v8;
  v155 = v8;
  v76 = v129;
  while ( 2 )
  {
    LOBYTE(v77) = v128;
    while ( 1 )
    {
      if ( (_BYTE)v77 || v76 <= 0 )
      {
        Scb = v140;
        goto LABEL_203;
      }
      if ( (v16 & 4) != 0 && (v40 & 1) == 0 )
      {
        NtfsAcquireRange(a1, a3, *(_QWORD *)(a3 + 632), v76, 0, (__int64)&v159);
        v40 |= 1u;
        BYTE1(v127) = v40;
      }
      if ( (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v154) && v145 != -1 )
        break;
      v98 = v76;
      if ( v76 >= (unsigned __int64)(v154 << *(_BYTE *)(v9 + 488)) )
        v98 = v154 << *(_BYTE *)(v9 + 488);
      v146 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v98) >> *(_BYTE *)(v9 + 488);
      v99 = v146 << *(_BYTE *)(v9 + 488);
      v8 += v99;
      v142 = v8;
      v155 = v8;
      v76 -= v99;
      v129 = v76;
      v135 = v76;
LABEL_199:
      v77 = (unsigned __int8)v128;
      if ( v8 >= *(_QWORD *)(a3 + 40) )
        v77 = 1;
      v128 = v77;
      v131 = v77;
    }
    v78 = v76;
    if ( v76 >= (unsigned __int64)(v154 << *(_BYTE *)(v9 + 488)) )
      v78 = v154 << *(_BYTE *)(v9 + 488);
    v146 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v78) >> *(_BYTE *)(v9 + 488);
    NtfsPurgeFileRecordCache(a1);
    if ( (unsigned __int8)NtfsAllocateClusters(
                            a1,
                            *(_QWORD *)(a3 + 192),
                            a3,
                            (v8 + *(unsigned int *)(v9 + 480)) >> *(_BYTE *)(v9 + 488),
                            1,
                            v146,
                            0,
                            0,
                            v16 >> 7,
                            1,
                            (__int64)&v146) )
    {
      v139 = 0;
      v144 = 0;
      if ( (v16 & 0x40) != 0 )
      {
        v151 = v146 << *(_BYTE *)(v9 + 488);
        LOWORD(v80) = 2 - ((*(_DWORD *)(a3 + 512) & 8) != 0);
        NtfsCreateMdlAndBuffer(a1, v79, v80, 516, &v151, &Mdl, &P);
      }
      v83 = *(_BYTE *)(v9 + 488);
      v84 = (v8 + *(unsigned int *)(v9 + 480)) >> v83;
      v162 = v84;
      v85 = v84 + v146 - 1;
      for ( j = v85; ; v85 = j )
      {
        if ( v84 > v85 || v84 < 0 )
        {
          if ( (v16 & 0x40) != 0 )
          {
            NtfsDeleteMdlAndBuffer(v9, Mdl, P);
            P = 0;
            Mdl = 0;
          }
          LfsSetDefragLsn(*(_QWORD *)(v9 + 232));
          NtfsPurgeFileRecordCache(a1);
          v76 = v129;
          goto LABEL_199;
        }
        v156 = v84 << v83;
        v147 = (_DWORD *)(v85 - v84 == 0x7FFFFFFFFFFFFFFFLL ? 0x7FFFFFFFFFFFFFFFLL : v85 - v84 + 1);
        if ( !FsRtlLookupBaseMcbEntry(
                (PBASE_MCB)(*(_QWORD *)(a1 + 192) + 40LL),
                v84,
                &Lbn,
                &SectorCountFromLbn,
                0,
                0,
                0) )
          break;
        if ( Lbn == -1 )
        {
          v97 = (__int64)v147;
          if ( SectorCountFromLbn <= (__int64)v147 )
            goto LABEL_192;
          goto LABEL_191;
        }
        v86 = SectorCountFromLbn;
        if ( SectorCountFromLbn > (__int64)v147 )
        {
          v86 = (int)v147;
          SectorCountFromLbn = (__int64)v147;
        }
        v87 = v86 << *(_DWORD *)(v9 + 488);
        v130 = 0;
        *(_QWORD *)(a2 + 8) = Mdl;
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v84 << *(_BYTE *)(v9 + 488),
          v145 << *(_BYTE *)(v9 + 488),
          v87,
          a2,
          3,
          0,
          (*v143 & 0x4000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, a2 + 48);
        *(_QWORD *)(a2 + 56) = 0;
        v88 = v143;
        if ( *(_QWORD *)(a3 + 504) && *v143 >= 0 && (*v143 & 0x4000000) != 0 && xmmword_140095740 )
        {
          xmmword_140095740(P, &v156, v87);
          v88 = v143;
        }
        if ( *(_QWORD *)(a3 + 504) && *v88 >= 0 && (*v88 & 0x2000000) != 0 && *(&xmmword_140095740 + 1) )
          ((void (__fastcall *)(PVOID, PVOID, LONGLONG *, _QWORD, _QWORD))*(&xmmword_140095740 + 1))(
            P,
            P,
            &v156,
            v87,
            *(_QWORD *)(a3 + 504));
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v84 << *(_BYTE *)(v9 + 488),
          Lbn << *(_BYTE *)(v9 + 488),
          v87,
          a2,
          4,
          0,
          (*v143 & 0x2000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, a2 + 48);
        *(_QWORD *)(a2 + 56) = 0;
        *(_QWORD *)(a2 + 8) = 0;
        if ( v132 )
        {
          v153 = SectorCountFromLbn;
          NtfsReleaseQuotaControlIfOwned(a1);
          NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v89 = v16 | 1;
          LOBYTE(v127) = v89;
          v90 = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
          v140 = v90;
          NtfsCreateInternalAttributeStream(a1, (__int64)v90, 0, 0, 0, 0);
          NtfsPreloadAllocationInternal(a1, v84 + v153 - 1, 0);
          BYTE5(v127) = 1;
          NtfsAddNtfsMcbEntry((unsigned __int64)(v90 + 200), v150[0], v145, SectorCountFromLbn, 0, 1u);
          NtfsRemoveNtfsMcbEntry(a3 + 400, v84);
          v91 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64))&xmmword_1400957A0 + 1))(
                  a1,
                  *(_QWORD *)(a3 + 184),
                  a3 + 264,
                  0,
                  v142 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488)));
          v8 = (unsigned int)v91;
          v130 = v91;
          if ( v91 < 0 )
            goto LABEL_303;
          memset(v161, 0, 0x58u);
          BYTE4(v127) = 1;
          v8 = (__int64)v140;
          LOBYTE(Indexa) = 0;
          v92 = NtfsLookupInFileRecord(
                  a1,
                  *((_QWORD *)v140 + 23),
                  *((_QWORD *)v140 + 23) + 8LL,
                  *((unsigned int *)v140 + 64),
                  v140 + 132,
                  0,
                  Indexa,
                  0,
                  0,
                  v161);
          v94 = 0;
          if ( !v92 && (*(_DWORD *)(v8 + 512) & 4) == 0 )
            goto LABEL_311;
          NtfsSnapshotScb(a1, v8);
          *(_QWORD *)(*(_QWORD *)(v8 + 496) + 96LL) = a1;
          LOBYTE(SectorCountFromStartingLbn) = 0;
          NtfsAddAttributeAllocation(a1, v8, v161, v150, &v153, SectorCountFromStartingLbn);
          NtfsCleanupAttributeContext(v95, v161);
          BYTE4(v127) = 0;
          v147 = *(_DWORD **)(v8 + 472);
          NtfsUpdateScbFromAttribute(a1, v8, 0);
          if ( *(_BYTE *)(*(_QWORD *)(v8 + 184) + 38LL) && *(_DWORD **)(v8 + 472) != v147 )
          {
            NtfsPurgeFileRecordCache(a1);
            NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v9 + 72), 0);
            LOBYTE(v127) = v89 | 0x10;
            NtfsAdjustFcbAllocatedClusterCount(
              a1,
              *(_QWORD *)(v8 + 184),
              (__int64)(*(_QWORD *)(v8 + 472) - (_QWORD)v147) >> *(_BYTE *)(v9 + 488));
            NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
            v89 &= ~0x10u;
            LOBYTE(v127) = v89;
          }
          LOBYTE(v96) = 1;
          NtfsPersistDelayedAllocation(a1, v84, v84 + v153 - 1, v96);
          v8 = v142;
          *(_QWORD *)(a3 + 632) = v142 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488));
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v16 = v89 & 0xFE;
          LOBYTE(v127) = v16;
          v150[0] += SectorCountFromLbn;
          BYTE5(v127) = 0;
        }
        else
        {
          v8 = v142;
        }
LABEL_192:
        v145 += SectorCountFromLbn;
        v83 = *(_BYTE *)(v9 + 488);
        v8 += SectorCountFromLbn << v83;
        v142 = v8;
        v155 = v8;
        v129 -= SectorCountFromLbn << v83;
        v135 = v129;
        v84 += SectorCountFromLbn;
        v162 = v84;
      }
      v97 = (__int64)v147;
LABEL_191:
      SectorCountFromLbn = v97;
      goto LABEL_192;
    }
    if ( !(_WORD)v139 )
    {
      v81 = 1;
      v139 = 1;
      v144 = 1;
      v82 = v16 | 0x20;
      LOBYTE(v127) = v82;
      if ( (v40 & 1) != 0 )
      {
        NtfsReleaseRangeInternal(&v159);
        v40 &= ~1u;
        BYTE1(v127) = v40;
      }
      NtfsReleasePagingResourcePriv(v81, a3);
      v16 = v82 & 0xF9;
      LOBYTE(v127) = v16;
      continue;
    }
    break;
  }
  LODWORD(v8) = -1073741697;
  if ( NtfsStatusDebugFlags )
  {
    v57 = 810706;
LABEL_81:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v8, v57);
  }
LABEL_82:
  v130 = v8;
LABEL_246:
  *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
  if ( (v16 & 0x10) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
    v16 &= ~0x10u;
    LOBYTE(v127) = v16;
  }
  if ( P && (v16 & 0x40) != 0 )
  {
    NtfsDeleteMdlAndBuffer(v9, Mdl, P);
    *(_QWORD *)(a2 + 8) = 0;
    P = 0;
    Mdl = 0;
  }
  if ( (v40 & 2) != 0 )
  {
    NtfsUnlockFsRtlHeader(a1, a3);
    v40 &= ~2u;
    BYTE1(v127) = v40;
  }
  NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
  if ( (v40 & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      *(_OWORD *)(a1 + 72) = v159;
      *(_OWORD *)(a1 + 88) = v160;
    }
    else
    {
      NtfsReleaseRangeInternal(&v159);
      *(_QWORD *)(a1 + 80) = 0;
    }
    BYTE1(v127) = v40 & 0xFE;
  }
  if ( (v16 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v138 = 0;
      for ( k = 0; ; ++k )
      {
        v138 = k;
        if ( k >= 2 )
          break;
        v13 = k;
        m = *(_QWORD *)(a1 + 8LL * k + 48);
        if ( !m || m == *(_QWORD *)(a3 + 184) )
        {
          *(_QWORD *)(a1 + 8LL * k + 48) = *(_QWORD *)(a3 + 184);
          break;
        }
      }
    }
    else
    {
      NtfsReleasePagingResourcePriv(m, *(_QWORD *)(a3 + 184));
      v137 = 0;
      for ( m = 0; ; m = (unsigned int)(m + 1) )
      {
        v137 = m;
        if ( (unsigned int)m >= 2 )
          break;
        v13 = (unsigned int)m;
        if ( *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) = 0;
      }
    }
    v16 &= 0xF9u;
    LOBYTE(v127) = v16;
  }
  if ( (v16 & 1) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
    v16 &= ~1u;
    LOBYTE(v127) = v16;
  }
  if ( (v16 & 8) != 0 )
  {
    NtfsReleaseVcb(a1, v9);
    v16 &= ~8u;
    LOBYTE(v127) = v16;
  }
LABEL_276:
  v114 = *(unsigned int *)(a1 + 16);
  LODWORD(v114) = v114 & 0x7FFFFFFF;
  *(_QWORD *)(a1 + 16) = v114;
  if ( BYTE4(v127) )
    NtfsCleanupAttributeContext(m, v161);
  NtfsFreeIoContext(a1, v13, v15);
  v116 = P;
  if ( P )
  {
    *(_QWORD *)(a2 + 8) = 0;
    IoFreeMdl(Mdl);
    ExFreePoolWithTag(v116, 0);
  }
  if ( (v16 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v117 = 0;
      while ( 1 )
      {
        v118 = *(_QWORD *)(a1 + 8LL * v117 + 48);
        if ( !v118 || v118 == *(_QWORD *)(a3 + 184) )
          break;
        if ( ++v117 >= 2 )
          goto LABEL_292;
      }
      *(_QWORD *)(a1 + 8LL * v117 + 48) = *(_QWORD *)(a3 + 184);
    }
    else
    {
      NtfsReleasePagingResourcePriv(v115, *(_QWORD *)(a3 + 184));
      for ( n = 0; n != 2; ++n )
      {
        if ( *(_QWORD *)(a1 + 8 * n + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8 * n + 48) = 0;
      }
    }
  }
LABEL_292:
  if ( (v16 & 1) != 0 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  if ( (v16 & 8) != 0 )
    NtfsReleaseVcb(a1, v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400cc78c  mov     rax, rsp
0x1400cc78f  mov     [rax+20h], r9
0x1400cc793  mov     [rax+18h], r8
0x1400cc797  mov     [rax+10h], rdx
0x1400cc79b  mov     [rax+8], rcx
0x1400cc79f  push    rbx
0x1400cc7a0  push    rsi
0x1400cc7a1  push    rdi
0x1400cc7a2  push    r12
0x1400cc7a4  push    r13
0x1400cc7a6  push    r14
0x1400cc7a8  push    r15
0x1400cc7aa  sub     rsp, 2A0h
0x1400cc7b1  mov     r15, r9
0x1400cc7b4  mov     r14, r8
0x1400cc7b7  mov     rsi, rcx
0x1400cc7ba  xor     r12d, r12d
0x1400cc7bd  mov     ebx, r12d
0x1400cc7c0  xor     edx, edx; Val
0x1400cc7c2  lea     r8d, [r12+58h]; Size
0x1400cc7c7  lea     rcx, [rax-148h]; void *
0x1400cc7ce  call    memset
0x1400cc7d3  mov     rax, [r14+0B8h]
0x1400cc7da  mov     r13, [rax+60h]
0x1400cc7de  mov     [rsp+2D8h+var_1B0], r13
0x1400cc7e6  mov     [rsp+2D8h+Mdl], r12
0x1400cc7ee  xor     al, al
0x1400cc7f0  mov     [rsp+2D8h+var_253], al
0x1400cc7f7  mov     [rsp+2D8h+P], r12
0x1400cc7ff  mov     eax, r12d
0x1400cc802  mov     [rsp+2D8h+var_24C], eax
0x1400cc809  mov     [rsp+2D8h+var_228], eax
0x1400cc810  mov     [rsp+2D8h+var_94], eax
0x1400cc817  xor     edx, edx; Val
0x1400cc819  lea     r8d, [r12+5Ch]; Size
0x1400cc81e  lea     rcx, [rsp+2D8h+var_98]; void *
0x1400cc826  call    memset
0x1400cc82b  xorps   xmm0, xmm0
0x1400cc82e  movups  [rsp+2D8h+var_168], xmm0
0x1400cc836  movups  [rsp+2D8h+var_158], xmm0
0x1400cc83e  mov     [rsp+2D8h+var_1D8], r12
0x1400cc846  mov     [rsp+2D8h+var_210], r12d
0x1400cc84e  mov     [rsp+2D8h+SectorCountFromLbn], r12
0x1400cc856  mov     [rsp+2D8h+Lbn], r12
0x1400cc85e  mov     byte ptr [rsp+2D8h+var_250], r12b
0x1400cc866  mov     [rsp+2D8h+var_208], r12
0x1400cc86e  mov     [rsp+2D8h+var_258], r12d
0x1400cc876  mov     byte ptr [rsp+2D8h+var_258], 80h
0x1400cc87e  mov     ecx, 80000000h
0x1400cc883  or      [rsi+10h], rcx
0x1400cc887  lea     ecx, [r12+1]
0x1400cc88c  mov     [rsp+2D8h+var_254], cl
0x1400cc893  mov     dil, 80h
0x1400cc896  cmp     [r14+10h], r12
0x1400cc89a  jz      short loc_1400CC8EA
0x1400cc89c  test    [rsp+2D8h+arg_20], 2000000h
0x1400cc8a7  jnz     short loc_1400CC8CD
0x1400cc8a9  test    dword ptr [r15+8], 100h
0x1400cc8b1  jz      short loc_1400CC8CD
0x1400cc8b3  mov     r8b, [rsi+0Ch]
0x1400cc8b7  and     r8b, cl
0x1400cc8ba  xor     r9d, r9d
0x1400cc8bd  mov     rdx, r14
0x1400cc8c0  mov     rcx, rsi
0x1400cc8c3  call    NtfsAcquirePagingShared
0x1400cc8c8  mov     dil, 84h
0x1400cc8cb  jmp     short loc_1400CC8E2
0x1400cc8cd  mov     r8b, [rsi+0Ch]
0x1400cc8d1  and     r8b, cl
0x1400cc8d4  mov     rdx, r14
0x1400cc8d7  mov     rcx, rsi
0x1400cc8da  call    NtfsAcquirePagingResourceExclusive
0x1400cc8df  mov     dil, 82h
0x1400cc8e2  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cc8ea  mov     r9d, 8
0x1400cc8f0  mov     r8, r14
0x1400cc8f3  mov     rdx, [r14+0B8h]
0x1400cc8fa  mov     rcx, rsi
0x1400cc8fd  call    NtfsAcquireExclusiveFcb
0x1400cc902  mov     r10d, 1
0x1400cc908  or      dil, r10b
0x1400cc90b  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cc913  mov     r12d, [r14+200h]
0x1400cc91a  lea     r9d, [r10+1]
0x1400cc91e  test    r9b, r12b
0x1400cc921  jz      loc_1400CCA49
0x1400cc927  xor     edx, edx
0x1400cc929  test    r15, r15
0x1400cc92c  jz      loc_1400CCA49
0x1400cc932  mov     r15d, [r15+4]
0x1400cc936  bt      r15d, 1Bh
0x1400cc93b  jb      loc_1400CCA41
0x1400cc941  mov     eax, [rsi+10h]
0x1400cc944  bt      rax, 14h
0x1400cc949  jb      loc_1400CCA17
0x1400cc94f  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400cc956  test    al, 20h
0x1400cc958  jz      loc_1400CCA17
0x1400cc95e  mov     r9, [r14+0C0h]
0x1400cc965  mov     r11, [r9+0F8h]
0x1400cc96c  movzx   eax, word ptr [r11+6]
0x1400cc971  lea     ecx, [rdx+40h]
0x1400cc974  cmp     ax, cx
0x1400cc977  ja      short loc_1400CC987
0x1400cc979  test    r10b, al
0x1400cc97c  jnz     short loc_1400CC987
0x1400cc97e  mov     [rsp+2D8h+var_240], eax
0x1400cc985  jmp     short loc_1400CC990
0x1400cc987  mov     eax, edx
0x1400cc989  mov     [rsp+2D8h+var_240], edx
0x1400cc990  mov     word ptr [rsp+2D8h+var_178], ax
0x1400cc998  add     r11, 20h ; ' '
0x1400cc99c  mov     [rsp+2D8h+var_170], r11
0x1400cc9a4  mov     r8, gs:188h
0x1400cc9ad  mov     rcx, [r14+0B8h]
0x1400cc9b4  movzx   edx, ax
0x1400cc9b7  shr     edx, 1
0x1400cc9b9  movzx   r10d, word ptr [r9+1EC0h]
0x1400cc9c1  shr     r10d, 1
0x1400cc9c4  mov     [rsp+2D8h+var_268], r15d
0x1400cc9c9  mov     dword ptr [rsp+2D8h+var_270], r12d
0x1400cc9ce  mov     rax, [r14+110h]
0x1400cc9d5  mov     [rsp+2D8h+var_278], rax
0x1400cc9da  mov     eax, [r14+100h]
0x1400cc9e1  mov     [rsp+2D8h+var_280], eax
0x1400cc9e5  mov     [rsp+2D8h+var_288], r14
0x1400cc9ea  mov     rax, [rcx+8]
0x1400cc9ee  mov     [rsp+2D8h+var_290], rax
0x1400cc9f3  mov     [rsp+2D8h+var_298], rcx
0x1400cc9f8  mov     [rsp+2D8h+Size], r11
0x1400cc9fd  mov     dword ptr [rsp+2D8h+Index], edx
0x1400cca01  mov     rax, [r9+1EC8h]
0x1400cca08  mov     [rsp+2D8h+SectorCountFromStartingLbn], rax
0x1400cca0d  mov     dword ptr [rsp+2D8h+Irp], r10d
0x1400cca12  call    McTemplateU0ppwwpipdzdd_EtwWriteTransfer
0x1400cca17  mov     al, cs:NtfsStatusDebugFlags
0x1400cca1d  xor     r12d, r12d
0x1400cca20  mov     ebx, 0C0000022h
0x1400cca25  test    al, al
0x1400cca27  jz      loc_1400CE8CA
0x1400cca2d  mov     r8d, 0C5BA9h
0x1400cca33  mov     edx, ebx
0x1400cca35  xor     ecx, ecx
0x1400cca37  call    NtfsStatusTraceAndDebugInternal
0x1400cca3c  jmp     loc_1400CE8CA
0x1400cca41  mov     r15, [rsp+2D8h+arg_18]
0x1400cca49  test    dil, 4
0x1400cca4d  jz      loc_1400CCAE5
0x1400cca53  lea     r12, [r15+8]
0x1400cca57  test    dword ptr [r12], 100h
0x1400cca5f  jnz     loc_1400CCAF1
0x1400cca65  mov     rdx, r14
0x1400cca68  call    NtfsReleasePagingResourcePriv
0x1400cca6d  and     dil, 0FBh
0x1400cca71  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cca79  xor     r8d, r8d
0x1400cca7c  mov     rdx, [r14+0B8h]
0x1400cca83  mov     rcx, rsi
0x1400cca86  call    NtfsReleaseFcbEx
0x1400cca8b  and     dil, 0FEh
0x1400cca8f  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cca97  mov     r8b, [rsi+0Ch]
0x1400cca9b  and     r8b, 1
0x1400cca9f  mov     rdx, r14
0x1400ccaa2  mov     rcx, rsi
0x1400ccaa5  call    NtfsAcquirePagingResourceExclusive
0x1400ccaaa  or      dil, 2
0x1400ccaae  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccab6  mov     r9d, 8
0x1400ccabc  mov     r8, r14
0x1400ccabf  mov     rdx, [r14+0B8h]
0x1400ccac6  mov     rcx, rsi
0x1400ccac9  call    NtfsAcquireExclusiveFcb
0x1400ccace  mov     r10d, 1
0x1400ccad4  or      dil, r10b
0x1400ccad7  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccadf  lea     r9d, [r10+1]
0x1400ccae3  jmp     short loc_1400CCAF1
0x1400ccae5  mov     r12, [rsp+2D8h+arg_18]
0x1400ccaed  add     r12, 8
0x1400ccaf1  mov     r15b, dil
0x1400ccaf4  test    dword ptr [r12], 100h
0x1400ccafc  jnz     short loc_1400CCB12
0x1400ccafe  mov     edx, 100h
0x1400ccb03  mov     rcx, r12
0x1400ccb06  call    SetFlagInterlocked
0x1400ccb0b  add     [r14+1C0h], r10d
0x1400ccb12  lea     rcx, [r14+0C8h]
0x1400ccb19  mov     [rsp+2D8h+var_1F0], rcx
0x1400ccb21  test    r9b, r15b
0x1400ccb24  jz      short loc_1400CCB6D
0x1400ccb26  test    dword ptr [rcx], 2000000h
0x1400ccb2c  jnz     short loc_1400CCB65
0x1400ccb2e  mov     rcx, [r14+10h]; Resource
0x1400ccb32  call    cs:__imp_ExConvertExclusiveToSharedLite
0x1400ccb39  nop     dword ptr [rax+rax+00h]
0x1400ccb3e  mov     dil, r15b
0x1400ccb41  and     dil, 0FDh
0x1400ccb45  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccb4d  or      dil, 4
0x1400ccb51  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccb59  mov     r15b, dil
0x1400ccb5c  lea     rcx, [r14+0C8h]
0x1400ccb63  jmp     short loc_1400CCB6D
0x1400ccb65  mov     [rsp+2D8h+var_1F0], rcx
0x1400ccb6d  mov     eax, [r14+200h]
0x1400ccb74  xor     r12d, r12d
0x1400ccb77  bt      eax, 10h
0x1400ccb7b  jnb     short loc_1400CCB9B
0x1400ccb7d  mov     al, cs:NtfsStatusDebugFlags
0x1400ccb83  mov     ebx, 0C000026Eh
0x1400ccb88  test    al, al
0x1400ccb8a  jz      loc_1400CE8CA
0x1400ccb90  mov     r8d, 0C5BFAh
0x1400ccb96  jmp     loc_1400CCA33
0x1400ccb9b  bt      eax, 1Ah
0x1400ccb9f  jnb     short loc_1400CCBBF
0x1400ccba1  mov     al, cs:NtfsStatusDebugFlags
0x1400ccba7  mov     ebx, 0C0000189h
0x1400ccbac  test    al, al
0x1400ccbae  jz      loc_1400CE8CA
0x1400ccbb4  mov     r8d, 0C5C04h
0x1400ccbba  jmp     loc_1400CCA33
0x1400ccbbf  mov     eax, [rcx]
0x1400ccbc1  test    al, 20h
0x1400ccbc3  jnz     short loc_1400CCC40
0x1400ccbc5  mov     rdx, [r14+0B8h]
0x1400ccbcc  lea     rax, [r14+108h]
0x1400ccbd3  lea     r8, [rdx+8]
0x1400ccbd7  lea     rcx, [rsp+2D8h+var_148]
0x1400ccbdf  mov     [rsp+2D8h+var_290], rcx
0x1400ccbe4  mov     dword ptr [rsp+2D8h+var_298], r12d
0x1400ccbe9  mov     [rsp+2D8h+Size], r12
0x1400ccbee  mov     byte ptr [rsp+2D8h+Index], r12b
0x1400ccbf3  mov     [rsp+2D8h+SectorCountFromStartingLbn], r12
0x1400ccbf8  mov     [rsp+2D8h+Irp], rax
0x1400ccbfd  mov     r9d, [r14+100h]
0x1400ccc04  mov     rcx, rsi
0x1400ccc07  call    NtfsLookupInFileRecord
0x1400ccc0c  test    al, al
0x1400ccc0e  jnz     short loc_1400CCC18
0x1400ccc10  mov     ebx, r12d
0x1400ccc13  jmp     loc_1400CE8CA
0x1400ccc18  mov     r8, [rsp+2D8h+var_148]
0x1400ccc20  mov     rdx, r14
0x1400ccc23  mov     rcx, rsi
0x1400ccc26  call    NtfsUpdateScbFromAttribute
0x1400ccc2b  lea     rdx, [rsp+2D8h+var_148]
0x1400ccc33  call    NtfsCleanupAttributeContext
0x1400ccc38  mov     [rsp+2D8h+var_254], r12b
0x1400ccc40  xor     r8d, r8d
0x1400ccc43  mov     rdx, [r14+0B8h]
0x1400ccc4a  mov     rcx, rsi
0x1400ccc4d  call    NtfsReleaseFcbEx
0x1400ccc52  mov     dil, r15b
0x1400ccc55  and     dil, 0FEh
0x1400ccc59  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccc61  lea     rdx, [rsp+2D8h+var_148]
0x1400ccc69  call    NtfsCleanupAttributeContext
0x1400ccc6e  mov     [rsp+2D8h+var_254], r12b
0x1400ccc76  mov     r12d, [r13+164h]
0x1400ccc7d  mov     eax, 200000h
0x1400ccc82  cmp     r12d, eax
0x1400ccc85  cmovb   r12d, eax
0x1400ccc89  mov     [rsp+2D8h+var_200], r12d
0x1400ccc91  mov     edx, r12d; NumberOfBytes
0x1400ccc94  mov     ecx, 200h; PoolType
0x1400ccc99  mov     r8d, 4446744Eh; Tag
0x1400ccc9f  call    cs:__imp_ExAllocatePoolWithTag
0x1400ccca6  nop     dword ptr [rax+rax+00h]
0x1400cccab  mov     r15, rax
0x1400cccae  mov     [rsp+2D8h+P], rax
0x1400cccb6  xor     eax, eax
0x1400cccb8  test    r15, r15
0x1400cccbb  jz      short loc_1400CCD2D
0x1400cccbd  mov     [rsp+2D8h+Irp], rax; Irp
0x1400cccc2  xor     r9d, r9d; ChargeQuota
0x1400cccc5  xor     r8d, r8d; SecondaryBuffer
0x1400cccc8  mov     edx, r12d; Length
0x1400ccccb  mov     rcx, r15; VirtualAddress
0x1400cccce  call    cs:__imp_IoAllocateMdl
0x1400cccd5  nop     dword ptr [rax+rax+00h]
0x1400cccda  mov     r12, rax
0x1400cccdd  mov     [rsp+2D8h+Mdl], rax
0x1400ccce5  test    rax, rax
0x1400ccce8  jz      short loc_1400CCD12
0x1400cccea  mov     rcx, rax; MemoryDescriptorList
0x1400ccced  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400cccf4  nop     dword ptr [rax+rax+00h]
0x1400cccf9  mov     edx, 1
0x1400cccfe  mov     rcx, r12
0x1400ccd01  call    cs:__imp_MmMdlPageContentsState
0x1400ccd08  nop     dword ptr [rax+rax+00h]
0x1400ccd0d  mov     rax, r15
0x1400ccd10  jmp     short loc_1400CCD2D
0x1400ccd12  xor     edx, edx; Tag
0x1400ccd14  mov     rcx, r15; P
0x1400ccd17  call    cs:__imp_ExFreePoolWithTag
0x1400ccd1e  nop     dword ptr [rax+rax+00h]
0x1400ccd23  xor     eax, eax
  ... truncated ...
```
