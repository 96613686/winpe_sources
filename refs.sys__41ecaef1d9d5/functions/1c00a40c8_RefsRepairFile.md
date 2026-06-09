# RefsRepairFile

- ea: `0x1c00a40c8`
- end: `0x1c00a56e8`
- name: `RefsRepairFile`
- size: `5664`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1c00a1b4c`

## callees

- `0x1c0001f1c`
- `0x1c0002bac`
- `0x1c0002ce0`
- `0x1c0002ef8`
- `0x1c00039b8`
- `0x1c00040f8`
- `0x1c0004330`
- `0x1c000440c`
- `0x1c00045c4`
- `0x1c00046d4`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c0092304`
- `0x1c0092430`
- `0x1c009d5c4`
- `0x1c00a08f8`
- `0x1c00a097c`
- `0x1c00a163c`
- `0x1c00a2fbc`
- `0x1c00a40c8`
- `0x1c00a77b0`
- `0x1c00ae880`
- `0x1c00aeae0`
- `0x1c00b18ec`
- `0x1c00b19b0`
- `0x1c00b1b78`
- `0x1c00b37c0`
- `0x1c00b38ac`
- `0x1c00cb0b8`
- `0x1c0151cec`
- `0x1c0156b80`
- `0x1c015e134`
- `0x1c01632d4`
- `0x1c01c0908`
- `0x1c01c42bc`
- `0x1c01cd240`
- `0x1c01d4c30`
- `0x1c01d541c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00a41cf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00a41cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a538f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a53b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5427`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5637`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5659`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a56d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a538f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a53b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5427`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5637`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a5659`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a56d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a5369`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a560f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a5369`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a560f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a46ca`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a487f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a46ca`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a487f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a480d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a489f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a52f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a5592`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a480d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a489f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a52f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a5592`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a54d9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a5503`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a552d`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a5557`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a54d9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a5503`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a552d`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a5557`
- `ntoskrnl!RtlCompareMemory` at `0x1c00a51e7`
- `ntoskrnl!RtlCompareMemory` at `0x1c00a51e7`

## pseudocode

```c
__int64 __fastcall RefsRepairFile(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v7; // r14
  int v8; // edi
  int v9; // ecx
  __int64 v10; // r8
  int v11; // edi
  int v12; // eax
  __int16 v13; // di
  int v14; // eax
  __int64 v15; // r9
  BOOL v16; // eax
  int v17; // eax
  int v18; // edi
  char v19; // al
  BOOL v20; // eax
  int v21; // eax
  int IndexEntryByRow; // eax
  __int64 v23; // r14
  __int64 v24; // r15
  __int64 v25; // rdx
  __int64 Fcb; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rdx
  int v30; // eax
  int v31; // edx
  int v32; // eax
  __int64 v33; // r9
  BOOL v34; // eax
  __int64 v35; // rax
  __int64 v36; // rdi
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 i; // rdi
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rdx
  CmsBPlusTable *v52; // rdx
  __int64 v53; // r14
  SIZE_T v54; // r8
  __int64 NextChildLcb; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  SIZE_T v58; // rax
  __int64 v59; // r8
  __int64 v60; // rcx
  BOOL v61; // eax
  int Status; // [rsp+40h] [rbp-1D8h]
  char v64; // [rsp+44h] [rbp-1D4h]
  char v65; // [rsp+45h] [rbp-1D3h]
  char v66; // [rsp+46h] [rbp-1D2h] BYREF
  char v67; // [rsp+47h] [rbp-1D1h]
  char v68; // [rsp+48h] [rbp-1D0h]
  char v69; // [rsp+49h] [rbp-1CFh]
  char v70; // [rsp+4Ah] [rbp-1CEh]
  char v71; // [rsp+4Bh] [rbp-1CDh] BYREF
  _BYTE v72[4]; // [rsp+4Ch] [rbp-1CCh] BYREF
  __int64 v73; // [rsp+50h] [rbp-1C8h]
  __int64 v74; // [rsp+58h] [rbp-1C0h]
  __int16 v75[2]; // [rsp+60h] [rbp-1B8h] BYREF
  int v76; // [rsp+64h] [rbp-1B4h]
  __int64 v77; // [rsp+68h] [rbp-1B0h]
  SIZE_T NumberOfBytes; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 Scb; // [rsp+78h] [rbp-1A0h]
  __int64 v80; // [rsp+80h] [rbp-198h] BYREF
  char *v81; // [rsp+88h] [rbp-190h]
  __int64 v82; // [rsp+A0h] [rbp-178h]
  __int64 v83; // [rsp+A8h] [rbp-170h]
  PVOID P; // [rsp+B0h] [rbp-168h] BYREF
  void *Source2[2]; // [rsp+B8h] [rbp-160h] BYREF
  __int128 v86; // [rsp+C8h] [rbp-150h]
  char v87[8]; // [rsp+D8h] [rbp-140h] BYREF
  __int64 v88; // [rsp+E0h] [rbp-138h]
  PVOID v89[2]; // [rsp+E8h] [rbp-130h] BYREF
  __int64 v90; // [rsp+F8h] [rbp-120h] BYREF
  __int64 v91; // [rsp+108h] [rbp-110h]
  __int64 v92; // [rsp+110h] [rbp-108h]
  __int128 v93; // [rsp+118h] [rbp-100h] BYREF
  __int64 v94; // [rsp+128h] [rbp-F0h]
  _QWORD v95[2]; // [rsp+130h] [rbp-E8h] BYREF
  _QWORD v96[2]; // [rsp+140h] [rbp-D8h] BYREF
  int v97; // [rsp+150h] [rbp-C8h]
  __int64 v98; // [rsp+158h] [rbp-C0h]
  _BYTE v99[96]; // [rsp+170h] [rbp-A8h] BYREF

  v74 = a3;
  v77 = a1;
  v88 = a1;
  v90 = a2;
  v83 = a3;
  v7 = 0;
  v73 = 0;
  Scb = 0;
  v82 = 0;
  v80 = 0;
  v81 = 0;
  *(_OWORD *)Source2 = 0;
  v86 = 0;
  LODWORD(NumberOfBytes) = 0;
  P = 0;
  v93 = 0;
  *(_OWORD *)v89 = 0;
  v75[0] = 0;
  v72[0] = 1;
  v68 = 0;
  v65 = 0;
  v70 = 0;
  v64 = 0;
  v67 = 0;
  v71 = 0;
  v69 = 0;
  v76 = 1;
  MsTriageGetSubKey(a1, a2, 1, (unsigned int)&NumberOfBytes, (__int64)Source2);
  v8 = NumberOfBytes;
  Source2[1] = ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x48466552u);
  if ( !Source2[1] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, 3221225626LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741670);
    v11 = -1073741670;
    goto LABEL_9;
  }
  LODWORD(Source2[0]) = v8;
  MsTriageGetSubKey(v9, v90, 1, (unsigned int)&NumberOfBytes, (__int64)Source2);
  v12 = RefsIndexRowType(Source2, v75, v87);
  Status = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        81,
        WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
        (unsigned int)v12);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_18;
    goto LABEL_17;
  }
  v13 = v75[0];
  if ( v75[0] == 16 )
  {
    *a4 |= 2u;
    v14 = RefsRepairDirectory(a1, (unsigned int)&v90, a3, (_DWORD)a4, 0);
    v15 = (unsigned int)v14;
    Status = v14;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
LABEL_28:
      if ( !RefsStatusDebugEnabled )
        goto LABEL_18;
      goto LABEL_17;
    }
    if ( v14 < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
LABEL_27:
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, v15);
        goto LABEL_28;
      }
      v16 = 0;
    }
    else
    {
      v16 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    }
    if ( !v16 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v81 = (char *)Source2[1] + 4;
  WORD1(v80) = LOWORD(Source2[0]) - 4;
  LOWORD(v80) = LOWORD(Source2[0]) - 4;
  RefsBuildPathNameForEventLog(a1, a3, v10, (unsigned int)&v80, (__int64)v89, (__int64)&v71);
  v64 = 1;
  if ( v13 == 32 )
  {
    v17 = RefsBindMinstoreTransactionNoRaise(a1);
    Status = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          83,
          WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
          (unsigned int)v17);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_18;
      goto LABEL_17;
    }
    v18 = MsDeleteRows(*(struct CmsTransactionContext **)(a1 + 24), *(CmsTable **)(a3 + 384));
    Status = v18;
    if ( v18 == -1073741400 )
    {
      MsTriageGetContext(*(_QWORD *)(a1 + 24));
      v64 = 0;
    }
    RefsCheckpointCurrentTransaction(a1);
    v19 = v67;
    if ( v18 >= 0 )
      v19 = 1;
    v67 = v19;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
