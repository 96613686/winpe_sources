# FveTryInlineWriteEncrypt

- ea: `0x1400d6080`
- end: `0x1400d6b8e`
- name: `FveTryInlineWriteEncrypt`
- size: `2830`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400e8a30`

## callees

- `0x140001700`
- `0x140006fec`
- `0x140008070`
- `0x140008288`
- `0x140008904`
- `0x140008cd4`
- `0x140009910`
- `0x140009bf4`
- `0x140009f00`
- `0x14000c094`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x14002c140`
- `0x14009c16c`
- `0x14009c22c`
- `0x1400d5fc0`
- `0x1400d6080`
- `0x1400d7f90`
- `0x1400d8584`
- `0x1400d89b0`
- `0x1400d9450`
- `0x1400d9620`
- `0x1400dcbc4`
- `0x1400dcccc`
- `0x1400ea008`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400d6aba`
- `ntoskrnl!IofCallDriver` at `0x1400d6aba`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d6541`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400d6541`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d6555`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d6555`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d64c5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d64c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d68e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d6b1f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d68e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d6b1f`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d61ca`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d61ca`
- `ntoskrnl!IoGetFsTrackOffsetState` at `0x1400d622c`
- `ntoskrnl!IoGetFsTrackOffsetState` at `0x1400d622c`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400d61fc`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400d61fc`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400d6383`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400d6383`
- `ntoskrnl!IoSetFsTrackOffsetState` at `0x1400d6449`
- `ntoskrnl!IoSetFsTrackOffsetState` at `0x1400d6449`
- `ntoskrnl!IoFreeMdl` at `0x1400d6ae1`
- `ntoskrnl!IoFreeMdl` at `0x1400d6ae1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d658a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d658a`
- `ntoskrnl!IoAllocateMdl` at `0x1400d6521`
- `ntoskrnl!IoAllocateMdl` at `0x1400d6521`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6913`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6913`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d6b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d6b35`
- `ntoskrnl!ExAllocatePool2` at `0x1400d64ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400d64ec`

## string_xrefs

- `0x1400d6872`: `Filter inline write`

## pseudocode

```c
bool __fastcall FveTryInlineWriteEncrypt(__int64 a1, IRP *a2, unsigned __int64 a3, ULONG a4, _BYTE *a5)
{
  __int64 v9; // rdx
  char v10; // r13
  int v11; // eax
  struct _LIST_ENTRY *Flink; // rax
  __int64 v13; // r12
  int v14; // edi
  char v15; // r15
  int v16; // eax
  PMDL v17; // rsi
  char v18; // di
  char ShouldTryInlineIceIrp; // al
  int v20; // eax
  __int64 v21; // rdx
  struct _MDL *v22; // r8
  __int64 v23; // rax
  __int64 v24; // r15
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  struct _MDL *Pool2; // r15
  PVOID MappedSystemVa; // r13
  char v31; // di
  struct _MDL *v32; // rax
  char v33; // si
  struct _MDL *v34; // rax
  __int64 v35; // r8
  struct _MDL *v36; // r13
  PMDL MdlAddress; // rcx
  __int64 v38; // rsi
  __int64 v39; // rcx
  struct _EPROCESS *Process; // rdi
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rcx
  int v45; // ecx
  char v46; // r13
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  bool v52; // zf
  _QWORD *v53; // rax
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rax
  PMDL v57; // rcx
  void *v58; // rdx
  __int64 v59; // rsi
  struct _IO_STACK_LOCATION *v60; // rax
  int v61; // ecx
  struct _IO_STACK_LOCATION *v62; // rax
  __int64 (__fastcall *v63)(); // rcx
  struct _IO_STACK_LOCATION *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rdx
  struct _MDL *v67; // rcx
  __int64 v68; // rcx
  char v70; // [rsp+30h] [rbp-D0h]
  char v71; // [rsp+31h] [rbp-CFh]
  unsigned __int8 v72; // [rsp+32h] [rbp-CEh]
  char v73; // [rsp+33h] [rbp-CDh]
  char v74; // [rsp+34h] [rbp-CCh]
  PMDL Mdl; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v77; // [rsp+48h] [rbp-B8h]
  __int64 v78; // [rsp+50h] [rbp-B0h]
  __int64 v79; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v80; // [rsp+60h] [rbp-A0h]
  PMDL v81; // [rsp+68h] [rbp-98h]
  struct _LIST_ENTRY *v82; // [rsp+70h] [rbp-90h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+78h] [rbp-88h]
  _BYTE *v84; // [rsp+80h] [rbp-80h]
  __int64 v85[32]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v86; // [rsp+190h] [rbp+90h] BYREF
  __int128 v87; // [rsp+1A0h] [rbp+A0h]

  v77 = a3;
  v84 = a5;
  memset(v85, 0, sizeof(v85));
  v10 = 0;
  v78 = *(_QWORD *)(a1 + 8);
  v11 = *(_DWORD *)(a1 + 808);
  if ( (v11 & 0x17F) == 0 || (v71 = 1, (v11 & 0x40) != 0) )
    v71 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  *a5 = 0;
  v86 = 0;
  v82 = Flink;
  v87 = 0;
  if ( *(_DWORD *)(a1 + 2328) == 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 124LL));
  }
  else
  {
    v9 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v9 + *(_QWORD *)(a1 + 2336) + 124);
  }
  v13 = AcquireInlineControl(a1, v9, 1);
  if ( !v13 )
  {
    v14 = -1073741670;
    return v14 >= 0;
  }
  *(_QWORD *)(v13 + 8) = MEMORY[0xFFFFF78000000008];
  v70 = 0;
  *(_QWORD *)v13 = a2;
  v15 = 0;
  *(_QWORD *)(v13 + 64) = a3;
  *(_DWORD *)(v13 + 72) = a4;
  *(_BYTE *)(v13 + 274) = 1;
  *(_BYTE *)(v13 + 273) = FveIsPagingRequest(a1, a2, a3, a4);
  *(_DWORD *)(v13 + 76) = IoGetIoPriorityHint(a2);
  *(_BYTE *)(v13 + 80) = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  *(_QWORD *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 24) = 0;
  *(_QWORD *)(v13 + 32) = 0;
  *(_QWORD *)(v13 + 40) = 0;
  v16 = MmAreMdlPagesCached(a2->MdlAddress);
  Mdl = 0;
  v79 = 0;
  *(_BYTE *)(v13 + 272) = v16 != 0;
  if ( (int)IoGetFsTrackOffsetState(a2, &Mdl, &v79) >= 0
    && (v17 = Mdl, (v81 = Mdl) != 0)
    && (BYTE2(Mdl->Next) & 1) != 0
    && (v80 = v79, v79 != -1)
    && Mdl->Process )
  {
    v10 = 1;
  }
  else
  {
    v80 = -1;
    v17 = 0;
    v81 = 0;
  }
  v74 = v10;
  *(_BYTE *)(v13 + 276) = v10;
  v18 = (unsigned int)((__int64 (*)(void))Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline)() != 0
      ? v10
      : 0;
  if ( v71 && (*(_DWORD *)(a1 + 808) & 0xC000) == 0 && (*(_DWORD *)(v78 + 9680) & 8) == 0 )
  {
    if ( (unsigned int)((__int64 (*)(void))Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline)() )
      ShouldTryInlineIceIrp = FveShouldTryInlineIceIrp(a1, (_DWORD)a2, v77, a4, 1, v18);
    else
      ShouldTryInlineIceIrp = FveShouldTryInlineIceIrp(a1, (_DWORD)a2, v77, a4, 1, v10);
    v70 = ShouldTryInlineIceIrp;
    v15 = ShouldTryInlineIceIrp;
  }
  v20 = ((__int64 (*)(void))Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline)();
  v22 = 0;
  if ( v20 )
  {
    if ( (*(_DWORD *)(a1 + 808) & 0xC000) == 0 && (*(_DWORD *)(a1 + 808) & 0x19) != 0 )
    {
      v23 = *(_QWORD *)(a1 + 4736);
      if ( v23 )
      {
        if ( *(_DWORD *)(v23 + 88) && (!v15 || v10) )
        {
          if ( !*(_QWORD *)(a1 + 1008) )
          {
            v14 = -1073741823;
LABEL_152:
            ReleaseInlineControl((PVOID)v13);
            return v14 >= 0;
          }
          goto LABEL_115;
        }
      }
    }
  }
  v14 = -1073741823;
  if ( *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v78 + 884) + 1712) || (v73 = 0, !*(_BYTE *)(v13 + 272)) )
    v73 = 1;
  if ( !v15 )
  {
    v24 = v78;
    goto LABEL_50;
  }
  IoClearFsTrackOffsetState(a2, v21, 0);
  v24 = v78;
  if ( (unsigned __int8)FveSimulateResourceStress(v78) )
  {
    v25 = 3221225626LL;
    goto LABEL_38;
  }
  v26 = FveIceSetIrpExtensionSteelix(a2, *(_QWORD *)(a1 + 4736), v77, a1);
  v22 = 0;
  v25 = (unsigned int)v26;
  if ( v26 < 0 )
  {
LABEL_38:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_GLOBAL_Control, a1, a2, v25);
    }
    if ( !v10 )
      goto LABEL_152;
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v25) )
    {
      v27 = *(_QWORD *)(a1 + 4736);
      if ( v27 )
      {
        if ( *(_DWORD *)(v27 + 88) )
          goto LABEL_115;
      }
    }
    if ( !(unsigned __int8)FveSimulateResourceStress(v24) )
    {
      v28 = IoSetFsTrackOffsetState(a2, v17, v80);
      v22 = 0;
      if ( v28 >= 0 )
        goto LABEL_152;
    }
    v70 = (char)v22;
