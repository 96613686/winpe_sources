# FveTryInlineWriteEncrypt

- ea: `0x1400ecce0`
- end: `0x1400ed8f1`
- name: `FveTryInlineWriteEncrypt`
- size: `3089`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400ebc00`

## callees

- `0x140001710`
- `0x140006680`
- `0x1400070ac`
- `0x140008130`
- `0x140008348`
- `0x1400089c4`
- `0x140008d68`
- `0x140008d94`
- `0x1400099d0`
- `0x140009cb4`
- `0x140009fc0`
- `0x14000b998`
- `0x14000c224`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x14002a2a0`
- `0x14002d140`
- `0x14009e16c`
- `0x14009e22c`
- `0x1400bc8fc`
- `0x1400be3c0`
- `0x1400cebf8`
- `0x1400d0af0`
- `0x1400d0b64`
- `0x1400d7b80`
- `0x1400d8170`
- `0x1400db250`
- `0x1400db940`
- `0x1400dba60`
- `0x1400dbd00`
- `0x1400dfa54`
- `0x1400dfbcc`
- `0x1400ecce0`
- `0x1400ef008`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400ed7ea`
- `ntoskrnl!IofCallDriver` at `0x1400ed7ea`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ed1ec`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ed1ec`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ed204`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ed204`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ed169`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ed169`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ed867`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ed867`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ece67`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ece67`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400ece93`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400ece93`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400ed00c`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400ed00c`
- `ntoskrnl!IoSetFsTrackOffsetState` at `0x1400ed0ff`
- `ntoskrnl!IoSetFsTrackOffsetState` at `0x1400ed0ff`
- `ntoskrnl!IoFreeMdl` at `0x1400ed829`
- `ntoskrnl!IoFreeMdl` at `0x1400ed829`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ed23c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ed23c`
- `ntoskrnl!IoAllocateMdl` at `0x1400ed1cc`
- `ntoskrnl!IoAllocateMdl` at `0x1400ed1cc`
- `ntoskrnl!KeBugCheckEx` at `0x1400ed657`
- `ntoskrnl!KeBugCheckEx` at `0x1400ed657`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed87d`
- `ntoskrnl!ExAllocatePool2` at `0x1400ed195`
- `ntoskrnl!ExAllocatePool2` at `0x1400ed195`

## string_xrefs

- `0x1400ed5d1`: `Filter inline write`

## pseudocode

```c
bool __fastcall FveTryInlineWriteEncrypt(__int64 a1, IRP *a2, unsigned __int64 a3, ULONG a4, _BYTE *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r13
  int v10; // eax
  char v11; // r12
  void *v12; // r15
  struct _LIST_ENTRY *Flink; // rax
  __int64 v14; // rax
  ULONG_PTR v15; // rsi
  int v16; // ebx
  struct _MDL *v17; // r13
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  char ShouldTryInlineIceIrp; // al
  char v25; // bl
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  void *v29; // r9
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rcx
  int v33; // eax
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  PVOID MappedSystemVa; // r12
  char v38; // r15
  __int64 v39; // rcx
  PVOID v40; // rax
  struct _MDL *Mdl; // rax
  PMDL v42; // r10
  __int64 v43; // r13
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  int Flink_low_high; // eax
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  int v59; // ecx
  __int64 v60; // rax
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rax
  int v64; // eax
  bool v65; // zf
  _QWORD *v66; // rax
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  PMDL MdlAddress; // rax
  void *v72; // r15
  struct _IO_STACK_LOCATION *v73; // rax
  int v74; // ecx
  struct _IO_STACK_LOCATION *v75; // rax
  __int64 (__fastcall *v76)(); // rcx
  struct _IO_STACK_LOCATION *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rcx
  int Irp; // [rsp+20h] [rbp-E0h]
  char v83; // [rsp+30h] [rbp-D0h]
  char IsIrpWithEfsOffload2; // [rsp+31h] [rbp-CFh]
  unsigned __int8 v85; // [rsp+32h] [rbp-CEh]
  char v86; // [rsp+33h] [rbp-CDh]
  char v87; // [rsp+34h] [rbp-CCh]
  char v88; // [rsp+35h] [rbp-CBh]
  struct _MDL *v90; // [rsp+40h] [rbp-C0h]
  void *Pool2; // [rsp+48h] [rbp-B8h]
  __int64 v93; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v94; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v95; // [rsp+68h] [rbp-98h]
  struct _LIST_ENTRY *v96; // [rsp+70h] [rbp-90h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+78h] [rbp-88h]
  _BYTE *v98; // [rsp+80h] [rbp-80h]
  __int64 v99[32]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v100; // [rsp+190h] [rbp+90h] BYREF
  __int128 v101; // [rsp+1A0h] [rbp+A0h]

  v98 = a5;
  memset(v99, 0, sizeof(v99));
  v9 = *(_QWORD *)(a1 + 8);
  v10 = *(_DWORD *)(a1 + 808);
  v11 = 0;
  v95 = v9;
  v93 = 0;
  v94 = 0;
  if ( (v10 & 0x17F) == 0 || (v86 = 1, (v10 & 0x40) != 0) )
    v86 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12 = 0;
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  *a5 = 0;
  v100 = 0;
  v90 = 0;
  v101 = 0;
  Pool2 = 0;
  v85 = 0;
  v96 = Flink;
  if ( *(_DWORD *)(a1 + 2344) == 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 124LL));
  }
  else
  {
    v8 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
    ++*(_DWORD *)(v8 + *(_QWORD *)(a1 + 2352) + 124);
  }
  v14 = AcquireInlineControl(a1, v8, 1);
  v15 = v14;
  if ( !v14 )
  {
    v16 = -1073741670;
LABEL_9:
    v17 = 0;
    goto LABEL_10;
  }
  *(_QWORD *)(v14 + 8) = MEMORY[0xFFFFF78000000008];
  v83 = 0;
  *(_QWORD *)v14 = a2;
  *(_QWORD *)(v14 + 64) = a3;
  *(_DWORD *)(v14 + 72) = a4;
  *(_BYTE *)(v14 + 274) = 1;
  *(_BYTE *)(v14 + 273) = FveIsPagingRequest(a1, a2, a3, a4);
  *(_DWORD *)(v15 + 76) = IoGetIoPriorityHint(a2);
  *(_BYTE *)(v15 + 80) = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)(v15 + 24) = 0;
  *(_QWORD *)(v15 + 32) = 0;
  *(_QWORD *)(v15 + 40) = 0;
  *(_BYTE *)(v15 + 272) = (unsigned int)MmAreMdlPagesCached(a2->MdlAddress) != 0;
  IsIrpWithEfsOffload2 = FveIsIrpWithEfsOffload2(a2, &v93, &v94);
  *(_BYTE *)(v15 + 276) = IsIrpWithEfsOffload2;
  v21 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v20, v19) != 0
      ? (unsigned __int8)IsIrpWithEfsOffload2
      : 0;
  if ( !(unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline()
    || (*(_DWORD *)(v9 + 9928) & 0x8000000) != 0
    || !(unsigned __int8)FveHwAccelShouldTryInlineOffload(a1, a2, a3, a4)
    || (v87 = 1, IsIrpWithEfsOffload2) )
  {
    v87 = 0;
  }
  if ( !v86 || (*(_DWORD *)(a1 + 808) & 0xC000) != 0 || (*(_DWORD *)(v9 + 9928) & 8) != 0 )
  {
    v25 = 0;
  }
  else
  {
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v23, v22) )
      ShouldTryInlineIceIrp = FveShouldTryInlineIceIrp(a1, (_DWORD)a2, a3, a4, 1, v21);
    else
      ShouldTryInlineIceIrp = FveShouldTryInlineIceIrp(a1, (_DWORD)a2, a3, a4, 1, IsIrpWithEfsOffload2);
    v25 = ShouldTryInlineIceIrp;
    v83 = ShouldTryInlineIceIrp;
  }
  IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v23, v22);
  v29 = 0;
  if ( IsEnabledDeviceUsageNoInline )
  {
    v30 = *(_DWORD *)(a1 + 808);
    if ( (v30 & 0xC000) == 0 && (v30 & 0x19) != 0 )
    {
      v31 = *(_QWORD *)(a1 + 4752);
      if ( v31 )
      {
        if ( *(_DWORD *)(v31 + 88) && (!v25 || IsIrpWithEfsOffload2) )
        {
          if ( !*(_QWORD *)(a1 + 1008) )
          {
            v16 = -1073741823;
LABEL_34:
            v17 = 0;
            goto LABEL_10;
          }
          goto LABEL_128;
        }
      }
    }
  }
  v16 = -1073741823;
  if ( *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v9 + 884) + 1712) || (v88 = 0, !*(_BYTE *)(v15 + 272)) )
    v88 = 1;
  if ( !v83 )
  {
LABEL_56:
    if ( (*(_DWORD *)(a1 + 808) & 0xC000) == 0 )
      goto LABEL_59;
    goto LABEL_57;
  }
  IoClearFsTrackOffsetState(a2, v27, v28, 0);
  if ( (unsigned __int8)FveSimulateResourceStress(v9) )
  {
    v28 = 3221225626LL;
LABEL_45:
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 86, v28, a1, a2, v28);
    }
    if ( !IsIrpWithEfsOffload2 )
      goto LABEL_9;
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v34, v27) )
    {
      v35 = *(_QWORD *)(a1 + 4752);
      if ( v35 )
      {
        if ( *(_DWORD *)(v35 + 88) )
          goto LABEL_128;
      }
    }
    if ( !(unsigned __int8)FveSimulateResourceStress(v9) )
    {
      v36 = IoSetFsTrackOffsetState(a2, v94, v93);
      v29 = 0;
      if ( v36 >= 0 )
        goto LABEL_34;
    }
    v83 = (char)v29;
    goto LABEL_56;
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v32, v27) )
    v33 = FveIceSetIrpExtensionSteelix(a2, *(_QWORD *)(a1 + 4752), a3, a1);
  else
    v33 = FveIceSetIrpExtension(a2, *(_QWORD *)(a1 + 4752), a3 / *(unsigned int *)(a1 + 1308));
  v29 = 0;
  v28 = (unsigned int)v33;
  if ( v33 < 0 )
    goto LABEL_45;