LABEL_50:
      if ( !RefsStatusDebugEnabled )
        goto LABEL_18;
      goto LABEL_17;
    }
    if ( v18 < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
LABEL_49:
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          84,
          WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
          (unsigned int)v18);
        goto LABEL_50;
      }
      v20 = 0;
    }
    else
    {
      v20 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    }
    if ( !v20 )
      goto LABEL_50;
    goto LABEL_49;
  }
  if ( v13 != 48 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v11 = -1073741637;
    }
    else
    {
      v11 = -1073741637;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, 3221225659LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637);
    goto LABEL_9;
  }
  v21 = RefsBindMinstoreTransactionNoRaise(a1);
  Status = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        86,
        WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
        (unsigned int)v21);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_18;
    goto LABEL_17;
  }
  IndexEntryByRow = RefsFindIndexEntryByRow(a1, a3, (unsigned int)Source2, 0, (__int64)&P);
  v11 = IndexEntryByRow;
  Status = IndexEntryByRow;
  if ( IndexEntryByRow != -1073741772 && IndexEntryByRow != -1073741275 )
  {
    if ( IndexEntryByRow < 0 )
    {
      if ( IndexEntryByRow == -1073741400 )
      {
        MsTriageGetContext(*(_QWORD *)(a1 + 24));
        v64 = 0;
      }
      RefsCheckpointCurrentTransaction(a1);
      goto LABEL_190;
    }
    v23 = *((_QWORD *)P + 1);
    *((_QWORD *)&v93 + 1) = v23;
    v24 = *(_QWORD *)P;
    v94 = v24;
    *(_QWORD *)&v93 = v24;
    RefsCheckpointCurrentTransaction(a1);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
    v65 = 1;
    v25 = *(_QWORD *)(a1 + 64);
    if ( v24 )
    {
      v96[0] = v24;
      v96[1] = v23;
      Fcb = RefsCreateFcb(a1, v25, (unsigned int)v96, 0, a3, (__int64)&v80, 0);
    }
    else
    {
      v95[0] = 0;
      v95[1] = v23;
      Fcb = RefsCreateFcb(a1, v25, (unsigned int)v95, 2, 0, 0, 0);
    }
    v73 = Fcb;
    v7 = Fcb;
    if ( v11 < 0 )
      goto LABEL_190;
    ++*(_DWORD *)(Fcb + 32);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
    if ( (*(_DWORD *)(v7 + 4) & 0x8000) != 0 )
    {
      v29 = *(_QWORD *)(a1 + 64);
      if ( (*(_DWORD *)(v29 + 4) & 0x100000) == 0 )
        RefsAcquireAllFiles(a1, v29, 255, 0);
    }
    if ( *(_QWORD *)(v7 + 104) )
    {
      LOBYTE(v28) = 1;
      RefsAcquirePagingResourceExclusive(v27, v7, v28);
      v69 = 1;
    }
    RefsAcquireExclusiveFcb(a1, v7, 0, 5);
    v68 = 1;
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
    --*(_DWORD *)(v7 + 32);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
    v65 = 0;
    if ( !v24 )
    {
      v30 = RefsBindMinstoreTransactionNoRaise(a1);
      Status = v30;
      if ( v30 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            89,
            WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
            (unsigned int)v30);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_18;
        goto LABEL_17;
      }
      v11 = RefsDeleteDirectoryLinkByRow(a1, v7, a3, Source2);
      if ( v11 == -1073741566 )
        v11 = 0;
      Status = v11;
      if ( v11 == -1073741400 )
      {
        MsTriageGetContext(*(_QWORD *)(a1 + 24));
        v64 = 0;
      }
      RefsCheckpointCurrentTransaction(a1);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            90,
            WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
            (unsigned int)v11);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_18;
        goto LABEL_17;
      }
      goto LABEL_173;
    }
    if ( (*(_DWORD *)(v7 + 4) & 0x8000) != 0 && (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 4LL) & 0x100000) == 0 )
      RefsDeactivateAndPostRepairUsnJournal(a1);
    LODWORD(v80) = 0;
    v81 = 0;
    Scb = RefsCreateScb(a1, v7, 128, (unsigned int)&v80, 4, 0);
    RefsIncrementCloseCounts(Scb, 0, 0);
    v70 = 1;
    v32 = RefsInitializeFileFromDisk(a1, Scb, (unsigned int)(v31 + 2));
    v33 = (unsigned int)v32;
    Status = v32;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      if ( v32 < 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
LABEL_112:
          WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, v33);
          goto LABEL_113;
        }
        v34 = 0;
      }
      else
      {
        v34 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      }
      if ( v34 )
        goto LABEL_112;
    }