LABEL_50:
    if ( (*(_DWORD *)(a1 + 808) & 0xC000) == 0 )
      goto LABEL_53;
  }
  if ( !v10 )
  {
    Mdl = v22;
    Pool2 = v22;
    v72 = (unsigned __int8)v22;
    MappedSystemVa = v22;
    v31 = (char)v22;
    goto LABEL_65;
  }
LABEL_53:
  if ( a4 > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v24 + 884) + 1592)
    || (!*(_QWORD *)(a1 + 2024)
      ? (v32 = (struct _MDL *)ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016)))
      : (v32 = (struct _MDL *)PplAllocateFromLookasideList()),
        v72 = 1,
        (Pool2 = v32) == 0) )
  {
    v72 = 2;
    Pool2 = (struct _MDL *)ExAllocatePool2(74, a4, 1883592262);
    if ( !Pool2 )
      goto LABEL_152;
  }
  v33 = 0;
  v34 = IoAllocateMdl(Pool2, a4, 0, 0, 0);
  Mdl = v34;
  v36 = v34;
  if ( v34 )
  {
    MmBuildMdlForNonPagedPool(v34);
    MmMdlPageContentsState(v36, 1);
    MdlAddress = a2->MdlAddress;
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlAddress->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    v22 = 0;
    if ( !MappedSystemVa )
    {
      v67 = Mdl;
      goto LABEL_142;
    }
    v31 = 1;
LABEL_65:
    v38 = (__int64)v22;
    v79 = (__int64)v22;
    if ( *(struct _MDL **)(a1 + 4736) == v22 )
    {
      v38 = FveTestResolveRwStorageRequest(a1, a2, 0);
      v79 = v38;
    }
    FvePerfTraceDevPtrPtr(a1, FVE_PERF_WRITE_SUBREQUEST_INIT, a2, a2);
    if ( v31 )
    {
      if ( v73 )
        memmove(Pool2, MappedSystemVa, a4);
      if ( v74 )
        Process = v81->Process;
      else
        Process = 0;
      if ( v71 )
      {
        if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v39)
          && (*(_BYTE *)(a1 + 4403) & 8) != 0
          || (v42 = *(_QWORD *)(a1 + 976), *(_WORD *)(v42 + 10) == 1) )
        {
          v43 = 0;
        }
        else
        {
          v43 = *(unsigned int *)(v42 + 28);
          if ( !(_DWORD)v43 )
            v43 = 1;
        }
        LOBYTE(v41) = v77 < v43 * (unsigned __int64)*(unsigned int *)(a1 + 1308);
      }
      else
      {
        v41 = 0;
      }
      InitializeFilterData(a1, v85, v41, v80, Process, 0);
      v85[2] = v77;
      if ( v73 )
        MappedSystemVa = Pool2;
      v85[12] = (__int64)MappedSystemVa;
      v85[11] = (__int64)FveFilteredWrite;
      LODWORD(v85[14]) = a4;
      v85[13] = (__int64)Pool2;
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v44) )
        v45 = LODWORD(v85[15]) | 3;
      else
        v45 = 3;
      v46 = v70;
      LODWORD(v85[15]) = v45;
      if ( !v71 || (*(_DWORD *)(a1 + 808) & 0xC000) != 0 || v70 )
      {
        if ( !v74 )
          goto LABEL_115;
        v45 |= 0x1000u;
        LODWORD(v85[15]) = v45;
      }
      v47 = *(unsigned int *)(v78 + 884);
      if ( *(_BYTE *)(v47 + v78 + 1293) || *(_BYTE *)(a1 + v47 + 1949) )
      {
        v45 |= 0x100u;
        v85[15] = __PAIR64__(*(_DWORD *)(a1 + 4 * v47 + 1724), v45);
      }
      v48 = *(unsigned int *)(v78 + 884);
      if ( *(_BYTE *)(v48 + v78 + 1296) || *(_BYTE *)(a1 + v48 + 1952) )
      {
        v49 = *(_DWORD *)(a1 + 4 * v48 + 1736);
        v45 |= 0x200u;
        LODWORD(v85[15]) = v45;
        LODWORD(v85[16]) = v49;
      }
      v50 = *(unsigned int *)(v78 + 884);
      if ( *(_BYTE *)(v50 + v78 + 1417) )
      {
        v51 = *(_DWORD *)(v78 + 4 * v50 + 1396);
        LODWORD(v85[15]) = v45 | 0x400;
        HIDWORD(v85[16]) = v51;
      }
      v52 = (*(_DWORD *)(a1 + 808) & 0x100) == 0;
      v85[19] = (__int64)FveDeviceFastAlloc;
      v85[20] = (__int64)FveDeviceFastFree;
      v85[18] = a1;
      if ( !v52 )
      {
        v53 = *(_QWORD **)(a1 + 736);
        if ( v53 )
        {
          if ( *v53 )
            goto LABEL_115;
        }
      }
      *(_QWORD *)(v13 + 32) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)(v13 + 40) = a4;
      FvePerfTraceDevIoCrypto(a1, FVE_PERF_IO_ENCRYPT_START, a2, v85[2], v85[14]);
      v54 = v38 ? FveTestRwParseBlockAndFilter(v85, v38, &v86) : FveParseBlockAndFilterEx(v85, &v86);
      v14 = v54;
      FvePerfTraceDevIoCrypto(a1, FVE_PERF_IO_ENCRYPT_STOP, a2, v85[2], v85[14]);
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v55) )
      {
        v56 = *(_QWORD *)(a1 + 4736);
        if ( v56 )
        {
          if ( *(_DWORD *)(v56 + 88) && (v14 == -1073741662 || DWORD2(v87) == 259) )
LABEL_115:
            KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
        }
      }
      v33 = 1;
      LogFilterTrace((unsigned int)"Filter inline write", (unsigned int)&v86, v14, a1, v85[2], v85[14]);
      if ( v14 < 0 )
      {
LABEL_139:
        v67 = Mdl;
        if ( !Mdl )
        {
LABEL_143:
          if ( !Pool2 )
            goto LABEL_149;
          goto LABEL_144;
        }
LABEL_142:
        IoFreeMdl(v67);
        goto LABEL_143;
      }
      Pool2 = 0;
      v57 = Mdl;
      *(_QWORD *)(v13 + 32) = MEMORY[0xFFFFF78000000008] - *(_QWORD *)(v13 + 32);
      v58 = (void *)v85[7];
      v59 = (__int64)a2->MdlAddress | v72;
      a2->MdlAddress = v57;
      Mdl = 0;
      if ( v58 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 8) + 9024LL), v58);
      memset(v85, 0, sizeof(v85));
    }
    else
    {
      v46 = v70;
      v14 = 0;
      v59 = 0;
    }
    v60 = a2->Tail.Overlay.CurrentStackLocation;
    v61 = BYTE1(v82);
    *(_OWORD *)&v60[-1].MajorFunction = *(_OWORD *)&v60->MajorFunction;
    *(_OWORD *)&v60[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v60->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v60[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v60->Parameters.SetQuota + 6);
    v60[-1].FileObject = v60->FileObject;
    v60[-1].Control = 0;
    v62 = CurrentStackLocation;
    if ( CurrentStackLocation )
    {
      CurrentStackLocation->Parameters.WMI.ProviderId = v13;
      v62->Parameters.QueryDirectory.FileName = 0;
      v62->Parameters.Read.ByteOffset.QuadPart = 0;
      v62->Parameters.CreatePipe.Parameters = 0;
    }
    *(_QWORD *)(v13 + 24) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)(v13 + 44) = a4;
    *(_DWORD *)(v13 + 84) = v61;
    v13 = 0;
    if ( v61 == 1 )
    {
      v63 = FveInlineIceWriteCompletionRoutineRdpLevel1;
      if ( !v46 )
        v63 = FveInlineWriteCompletionRoutineRdpLevel1;
    }
    else
    {
      v63 = FveInlineWriteCompletionRoutineRdpLevel2;
      if ( v46 )
        v63 = FveInlineIceWriteCompletionRoutineRdpLevel2;
    }
    v64 = a2->Tail.Overlay.CurrentStackLocation;
    v64[-1].Context = (PVOID)v59;
    v64[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v63;
    v64[-1].Control = -32;
    *v84 = v70;
    if ( *(_DWORD *)(a1 + 2328) == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 128LL));
    }
    else
    {
      v65 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
      ++*(_DWORD *)(v65 + *(_QWORD *)(a1 + 2336) + 128);
    }
    if ( v70 )
    {
      if ( *(_DWORD *)(a1 + 2328) == 1 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 2336) + 240LL));
      }
      else
      {
        v66 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
        ++*(_QWORD *)(v66 + *(_QWORD *)(a1 + 2336) + 240);
      }
    }
    FvePerfTraceDevPtr(a1, FVE_PERF_WRITE_SUBREQUEST_START, a2);
    if ( v70 && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9680LL) & 2) != 0 )
    {
      FveIceSimQueueRequest(a1, a2, 0, 2);
    }
    else if ( v79 )
    {
      FveTestRwStorageRequest(v79, a2);
    }
    else
    {
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
    }
    v33 = 0;
    goto LABEL_139;
  }