LABEL_57:
  if ( IsIrpWithEfsOffload2 == (_BYTE)v29 )
  {
    MappedSystemVa = v29;
    v38 = (char)v29;
LABEL_71:
    v43 = (__int64)v29;
    if ( *(void **)(a1 + 4752) == v29 )
      v43 = FveTestResolveRwStorageRequest(a1, a2, 0);
    FvePerfTraceDevPtrPtr(a1, FVE_PERF_WRITE_SUBREQUEST_INIT, a2, a2);
    v44 = Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline();
    v48 = 0;
    if ( !v44 )
      goto LABEL_82;
    if ( v38 && !IsIrpWithEfsOffload2 && v87 )
    {
      if ( *(_BYTE *)(a1 + 1477) )
        Flink_low_high = (unsigned __int8)HIBYTE(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
      else
        Flink_low_high = GetPriorityFromIrpEx(a1, a2, 8, 0);
      *(_DWORD *)(v15 + 136) = Flink_low_high;
      v50 = FveHwAccelAcquireDescriptor(a1, v45, v47, v48);
      *(_QWORD *)(v15 + 304) = v50;
      v51 = v50;
      FveHwAccelReleaseDescriptor(a1, v50);
      v52 = *(_QWORD *)(v15 + 296);
      *(_QWORD *)(v15 + 304) = 0;
      FveHwAccelReleaseWorkRequest(a1, v52);
      *(_QWORD *)(v15 + 296) = 0;
      v16 = v51 != 0 ? -1073741823 : -1073741670;
    }
    if ( *(_BYTE *)(v15 + 80) >= 2u )
    {
      v11 = 0;
    }
    else
    {
LABEL_82:
      if ( v38 )
      {
        v12 = Pool2;
        if ( v88 )
          memmove(Pool2, MappedSystemVa, a4);
        if ( IsIrpWithEfsOffload2 )
          v53 = *(_QWORD *)(v94 + 16);
        else
          v53 = 0;
        if ( v86 )
        {
          if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v46, v45)
            && (*(_BYTE *)(a1 + 4419) & 8) != 0
            || (v55 = *(_QWORD *)(a1 + 976), *(_WORD *)(v55 + 10) == 1) )
          {
            v56 = 0;
          }
          else
          {
            v56 = *(unsigned int *)(v55 + 28);
            if ( !(_DWORD)v56 )
              v56 = 1;
          }
          LOBYTE(v54) = a3 < v56 * (unsigned __int64)*(unsigned int *)(a1 + 1308);
        }
        else
        {
          v54 = 0;
        }
        InitializeFilterData(a1, v99, v54, v93, v53, 0);
        v99[2] = a3;
        if ( v88 )
          MappedSystemVa = Pool2;
        v99[12] = (__int64)MappedSystemVa;
        v99[11] = (__int64)FveFilteredWrite;
        LODWORD(v99[14]) = a4;
        v99[13] = (__int64)Pool2;
        if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v58, v57) )
          v59 = LODWORD(v99[15]) | 3;
        else
          v59 = 3;
        LODWORD(v99[15]) = v59;
        if ( !v86 || (*(_DWORD *)(a1 + 808) & 0xC000) != 0 || v83 )
        {
          if ( !IsIrpWithEfsOffload2 )
            goto LABEL_128;
          v59 |= 0x1000u;
          LODWORD(v99[15]) = v59;
        }
        v60 = *(unsigned int *)(v95 + 884);
        if ( *(_BYTE *)(v60 + v95 + 1293) || *(_BYTE *)(a1 + v60 + 1949) )
        {
          v59 |= 0x100u;
          v99[15] = __PAIR64__(*(_DWORD *)(a1 + 4 * v60 + 1724), v59);
        }
        v61 = *(unsigned int *)(v95 + 884);
        if ( *(_BYTE *)(v61 + v95 + 1296) || *(_BYTE *)(a1 + v61 + 1952) )
        {
          v62 = *(_DWORD *)(a1 + 4 * v61 + 1736);
          v59 |= 0x200u;
          LODWORD(v99[15]) = v59;
          LODWORD(v99[16]) = v62;
        }
        v63 = *(unsigned int *)(v95 + 884);
        if ( *(_BYTE *)(v63 + v95 + 1417) )
        {
          v64 = *(_DWORD *)(v95 + 4 * v63 + 1396);
          LODWORD(v99[15]) = v59 | 0x400;
          HIDWORD(v99[16]) = v64;
        }
        v65 = (*(_DWORD *)(a1 + 808) & 0x100) == 0;
        v99[19] = (__int64)FveDeviceFastAlloc;
        v99[20] = (__int64)FveDeviceFastFree;
        v99[18] = a1;
        if ( !v65 )
        {
          v66 = *(_QWORD **)(a1 + 736);
          if ( v66 )
          {
            if ( *v66 )
              goto LABEL_128;
          }
        }
        *(_QWORD *)(v15 + 32) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)(v15 + 40) = a4;
        FvePerfTraceDevIoCrypto(a1, FVE_PERF_IO_ENCRYPT_START, a2, v99[2], v99[14]);
        v67 = v43 ? FveTestRwParseBlockAndFilter(v99, v43, &v100) : FveParseBlockAndFilterEx(v99, &v100);
        v16 = v67;
        FvePerfTraceDevIoCrypto(a1, FVE_PERF_IO_ENCRYPT_STOP, a2, v99[2], v99[14]);
        if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v69, v68) )
        {
          v70 = *(_QWORD *)(a1 + 4752);
          if ( v70 )
          {
            if ( *(_DWORD *)(v70 + 88) && (v16 == -1073741662 || DWORD2(v101) == 259) )
LABEL_128:
              KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
          }
        }
        v11 = 1;
        LogFilterTrace((unsigned int)"Filter inline write", (unsigned int)&v100, v16, a1, v99[2], v99[14]);
        if ( v16 < 0 )
          goto LABEL_152;
        *(_QWORD *)(v15 + 32) = MEMORY[0xFFFFF78000000008] - *(_QWORD *)(v15 + 32);
        MdlAddress = a2->MdlAddress;
        a2->MdlAddress = v90;
        v72 = (void *)((unsigned __int64)MdlAddress | v85);
        Pool2 = 0;
        v90 = 0;
        DeInitializeFilterData(a1, v99);
      }
      else
      {
        v16 = 0;
        v72 = 0;
      }
      v73 = a2->Tail.Overlay.CurrentStackLocation;
      v74 = BYTE1(v96);
      *(_OWORD *)&v73[-1].MajorFunction = *(_OWORD *)&v73->MajorFunction;
      *(_OWORD *)&v73[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v73->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v73[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v73->Parameters.SetQuota + 6);
      v73[-1].FileObject = v73->FileObject;
      v73[-1].Control = 0;
      v75 = CurrentStackLocation;
      if ( CurrentStackLocation )
      {
        CurrentStackLocation->Parameters.WMI.ProviderId = v15;
        v75->Parameters.QueryDirectory.FileName = 0;
        v75->Parameters.Read.ByteOffset.QuadPart = 0;
        v75->Parameters.CreatePipe.Parameters = 0;
      }
      *(_QWORD *)(v15 + 24) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)(v15 + 44) = a4;
      *(_DWORD *)(v15 + 84) = v74;
      v15 = 0;
      if ( v74 == 1 )
      {
        v76 = FveInlineIceWriteCompletionRoutineRdpLevel1;
        if ( !v83 )
          v76 = FveInlineWriteCompletionRoutineRdpLevel1;
      }
      else
      {
        v76 = FveInlineWriteCompletionRoutineRdpLevel2;
        if ( v83 )
          v76 = FveInlineIceWriteCompletionRoutineRdpLevel2;
      }
      v77 = a2->Tail.Overlay.CurrentStackLocation;
      v77[-1].Context = v72;
      v77[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v76;
      v77[-1].Control = -32;
      *v98 = v83;
      if ( *(_DWORD *)(a1 + 2344) == 1 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 128LL));
      }
      else
      {
        v78 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
        ++*(_DWORD *)(v78 + *(_QWORD *)(a1 + 2352) + 128);
      }
      if ( v83 )
      {
        if ( *(_DWORD *)(a1 + 2344) == 1 )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 2352) + 240LL));
        }
        else
        {
          v79 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
          ++*(_QWORD *)(v79 + *(_QWORD *)(a1 + 2352) + 240);
        }
      }
      FvePerfTraceDevPtr(a1, FVE_PERF_WRITE_SUBREQUEST_START, a2);
      if ( v83 && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9928LL) & 2) != 0 )
      {
        FveIceSimQueueRequest(a1, a2, 0, 2);
      }
      else if ( v43 )
      {
        FveTestRwStorageRequest(v43, a2);
      }
      else
      {
        IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
      }
      v11 = 0;
    }
    v12 = Pool2;