LABEL_113:
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    v11 = Status;
    if ( Status == -1073741400 )
    {
      MsTriageGetContext(*(_QWORD *)(a1 + 24));
      v64 = 0;
    }
    if ( Status < 0 )
      goto LABEL_10;
    memset(v99, 0, sizeof(v99));
    v7 = v73;
    v35 = RefsMapStandardInfo(a1, v73, v99);
    *(_OWORD *)(v7 + 272) = *(_OWORD *)(v35 + 96);
    *(_QWORD *)(v7 + 264) = *(_QWORD *)(v35 + 88);
    MsUnpinDataOrRow(*(_QWORD *)(a1 + 24), *(_QWORD *)(v7 + 240), v99);
    if ( !*(_QWORD *)(v7 + 8) || *(_QWORD *)(v7 + 16) == *(_QWORD *)(*(_QWORD *)(v74 + 120) + 16LL) )
    {
      v36 = v74;
    }
    else
    {
      v82 = RefsCreateAndAcquireFileIdParent(a1, v7);
      if ( v82 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 )
        {
          v36 = v74;
        }
        else
        {
          v36 = v74;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_iiii(
              WPP_GLOBAL_Control->AttachedDevice,
              95,
              WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
              *(_QWORD *)(*(_QWORD *)(v74 + 120) + 16LL),
              *(_QWORD *)(v7 + 16),
              *(_QWORD *)(v7 + 8),
              *(_QWORD *)(v7 + 264));
        }
        if ( (unsigned int)RefsDeleteFileId2(a1, v82, *(_QWORD *)(v7 + 272)) == -1073741400 )
        {
          v37 = *(_QWORD *)(a1 + 24);
          if ( v37 )
          {
            v91 = 0;
            MsTriageGetContext(v37);
            if ( v91 )
              RefsDeleteTriageContextInternal(v38, v91);
          }
          else
          {
            v39 = *(_QWORD *)(a1 + 160);
            if ( v39 )
            {
              RefsDeleteTriageContextInternal(0, v39);
              *(_QWORD *)(a1 + 160) = 0;
            }
          }
        }
      }
      else
      {
        v36 = v74;
      }
    }
    *(_DWORD *)(v7 + 4) &= ~0x10u;
    v40 = RefsBindMinstoreTransactionNoRaise(a1);
    Status = v40;
    if ( v40 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          96,
          WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
          (unsigned int)v40);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_18;