LABEL_144:
  if ( v72 == 1 )
  {
    v68 = *(_QWORD *)(a1 + 2024);
    if ( v68 )
    {
      LODWORD(v35) = HIDWORD(KeGetPcr()[1].LockArray);
      PplFreeToLookasideListProcessor(v68, Pool2, v35);
    }
    else
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016), Pool2);
    }
  }
  else
  {
    ExFreePoolWithTag(Pool2, 0x70455646u);
  }
LABEL_149:
  if ( v33 == 1 )
    DeInitializeFilterData(a1, v85);
  if ( v13 )
    goto LABEL_152;
  return v14 >= 0;
}

```

## disassembly

```asm
0x1400d6080  push    rbp
0x1400d6082  push    rbx
0x1400d6083  push    rsi
0x1400d6084  push    rdi
0x1400d6085  push    r12
0x1400d6087  push    r13
0x1400d6089  push    r14
0x1400d608b  push    r15
0x1400d608d  lea     rbp, [rsp-0C8h]
0x1400d6095  sub     rsp, 1C8h
0x1400d609c  mov     rax, cs:__security_cookie
0x1400d60a3  xor     rax, rsp
0x1400d60a6  mov     [rbp+100h+var_50], rax
0x1400d60ad  mov     r15, [rbp+100h+arg_20]
0x1400d60b4  mov     rdi, r8
0x1400d60b7  mov     [rsp+200h+var_1B8], r8
0x1400d60bc  mov     r14, rdx
0x1400d60bf  mov     rbx, rcx
0x1400d60c2  mov     [rbp+100h+var_180], r15
0x1400d60c6  xor     edx, edx; Val
0x1400d60c8  mov     [rsp+200h+Length], r9d
0x1400d60cd  mov     r8d, 100h; Size
0x1400d60d3  lea     rcx, [rbp+100h+var_170]; void *
0x1400d60d7  mov     esi, r9d
0x1400d60da  call    memset
0x1400d60df  mov     rax, [rbx+8]
0x1400d60e3  xor     r13d, r13d
0x1400d60e6  mov     [rsp+200h+var_1B0], rax
0x1400d60eb  mov     eax, [rbx+328h]
0x1400d60f1  lea     r8d, [r13+1]
0x1400d60f5  test    eax, 17Fh
0x1400d60fa  jz      short loc_1400D6105
0x1400d60fc  mov     [rsp+200h+var_1CF], r8b
0x1400d6101  test    al, 40h
0x1400d6103  jz      short loc_1400D610A
0x1400d6105  mov     [rsp+200h+var_1CF], r13b
0x1400d610a  mov     rax, [r14+0B8h]
0x1400d6111  xorps   xmm0, xmm0
0x1400d6114  mov     [rsp+200h+var_188], rax
0x1400d6119  mov     rax, [r14+78h]
0x1400d611d  mov     [r15], r13b
0x1400d6120  movups  [rbp+100h+var_70], xmm0
0x1400d6127  mov     [rsp+200h+var_190], rax
0x1400d612c  movups  [rbp+100h+var_60], xmm0
0x1400d6133  cmp     [rbx+918h], r8d
0x1400d613a  jnz     short loc_1400D6149
0x1400d613c  mov     rax, [rbx+920h]
0x1400d6143  lock inc dword ptr [rax+7Ch]
0x1400d6147  jmp     short loc_1400D6166
0x1400d6149  mov     eax, gs:1A4h
0x1400d6151  mov     ecx, eax
0x1400d6153  mov     rax, [rbx+920h]
0x1400d615a  imul    rdx, rcx, 128h
0x1400d6161  add     [rdx+rax+7Ch], r8d
0x1400d6166  mov     rcx, rbx
0x1400d6169  call    AcquireInlineControl
0x1400d616e  mov     r12, rax
0x1400d6171  test    rax, rax
0x1400d6174  jnz     short loc_1400D6180
0x1400d6176  mov     edi, 0C000009Ah
0x1400d617b  jmp     loc_1400D6B60
0x1400d6180  mov     rax, ds:0FFFFF78000000008h
0x1400d618a  mov     r9d, esi
0x1400d618d  mov     r8, rdi
0x1400d6190  mov     [r12+8], rax
0x1400d6195  mov     rdx, r14
0x1400d6198  mov     [rsp+200h+var_1D0], r13b
0x1400d619d  mov     rcx, rbx
0x1400d61a0  mov     [r12], r14
0x1400d61a4  mov     r15b, r13b
0x1400d61a7  mov     [r12+40h], rdi
0x1400d61ac  mov     [r12+48h], esi
0x1400d61b1  mov     byte ptr [r12+112h], 1
0x1400d61ba  call    FveIsPagingRequest
0x1400d61bf  mov     rcx, r14; Irp
0x1400d61c2  mov     [r12+111h], al
0x1400d61ca  call    cs:__imp_IoGetIoPriorityHint
0x1400d61d1  nop     dword ptr [rax+rax+00h]
0x1400d61d6  mov     [r12+4Ch], eax
0x1400d61db  mov     rax, [r14+78h]
0x1400d61df  mov     [r12+50h], al
0x1400d61e4  mov     [r12+10h], r13
0x1400d61e9  mov     [r12+18h], r13
0x1400d61ee  mov     [r12+20h], r13
0x1400d61f3  mov     [r12+28h], r13
0x1400d61f8  mov     rcx, [r14+8]
0x1400d61fc  call    cs:__imp_MmAreMdlPagesCached
0x1400d6203  nop     dword ptr [rax+rax+00h]
0x1400d6208  lea     r8, [rsp+200h+var_1A8]
0x1400d620d  mov     [rsp+200h+Mdl], r13
0x1400d6212  test    eax, eax
0x1400d6214  mov     [rsp+200h+var_1A8], r13
0x1400d6219  lea     rdx, [rsp+200h+Mdl]
0x1400d621e  mov     rcx, r14
0x1400d6221  setnz   al
0x1400d6224  mov     [r12+110h], al
0x1400d622c  call    cs:__imp_IoGetFsTrackOffsetState
0x1400d6233  nop     dword ptr [rax+rax+00h]
0x1400d6238  test    eax, eax
0x1400d623a  js      short loc_1400D6270
0x1400d623c  mov     rsi, [rsp+200h+Mdl]
0x1400d6241  mov     [rsp+200h+var_198], rsi
0x1400d6246  test    rsi, rsi
0x1400d6249  jz      short loc_1400D6270
0x1400d624b  mov     ecx, 1
0x1400d6250  test    [rsi+2], cl
0x1400d6253  jz      short loc_1400D6270
0x1400d6255  mov     rax, [rsp+200h+var_1A8]
0x1400d625a  mov     [rsp+200h+var_1A0], rax
0x1400d625f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400d6263  jz      short loc_1400D6270
0x1400d6265  cmp     [rsi+10h], r13
0x1400d6269  jz      short loc_1400D6270
0x1400d626b  mov     r13b, cl
0x1400d626e  jmp     short loc_1400D6281
0x1400d6270  mov     [rsp+200h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x1400d6279  mov     rsi, r13
0x1400d627c  mov     [rsp+200h+var_198], r13
0x1400d6281  mov     [rsp+200h+var_1CC], r13b
0x1400d6286  mov     [r12+114h], r13b
0x1400d628e  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d6293  neg     eax
0x1400d6295  sbb     dil, dil
0x1400d6298  and     dil, r13b
0x1400d629b  cmp     [rsp+200h+var_1CF], r15b
0x1400d62a0  jz      short loc_1400D62F3
0x1400d62a2  test    dword ptr [rbx+328h], 0C000h
0x1400d62ac  jnz     short loc_1400D62F3
0x1400d62ae  mov     rax, [rsp+200h+var_1B0]
0x1400d62b3  mov     eax, [rax+25D0h]
0x1400d62b9  test    al, 8
0x1400d62bb  jnz     short loc_1400D62F3
0x1400d62bd  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d62c2  mov     r9d, [rsp+200h+Length]
0x1400d62c7  mov     rdx, r14
0x1400d62ca  mov     r8, [rsp+200h+var_1B8]
0x1400d62cf  mov     rcx, rbx
0x1400d62d2  test    eax, eax
0x1400d62d4  jz      short loc_1400D62DD
0x1400d62d6  mov     byte ptr [rsp+200h+Priority], dil
0x1400d62db  jmp     short loc_1400D62E2
0x1400d62dd  mov     byte ptr [rsp+200h+Priority], r13b
0x1400d62e2  mov     byte ptr [rsp+200h+Irp], 1
0x1400d62e7  call    FveShouldTryInlineIceIrp
0x1400d62ec  mov     [rsp+200h+var_1D0], al
0x1400d62f0  mov     r15b, al
0x1400d62f3  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d62f8  xor     r8d, r8d
0x1400d62fb  test    eax, eax
0x1400d62fd  jz      short loc_1400D6349
0x1400d62ff  mov     eax, [rbx+328h]
0x1400d6305  test    eax, 0C000h
0x1400d630a  setz    cl
0x1400d630d  test    al, 19h
0x1400d630f  setnz   al
0x1400d6312  test    al, cl
0x1400d6314  jz      short loc_1400D6349
0x1400d6316  mov     rax, [rbx+1280h]
0x1400d631d  test    rax, rax
0x1400d6320  jz      short loc_1400D6349
0x1400d6322  cmp     [rax+58h], r8d
0x1400d6326  jz      short loc_1400D6349
0x1400d6328  test    r15b, r15b
0x1400d632b  jz      short loc_1400D6332
0x1400d632d  test    r13b, r13b
0x1400d6330  jz      short loc_1400D6349
0x1400d6332  cmp     [rbx+3F0h], r8
0x1400d6339  jnz     loc_1400D68FF
0x1400d633f  mov     edi, 0C0000001h
0x1400d6344  jmp     loc_1400D6B58
0x1400d6349  mov     rax, [rsp+200h+var_1B0]
0x1400d634e  mov     edi, 0C0000001h
0x1400d6353  mov     eax, [rax+374h]
0x1400d6359  cmp     [rbx+rax*4+6B0h], r8d
0x1400d6361  jnz     short loc_1400D6372
0x1400d6363  mov     [rsp+200h+var_1CD], r8b
0x1400d6368  cmp     [r12+110h], r8b
0x1400d6370  jnz     short loc_1400D6377
0x1400d6372  mov     [rsp+200h+var_1CD], 1
0x1400d6377  test    r15b, r15b
0x1400d637a  jz      loc_1400D6467
0x1400d6380  mov     rcx, r14
0x1400d6383  call    cs:__imp_IoClearFsTrackOffsetState
0x1400d638a  nop     dword ptr [rax+rax+00h]
0x1400d638f  mov     r15, [rsp+200h+var_1B0]
0x1400d6394  mov     rcx, r15
0x1400d6397  call    FveSimulateResourceStress
0x1400d639c  test    al, al
0x1400d639e  jz      short loc_1400D63A7
0x1400d63a0  mov     ecx, 0C000009Ah
0x1400d63a5  jmp     short loc_1400D63CB
0x1400d63a7  mov     r8, [rsp+200h+var_1B8]
0x1400d63ac  mov     r9, rbx
0x1400d63af  mov     rdx, [rbx+1280h]
0x1400d63b6  mov     rcx, r14
0x1400d63b9  call    FveIceSetIrpExtensionSteelix
0x1400d63be  xor     r8d, r8d
0x1400d63c1  mov     ecx, eax
0x1400d63c3  test    eax, eax
0x1400d63c5  jns     loc_1400D6478
0x1400d63cb  mov     r8, cs:WPP_GLOBAL_Control
0x1400d63d2  lea     rax, WPP_GLOBAL_Control
0x1400d63d9  cmp     r8, rax
0x1400d63dc  jz      short loc_1400D6407
0x1400d63de  mov     eax, [r8+2Ch]
0x1400d63e2  test    al, al
0x1400d63e4  jns     short loc_1400D6407
0x1400d63e6  cmp     byte ptr [r8+29h], 5
0x1400d63eb  jb      short loc_1400D6407
0x1400d63ed  mov     [rsp+200h+Priority], ecx
0x1400d63f1  mov     edx, 4Fh ; 'O'
0x1400d63f6  mov     rcx, [r8+18h]
0x1400d63fa  mov     r9, rbx
0x1400d63fd  mov     [rsp+200h+Irp], r14
0x1400d6402  call    WPP_SF_qqd
0x1400d6407  test    r13b, r13b
0x1400d640a  jz      loc_1400D6B58
0x1400d6410  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d6415  xor     r8d, r8d
0x1400d6418  test    eax, eax
0x1400d641a  jz      short loc_1400D6432
0x1400d641c  mov     rax, [rbx+1280h]
0x1400d6423  test    rax, rax
0x1400d6426  jz      short loc_1400D6432
0x1400d6428  cmp     [rax+58h], r8d
0x1400d642c  jnz     loc_1400D68FF
0x1400d6432  mov     rcx, r15
0x1400d6435  call    FveSimulateResourceStress
0x1400d643a  test    al, al
0x1400d643c  jnz     short loc_1400D6460
0x1400d643e  mov     r8, [rsp+200h+var_1A0]
0x1400d6443  mov     rdx, rsi
0x1400d6446  mov     rcx, r14
0x1400d6449  call    cs:__imp_IoSetFsTrackOffsetState
0x1400d6450  nop     dword ptr [rax+rax+00h]
0x1400d6455  xor     r8d, r8d
0x1400d6458  test    eax, eax
0x1400d645a  jns     loc_1400D6B58
0x1400d6460  mov     [rsp+200h+var_1D0], r8b
0x1400d6465  jmp     short loc_1400D646C
0x1400d6467  mov     r15, [rsp+200h+var_1B0]
0x1400d646c  test    dword ptr [rbx+328h], 0C000h
0x1400d6476  jz      short loc_1400D6495
0x1400d6478  test    r13b, r13b
0x1400d647b  jnz     short loc_1400D6495
0x1400d647d  mov     [rsp+200h+Mdl], r8
0x1400d6482  mov     r15, r8
0x1400d6485  mov     [rsp+200h+var_1CE], r8b
0x1400d648a  mov     r13, r8
0x1400d648d  mov     dil, r8b
0x1400d6490  jmp     loc_1400D65A8
0x1400d6495  mov     eax, [r15+374h]
0x1400d649c  mov     r13d, [rsp+200h+Length]
0x1400d64a1  cmp     r13d, [rbx+rax*4+638h]
0x1400d64a9  ja      short loc_1400D64DE
0x1400d64ab  mov     rcx, [rbx+7E8h]
0x1400d64b2  test    rcx, rcx
0x1400d64b5  jz      short loc_1400D64BE
0x1400d64b7  call    PplAllocateFromLookasideList
0x1400d64bc  jmp     short loc_1400D64D1
0x1400d64be  mov     rcx, [rbx+7E0h]; Lookaside
0x1400d64c5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400d64cc  nop     dword ptr [rax+rax+00h]
0x1400d64d1  mov     [rsp+200h+var_1CE], 1
0x1400d64d6  mov     r15, rax
0x1400d64d9  test    rax, rax
0x1400d64dc  jnz     short loc_1400D6509
0x1400d64de  mov     rdx, r13
0x1400d64e1  mov     ecx, 4Ah ; 'J'
0x1400d64e6  mov     r8d, 70455646h
0x1400d64ec  call    cs:__imp_ExAllocatePool2
0x1400d64f3  nop     dword ptr [rax+rax+00h]
0x1400d64f8  mov     [rsp+200h+var_1CE], 2
0x1400d64fd  mov     r15, rax
0x1400d6500  test    rax, rax
0x1400d6503  jz      loc_1400D6B58
0x1400d6509  xor     r9d, r9d; ChargeQuota
0x1400d650c  mov     [rsp+200h+Irp], 0; Irp
0x1400d6515  xor     r8d, r8d; SecondaryBuffer
0x1400d6518  mov     edx, r13d; Length
0x1400d651b  mov     rcx, r15; VirtualAddress
0x1400d651e  xor     sil, sil
0x1400d6521  call    cs:__imp_IoAllocateMdl
0x1400d6528  nop     dword ptr [rax+rax+00h]
0x1400d652d  mov     [rsp+200h+Mdl], rax
0x1400d6532  mov     r13, rax
0x1400d6535  test    rax, rax
0x1400d6538  jz      loc_1400D6AF2
0x1400d653e  mov     rcx, rax; MemoryDescriptorList
0x1400d6541  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400d6548  nop     dword ptr [rax+rax+00h]
0x1400d654d  mov     edx, 1
0x1400d6552  mov     rcx, r13
0x1400d6555  call    cs:__imp_MmMdlPageContentsState
0x1400d655c  nop     dword ptr [rax+rax+00h]
0x1400d6561  mov     rcx, [r14+8]; MemoryDescriptorList
0x1400d6565  test    byte ptr [rcx+0Ah], 5
0x1400d6569  jz      short loc_1400D6571
0x1400d656b  mov     r13, [rcx+18h]
0x1400d656f  jmp     short loc_1400D6599
  ... truncated ...
```
