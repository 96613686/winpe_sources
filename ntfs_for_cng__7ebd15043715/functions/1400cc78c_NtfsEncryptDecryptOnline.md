# NtfsEncryptDecryptOnline

- ea: `0x1400cc78c`
- end: `0x1400ceb84`
- name: `NtfsEncryptDecryptOnline`
- size: `9208`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `67`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027af08`

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
- `0x14004601c`
- `0x140059370`
- `0x1400596c0`
- `0x1400cc78c`
- `0x1401250b0`
- `0x1401261d0`
- `0x140128d50`
- `0x14012be00`
- `0x14013cde0`
- `0x140140380`
- `0x140158af0`
- `0x140159768`
- `0x14015a570`
- `0x140160be0`
- `0x140160e90`
- `0x1401620c0`
- `0x140162370`
- `0x140163f78`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0ba1`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0ba1`
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
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccd17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce926`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0bb2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c07c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c07c8`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`

## pseudocode

```c
__int64 __fastcall NtfsEncryptDecryptOnline(__int64 a1, IRP *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r15
  unsigned int v8; // ebx
  __int64 v9; // r13
  __int64 v10; // r8
  char v11; // di
  __int64 m; // rcx
  unsigned __int8 v13; // di
  char v14; // r9
  __int64 v15; // r11
  unsigned __int16 v16; // ax
  unsigned int v17; // r8d
  unsigned int *v18; // r12
  __int64 v19; // r8
  char v20; // r15
  int v21; // r10d
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  ULONG v25; // r12d
  PVOID PoolWithTag; // r15
  PVOID v27; // rax
  struct _MDL *v28; // rax
  struct _MDL *v29; // r12
  unsigned int v30; // r12d
  unsigned __int8 v31; // r15
  __int64 v32; // rcx
  char v33; // r15
  __int64 Scb; // r12
  char v35; // r15
  __int64 v36; // r8
  char v37; // di
  _QWORD *v38; // rbx
  int v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // r9
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // r8
  char v45; // di
  __int64 v46; // r8
  unsigned int v47; // r8d
  __int64 v48; // rbx
  int v49; // eax
  int v50; // edx
  __int64 v51; // rbx
  char v52; // r15
  __int64 v53; // rcx
  char v54; // di
  __int64 v55; // rcx
  __int64 v56; // rcx
  char v57; // r15
  __int64 v58; // rax
  char v59; // di
  __int64 v60; // rdx
  bool v61; // zf
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // r8
  int v66; // r12d
  int v67; // eax
  unsigned int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rcx
  char v72; // di
  char v73; // cl
  LONGLONG v74; // r12
  __int64 v75; // rdx
  int v76; // ebx
  unsigned int v77; // ebx
  int *v78; // rdx
  char v79; // di
  __int64 v80; // rbx
  int v81; // ebx
  __int64 v82; // rbx
  int v83; // r9d
  __int64 v84; // rcx
  __int64 v85; // r9
  __int64 v86; // rax
  unsigned int v87; // eax
  __int64 v88; // rdx
  __int64 v89; // r9
  signed int v90; // eax
  __int64 v91; // r9
  int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // r8
  unsigned int i; // eax
  __int64 v97; // rcx
  char v98; // al
  __int64 v99; // rcx
  unsigned int v100; // r8d
  __int64 v101; // rdx
  unsigned int k; // eax
  __int64 v103; // rax
  __int64 v104; // rcx
  PVOID v105; // r15
  unsigned int v106; // eax
  __int64 v107; // rdx
  __int64 n; // rcx
  int SectorCountFromStartingLbn; // [rsp+C0h] [rbp-2B0h]
  int Index; // [rsp+C8h] [rbp-2A8h]
  int Indexb; // [rsp+C8h] [rbp-2A8h]
  int Indexa; // [rsp+C8h] [rbp-2A8h]
  int Indexc; // [rsp+C8h] [rbp-2A8h]
  size_t Size; // [rsp+D0h] [rbp-2A0h]
  char v116; // [rsp+11Ch] [rbp-254h]
  bool v117; // [rsp+11Eh] [rbp-252h] BYREF
  char v118; // [rsp+11Fh] [rbp-251h]
  int v119; // [rsp+120h] [rbp-250h]
  int v120; // [rsp+124h] [rbp-24Ch]
  unsigned int v121; // [rsp+128h] [rbp-248h]
  char v122; // [rsp+12Ch] [rbp-244h]
  int v123; // [rsp+130h] [rbp-240h]
  PVOID P; // [rsp+138h] [rbp-238h] BYREF
  PMDL Mdl; // [rsp+140h] [rbp-230h] BYREF
  int v126; // [rsp+148h] [rbp-228h]
  __int64 SectorCountFromLbn; // [rsp+150h] [rbp-220h] BYREF
  int v128; // [rsp+158h] [rbp-218h]
  unsigned int v129; // [rsp+15Ch] [rbp-214h]
  int v130; // [rsp+160h] [rbp-210h]
  __int64 v131; // [rsp+168h] [rbp-208h]
  signed int v132; // [rsp+170h] [rbp-200h]
  __int64 v133; // [rsp+178h] [rbp-1F8h]
  int *v134; // [rsp+180h] [rbp-1F0h]
  __int16 v135; // [rsp+188h] [rbp-1E8h]
  LONGLONG v136; // [rsp+190h] [rbp-1E0h]
  __int64 v137; // [rsp+198h] [rbp-1D8h] BYREF
  _DWORD *v138; // [rsp+1A0h] [rbp-1D0h]
  __int64 v139; // [rsp+1A8h] [rbp-1C8h]
  unsigned int v140; // [rsp+1B0h] [rbp-1C0h]
  __int64 v141[2]; // [rsp+1B8h] [rbp-1B8h] BYREF
  int v142; // [rsp+1C8h] [rbp-1A8h] BYREF
  __int64 Lbn; // [rsp+1D0h] [rbp-1A0h] BYREF
  __int64 v144; // [rsp+1D8h] [rbp-198h] BYREF
  __int64 v145; // [rsp+1E0h] [rbp-190h] BYREF
  __int64 v146; // [rsp+1E8h] [rbp-188h]
  LONGLONG v147; // [rsp+1F0h] [rbp-180h] BYREF
  __int64 j; // [rsp+1F8h] [rbp-178h]
  __int64 v149; // [rsp+200h] [rbp-170h]
  __int128 v150; // [rsp+208h] [rbp-168h] BYREF
  __int128 v151; // [rsp+218h] [rbp-158h]
  __int64 v152[12]; // [rsp+228h] [rbp-148h] BYREF
  LONGLONG v153; // [rsp+288h] [rbp-E8h]
  _OWORD v154[3]; // [rsp+298h] [rbp-D8h] BYREF
  __int64 v155; // [rsp+2C8h] [rbp-A8h]
  _OWORD v156[9]; // [rsp+2D8h] [rbp-98h] BYREF

  v5 = a4;
  v8 = 0;
  memset(v152, 0, 0x58u);
  v9 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 96LL);
  v141[1] = v9;
  Mdl = 0;
  P = 0;
  v120 = 0;
  v126 = 0;
  memset(v156, 0, 0x5Cu);
  v150 = 0;
  v151 = 0;
  v137 = 0;
  v130 = 0;
  SectorCountFromLbn = 0;
  Lbn = 0;
  LOBYTE(v119) = 0;
  v131 = 0;
  *(_QWORD *)(a1 + 16) |= 0x80000000uLL;
  v116 = 1;
  v11 = 0x80;
  if ( *(_QWORD *)(a3 + 16) )
  {
    if ( (a5 & 0x2000000) != 0 || (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v10);
      v11 = -126;
    }
    else
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingShared(a1, a3, v10, 0);
      v11 = -124;
    }
  }
  NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
  v13 = v11 | 1;
  v14 = 2;
  if ( (*(_DWORD *)(a3 + 512) & 2) != 0 && v5 )
  {
    if ( (*(_DWORD *)(v5 + 4) & 0x8000000) == 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v15 = *(_QWORD *)(*(_QWORD *)(a3 + 192) + 248LL);
        v16 = *(_WORD *)(v15 + 6);
        if ( v16 > 0x40u || (v16 & 1) != 0 )
        {
          v16 = 0;
          v123 = 0;
        }
        else
        {
          v123 = *(unsigned __int16 *)(v15 + 6);
        }
        LOWORD(j) = v16;
        v149 = v15 + 32;
        McTemplateU0ppwwpipdzdd_EtwWriteTransfer(*(_QWORD *)(a3 + 184), v16 >> 1, KeGetCurrentThread());
      }
      v8 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_274;
      v17 = 809897;
LABEL_18:
      NtfsStatusTraceAndDebugInternal(0, v8, v17);
      goto LABEL_274;
    }
    v5 = a4;
  }
  if ( (v13 & 4) != 0 )
  {
    v18 = (unsigned int *)(v5 + 8);
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      NtfsReleasePagingResourcePriv(m, a3);
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      LOBYTE(v19) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v19);
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v13 = v13 & 0xF8 | 3;
      v14 = 2;
    }
  }
  else
  {
    v18 = (unsigned int *)(a4 + 8);
  }
  v20 = v13;
  if ( (*v18 & 0x100) == 0 )
  {
    SetFlagInterlocked(v18, 0x100u);
    *(_DWORD *)(a3 + 448) += v21;
  }
  m = a3 + 200;
  v134 = (int *)(a3 + 200);
  if ( (v13 & (unsigned __int8)v14) != 0 )
  {
    if ( (*(_DWORD *)m & 0x2000000) != 0 )
    {
      v134 = (int *)(a3 + 200);
    }
    else
    {
      ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
      v13 = v13 & 0xF9 | 4;
      v20 = v20 & 0xF9 | 4;
      m = a3 + 200;
    }
  }
  v22 = *(_DWORD *)(a3 + 512);
  if ( (v22 & 0x10000) != 0 )
  {
    v8 = -1073741202;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_274;
    v17 = 809978;
    goto LABEL_18;
  }
  if ( (v22 & 0x4000000) != 0 )
  {
    v8 = -1073741431;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_274;
    v17 = 809988;
    goto LABEL_18;
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
                             v152) )
    {
      v8 = 0;
      goto LABEL_274;
    }
    NtfsUpdateScbFromAttribute(a1, a3, v152[0]);
    NtfsCleanupAttributeContext(v23, v152);
  }
  NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  v13 = v20 & 0xFE;
  NtfsCleanupAttributeContext(v24, v152);
  v116 = 0;
  v25 = *(_DWORD *)(v9 + 356);
  if ( v25 < 0x200000 )
    v25 = 0x200000;
  v132 = v25;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v25, 0x4446744Eu);
  P = PoolWithTag;
  v27 = 0;
  if ( PoolWithTag )
  {
    v28 = IoAllocateMdl(PoolWithTag, v25, 0, 0, 0);
    v29 = v28;
    Mdl = v28;
    if ( v28 )
    {
      MmBuildMdlForNonPagedPool(v28);
      MmMdlPageContentsState(v29, 1);
      v27 = PoolWithTag;
    }
    else
    {
      ExFreePoolWithTag(PoolWithTag, 0);
      v27 = 0;
      P = 0;
    }
  }
  if ( v27 )
  {
    v31 = v13;
  }
  else
  {
    v13 |= 0x40u;
    if ( (*(_DWORD *)(a3 + 512) & 8) != 0 )
      v30 = *(_DWORD *)(*(_QWORD *)(v9 + 5512) + 144LL);
    else
      v30 = dword_140095988;
    v132 = v30;
    v31 = v13;
    if ( v30 < *(_DWORD *)(v9 + 356) )
      v132 = *(_DWORD *)(v9 + 356);
  }
  NtfsInitializeIoContext(a1, v156, 0);
  if ( (v31 & 6) != 0 )
  {
    NtfsReleasePagingResourcePriv(v32, a3);
    v13 = v31 & 0xF9;
  }
  v33 = 0;
  Scb = v131;
  while ( 1 )
  {
    if ( (_BYTE)v119 )
      goto LABEL_245;
    v136 = 0;
    v145 = 0;
    v141[0] = 0;
    NtfsPurgeFileRecordCache(a1);
    if ( (v13 & 0x20) != 0 )
    {
      memset(v154, 0, sizeof(v154));
      v155 = 0;
      v117 = 0;
      v35 = v33 & 0xF7;
      NtfsAcquireCheckpointSynchronization(a1, v9, 18);
      v118 = 0;
      LOBYTE(v36) = 1;
      NtfsAcquireSharedVcb(a1, v9, v36);
      v37 = v13 & 0xD7 | 8;
      v38 = (_QWORD *)(a1 + 104);
      v39 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL);
      if ( (v39 & 1) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000026E, 0xC5CDAu);
        NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 810202);
      }
      if ( (v39 & 0x20) != 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0000189, 0xC5CE3u);
        NtfsRaiseStatusInternal(a1, -1073741431, 0, 0, 810211);
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 1;
      if ( *(_WORD *)(*(_QWORD *)(v9 + 1272) + 4LL) )
      {
        KeClearEvent((PRKEVENT)(v9 + 1400));
        v118 = 1;
        v38 = (_QWORD *)(a1 + 104);
      }
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      if ( v118 )
        KeWaitForSingleObject((PVOID)(v9 + 1400), Executive, 0, 0, 0);
      else
        v38 = (_QWORD *)(a1 + 104);
      NtfsCheckpointVolume((PVOID)a1, 0, 0, *(_QWORD *)(a1 + 200));
      LfsFlushToLsn(*(_QWORD *)(*v38 + 232LL), NtfsLargeMax);
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v40, (const EVENT_DESCRIPTOR *)deviosup_c23811, v9);
      }
      LOBYTE(v41) = 1;
      NtfsFreeRecentlyDeallocated(a1, *v38, &NtfsLargeMax, v41);
      NtfsMarkUnusedContextPreTrimProcessing(a1);
      NtfsPrepareToWaitForDeallocatedClustersToDrain(a1, v154);
      v33 = v35 | 8;
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v42, (const EVENT_DESCRIPTOR *)deviosup_c23826, v9);
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 0;
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      NtfsReleaseCheckpointSynchronization(v43, v9, 18);
      v117 = (v37 & 8) != 0;
      NtfsWaitForDeallocatedClustersToDrainAfterPrepare(a1, v154, &v117);
      if ( v117 )
        NtfsReleaseVcb(a1, v9);
      v13 = v37 & 0xF7;
    }
    while ( 1 )
    {
      NtfsReleaseQuotaControlIfOwned(a1);
      LOBYTE(v44) = 1;
      NtfsAcquireSharedVcb(a1, v9, v44);
      v45 = v13 | 8;
      LOBYTE(v46) = 1;
      if ( (v33 & 4) != 0 )
      {
        NtfsAcquirePagingResourceExclusive(a1, a3, v46);
        v13 = v45 | 2;
      }
      else
      {
        NtfsAcquirePagingShared(a1, a3, v46, 0);
        v13 = v45 | 4;
      }
      LODWORD(v133) = *(_DWORD *)(a3 + 512);
      if ( (v133 & 0x10000) != 0 )
      {
        v8 = -1073741202;
        if ( NtfsStatusDebugFlags )
        {
          v47 = 810330;
          goto LABEL_80;
        }
        goto LABEL_81;
      }
      if ( (v133 & 0x4000000) != 0 )
      {
        v8 = -1073741431;
        if ( NtfsStatusDebugFlags )
        {
          v47 = 810340;
          goto LABEL_80;
        }
        goto LABEL_81;
      }
      if ( (v133 & 0x40) != 0 )
      {
        v8 = -1073741533;
        if ( NtfsStatusDebugFlags )
        {
          v47 = 810350;
          goto LABEL_80;
        }
        goto LABEL_81;
      }
      if ( (v133 & 2) != 0 )
      {
        if ( a4 )
        {
          v123 = *(_DWORD *)(a4 + 4);
          if ( (v123 & 0x8000000) == 0 )
          {
            if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
            {
              v48 = *(_QWORD *)(*(_QWORD *)(a3 + 192) + 248LL);
              v49 = *(unsigned __int16 *)(v48 + 6);
              if ( (unsigned __int16)v49 > 0x40u || (v49 & 1) != 0 )
                v49 = 0;
              v130 = v49;
              LOWORD(v138) = v49;
              v139 = v48 + 32;
              McTemplateU0ppwwpipdwdd_EtwWriteTransfer(
                *(unsigned __int16 *)(a3 + 264) >> 1,
                (const EVENT_DESCRIPTOR *)deviosup_c23931,
                KeGetCurrentThread());
            }
            v8 = -1073741790;
            if ( NtfsStatusDebugFlags )
            {
              v47 = 810381;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
        }
      }
      if ( *(_DWORD *)(a3 + 516) == 3 && *(_DWORD *)(a3 + 256) == 128 )
      {
        v8 = -1073740637;
        if ( NtfsStatusDebugFlags )
        {
          v47 = 810391;
          goto LABEL_80;
        }
        goto LABEL_81;
      }
      v50 = v132;
      v120 = v132;
      v126 = v132;
      if ( *(_QWORD *)(a3 + 632) + v132 >= *(__int64 *)(a3 + 40) )
      {
        v50 = -*(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL)
            & (*(_DWORD *)(a3 + 40) + *(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL) + ~*(_DWORD *)(a3 + 632));
        v126 = v50;
        if ( v50 > v132 )
          v50 = v132;
        v120 = v50;
        v126 = v50;
      }
      v51 = v50;
      j = v50;
      if ( (v13 & 4) == 0 )
        break;
      NtfsLockFsRtlHeader(a1, a3);
      v52 = v33 | 2;
      v53 = v51 + *(_QWORD *)(a3 + 632);
      if ( v53 < *(_QWORD *)(a3 + 40) )
      {
        if ( (a5 & 0x2000000) != 0 )
        {
          memset(v152, 0, 0x58u);
          NtfsAcquireSharedFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v54 = v13 | 1;
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
                                   v152) )
          {
            NtfsReleasePagingResourcePriv(v55, a3);
            v54 &= ~4u;
            v52 |= 0x14u;
          }
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v13 = v54 & 0xFE;
          NtfsCleanupAttributeContext(v56, v152);
          v116 = 0;
        }
      }
      else
      {
        NtfsReleasePagingResourcePriv(v53, a3);
        v13 &= ~4u;
        v52 |= 4u;
      }
      NtfsUnlockFsRtlHeader(a1, a3);
      v33 = v52 & 0xFD;
      if ( (v33 & 4) == 0 )
        break;
      if ( (v13 & 8) != 0 )
      {
        NtfsReleaseVcb(a1, v9);
        v13 &= ~8u;
      }
    }
    v57 = v33 & 0xFB;
    LODWORD(v58) = a5 & 0x2000000;
    v123 = a5 & 0x2000000;
    if ( (a5 & 0x2000000) != 0 )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v59 = v13 | 1;
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (unsigned int)&NtfsEfsBackupName, 0, 0, 0);
      v131 = Scb;
      *(_DWORD *)(Scb + 512) |= 0x800000u;
      NtfsCreateInternalAttributeStream(a1, Scb, 0, 0, 0, 0);
      memset(v152, 0, 0x58u);
      v60 = *(_QWORD *)(Scb + 184);
      v138 = (_DWORD *)(Scb + 512);
      LOBYTE(Indexb) = 0;
      v61 = (unsigned __int8)NtfsLookupInFileRecord(
                               a1,
                               v60,
                               v60 + 8,
                               *(unsigned int *)(Scb + 256),
                               Scb + 264,
                               0,
                               Indexb,
                               0,
                               0,
                               v152) == 0;
      v62 = *(_DWORD *)(Scb + 512);
      if ( v61 )
      {
        *v138 = v62 & 0xFFFFFF7F;
        NtfsCreateAttribute(a1, 0, 0, 0, 1, 0, 0);
        *(_DWORD *)(Scb + 512) &= ~0x40u;
      }
      else
      {
        *v138 = v62 | 0x80;
        NtfsUpdateScbFromAttribute(a1, Scb, v152[0]);
        NtfsSnapshotScb(a1, Scb);
        *(_QWORD *)(*(_QWORD *)(Scb + 496) + 96LL) = a1;
        if ( *(_BYTE *)(v152[0] + 8) )
          NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
      }
      NtfsCheckpointCurrentTransaction(a1);
      NtfsCleanupAttributeContext(v63, v152);
      v116 = 0;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v13 = v59 & 0xFE;
      v58 = NtfsReleaseQuotaControlIfOwned(a1);
    }
    if ( (v57 & 0x10) != 0 )
    {
      v58 = *(_QWORD *)(a3 + 632) + v120;
      if ( v58 < *(_QWORD *)(a3 + 40) )
      {
        ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
        v13 = v13 & 0xF9 | 4;
      }
    }
    v33 = v57 & 0xEF;
    v64 = *(_QWORD *)(a3 + 40);
    v133 = v64;
    v65 = *(_QWORD *)(a3 + 632);
    if ( v65 < v64 )
      break;
    v146 = v64;
    LOBYTE(v58) = 1;
    v119 = v58;
    v122 = 1;
LABEL_202:
    NtfsReleaseQuotaControlIfOwned(a1);
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
    v13 |= 1u;
    if ( (_BYTE)v119 )
      v64 = -1;
    v89 = (unsigned __int8)v119;
    if ( !v123 )
      v89 = 0;
    v90 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))&xmmword_1400957A0 + 1))(
            a1,
            *(_QWORD *)(a3 + 184),
            a3 + 264,
            v89,
            v64);
    v8 = v90;
    v121 = v90;
    if ( v90 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v90 < 0xFFFFFFED
        && v90 != -1073741802
        && (unsigned int)(v90 + 2147483643) > 1
        && v90 != -1073741807
        && v90 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v90, 0xC60A4u);
      }
      NtfsRaiseStatusInternal(a1, v8, 0, 0, 811172);
    }
    LOBYTE(v91) = 1;
    NtfsPersistDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL, v91);
    if ( (_BYTE)v119 )
    {
      v92 = a5;
      if ( (a5 & 0x4000000) != 0 )
      {
        NtfsDeleteEncryptionContext(a3);
        *(_QWORD *)(a3 + 632) = -1;
        v92 = a5;
      }
      else
      {
        *(_QWORD *)(a3 + 632) = 0;
      }
      *v134 &= ~v92;
    }
    else
    {
      *(_QWORD *)(a3 + 632) = v133;
    }
    *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
    if ( (v33 & 2) != 0 )
    {
      NtfsUnlockFsRtlHeader(a1, a3);
      v33 &= ~2u;
    }
    NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
    if ( P && (v13 & 0x40) != 0 )
    {
      NtfsDeleteMdlAndBuffer(v9, (__int64)Mdl, P);
      v93 = 0;
      a2->MdlAddress = 0;
      P = 0;
      Mdl = 0;
    }
    if ( (v33 & 1) != 0 )
    {
      NtfsReleaseRangeInternal((int *)&v150);
      v33 &= ~1u;
    }
    if ( Scb )
    {
      LOBYTE(v94) = 1;
      NtfsDeleteInternalAttributeStream(a1, Scb, v94, 0);
      Scb = 0;
      v131 = 0;
    }
    if ( (v13 & 6) != 0 )
    {
      NtfsReleasePagingResourcePriv(v93, a3);
      v13 &= 0xF9u;
    }
    if ( (v13 & 1) != 0 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v13 &= ~1u;
    }
    if ( v123 )
    {
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
      if ( !(_BYTE)v119 )
        goto LABEL_242;
      NtfsReleaseQuotaControlIfOwned(a1);
      memset(v152, 0, 0x58u);
      LOBYTE(v95) = 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v95);
      v140 = 0;
      for ( i = 0; ; ++i )
      {
        v140 = i;
        if ( i >= 2 )
          break;
        v97 = *(_QWORD *)(a1 + 8LL * i + 48);
        if ( !v97 || v97 == *(_QWORD *)(a3 + 184) )
        {
          *(_QWORD *)(a1 + 8LL * i + 48) = *(_QWORD *)(a3 + 184);
          break;
        }
      }
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (unsigned int)&NtfsEfsBackupName, 0, 0, 0);
      v131 = Scb;
      *(_DWORD *)(Scb + 512) |= 0x800000u;
      *(_DWORD *)(Scb + 512) |= 0x80u;
      LOBYTE(Indexc) = 0;
      v98 = NtfsLookupInFileRecord(
              a1,
              *(_QWORD *)(a3 + 184),
              *(_QWORD *)(a3 + 184) + 8LL,
              128,
              &NtfsEfsBackupName,
              0,
              Indexc,
              0,
              0,
              v152);
      while ( v98 )
      {
        NtfsDeleteAttributeRecord(a1, *(_QWORD *)(a3 + 184), 7, v152);
        v100 = *(_DWORD *)(Scb + 256);
        v101 = *(_QWORD *)(Scb + 184);
        if ( v152[5] )
        {
          LODWORD(Size) = 0;
          v98 = NtfsLookupExternalAttribute(a1, v101, v100, (PCUNICODE_STRING)(Scb + 264), 0, 0, 0, Size, (__int64)v152);
        }
        else
        {
          LOBYTE(Index) = 0;
          v98 = NtfsLookupInFileRecord(a1, v101, 0, v100, Scb + 264, 0, Index, 0, 0, v152);
        }
      }
      NtfsCleanupAttributeContext(v99, v152);
      v116 = 0;
      NtfsCheckpointCurrentTransaction(a1);
      *(_DWORD *)(Scb + 512) |= 0x40u;
      NtfsTeardownStructures(a1, Scb, 0);
      *(_DWORD *)(a1 + 4) |= 0x40400u;
      NtfsExtendedCompleteRequestInternal(a1, 0, 0, 0, 1);
    }
    if ( (_BYTE)v119 )
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
LABEL_242:
    if ( (v13 & 8) != 0 )
    {
      NtfsReleaseVcb(a1, v9);
      v13 &= ~8u;
    }
  }
  if ( (v13 & 4) != 0 )
  {
    NtfsAcquireRange(a1, a3, v65, j, 0, (__int64)&v150);
    v33 |= 1u;
  }
  if ( (*v134 & a5) == 0 )
    *v134 |= a5;
  *(_QWORD *)(a1 + 16) |= 0x40000uLL;
  v64 = *(_QWORD *)(a3 + 632);
  v133 = v64;
  v146 = v64;
  v66 = v120;
  while ( 2 )
  {
    LOBYTE(v67) = v119;
    while ( 1 )
    {
      if ( (_BYTE)v67 || v66 <= 0 )
      {
        Scb = v131;
        goto LABEL_202;
      }
      if ( (v13 & 4) != 0 && (v33 & 1) == 0 )
      {
        NtfsAcquireRange(a1, a3, *(_QWORD *)(a3 + 632), v66, 0, (__int64)&v150);
        v33 |= 1u;
      }
      if ( (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v145) && v136 != -1 )
        break;
      v87 = v66;
      if ( v66 >= (unsigned __int64)(v145 << *(_BYTE *)(v9 + 488)) )
        v87 = v145 << *(_BYTE *)(v9 + 488);
      v137 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v87) >> *(_BYTE *)(v9 + 488);
      v88 = v137 << *(_BYTE *)(v9 + 488);
      v64 += v88;
      v133 = v64;
      v146 = v64;
      v66 -= v88;
      v120 = v66;
      v126 = v66;
LABEL_198:
      v67 = (unsigned __int8)v119;
      if ( v64 >= *(_QWORD *)(a3 + 40) )
        v67 = 1;
      v119 = v67;
      v122 = v67;
    }
    v68 = v66;
    if ( v66 >= (unsigned __int64)(v145 << *(_BYTE *)(v9 + 488)) )
      v68 = v145 << *(_BYTE *)(v9 + 488);
    v137 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v68) >> *(_BYTE *)(v9 + 488);
    NtfsPurgeFileRecordCache(a1);
    if ( (unsigned __int8)NtfsAllocateClusters(
                            a1,
                            *(_QWORD *)(a3 + 192),
                            a3,
                            (v64 + *(unsigned int *)(v9 + 480)) >> *(_BYTE *)(v9 + 488),
                            1,
                            v137,
                            0,
                            0,
                            v13 >> 7,
                            1,
                            (__int64)&v137) )
    {
      v130 = 0;
      v135 = 0;
      if ( (v13 & 0x40) != 0 )
      {
        v142 = v137 << *(_BYTE *)(v9 + 488);
        LOWORD(v70) = 2 - ((*(_DWORD *)(a3 + 512) & 8) != 0);
        NtfsCreateMdlAndBuffer(a1, v69, v70, 516, &v142, &Mdl, &P);
      }
      v73 = *(_BYTE *)(v9 + 488);
      v74 = (v64 + *(unsigned int *)(v9 + 480)) >> v73;
      v153 = v74;
      v75 = v74 + v137 - 1;
      for ( j = v75; ; v75 = j )
      {
        if ( v74 > v75 || v74 < 0 )
        {
          if ( (v13 & 0x40) != 0 )
          {
            NtfsDeleteMdlAndBuffer(v9, (__int64)Mdl, P);
            P = 0;
            Mdl = 0;
          }
          LfsSetDefragLsn(*(_QWORD *)(v9 + 232));
          NtfsPurgeFileRecordCache(a1);
          v66 = v120;
          goto LABEL_198;
        }
        v147 = v74 << v73;
        v138 = (_DWORD *)(v75 - v74 == 0x7FFFFFFFFFFFFFFFLL ? 0x7FFFFFFFFFFFFFFFLL : v75 - v74 + 1);
        if ( !FsRtlLookupBaseMcbEntry(
                (PBASE_MCB)(*(_QWORD *)(a1 + 192) + 40LL),
                v74,
                &Lbn,
                &SectorCountFromLbn,
                0,
                0,
                0) )
          break;
        if ( Lbn == -1 )
        {
          v86 = (__int64)v138;
          if ( SectorCountFromLbn <= (__int64)v138 )
            goto LABEL_191;
          goto LABEL_190;
        }
        v76 = SectorCountFromLbn;
        if ( SectorCountFromLbn > (__int64)v138 )
        {
          v76 = (int)v138;
          SectorCountFromLbn = (__int64)v138;
        }
        v77 = v76 << *(_DWORD *)(v9 + 488);
        v121 = 0;
        a2->MdlAddress = Mdl;
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v74 << *(_BYTE *)(v9 + 488),
          v136 << *(_BYTE *)(v9 + 488),
          v77,
          (__int64)a2,
          3,
          0,
          (*v134 & 0x4000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, (NTSTATUS *)&a2->IoStatus.0);
        a2->IoStatus.Information = 0;
        v78 = v134;
        if ( *(_QWORD *)(a3 + 504) && *v134 >= 0 && (*v134 & 0x4000000) != 0 && xmmword_140095740 )
        {
          xmmword_140095740(P, &v147, v77);
          v78 = v134;
        }
        if ( *(_QWORD *)(a3 + 504) && *v78 >= 0 && (*v78 & 0x2000000) != 0 && *(&xmmword_140095740 + 1) )
          ((void (__fastcall *)(PVOID, PVOID, LONGLONG *, _QWORD, _QWORD))*(&xmmword_140095740 + 1))(
            P,
            P,
            &v147,
            v77,
            *(_QWORD *)(a3 + 504));
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v74 << *(_BYTE *)(v9 + 488),
          Lbn << *(_BYTE *)(v9 + 488),
          v77,
          (__int64)a2,
          4,
          0,
          (*v134 & 0x2000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, (NTSTATUS *)&a2->IoStatus.0);
        a2->IoStatus.Information = 0;
        a2->MdlAddress = 0;
        if ( v123 )
        {
          v144 = SectorCountFromLbn;
          NtfsReleaseQuotaControlIfOwned(a1);
          NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v79 = v13 | 1;
          v80 = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (unsigned int)&NtfsEfsBackupName, 0, 0, 0);
          v131 = v80;
          NtfsCreateInternalAttributeStream(a1, v80, 0, 0, 0, 0);
          NtfsPreloadAllocationInternal(a1, v74 + v144 - 1, 0);
          NtfsAddNtfsMcbEntry(v80 + 400, v141[0], v136, SectorCountFromLbn, 0, 1u);
          NtfsRemoveNtfsMcbEntry(a3 + 400, v74, SectorCountFromLbn);
          v81 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64))&xmmword_1400957A0 + 1))(
                  a1,
                  *(_QWORD *)(a3 + 184),
                  a3 + 264,
                  0,
                  v133 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488)));
          v121 = v81;
          if ( v81 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v81 < 0xFFFFFFED
              && v81 != -1073741802
              && (unsigned int)(v81 + 2147483643) > 1
              && v81 != -1073741807
              && v81 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(a1, v81, 0xC5FF4u);
            }
            NtfsRaiseStatusInternal(a1, v81, 0, 0, 810996);
          }
          memset(v152, 0, 0x58u);
          v82 = v131;
          LOBYTE(Indexa) = 0;
          if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                   a1,
                                   *(_QWORD *)(v131 + 184),
                                   *(_QWORD *)(v131 + 184) + 8LL,
                                   *(unsigned int *)(v131 + 256),
                                   v131 + 264,
                                   0,
                                   Indexa,
                                   0,
                                   0,
                                   v152)
            && (*(_DWORD *)(v82 + 512) & 4) == 0 )
          {
            NtfsAttachCorruption_BadOrOrphanFRS(
              a1,
              2,
              811006,
              v83,
              *(_QWORD *)(v82 + 184) + 8LL,
              *(_QWORD *)(v82 + 184),
              0);
            NtfsAttachRepairInfoPriv(a1, 512, 0, (struct _LIST_ENTRY *)0xA9000C5FFELL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0xC5FFEu);
            NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v82 + 184) + 8, *(_QWORD *)(v82 + 184), 811006);
          }
          NtfsSnapshotScb(a1, v82);
          *(_QWORD *)(*(_QWORD *)(v82 + 496) + 96LL) = a1;
          LOBYTE(SectorCountFromStartingLbn) = 0;
          NtfsAddAttributeAllocation(a1, v82, v152, v141, &v144, SectorCountFromStartingLbn);
          NtfsCleanupAttributeContext(v84, v152);
          v116 = 0;
          v138 = *(_DWORD **)(v82 + 472);
          NtfsUpdateScbFromAttribute(a1, v82, 0);
          if ( *(_BYTE *)(*(_QWORD *)(v82 + 184) + 38LL) && *(_DWORD **)(v82 + 472) != v138 )
          {
            NtfsPurgeFileRecordCache(a1);
            NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v9 + 72), 0);
            NtfsAdjustFcbAllocatedClusterCount(
              a1,
              *(_QWORD *)(v82 + 184),
              (__int64)(*(_QWORD *)(v82 + 472) - (_QWORD)v138) >> *(_BYTE *)(v9 + 488));
            NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
            v79 &= ~0x10u;
          }
          LOBYTE(v85) = 1;
          NtfsPersistDelayedAllocation(a1, v74, v74 + v144 - 1, v85);
          v64 = v133;
          *(_QWORD *)(a3 + 632) = v133 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488));
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v13 = v79 & 0xFE;
          v141[0] += SectorCountFromLbn;
        }
        else
        {
          v64 = v133;
        }
LABEL_191:
        v136 += SectorCountFromLbn;
        v73 = *(_BYTE *)(v9 + 488);
        v64 += SectorCountFromLbn << v73;
        v133 = v64;
        v146 = v64;
        v120 -= SectorCountFromLbn << v73;
        v126 = v120;
        v74 += SectorCountFromLbn;
        v153 = v74;
      }
      v86 = (__int64)v138;
LABEL_190:
      SectorCountFromLbn = v86;
      goto LABEL_191;
    }
    if ( !(_WORD)v130 )
    {
      v71 = 1;
      v130 = 1;
      v135 = 1;
      v72 = v13 | 0x20;
      if ( (v33 & 1) != 0 )
      {
        NtfsReleaseRangeInternal((int *)&v150);
        v33 &= ~1u;
      }
      NtfsReleasePagingResourcePriv(v71, a3);
      v13 = v72 & 0xF9;
      continue;
    }
    break;
  }
  v8 = -1073741697;
  if ( NtfsStatusDebugFlags )
  {
    v47 = 810706;
LABEL_80:
    NtfsStatusTraceAndDebugInternal(0, v8, v47);
  }
LABEL_81:
  v121 = v8;
LABEL_245:
  *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
  if ( (v13 & 0x10) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
    v13 &= ~0x10u;
  }
  if ( P && (v13 & 0x40) != 0 )
  {
    NtfsDeleteMdlAndBuffer(v9, (__int64)Mdl, P);
    a2->MdlAddress = 0;
    P = 0;
    Mdl = 0;
  }
  if ( (v33 & 2) != 0 )
  {
    NtfsUnlockFsRtlHeader(a1, a3);
    v33 &= ~2u;
  }
  NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
  if ( (v33 & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      *(_OWORD *)(a1 + 72) = v150;
      *(_OWORD *)(a1 + 88) = v151;
    }
    else
    {
      NtfsReleaseRangeInternal((int *)&v150);
      *(_QWORD *)(a1 + 80) = 0;
    }
  }
  if ( (v13 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v129 = 0;
      for ( k = 0; ; ++k )
      {
        v129 = k;
        if ( k >= 2 )
          break;
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
      v128 = 0;
      for ( m = 0; ; m = (unsigned int)(m + 1) )
      {
        v128 = m;
        if ( (unsigned int)m >= 2 )
          break;
        if ( *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) = 0;
      }
    }
    v13 &= 0xF9u;
  }
  if ( (v13 & 1) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
    v13 &= ~1u;
  }
  if ( (v13 & 8) != 0 )
  {
    NtfsReleaseVcb(a1, v9);
    v13 &= ~8u;
  }
LABEL_274:
  v103 = *(unsigned int *)(a1 + 16);
  LODWORD(v103) = v103 & 0x7FFFFFFF;
  *(_QWORD *)(a1 + 16) = v103;
  if ( v116 )
    NtfsCleanupAttributeContext(m, v152);
  NtfsFreeIoContext(a1);
  v105 = P;
  if ( P )
  {
    a2->MdlAddress = 0;
    IoFreeMdl(Mdl);
    ExFreePoolWithTag(v105, 0);
  }
  if ( (v13 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v106 = 0;
      while ( 1 )
      {
        v107 = *(_QWORD *)(a1 + 8LL * v106 + 48);
        if ( !v107 || v107 == *(_QWORD *)(a3 + 184) )
          break;
        if ( ++v106 >= 2 )
          goto LABEL_290;
      }
      *(_QWORD *)(a1 + 8LL * v106 + 48) = *(_QWORD *)(a3 + 184);
    }
    else
    {
      NtfsReleasePagingResourcePriv(v104, *(_QWORD *)(a3 + 184));
      for ( n = 0; n != 2; ++n )
      {
        if ( *(_QWORD *)(a1 + 8 * n + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8 * n + 48) = 0;
      }
    }
  }
LABEL_290:
  if ( (v13 & 1) != 0 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  if ( (v13 & 8) != 0 )
    NtfsReleaseVcb(a1, v9);
  return v8;
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