LABEL_17:
      RefsStatusDebug(Status);
LABEL_18:
      v11 = Status;
LABEL_9:
      Status = v11;
LABEL_10:
      v7 = v73;
      goto LABEL_190;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_iiii(
        WPP_GLOBAL_Control->AttachedDevice,
        97,
        WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v36 + 120) + 16LL),
        *(_QWORD *)(v7 + 16),
        *(_QWORD *)(v7 + 8),
        *(_QWORD *)(v7 + 264));
    }
    v11 = RefsDeleteFileId2(a1, v36, *(_QWORD *)(v7 + 264));
    Status = v11;
    v88 += 160;
    if ( v11 == -1073741400 )
    {
      MsTriageGetContext(*(_QWORD *)(a1 + 24));
      v64 = 0;
    }
    if ( v11 < 0 )
      goto LABEL_149;
    v11 = MsDeleteRows(*(struct CmsTransactionContext **)(a1 + 24), *(CmsTable **)(v74 + 384));
    Status = v11;
    if ( v11 == -1073741400 )
    {
      MsTriageGetContext(*(_QWORD *)(a1 + 24));
      v64 = 0;
    }
    if ( v11 < 0 )
    {
LABEL_149:
      RefsAbortTransaction(a1);
      goto LABEL_190;
    }
    v43 = *(_QWORD *)(Scb + 360);
    if ( v43 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v43 + 16) + 64LL))(
        *(_QWORD *)(v43 + 16),
        *(_QWORD *)(a1 + 24),
        0);
      v44 = *(_QWORD *)(v43 + 16);
      *(_QWORD *)(v44 + 16) |= 0x200000uLL;
      *(_DWORD *)(*(_QWORD *)(v44 + 96) + 16LL) |= 0x400u;
    }
    if ( *(_QWORD *)(v7 + 240) )
      MsDoomTable(*(_QWORD *)(a1 + 24));
    for ( i = RefsGetNextChildScb(v7, 0, v41, v42); i; i = RefsGetNextChildScb(v7, i, v46, v47) )
    {
      if ( *(_WORD *)i == 2053 )
      {
        v48 = *(_QWORD *)(i + 360);
        if ( v48 )
        {
          if ( (*(_DWORD *)(i + 304) & 0x40) == 0
            && (unsigned int)CmsBPlusTable::DeleteTable(
                               *(CmsBPlusTable **)(v48 + 16),
                               *(struct CmsTransactionContext **)(a1 + 24)) == -1073741400 )
          {
            v49 = *(_QWORD *)(a1 + 24);
            if ( v49 )
            {
              v92 = 0;
              MsTriageGetContext(v49);
              if ( v92 )
                RefsDeleteTriageContextInternal(v50, v92);
            }
            else
            {
              v51 = *(_QWORD *)(a1 + 160);
              if ( v51 )
              {
                RefsDeleteTriageContextInternal(0, v51);
                *(_QWORD *)(a1 + 160) = 0;
              }
            }
          }
        }
      }
    }
    v52 = *(CmsBPlusTable **)(v7 + 240);
    if ( v52 )
      MsDeleteTable(*(struct CmsTransactionContext **)(a1 + 24), v52);
    RefsCheckpointCurrentTransaction(a1);
    v11 = 0;
    Status = 0;
    if ( v82 )
      RefsTeardownStructures(a1, v82, 0, 0);