LABEL_152:
    v17 = v90;
    goto LABEL_10;
  }
LABEL_59:
  if ( a4 > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v9 + 884) + 1592)
    || ((v39 = *(_QWORD *)(a1 + 2024)) == 0
      ? (v40 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016)))
      : (v40 = (PVOID)PplAllocateFromLookasideList(v39, v27, v28, v29)),
        Pool2 = v40,
        v12 = v40,
        v85 = 1,
        !v40) )
  {
    Pool2 = (void *)ExAllocatePool2(74, a4, 1883592262);
    v12 = Pool2;
    v85 = 2;
    if ( !Pool2 )
      goto LABEL_152;
  }
  Mdl = IoAllocateMdl(v12, a4, 0, 0, 0);
  v90 = Mdl;
  v17 = Mdl;
  if ( !Mdl )
    goto LABEL_10;
  MmBuildMdlForNonPagedPool(Mdl);
  MmMdlPageContentsState(v17, 1);
  v42 = a2->MdlAddress;
  if ( (v42->MdlFlags & 5) != 0 )
    MappedSystemVa = v42->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v42, 0, MmCached, 0, 0, 0x40000010u);
  v29 = 0;
  if ( MappedSystemVa )
  {
    v38 = 1;
    goto LABEL_71;
  }
  v11 = 0;
LABEL_10:
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    LOBYTE(Irp) = v85;
    FveReleaseInlineResources(a1, v15, v12, v17, Irp);
  }
  else
  {
    if ( v17 )
      IoFreeMdl(v17);
    if ( v12 )
    {
      if ( v85 == 1 )
      {
        v80 = *(_QWORD *)(a1 + 2024);
        if ( v80 )
        {
          LODWORD(v18) = HIDWORD(KeGetPcr()[1].LockArray);
          PplFreeToLookasideListProcessor(v80, v12, v18);
        }
        else
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016), v12);
        }
      }
      else
      {
        ExFreePoolWithTag(v12, 0x70455646u);
      }
    }
    if ( v15 )
      ReleaseInlineControl(v15);
  }
  if ( v11 == 1 )
    DeInitializeFilterData(a1, v99);
  Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline();
  return v16 >= 0;
}

```

## disassembly

```asm
0x1400ecce0  push    rbp
0x1400ecce2  push    rbx
0x1400ecce3  push    rsi
0x1400ecce4  push    rdi
0x1400ecce5  push    r12
0x1400ecce7  push    r13
0x1400ecce9  push    r14
0x1400ecceb  push    r15
0x1400ecced  lea     rbp, [rsp-0C8h]
0x1400eccf5  sub     rsp, 1C8h
0x1400eccfc  mov     rax, cs:__security_cookie
0x1400ecd03  xor     rax, rsp
0x1400ecd06  mov     [rbp+100h+var_50], rax
0x1400ecd0d  mov     rsi, [rbp+100h+arg_20]
0x1400ecd14  mov     rbx, r8
0x1400ecd17  mov     r14, rdx
0x1400ecd1a  mov     [rsp+200h+var_1B0], rbx
0x1400ecd1f  mov     rdi, rcx
0x1400ecd22  mov     [rbp+100h+var_180], rsi
0x1400ecd26  xor     edx, edx; Val
0x1400ecd28  mov     [rsp+200h+Length], r9d
0x1400ecd2d  mov     r8d, 100h; Size
0x1400ecd33  lea     rcx, [rbp+100h+var_170]; void *
0x1400ecd37  call    memset
0x1400ecd3c  mov     r13, [rdi+8]
0x1400ecd40  xor     ecx, ecx
0x1400ecd42  mov     eax, [rdi+328h]
0x1400ecd48  mov     r12b, cl
0x1400ecd4b  mov     [rsp+200h+var_198], r13
0x1400ecd50  mov     [rsp+200h+var_1A8], rcx
0x1400ecd55  mov     [rsp+200h+var_1A0], rcx
0x1400ecd5a  lea     r8d, [rcx+1]
0x1400ecd5e  mov     [rsp+200h+var_1CA], cl
0x1400ecd62  test    eax, 17Fh
0x1400ecd67  jz      short loc_1400ECD72
0x1400ecd69  mov     [rsp+200h+var_1CD], r8b
0x1400ecd6e  test    al, 40h
0x1400ecd70  jz      short loc_1400ECD76
0x1400ecd72  mov     [rsp+200h+var_1CD], cl
0x1400ecd76  mov     rax, [r14+0B8h]
0x1400ecd7d  xorps   xmm0, xmm0
0x1400ecd80  mov     [rsp+200h+var_188], rax
0x1400ecd85  mov     r15, rcx
0x1400ecd88  mov     rax, [r14+78h]
0x1400ecd8c  mov     [rsi], cl
0x1400ecd8e  movups  [rbp+100h+var_70], xmm0
0x1400ecd95  mov     [rsp+200h+var_1C0], rcx
0x1400ecd9a  movups  [rbp+100h+var_60], xmm0
0x1400ecda1  mov     [rsp+200h+var_1B8], rcx
0x1400ecda6  mov     [rsp+200h+var_1CE], cl
0x1400ecdaa  mov     [rsp+200h+var_190], rax
0x1400ecdaf  cmp     [rdi+928h], r8d
0x1400ecdb6  jnz     short loc_1400ECDC5
0x1400ecdb8  mov     rax, [rdi+930h]
0x1400ecdbf  lock inc dword ptr [rax+7Ch]
0x1400ecdc3  jmp     short loc_1400ECDE2
0x1400ecdc5  mov     eax, gs:1A4h
0x1400ecdcd  mov     ecx, eax
0x1400ecdcf  mov     rax, [rdi+930h]
0x1400ecdd6  imul    rdx, rcx, 128h
0x1400ecddd  add     [rdx+rax+7Ch], r8d
0x1400ecde2  mov     rcx, rdi
0x1400ecde5  call    AcquireInlineControl
0x1400ecdea  mov     rsi, rax
0x1400ecded  test    rax, rax
0x1400ecdf0  jnz     short loc_1400ECE25
0x1400ecdf2  mov     ebx, 0C000009Ah
0x1400ecdf7  mov     r13, r15
0x1400ecdfa  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400ecdff  test    eax, eax
0x1400ece01  jz      loc_1400ED821
0x1400ece07  mov     al, [rsp+200h+var_1CE]
0x1400ece0b  mov     r9, r13
0x1400ece0e  mov     r8, r15
0x1400ece11  mov     byte ptr [rsp+200h+Irp], al
0x1400ece15  mov     rdx, rsi
0x1400ece18  mov     rcx, rdi
0x1400ece1b  call    FveReleaseInlineResources
0x1400ece20  jmp     loc_1400ED896
0x1400ece25  mov     rax, ds:0FFFFF78000000008h
0x1400ece2f  mov     r8, rbx
0x1400ece32  mov     [rsi+8], rax
0x1400ece36  mov     rdx, r14
0x1400ece39  mov     eax, [rsp+200h+Length]
0x1400ece3d  mov     rcx, rdi
0x1400ece40  mov     r9d, eax
0x1400ece43  mov     [rsp+200h+var_1D0], r12b
0x1400ece48  mov     [rsi], r14
0x1400ece4b  mov     [rsi+40h], rbx
0x1400ece4f  mov     [rsi+48h], eax
0x1400ece52  mov     byte ptr [rsi+112h], 1
0x1400ece59  call    FveIsPagingRequest
0x1400ece5e  mov     rcx, r14; Irp
0x1400ece61  mov     [rsi+111h], al
0x1400ece67  call    cs:__imp_IoGetIoPriorityHint
0x1400ece6e  nop     dword ptr [rax+rax+00h]
0x1400ece73  xor     ebx, ebx
0x1400ece75  mov     [rsi+4Ch], eax
0x1400ece78  mov     rax, [r14+78h]
0x1400ece7c  mov     [rsi+50h], al
0x1400ece7f  mov     [rsi+10h], rbx
0x1400ece83  mov     [rsi+18h], rbx
0x1400ece87  mov     [rsi+20h], rbx
0x1400ece8b  mov     [rsi+28h], rbx
0x1400ece8f  mov     rcx, [r14+8]
0x1400ece93  call    cs:__imp_MmAreMdlPagesCached
0x1400ece9a  nop     dword ptr [rax+rax+00h]
0x1400ece9f  lea     r8, [rsp+200h+var_1A0]
0x1400ecea4  mov     rcx, r14
0x1400ecea7  test    eax, eax
0x1400ecea9  lea     rdx, [rsp+200h+var_1A8]
0x1400eceae  setnz   al
0x1400eceb1  mov     [rsi+110h], al
0x1400eceb7  call    FveIsIrpWithEfsOffload2
0x1400ecebc  mov     [rsp+200h+var_1CF], al
0x1400ecec0  mov     [rsi+114h], al
0x1400ecec6  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ececb  neg     eax
0x1400ececd  sbb     bl, bl
0x1400ececf  and     bl, [rsp+200h+var_1CF]
0x1400eced3  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400eced8  test    eax, eax
0x1400eceda  jz      short loc_1400ECF0E
0x1400ecedc  test    dword ptr [r13+26C8h], 8000000h
0x1400ecee7  jnz     short loc_1400ECF0E
0x1400ecee9  mov     r9d, [rsp+200h+Length]
0x1400eceee  mov     rdx, r14
0x1400ecef1  mov     r8, [rsp+200h+var_1B0]
0x1400ecef6  mov     rcx, rdi
0x1400ecef9  call    FveHwAccelShouldTryInlineOffload
0x1400ecefe  test    al, al
0x1400ecf00  jz      short loc_1400ECF0E
0x1400ecf02  mov     [rsp+200h+var_1CC], 1
0x1400ecf07  cmp     [rsp+200h+var_1CF], r12b
0x1400ecf0c  jz      short loc_1400ECF13
0x1400ecf0e  mov     [rsp+200h+var_1CC], r12b
0x1400ecf13  cmp     [rsp+200h+var_1CD], r12b
0x1400ecf18  jz      short loc_1400ECF6A
0x1400ecf1a  test    dword ptr [rdi+328h], 0C000h
0x1400ecf24  jnz     short loc_1400ECF6A
0x1400ecf26  mov     eax, [r13+26C8h]
0x1400ecf2d  test    al, 8
0x1400ecf2f  jnz     short loc_1400ECF6A
0x1400ecf31  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ecf36  mov     r9d, [rsp+200h+Length]
0x1400ecf3b  mov     rdx, r14
0x1400ecf3e  mov     r8, [rsp+200h+var_1B0]
0x1400ecf43  mov     rcx, rdi
0x1400ecf46  test    eax, eax
0x1400ecf48  jz      short loc_1400ECF60
0x1400ecf4a  mov     byte ptr [rsp+200h+Priority], bl
0x1400ecf4e  mov     byte ptr [rsp+200h+Irp], 1
0x1400ecf53  call    FveShouldTryInlineIceIrp
0x1400ecf58  mov     bl, al
0x1400ecf5a  mov     [rsp+200h+var_1D0], al
0x1400ecf5e  jmp     short loc_1400ECF6D
0x1400ecf60  mov     al, [rsp+200h+var_1CF]
0x1400ecf64  mov     byte ptr [rsp+200h+Priority], al
0x1400ecf68  jmp     short loc_1400ECF4E
0x1400ecf6a  mov     bl, r12b
0x1400ecf6d  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ecf72  xor     r9d, r9d
0x1400ecf75  test    eax, eax
0x1400ecf77  jz      short loc_1400ECFC1
0x1400ecf79  mov     eax, [rdi+328h]
0x1400ecf7f  test    eax, 0C000h
0x1400ecf84  jnz     short loc_1400ECFC1
0x1400ecf86  test    al, 19h
0x1400ecf88  jz      short loc_1400ECFC1
0x1400ecf8a  mov     rax, [rdi+1290h]
0x1400ecf91  test    rax, rax
0x1400ecf94  jz      short loc_1400ECFC1
0x1400ecf96  cmp     [rax+58h], r9d
0x1400ecf9a  jz      short loc_1400ECFC1
0x1400ecf9c  test    bl, bl
0x1400ecf9e  jz      short loc_1400ECFA7
0x1400ecfa0  cmp     [rsp+200h+var_1CF], r9b
0x1400ecfa5  jz      short loc_1400ECFC1
0x1400ecfa7  cmp     [rdi+3F0h], r9
0x1400ecfae  jnz     loc_1400ED643
0x1400ecfb4  mov     ebx, 0C0000001h
0x1400ecfb9  mov     r13, r9
0x1400ecfbc  jmp     loc_1400ECDFA
0x1400ecfc1  mov     eax, [r13+374h]
0x1400ecfc8  mov     ebx, 0C0000001h
0x1400ecfcd  cmp     [rdi+rax*4+6B0h], r9d
0x1400ecfd5  jnz     short loc_1400ECFE5
0x1400ecfd7  mov     [rsp+200h+var_1CB], r9b
0x1400ecfdc  cmp     [rsi+110h], r9b
0x1400ecfe3  jnz     short loc_1400ECFEA
0x1400ecfe5  mov     [rsp+200h+var_1CB], 1
0x1400ecfea  mov     rax, [rsp+200h+var_1A8]
0x1400ecfef  mov     [rsp+200h+var_1A8], rax
0x1400ecff4  mov     rax, [rsp+200h+var_1A0]
0x1400ecff9  mov     [rsp+200h+var_1A0], rax
0x1400ecffe  cmp     [rsp+200h+var_1D0], r9b
0x1400ed003  jz      loc_1400ED11B
0x1400ed009  mov     rcx, r14
0x1400ed00c  call    cs:__imp_IoClearFsTrackOffsetState
0x1400ed013  nop     dword ptr [rax+rax+00h]
0x1400ed018  mov     rcx, r13
0x1400ed01b  call    FveSimulateResourceStress
0x1400ed020  test    al, al
0x1400ed022  jz      short loc_1400ED02C
0x1400ed024  mov     r8d, 0C000009Ah
0x1400ed02a  jmp     short loc_1400ED07E
0x1400ed02c  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ed031  test    eax, eax
0x1400ed033  jnz     short loc_1400ED059
0x1400ed035  mov     ecx, [rdi+51Ch]
0x1400ed03b  xor     edx, edx
0x1400ed03d  mov     rax, [rsp+200h+var_1B0]
0x1400ed042  div     rcx
0x1400ed045  mov     rdx, [rdi+1290h]
0x1400ed04c  mov     rcx, r14
0x1400ed04f  mov     r8, rax
0x1400ed052  call    FveIceSetIrpExtension
0x1400ed057  jmp     short loc_1400ED070
0x1400ed059  mov     r8, [rsp+200h+var_1B0]
0x1400ed05e  mov     r9, rdi
0x1400ed061  mov     rdx, [rdi+1290h]
0x1400ed068  mov     rcx, r14
0x1400ed06b  call    FveIceSetIrpExtensionSteelix
0x1400ed070  xor     r9d, r9d
0x1400ed073  mov     r8d, eax
0x1400ed076  test    eax, eax
0x1400ed078  jns     loc_1400ED127
0x1400ed07e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed085  lea     rax, WPP_GLOBAL_Control
0x1400ed08c  cmp     rcx, rax
0x1400ed08f  jz      short loc_1400ED0B9
0x1400ed091  mov     eax, [rcx+2Ch]
0x1400ed094  test    al, al
0x1400ed096  jns     short loc_1400ED0B9
0x1400ed098  cmp     byte ptr [rcx+29h], 5
0x1400ed09c  jb      short loc_1400ED0B9
0x1400ed09e  mov     rcx, [rcx+18h]
0x1400ed0a2  mov     edx, 56h ; 'V'
0x1400ed0a7  mov     [rsp+200h+Priority], r8d
0x1400ed0ac  mov     r9, rdi
0x1400ed0af  mov     [rsp+200h+Irp], r14
0x1400ed0b4  call    WPP_SF_qqd
0x1400ed0b9  cmp     [rsp+200h+var_1CF], r12b
0x1400ed0be  jz      loc_1400ECDF7
0x1400ed0c4  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ed0c9  xor     r9d, r9d
0x1400ed0cc  test    eax, eax
0x1400ed0ce  jz      short loc_1400ED0E6
0x1400ed0d0  mov     rax, [rdi+1290h]
0x1400ed0d7  test    rax, rax
0x1400ed0da  jz      short loc_1400ED0E6
0x1400ed0dc  cmp     [rax+58h], r9d
0x1400ed0e0  jnz     loc_1400ED643
0x1400ed0e6  mov     rcx, r13
0x1400ed0e9  call    FveSimulateResourceStress
0x1400ed0ee  test    al, al
0x1400ed0f0  jnz     short loc_1400ED116
0x1400ed0f2  mov     r8, [rsp+200h+var_1A8]
0x1400ed0f7  mov     rcx, r14
0x1400ed0fa  mov     rdx, [rsp+200h+var_1A0]
0x1400ed0ff  call    cs:__imp_IoSetFsTrackOffsetState
0x1400ed106  nop     dword ptr [rax+rax+00h]
0x1400ed10b  xor     r9d, r9d
0x1400ed10e  test    eax, eax
0x1400ed110  jns     loc_1400ECFB9
0x1400ed116  mov     [rsp+200h+var_1D0], r9b
0x1400ed11b  test    dword ptr [rdi+328h], 0C000h
0x1400ed125  jz      short loc_1400ED139
0x1400ed127  cmp     [rsp+200h+var_1CF], r9b
0x1400ed12c  jnz     short loc_1400ED139
0x1400ed12e  mov     r12, r9
0x1400ed131  mov     r15b, r9b
0x1400ed134  jmp     loc_1400ED25A
0x1400ed139  mov     eax, [r13+374h]
0x1400ed140  mov     r13d, [rsp+200h+Length]
0x1400ed145  cmp     r13d, [rdi+rax*4+638h]
0x1400ed14d  ja      short loc_1400ED187
0x1400ed14f  mov     rcx, [rdi+7E8h]
0x1400ed156  test    rcx, rcx
0x1400ed159  jz      short loc_1400ED162
0x1400ed15b  call    PplAllocateFromLookasideList
0x1400ed160  jmp     short loc_1400ED175
0x1400ed162  mov     rcx, [rdi+7E0h]; Lookaside
0x1400ed169  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400ed170  nop     dword ptr [rax+rax+00h]
0x1400ed175  mov     [rsp+200h+var_1B8], rax
0x1400ed17a  mov     r15, rax
0x1400ed17d  mov     [rsp+200h+var_1CE], 1
0x1400ed182  test    rax, rax
0x1400ed185  jnz     short loc_1400ED1B7
0x1400ed187  mov     rdx, r13
0x1400ed18a  mov     ecx, 4Ah ; 'J'
0x1400ed18f  mov     r8d, 70455646h
0x1400ed195  call    cs:__imp_ExAllocatePool2
0x1400ed19c  nop     dword ptr [rax+rax+00h]
0x1400ed1a1  mov     [rsp+200h+var_1B8], rax
0x1400ed1a6  mov     r15, rax
0x1400ed1a9  mov     [rsp+200h+var_1CE], 2
0x1400ed1ae  test    rax, rax
0x1400ed1b1  jz      loc_1400ED7FE
  ... truncated ...
```