LABEL_173:
    *(_DWORD *)(v7 + 4) |= 1u;
    LOBYTE(v10) = 1;
    RefsMarkAllScbsAsDeletedEx(a1, v7, v10, 0);
    RefsMarkAllLcbsAsDeleted(a1, v7, v74, v72);
    v67 = 1;
    goto LABEL_190;
  }
  v53 = 0;
  v64 = 0;
  v54 = LODWORD(Source2[0]);
  while ( 1 )
  {
    NextChildLcb = RefsGetNextChildLcb(a3, v53, v54);
    v53 = NextChildLcb;
    if ( !NextChildLcb )
      break;
    v57 = *(_QWORD *)(NextChildLcb + 200);
    v98 = v57 + 78;
    v97 = 2 * *(unsigned __int16 *)(v57 + 72) + 4;
    if ( v97 == (_DWORD)v54 )
    {
      v58 = RtlCompareMemory((const void *)(v57 + 78), Source2[1], v54);
      v54 = LODWORD(Source2[0]);
      if ( v58 == LODWORD(Source2[0]) )
        break;
    }
  }
  if ( !v53 )
  {
    RefsCheckpointCurrentTransaction(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, 0);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    v11 = 0;
    Status = 0;
    goto LABEL_10;
  }
  v7 = *(_QWORD *)(v53 + 32);
  v73 = v7;
  if ( *(_QWORD *)(v7 + 104) )
  {
    LOBYTE(v54) = 1;
    RefsAcquirePagingResourceExclusive(v56, v7, v54);
    v69 = 1;
  }
  RefsAcquireExclusiveFcb(a1, v7, 0, 5);
  v68 = 1;
  *(_DWORD *)(v7 + 4) |= 1u;
  LOBYTE(v59) = 1;
  RefsMarkAllScbsAsDeletedEx(a1, v7, v59, 0);
  RefsMarkAllLcbsAsDeleted(a1, v7, a3, v72);
  RefsCheckpointCurrentTransaction(a1);
  v11 = 0;
  Status = 0;
LABEL_190:
  if ( v65 )
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
  if ( v68 )
  {
    v66 = 0;
    if ( v70 )
      RefsDecrementCloseCounts(a1, Scb, 0, 0, 0, 1, 0);
    RefsTeardownStructures(a1, v7, 0, &v66);
    if ( !v66 )
    {
      if ( v69 )
      {
        v60 = v7;
        if ( *(_WORD *)v7 != 2050 )
          v60 = *(_QWORD *)(v7 + 120);
        ExReleaseResourceLite(*(PERESOURCE *)(v60 + 104));
      }
      RefsReleaseFcb(a1, v7);
    }
  }
  if ( Source2[1] )
  {
    ExFreePoolWithTag(Source2[1], 0);
    Source2[1] = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v64 )
  {
    if ( v11 == -1073741670 || v11 == -1073741801 || v11 == -1073741663 )
      v76 = -2147483647;
    LOBYTE(v10) = v67;
    RefsEtwPostSalvageEvent(*(_QWORD *)(a1 + 64), (unsigned int)v89, v10, v11, v76, 0, (__int64)&v93);
  }
  if ( v71 )
  {
    ExFreePoolWithTag(v89[1], 0);
    v89[1] = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( v11 < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
LABEL_220:
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          98,
          WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
          (unsigned int)v11);
        goto LABEL_221;
      }
      v61 = 0;
    }
    else
    {
      v61 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    }
    if ( !v61 )
      goto LABEL_221;
    goto LABEL_220;
  }
LABEL_221:
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1c00a40c8  mov     r11, rsp
0x1c00a40cb  push    rbx
0x1c00a40cc  push    rsi
0x1c00a40cd  push    rdi
0x1c00a40ce  push    r12
0x1c00a40d0  push    r13
0x1c00a40d2  push    r14
0x1c00a40d4  push    r15
0x1c00a40d6  sub     rsp, 1E0h
0x1c00a40dd  mov     rax, cs:__security_cookie
0x1c00a40e4  xor     rax, rsp
0x1c00a40e7  mov     [rsp+218h+var_48], rax
0x1c00a40ef  mov     r15, r9
0x1c00a40f2  mov     r13, r8
0x1c00a40f5  mov     [rsp+218h+var_1C0], r8
0x1c00a40fa  mov     rsi, rcx
0x1c00a40fd  mov     [rsp+218h+var_1B0], rcx
0x1c00a4102  mov     [rsp+218h+var_138], rcx
0x1c00a410a  mov     [r11-120h], rdx
0x1c00a4111  mov     [rsp+218h+var_170], r8
0x1c00a4119  xor     ebx, ebx
0x1c00a411b  mov     r14d, ebx
0x1c00a411e  mov     [rsp+218h+var_1C8], rbx
0x1c00a4123  mov     [rsp+218h+var_1A0], rbx
0x1c00a4128  mov     [r11-178h], rbx
0x1c00a412f  mov     [r11-198h], rbx
0x1c00a4136  xor     eax, eax
0x1c00a4138  mov     [r11-190h], rbx
0x1c00a413f  xorps   xmm0, xmm0
0x1c00a4142  movups  xmmword ptr [rsp+218h+Source2], xmm0
0x1c00a414a  movups  [rsp+218h+var_150], xmm0
0x1c00a4152  mov     dword ptr [rsp+218h+NumberOfBytes], ebx
0x1c00a4156  mov     [r11-168h], rbx
0x1c00a415d  movups  [rsp+218h+var_100], xmm0
0x1c00a4165  mov     [rsp+218h+Status], ebx
0x1c00a4169  xorps   xmm1, xmm1
0x1c00a416c  movups  xmmword ptr [rsp+218h+var_130], xmm1
0x1c00a4174  mov     [rsp+218h+var_1B8], bx
0x1c00a4179  lea     r12d, [rbx+1]
0x1c00a417d  mov     [rsp+218h+var_1CC], r12b
0x1c00a4182  mov     [rsp+218h+var_1D0], bl
0x1c00a4186  mov     [rsp+218h+var_1D3], bl
0x1c00a418a  mov     [rsp+218h+var_1CE], bl
0x1c00a418e  mov     [rsp+218h+var_1D4], bl
0x1c00a4192  mov     [rsp+218h+var_1D1], bl
0x1c00a4196  mov     [rsp+218h+var_1CD], bl
0x1c00a419a  mov     [rsp+218h+var_1CF], bl
0x1c00a419e  mov     [rsp+218h+var_1B4], r12d
0x1c00a41a3  lea     rax, [r11-160h]
0x1c00a41aa  mov     [rsp+218h+var_1F8], rax
0x1c00a41af  lea     r9, [rsp+218h+NumberOfBytes]
0x1c00a41b4  mov     r8d, r12d
0x1c00a41b7  call    MsTriageGetSubKey
0x1c00a41bc  mov     [rsp+218h+Status], eax
0x1c00a41c0  mov     edi, dword ptr [rsp+218h+NumberOfBytes]
0x1c00a41c4  mov     edx, edi; NumberOfBytes
0x1c00a41c6  mov     r8d, 48466552h; Tag
0x1c00a41cc  mov     ecx, r12d; PoolType
0x1c00a41cf  call    cs:__imp_ExAllocatePoolWithTag
0x1c00a41d6  nop     dword ptr [rax+rax+00h]
0x1c00a41db  mov     [rsp+218h+Source2+8], rax
0x1c00a41e3  test    rax, rax
0x1c00a41e6  jnz     short loc_1C00A425B
0x1c00a41e8  lea     r15, WPP_GLOBAL_Control
0x1c00a41ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a41f6  lea     r12d, [rbx+4]
0x1c00a41fa  cmp     rcx, r15
0x1c00a41fd  jz      short loc_1C00A4227
0x1c00a41ff  mov     eax, [rcx+2Ch]
0x1c00a4202  bt      eax, 8
0x1c00a4206  jnb     short loc_1C00A4227
0x1c00a4208  cmp     [rcx+29h], r12b
0x1c00a420c  jb      short loc_1C00A4227
0x1c00a420e  lea     edx, [rbx+50h]
0x1c00a4211  mov     r9d, 0C000009Ah
0x1c00a4217  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a421e  mov     rcx, [rcx+18h]
0x1c00a4222  call    WPP_SF_D
0x1c00a4227  mov     al, cs:RefsStatusDebugEnabled
0x1c00a422d  test    al, al
0x1c00a422f  jz      short loc_1C00A4248
0x1c00a4231  mov     r8d, 0DB2h
0x1c00a4237  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a423e  mov     ecx, 0C000009Ah; Status
0x1c00a4243  call    RefsStatusDebug
0x1c00a4248  mov     edi, 0C000009Ah
0x1c00a424d  mov     [rsp+218h+Status], edi
0x1c00a4251  mov     r14, [rsp+218h+var_1C8]
0x1c00a4256  jmp     loc_1C00A52E6
0x1c00a425b  mov     dword ptr [rsp+218h+Source2], edi
0x1c00a4262  lea     rax, [rsp+218h+Source2]
0x1c00a426a  mov     [rsp+218h+var_1F8], rax
0x1c00a426f  lea     r9, [rsp+218h+NumberOfBytes]
0x1c00a4274  mov     r8d, r12d
0x1c00a4277  mov     rdx, [rsp+218h+var_120]
0x1c00a427f  call    MsTriageGetSubKey
0x1c00a4284  mov     [rsp+218h+Status], eax
0x1c00a4288  lea     r8, [rsp+218h+var_140]
0x1c00a4290  lea     rdx, [rsp+218h+var_1B8]
0x1c00a4295  lea     rcx, [rsp+218h+Source2]
0x1c00a429d  call    RefsIndexRowType
0x1c00a42a2  mov     r9d, eax
0x1c00a42a5  mov     [rsp+218h+Status], eax
0x1c00a42a9  test    eax, eax
0x1c00a42ab  jns     short loc_1C00A4313
0x1c00a42ad  lea     r15, WPP_GLOBAL_Control
0x1c00a42b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a42bb  mov     r12d, 4
0x1c00a42c1  cmp     rcx, r15
0x1c00a42c4  jz      short loc_1C00A42EA
0x1c00a42c6  mov     eax, [rcx+2Ch]
0x1c00a42c9  bt      eax, 8
0x1c00a42cd  jnb     short loc_1C00A42EA
0x1c00a42cf  cmp     [rcx+29h], r12b
0x1c00a42d3  jb      short loc_1C00A42EA
0x1c00a42d5  lea     edx, [r12+4Dh]
0x1c00a42da  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a42e1  mov     rcx, [rcx+18h]
0x1c00a42e5  call    WPP_SF_D
0x1c00a42ea  mov     al, cs:RefsStatusDebugEnabled
0x1c00a42f0  test    al, al
0x1c00a42f2  jz      short loc_1C00A430A
0x1c00a42f4  mov     r8d, 0DCDh
0x1c00a42fa  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a4301  mov     ecx, [rsp+218h+Status]; Status
0x1c00a4305  call    RefsStatusDebug
0x1c00a430a  mov     edi, [rsp+218h+Status]
0x1c00a430e  jmp     loc_1C00A424D
0x1c00a4313  movzx   edi, [rsp+218h+var_1B8]
0x1c00a4318  mov     rcx, rsi
0x1c00a431b  cmp     di, 10h
0x1c00a431f  jnz     loc_1C00A43BB
0x1c00a4325  or      dword ptr [r15], 2
0x1c00a4329  mov     byte ptr [rsp+218h+var_1F8], bl
0x1c00a432d  mov     r9, r15
0x1c00a4330  mov     r8, r13
0x1c00a4333  lea     rdx, [rsp+218h+var_120]
0x1c00a433b  call    RefsRepairDirectory
0x1c00a4340  mov     r9d, eax
0x1c00a4343  mov     [rsp+218h+Status], eax
0x1c00a4347  lea     r15, WPP_GLOBAL_Control
0x1c00a434e  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a4355  cmp     rcx, r15
0x1c00a4358  jz      short loc_1C00A439C
0x1c00a435a  mov     eax, [rcx+2Ch]
0x1c00a435d  bt      eax, 8
0x1c00a4361  jnb     short loc_1C00A439C
0x1c00a4363  mov     r12d, 4
0x1c00a4369  test    r9d, r9d
0x1c00a436c  js      short loc_1C00A4379
0x1c00a436e  mov     eax, ebx
0x1c00a4370  cmp     byte ptr [rcx+29h], 5
0x1c00a4374  setnb   al
0x1c00a4377  jmp     short loc_1C00A4381
0x1c00a4379  cmp     [rcx+29h], r12b
0x1c00a437d  jnb     short loc_1C00A4385
0x1c00a437f  mov     eax, ebx
0x1c00a4381  test    eax, eax
0x1c00a4383  jz      short loc_1C00A43A2
0x1c00a4385  mov     edx, 52h ; 'R'
0x1c00a438a  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a4391  mov     rcx, [rcx+18h]
0x1c00a4395  call    WPP_SF_D
0x1c00a439a  jmp     short loc_1C00A43A2
0x1c00a439c  mov     r12d, 4
0x1c00a43a2  mov     al, cs:RefsStatusDebugEnabled
0x1c00a43a8  test    al, al
0x1c00a43aa  jz      loc_1C00A430A
0x1c00a43b0  mov     r8d, 0DDBh
0x1c00a43b6  jmp     loc_1C00A42FA
0x1c00a43bb  mov     rax, [rsp+218h+Source2+8]
0x1c00a43c3  add     rax, 4
0x1c00a43c7  mov     [rsp+218h+var_190], rax
0x1c00a43cf  movzx   eax, word ptr [rsp+218h+Source2]
0x1c00a43d7  mov     r12d, 4
0x1c00a43dd  sub     ax, r12w
0x1c00a43e1  mov     word ptr [rsp+218h+var_198+2], ax
0x1c00a43e9  mov     word ptr [rsp+218h+var_198], ax
0x1c00a43f1  lea     rax, [rsp+218h+var_1CD]
0x1c00a43f6  mov     [rsp+218h+var_1F0], rax
0x1c00a43fb  lea     rax, [rsp+218h+var_130]
0x1c00a4403  mov     [rsp+218h+var_1F8], rax
0x1c00a4408  lea     r9, [rsp+218h+var_198]
0x1c00a4410  mov     rdx, r13
0x1c00a4413  call    RefsBuildPathNameForEventLog
0x1c00a4418  lea     r15d, [r12-3]
0x1c00a441d  mov     [rsp+218h+var_1D4], r15b
0x1c00a4422  cmp     di, 20h ; ' '
0x1c00a4426  jnz     loc_1C00A454B
0x1c00a442c  mov     rcx, rsi
0x1c00a442f  call    RefsBindMinstoreTransactionNoRaise
0x1c00a4434  mov     r9d, eax
0x1c00a4437  mov     [rsp+218h+Status], eax
0x1c00a443b  test    eax, eax
0x1c00a443d  jns     short loc_1C00A448F
0x1c00a443f  lea     r15, WPP_GLOBAL_Control
0x1c00a4446  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a444d  cmp     rcx, r15
0x1c00a4450  jz      short loc_1C00A4476
0x1c00a4452  mov     eax, [rcx+2Ch]
0x1c00a4455  bt      eax, 8
0x1c00a4459  jnb     short loc_1C00A4476
0x1c00a445b  cmp     [rcx+29h], r12b
0x1c00a445f  jb      short loc_1C00A4476
0x1c00a4461  lea     edx, [r12+4Fh]
0x1c00a4466  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a446d  mov     rcx, [rcx+18h]
0x1c00a4471  call    WPP_SF_D
0x1c00a4476  mov     al, cs:RefsStatusDebugEnabled
0x1c00a447c  test    al, al
0x1c00a447e  jz      loc_1C00A430A
0x1c00a4484  mov     r8d, 0E0Ch
0x1c00a448a  jmp     loc_1C00A42FA
0x1c00a448f  lea     r9, [rsp+218h+Source2]
0x1c00a4497  mov     rdx, [r13+180h]; this
0x1c00a449e  mov     rcx, [rsi+18h]; struct CmsTransactionContext *
0x1c00a44a2  call    MsDeleteRows
0x1c00a44a7  mov     edi, eax
0x1c00a44a9  mov     [rsp+218h+Status], eax
0x1c00a44ad  mov     r13d, 0C00001A8h
0x1c00a44b3  cmp     eax, r13d
0x1c00a44b6  jnz     short loc_1C00A44CC
0x1c00a44b8  lea     rdx, [rsi+0A0h]
0x1c00a44bf  mov     rcx, [rsi+18h]
0x1c00a44c3  call    MsTriageGetContext
0x1c00a44c8  mov     [rsp+218h+var_1D4], bl
0x1c00a44cc  mov     rcx, rsi
0x1c00a44cf  call    RefsCheckpointCurrentTransaction
0x1c00a44d4  movzx   eax, [rsp+218h+var_1D1]
0x1c00a44d9  test    edi, edi
0x1c00a44db  cmovns  eax, r15d
0x1c00a44df  mov     [rsp+218h+var_1D1], al
0x1c00a44e3  lea     r15, WPP_GLOBAL_Control
0x1c00a44ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a44f1  cmp     rcx, r15
0x1c00a44f4  jz      short loc_1C00A4532
0x1c00a44f6  mov     eax, [rcx+2Ch]
0x1c00a44f9  bt      eax, 8
0x1c00a44fd  jnb     short loc_1C00A4532
0x1c00a44ff  test    edi, edi
0x1c00a4501  js      short loc_1C00A450E
0x1c00a4503  mov     eax, ebx
0x1c00a4505  cmp     byte ptr [rcx+29h], 5
0x1c00a4509  setnb   al
0x1c00a450c  jmp     short loc_1C00A4516
0x1c00a450e  cmp     [rcx+29h], r12b
0x1c00a4512  jnb     short loc_1C00A451A
0x1c00a4514  mov     eax, ebx
0x1c00a4516  test    eax, eax
0x1c00a4518  jz      short loc_1C00A4532
0x1c00a451a  mov     edx, 54h ; 'T'
0x1c00a451f  mov     r9d, edi
0x1c00a4522  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a4529  mov     rcx, [rcx+18h]
0x1c00a452d  call    WPP_SF_D
0x1c00a4532  mov     al, cs:RefsStatusDebugEnabled
0x1c00a4538  test    al, al
0x1c00a453a  jz      loc_1C00A430A
0x1c00a4540  mov     r8d, 0E2Fh
0x1c00a4546  jmp     loc_1C00A42FA
0x1c00a454b  cmp     di, 30h ; '0'
0x1c00a454f  jz      short loc_1C00A45BE
0x1c00a4551  lea     r15, WPP_GLOBAL_Control
0x1c00a4558  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a455f  cmp     rcx, r15
0x1c00a4562  jz      short loc_1C00A4592
0x1c00a4564  mov     eax, [rcx+2Ch]
0x1c00a4567  bt      eax, 8
0x1c00a456b  jnb     short loc_1C00A4592
0x1c00a456d  cmp     [rcx+29h], r12b
0x1c00a4571  jb      short loc_1C00A4592
0x1c00a4573  mov     edx, 55h ; 'U'
0x1c00a4578  mov     edi, 0C00000BBh
0x1c00a457d  mov     r9d, edi
0x1c00a4580  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a4587  mov     rcx, [rcx+18h]
0x1c00a458b  call    WPP_SF_D
0x1c00a4590  jmp     short loc_1C00A4597
0x1c00a4592  mov     edi, 0C00000BBh
0x1c00a4597  mov     al, cs:RefsStatusDebugEnabled
0x1c00a459d  test    al, al
0x1c00a459f  jz      loc_1C00A424D
0x1c00a45a5  mov     r8d, 0E3Eh
0x1c00a45ab  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a45b2  mov     ecx, edi; Status
0x1c00a45b4  call    RefsStatusDebug
0x1c00a45b9  jmp     loc_1C00A424D
0x1c00a45be  mov     rcx, rsi
0x1c00a45c1  call    RefsBindMinstoreTransactionNoRaise
0x1c00a45c6  mov     r9d, eax
0x1c00a45c9  mov     [rsp+218h+Status], eax
0x1c00a45cd  test    eax, eax
0x1c00a45cf  jns     short loc_1C00A4621
0x1c00a45d1  lea     r15, WPP_GLOBAL_Control
0x1c00a45d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a45df  cmp     rcx, r15
0x1c00a45e2  jz      short loc_1C00A4608
0x1c00a45e4  mov     eax, [rcx+2Ch]
0x1c00a45e7  bt      eax, 8
0x1c00a45eb  jnb     short loc_1C00A4608
  ... truncated ...
```
