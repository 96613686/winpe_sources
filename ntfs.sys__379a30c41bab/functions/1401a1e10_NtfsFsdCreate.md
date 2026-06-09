# NtfsFsdCreate

- ea: `0x1401a1e10`
- end: `0x1401a2b87`
- name: `NtfsFsdCreate`
- size: `3447`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140012ab0`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x1400211b0`
- `0x1400211f0`
- `0x1400291f0`
- `0x140029d80`
- `0x1400593e0`
- `0x140059740`
- `0x1400cb6b0`
- `0x14013add0`
- `0x1401850c0`
- `0x1401a0ba0`
- `0x1401a0e20`
- `0x1401a1e10`
- `0x1401a2b90`
- `0x1401a2d00`
- `0x1401e7b00`
- `0x140206e10`
- `0x14024f7dc`
- `0x14026f7c4`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x1401a2009`
- `ntoskrnl!IoGetStackLimits` at `0x1401a284e`
- `ntoskrnl!IoGetStackLimits` at `0x1401a2009`
- `ntoskrnl!IoGetStackLimits` at `0x1401a284e`
- `ntoskrnl!KeSetEvent` at `0x1401a2a98`
- `ntoskrnl!KeSetEvent` at `0x1401a2a98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1eea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2692`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402caecb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1eea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2692`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402caecb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a252a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2767`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cb032`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a252a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2767`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cb032`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2778`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2998`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2778`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2998`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401a2117`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401a2117`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2985`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2985`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401a2517`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401a2517`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1401a2701`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1401a2701`
- `ntoskrnl!IoCancelIrp` at `0x1401a2a80`
- `ntoskrnl!IoCancelIrp` at `0x1401a2a80`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1401a1eac`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1401a1eac`
- `ntoskrnl!KeClearEvent` at `0x1401a272d`
- `ntoskrnl!KeClearEvent` at `0x1401a272d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a2ab9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a2ab9`
- `ntoskrnl!KeInitializeEvent` at `0x1401a1f44`
- `ntoskrnl!KeInitializeEvent` at `0x1401a1f44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a26dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a26dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb026`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb026`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401a24f9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401a24f9`
- `HAL!KeQueryPerformanceCounter` at `0x1401a1f1a`
- `HAL!KeQueryPerformanceCounter` at `0x1401a1f1a`

## pseudocode

```c
__int64 __fastcall NtfsFsdCreate(__int64 a1, IRP *a2)
{
  __int64 v3; // r15
  __int64 VcbFromIrp; // rax
  __int64 v5; // rbx
  int Status; // edi
  __int64 v7; // r9
  char v8; // r14
  __int64 v9; // rdx
  LARGE_INTEGER *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  LARGE_INTEGER v14; // rax
  unsigned int v15; // edi
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v16; // r13
  PIRP TopLevelIrp; // rax
  int v18; // ecx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v20; // r13d
  int v21; // r14d
  unsigned int v22; // r15d
  PCHAR AuxiliaryBuffer; // rcx
  unsigned int v25; // eax
  __int64 v26; // rax
  __int64 v27; // r14
  unsigned __int64 v28; // rcx
  _QWORD *FsContext; // r13
  __int64 v30; // r13
  int v31; // r15d
  __int64 v32; // r8
  __int64 v33; // r13
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rdx
  int v37; // r9d
  struct _ERESOURCE *v38; // rcx
  int v39; // [rsp+28h] [rbp-220h]
  unsigned __int64 LowLimit; // [rsp+58h] [rbp-1F0h] BYREF
  int v41; // [rsp+60h] [rbp-1E8h]
  unsigned __int64 v42; // [rsp+68h] [rbp-1E0h] BYREF
  LARGE_INTEGER *Parameter; // [rsp+70h] [rbp-1D8h] BYREF
  unsigned __int64 Parameter_8; // [rsp+78h] [rbp-1D0h]
  __int128 v45; // [rsp+80h] [rbp-1C8h]
  __int128 v46; // [rsp+90h] [rbp-1B8h]
  __int128 v47; // [rsp+A0h] [rbp-1A8h]
  unsigned __int64 HighLimit; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int64 v49; // [rsp+B8h] [rbp-190h] BYREF
  IRP *v50; // [rsp+C0h] [rbp-188h]
  __int64 v51; // [rsp+C8h] [rbp-180h]
  _QWORD Event[4]; // [rsp+D0h] [rbp-178h] BYREF
  _QWORD v53[30]; // [rsp+F0h] [rbp-158h] BYREF
  _BYTE v54[32]; // [rsp+1E0h] [rbp-68h] BYREF
  __int64 v55; // [rsp+200h] [rbp-48h]
  char v57; // [rsp+250h] [rbp+8h]
  LARGE_INTEGER *v58; // [rsp+260h] [rbp+18h] BYREF
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+268h] [rbp+20h]

  v3 = a1;
  memset(v54, 0, sizeof(v54));
  v55 = 0;
  v58 = 0;
  memset(v53, 0, sizeof(v53));
  memset(Event, 0, sizeof(Event));
  if ( *(_WORD *)(v3 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  VcbFromIrp = NtfsGetVcbFromIrp(a2);
  v5 = NtfsInitializeTopLevelIrp(v54, 0, VcbFromIrp);
  v51 = v5;
  IoIsOperationSynchronous(a2);
  Status = NtfsInitializeIrpContextInternal(a2, 1, 0, (__int64 *)&v58);
  if ( Status < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)Status < 0xFFFFFFED
      && Status != -1073741802
      && Status != -1073741807
      && (unsigned int)(Status + 2147483643) > 1
      && Status != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)Status, 656732);
    }
    LOBYTE(v7) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(0, a2, (unsigned int)Status, v7, Status >= 0);
    return (unsigned int)Status;
  }
  v50 = a2;
  v8 = 0;
  KeEnterCriticalRegion();
  v9 = v5;
  v10 = v58;
  NtfsUpdateIrpContextWithTopLevel(v58, v9);
  if ( *(_BYTE *)(v10[13].QuadPart + 10496) )
  {
    v10[62] = KeQueryPerformanceCounter(0);
    v10[63].LowPart = 27;
  }
  KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
  while ( 1 )
  {
    memset(v53, 0, sizeof(v53));
    p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
    v53[22] = a2->Tail.Overlay.CurrentStackLocation;
    if ( Status == -1073741432 )
      NtfsCheckpointForLogFileFull(v10);
    if ( v10 )
      NtfsPreRequestProcessingExtend((_DWORD)v10);
    v53[7] = Event;
    v10[1].HighPart |= 0x10002u;
    if ( (v10[1].HighPart & 0x200) != 0 )
    {
      Status = NtfsCommonVolumeOpen((__int64)v10, (__int64)a2);
      v41 = Status;
      goto LABEL_73;
    }
    TxfMarshalTransactionForCreate(v10, v53);
    if ( (p_CurrentStackLocation->CurrentStackLocation->Flags & 0x10) != 0 )
      v8 = 1;
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit > 0x4800 )
    {
      Status = NtfsCommonCreate((__int64)v10, a2, (__int64)v53);
      v41 = Status;
      goto LABEL_15;
    }
    *(_QWORD *)&v46 = 0;
    Parameter = v10;
    Parameter_8 = (unsigned __int64)a2;
    v45 = (unsigned __int64)v53;
    v10[2].QuadPart |= 1uLL;
    Status = KeExpandKernelStackAndCalloutEx(NtfsCommonCreateCallout, &Parameter, 0x6000u, 0, 0);
    if ( Status >= 0 && (_DWORD)v46 == 259 )
    {
      Status = 259;
      v41 = 259;
    }
    else
    {
      v10[2].QuadPart &= ~1uLL;
      v14 = v10[2];
      if ( Status >= 0 )
      {
        if ( (v14.LowPart & 2) != 0 )
        {
          v10[2].QuadPart = v14.QuadPart & 0xFFFFFFFFFFFFFFFDuLL;
          v15 = v46;
          if ( (v10[1].HighPart & 2) != 0 || v53[17] )
          {
            if ( NtfsStatusDebugFlags
              && (_DWORD)v46
              && (_DWORD)v46 != 294
              && (unsigned int)(v46 - 298) > 1
              && (unsigned int)v46 < 0xFFFFFFED
              && (_DWORD)v46 != -1073741608
              && (_DWORD)v46 != -1073741802
              && (_DWORD)v46 != -1073741807
              && (unsigned int)(v46 + 2147483643) > 1
              && (_DWORD)v46 != 259 )
            {
              NtfsStatusTraceAndDebugInternal(v10, (unsigned int)v46, 679952);
            }
            LOBYTE(v11) = 1;
            NtfsExtendedCompleteRequestInternal(v10, 0, v15, v11, (v15 & 0x80000000) == 0);
          }
          else
          {
            if ( NtfsStatusDebugFlags
              && (_DWORD)v46
              && (_DWORD)v46 != 294
              && (unsigned int)(v46 - 298) > 1
              && (unsigned int)v46 < 0xFFFFFFED
              && (_DWORD)v46 != -1073741608
              && (_DWORD)v46 != -1073741802
              && (_DWORD)v46 != -1073741807
              && (unsigned int)(v46 + 2147483643) > 1
              && (_DWORD)v46 != 259 )
            {
              NtfsStatusTraceAndDebugInternal(v10, (unsigned int)v46, 679975);
            }
            LOBYTE(v11) = a2 != 0;
            NtfsExtendedCompleteRequestInternal(v10, a2, v15, v11, (v15 & 0x80000000) == 0);
          }
        }
        if ( NtfsStatusDebugFlags
          && (_DWORD)v46
          && (_DWORD)v46 != 294
          && (unsigned int)(v46 - 298) > 1
          && (unsigned int)v46 < 0xFFFFFFED
          && (_DWORD)v46 != -1073741608
          && (_DWORD)v46 != -1073741802
          && (_DWORD)v46 != -1073741807
          && (unsigned int)(v46 + 2147483643) > 1
          && (_DWORD)v46 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v46, 656648);
        }
        Status = v46;
LABEL_26:
        v41 = Status;
        goto LABEL_15;
      }
      if ( Status == -1073741801 )
        Status = -1073741670;
      NtfsCompleteCreateRequest(v10, v53, a2, (unsigned int)Status);
      if ( !NtfsStatusDebugFlags
        || (unsigned int)Status >= 0xFFFFFFED
        || Status == -1073741802
        || Status == -1073741807
        || (unsigned int)(Status + 2147483643) <= 1
        || Status == -1073741608 )
      {
        goto LABEL_26;
      }
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)Status, 656615);
      v41 = Status;
    }
LABEL_15:
    if ( Status == 871 )
    {
      v10->HighPart |= 0x400u;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v10, 871, 656847);
      NtfsExtendedCompleteRequestInternal(v10, 0, 871, 0, 1);
      NtfsWaitForOplockCompletionEvent(v12, a2, v13, v53[7] + 8LL);
      *(_BYTE *)(v53[22] + 3LL) &= ~1u;
    }
LABEL_73:
    if ( Status != -1073741608 && Status != -1073741432 && Status != 871 )
      break;
    if ( v53[23] )
    {
      ObDereferenceObjectDeferDelete((PVOID)v53[23]);
      v53[23] = 0;
    }
    AuxiliaryBuffer = a2->Tail.Overlay.AuxiliaryBuffer;
    if ( AuxiliaryBuffer )
    {
      ExFreePoolWithTag(AuxiliaryBuffer, 0);
      a2->Tail.Overlay.AuxiliaryBuffer = 0;
    }
  }
  if ( Status == 259 )
  {
    v25 = FsRtlCancellableWaitForSingleObject(&Event[1], 0, a2);
    if ( v25 == -1073741749 || v25 == -1073741536 )
    {
      if ( NtfsStatusDebugFlags && v25 - 298 > 1 && v25 + 2147483643 > 1 )
        NtfsStatusTraceAndDebugInternal(0, v25, 656132);
      IoCancelIrp(a2);
      KeSetEvent(&NtfsEncryptionPendingEvent, 0, 0);
      KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    }
    KeClearEvent((PRKEVENT)&Event[1]);
    Status = a2->IoStatus.Status;
    v16 = p_CurrentStackLocation;
    v53[22] = p_CurrentStackLocation->CurrentStackLocation;
    *(_BYTE *)(v53[22] + 3LL) &= ~1u;
  }
  else
  {
    v16 = p_CurrentStackLocation;
  }
  LOBYTE(v58) = 0;
  if ( (_QWORD)xmmword_140095730 )
  {
    if ( (v10[1].HighPart & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      TopLevelIrp->ThreadListEntry.Flink = 0;
      if ( !LOBYTE(TopLevelIrp->Size) )
      {
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        IoSetTopLevelIrp(TopLevelIrp->AssociatedIrp.MasterIrp);
      }
      v10[1].HighPart &= ~0x100000u;
    }
    KeLeaveCriticalRegion();
    CurrentStackLocation = v16->CurrentStackLocation;
    v53[22] = v16->CurrentStackLocation;
    if ( v53[21] )
    {
      FsContext = CurrentStackLocation->FileObject->FsContext;
      if ( FsContext )
        v30 = FsContext[24];
      else
        v30 = 0;
      if ( v30 )
      {
        LowLimit = *(_QWORD *)(v30 + 224);
        v31 = (*(unsigned __int8 *)(v30 + 24) >> 4) & 1;
      }
      else
      {
        LowLimit = 0;
        v31 = 0;
      }
      v49 = 0;
      v42 = 0;
      IoGetStackLimits(&v42, &v49);
      v32 = v30 + 24;
      v33 = v30 + 7872;
      if ( (unsigned __int64)&v49 - v42 <= 0x4800 )
      {
        v46 = 0;
        v47 = 0;
        Parameter = (LARGE_INTEGER *)a1;
        Parameter_8 = LowLimit;
        v45 = (unsigned __int64)a2;
        *((_QWORD *)&v45 + 1) = *(_QWORD *)(v53[22] + 48LL);
        *(_QWORD *)&v46 = __PAIR64__(v31, Status);
        *((_QWORD *)&v46 + 1) = v33;
        *(_QWORD *)&v47 = v32;
        *((_QWORD *)&v47 + 1) = &v53[21];
        v20 = NtfsPostCreateOnNewStack(v10, a2, &Parameter);
        v3 = a1;
      }
      else
      {
        v39 = v31;
        v3 = a1;
        v20 = ((__int64 (__fastcall *)(__int64, unsigned __int64, IRP *, _QWORD, int, int, __int64, __int64, _QWORD *))xmmword_140095730)(
                a1,
                LowLimit,
                a2,
                *(_QWORD *)(v53[22] + 48LL),
                Status,
                v39,
                v33,
                v32,
                &v53[21]);
      }
    }
    else
    {
      v20 = Status;
    }
    if ( v8 && (dword_1400956B8 & 0x2000) != 0 && Status >= 0 && Status != 260 )
    {
      NtfsSetupPagingFileEncryption(v18, v10[13].QuadPart, v53[13], (_DWORD)a2, v3);
      LOBYTE(v58) = 1;
    }
    if ( v20 == -1073741790
      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v53[22] + 8LL) + 8LL) + 24LL) & 0x2000000) != 0
      && a2->IoStatus.Information == 1 )
    {
      v26 = *(_QWORD *)(v53[22] + 48LL);
      v27 = *(_QWORD *)(v26 + 24);
      v28 = *(_QWORD *)(v26 + 32);
      v42 = v28;
      v57 = *(_BYTE *)(v26 + 76);
      LowLimit = 0;
      if ( v27 && v28 )
        LowLimit = *(_QWORD *)(v28 + 72);
      v20 = 0;
      KeEnterCriticalRegion();
      if ( v27 )
      {
        LOBYTE(v35) = 1;
        NtfsAcquireResourceExclusive(v34, v27, v35);
        if ( (v53[19] & 0x4000000000LL) != 0 )
        {
          v36 = 1;
        }
        else
        {
          v36 = 0;
          if ( *(_BYTE *)(v42 + 88) == 4 )
            v36 = 2;
        }
        NtfsRemoveShareAccess(*(_QWORD *)(v53[22] + 48LL), v36, v27, LowLimit);
      }
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 74LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 75LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 76LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 77LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 78LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v53[22] + 48LL) + 79LL) = 0;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v53[22] + 8LL) + 8LL) + 20LL) &= 0xFFFFFFD8;
      if ( v27 )
      {
        if ( v57 )
        {
          if ( (v53[19] & 0x4000000000LL) != 0 )
          {
            v37 = 1;
          }
          else
          {
            v37 = 0;
            if ( *(_BYTE *)(v42 + 88) == 4 )
              v37 = 2;
          }
          v20 = NtfsCheckShareAccess(
                  0x10000,
                  *(unsigned __int16 *)(v53[22] + 26LL),
                  *(_QWORD *)(v53[22] + 48LL),
                  v37,
                  v27,
                  LowLimit,
                  1);
        }
        if ( *(_WORD *)v27 == 1794 )
          v38 = (struct _ERESOURCE *)(*(_QWORD *)(v27 + 104) + 64LL);
        else
          v38 = *(struct _ERESOURCE **)(v27 + 8);
        ExReleaseResourceLite(v38);
      }
      KeLeaveCriticalRegion();
    }
    v21 = 0;
  }
  else
  {
    v21 = 1;
    v20 = 0;
  }
  v10[1].HighPart &= ~0x40u;
  if ( Status < 0 || v20 >= 0 )
  {
    v22 = 0;
    if ( (v53[20] & 5) != 0 )
      goto LABEL_112;
  }
  else
  {
    v22 = 1;
LABEL_112:
    if ( !v21 )
    {
      KeEnterCriticalRegion();
      v21 = 1;
    }
    NtfsUpdateIrpContextWithTopLevel(v10, v51);
    if ( Status >= 0 && Status != 260 )
      NtfsPostProcessEncryptedCreate(
        v10,
        p_CurrentStackLocation->CurrentStackLocation->FileObject,
        LODWORD(v53[20]),
        v22);
  }
  if ( v22 )
  {
    if ( NtfsStatusDebugFlags
      && v20
      && v20 != 294
      && (unsigned int)(v20 - 298) > 1
      && (unsigned int)v20 < 0xFFFFFFED
      && v20 != -1073741608
      && v20 != -1073741802
      && v20 != -1073741807
      && (unsigned int)(v20 + 2147483643) > 1
      && v20 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)v20, 657292);
    }
    Status = v20;
  }
  if ( Status >= 0 && (_BYTE)v58 )
    _InterlockedIncrement((volatile signed __int32 *)(v10[13].QuadPart + 6616));
  v10[1].HighPart &= ~0x10000u;
  if ( NtfsStatusDebugFlags
    && Status
    && Status != 294
    && (unsigned int)(Status - 298) > 1
    && (unsigned int)Status < 0xFFFFFFED
    && Status != -1073741608
    && Status != -1073741802
    && Status != -1073741807
    && (unsigned int)(Status + 2147483643) > 1
    && Status != 259 )
  {
    NtfsStatusTraceAndDebugInternal(v10, (unsigned int)Status, 657325);
  }
  LOBYTE(v11) = v50 != 0;
  NtfsExtendedCompleteRequestInternal(v10, a2, (unsigned int)Status, v11, Status >= 0);
  if ( v53[23] )
  {
    ObDereferenceObjectDeferDelete((PVOID)v53[23]);
    v53[23] = 0;
  }
  if ( v21 )
    KeLeaveCriticalRegion();
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1401a1e10  mov     r11, rsp
0x1401a1e13  mov     [r11+10h], rdx
0x1401a1e17  mov     [r11+8], rcx
0x1401a1e1b  push    rbx
0x1401a1e1c  push    rsi
0x1401a1e1d  push    rdi
0x1401a1e1e  push    r12
0x1401a1e20  push    r13
0x1401a1e22  push    r14
0x1401a1e24  push    r15
0x1401a1e26  sub     rsp, 210h
0x1401a1e2d  mov     rsi, rdx
0x1401a1e30  mov     r15, rcx
0x1401a1e33  xorps   xmm0, xmm0
0x1401a1e36  xor     eax, eax
0x1401a1e38  movups  xmmword ptr [r11-68h], xmm0
0x1401a1e3d  movups  xmmword ptr [r11-58h], xmm0
0x1401a1e42  mov     [r11-48h], rax
0x1401a1e46  xor     r12d, r12d
0x1401a1e49  mov     [r11+18h], r12
0x1401a1e4d  xor     edx, edx; Val
0x1401a1e4f  mov     r8d, 0F0h; Size
0x1401a1e55  lea     rcx, [r11-158h]; void *
0x1401a1e5c  call    memset
0x1401a1e61  xorps   xmm0, xmm0
0x1401a1e64  movups  xmmword ptr [rsp+248h+Event], xmm0
0x1401a1e6c  movups  xmmword ptr [rsp+248h+Event+10h], xmm0
0x1401a1e74  mov     eax, 150h
0x1401a1e79  mov     rcx, rsi; Irp
0x1401a1e7c  cmp     [r15+2], ax
0x1401a1e81  jz      loc_1401A2977
0x1401a1e87  call    NtfsGetVcbFromIrp
0x1401a1e8c  mov     r8, rax
0x1401a1e8f  xor     edx, edx
0x1401a1e91  lea     rcx, [rsp+248h+var_68]
0x1401a1e99  call    NtfsInitializeTopLevelIrp
0x1401a1e9e  mov     rbx, rax
0x1401a1ea1  mov     [rsp+248h+var_180], rax
0x1401a1ea9  mov     rcx, rsi; Irp
0x1401a1eac  call    cs:__imp_IoIsOperationSynchronous
0x1401a1eb3  nop     dword ptr [rax+rax+00h]
0x1401a1eb8  lea     r9, [rsp+248h+arg_10]
0x1401a1ec0  xor     r8d, r8d
0x1401a1ec3  mov     dl, 1
0x1401a1ec5  mov     rcx, rsi; Irp
0x1401a1ec8  call    NtfsInitializeIrpContextInternal
0x1401a1ecd  mov     edi, eax
0x1401a1ecf  test    eax, eax
0x1401a1ed1  js      loc_1401A29B9
0x1401a1ed7  mov     r13, rsi
0x1401a1eda  mov     [rsp+248h+var_188], rsi
0x1401a1ee2  xor     r14b, r14b
0x1401a1ee5  mov     [rsp+248h+var_1F8], r14b
0x1401a1eea  call    cs:__imp_KeEnterCriticalRegion
0x1401a1ef1  nop     dword ptr [rax+rax+00h]
0x1401a1ef6  mov     rdx, rbx
0x1401a1ef9  mov     rbx, [rsp+248h+arg_10]
0x1401a1f01  mov     rcx, rbx
0x1401a1f04  call    NtfsUpdateIrpContextWithTopLevel
0x1401a1f09  mov     rax, [rbx+68h]
0x1401a1f0d  movzx   ecx, byte ptr [rax+2900h]
0x1401a1f14  test    cl, cl
0x1401a1f16  jz      short loc_1401A1F37
0x1401a1f18  xor     ecx, ecx; PerformanceFrequency
0x1401a1f1a  call    cs:__imp_KeQueryPerformanceCounter
0x1401a1f21  nop     dword ptr [rax+rax+00h]
0x1401a1f26  mov     [rbx+1F0h], rax
0x1401a1f2d  mov     dword ptr [rbx+1F8h], 1Bh
0x1401a1f37  xor     r8d, r8d; State
0x1401a1f3a  xor     edx, edx; Type
0x1401a1f3c  lea     rcx, [rsp+248h+Event+8]; Event
0x1401a1f44  call    cs:__imp_KeInitializeEvent
0x1401a1f4b  nop     dword ptr [rax+rax+00h]
0x1401a1f50  xor     edx, edx; Val
0x1401a1f52  mov     r8d, 0F0h; Size
0x1401a1f58  lea     rcx, [rsp+248h+var_158]; void *
0x1401a1f60  call    memset
0x1401a1f65  lea     rax, [rsi+0B8h]
0x1401a1f6c  mov     [rsp+248h+arg_18], rax
0x1401a1f74  mov     rax, [rax]
0x1401a1f77  mov     [rsp+248h+var_A8], rax
0x1401a1f7f  cmp     edi, 0C0000188h
0x1401a1f85  jz      loc_1401A23E1
0x1401a1f8b  test    rbx, rbx
0x1401a1f8e  jz      short loc_1401A1F9A
0x1401a1f90  mov     edx, edi
0x1401a1f92  mov     rcx, rbx
0x1401a1f95  call    NtfsPreRequestProcessingExtend
0x1401a1f9a  lea     rax, [rsp+248h+Event]
0x1401a1fa2  mov     [rsp+248h+var_120], rax
0x1401a1faa  or      dword ptr [rbx+0Ch], 10002h
0x1401a1fb1  mov     rcx, rbx
0x1401a1fb4  test    dword ptr [rbx+0Ch], 200h
0x1401a1fbb  jnz     loc_1401A20B1
0x1401a1fc1  lea     rdx, [rsp+248h+var_158]
0x1401a1fc9  call    TxfMarshalTransactionForCreate
0x1401a1fce  mov     rdx, [rsp+248h+arg_18]
0x1401a1fd6  mov     rax, [rdx]
0x1401a1fd9  test    byte ptr [rax+2], 10h
0x1401a1fdd  movzx   r14d, r14b
0x1401a1fe1  mov     eax, 1
0x1401a1fe6  cmovnz  r14d, eax
0x1401a1fea  mov     [rsp+248h+var_1F8], r14b
0x1401a1fef  mov     [rsp+248h+HighLimit], r12
0x1401a1ff7  mov     [rsp+248h+LowLimit], r12
0x1401a1ffc  lea     rdx, [rsp+248h+HighLimit]; HighLimit
0x1401a2004  lea     rcx, [rsp+248h+LowLimit]; LowLimit
0x1401a2009  call    cs:__imp_IoGetStackLimits
0x1401a2010  nop     dword ptr [rax+rax+00h]
0x1401a2015  lea     rax, [rsp+248h+HighLimit]
0x1401a201d  sub     rax, [rsp+248h+LowLimit]
0x1401a2022  cmp     rax, 4800h
0x1401a2028  jbe     loc_1401A20C4
0x1401a202e  lea     r8, [rsp+248h+var_158]
0x1401a2036  mov     rdx, rsi; Irp
0x1401a2039  mov     rcx, rbx; int
0x1401a203c  call    NtfsCommonCreate
0x1401a2041  mov     edi, eax
0x1401a2043  mov     [rsp+248h+var_1E8], eax
0x1401a2047  cmp     edi, 367h
0x1401a204d  jnz     loc_1401A23EE
0x1401a2053  or      dword ptr [rbx+4], 400h
0x1401a205a  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2061  test    al, al
0x1401a2063  jnz     loc_1401A23C9
0x1401a2069  mov     dword ptr [rsp+248h+Context], 1
0x1401a2071  xor     r9d, r9d
0x1401a2074  xor     edx, edx
0x1401a2076  mov     r8d, 367h
0x1401a207c  mov     rcx, rbx
0x1401a207f  call    NtfsExtendedCompleteRequestInternal
0x1401a2084  mov     r9, [rsp+248h+var_120]
0x1401a208c  add     r9, 8
0x1401a2090  mov     dword ptr [rsp+248h+var_220], 1
0x1401a2098  mov     rdx, rsi
0x1401a209b  call    NtfsWaitForOplockCompletionEvent
0x1401a20a0  mov     rax, [rsp+248h+var_A8]
0x1401a20a8  and     byte ptr [rax+3], 0FEh
0x1401a20ac  jmp     loc_1401A23EE
0x1401a20b1  mov     rdx, rsi
0x1401a20b4  call    NtfsCommonVolumeOpen
0x1401a20b9  mov     edi, eax
0x1401a20bb  mov     [rsp+248h+var_1E8], eax
0x1401a20bf  jmp     loc_1401A23EE
0x1401a20c4  xorps   xmm0, xmm0
0x1401a20c7  xor     eax, eax
0x1401a20c9  movups  [rsp+248h+Parameter], xmm0
0x1401a20ce  movups  [rsp+248h+var_1C8], xmm0
0x1401a20d6  mov     qword ptr [rsp+248h+var_1B8], rax
0x1401a20de  mov     qword ptr [rsp+248h+Parameter], rbx
0x1401a20e3  mov     qword ptr [rsp+248h+Parameter+8], rsi
0x1401a20e8  lea     rax, [rsp+248h+var_158]
0x1401a20f0  mov     qword ptr [rsp+248h+var_1C8], rax
0x1401a20f8  or      qword ptr [rbx+10h], 1
0x1401a20fd  mov     [rsp+248h+Context], r12; Context
0x1401a2102  xor     r9d, r9d; Wait
0x1401a2105  mov     r8d, 6000h; Size
0x1401a210b  lea     rdx, [rsp+248h+Parameter]; Parameter
0x1401a2110  lea     rcx, NtfsCommonCreateCallout; Callout
0x1401a2117  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1401a211e  nop     dword ptr [rax+rax+00h]
0x1401a2123  mov     edi, eax
0x1401a2125  test    eax, eax
0x1401a2127  js      short loc_1401A213A
0x1401a2129  cmp     dword ptr [rsp+248h+var_1B8], 103h
0x1401a2134  jz      loc_1401A220C
0x1401a213a  and     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFEh
0x1401a213f  mov     rax, [rbx+10h]
0x1401a2143  test    edi, edi
0x1401a2145  js      loc_1401A22C2
0x1401a214b  test    al, 2
0x1401a214d  jnz     short loc_1401A21C7
0x1401a214f  mov     edx, dword ptr [rsp+248h+var_1B8]
0x1401a2156  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a215d  test    al, al
0x1401a215f  jnz     short loc_1401A2171
0x1401a2161  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a2168  mov     [rsp+248h+var_1E8], edi
0x1401a216c  jmp     loc_1401A2047
0x1401a2171  test    edx, edx
0x1401a2173  jz      short loc_1401A2161
0x1401a2175  cmp     edx, 126h
0x1401a217b  jz      short loc_1401A2161
0x1401a217d  lea     eax, [rdx-12Ah]
0x1401a2183  cmp     eax, 1
0x1401a2186  jbe     short loc_1401A2161
0x1401a2188  cmp     edx, 0FFFFFFEDh
0x1401a218b  jnb     short loc_1401A2161
0x1401a218d  cmp     edx, 0C00000D8h
0x1401a2193  jz      short loc_1401A2161
0x1401a2195  cmp     edx, 0C0000016h
0x1401a219b  jz      short loc_1401A2161
0x1401a219d  cmp     edx, 0C0000011h
0x1401a21a3  jz      short loc_1401A2161
0x1401a21a5  lea     eax, [rdx+7FFFFFFBh]
0x1401a21ab  cmp     eax, 1
0x1401a21ae  jbe     short loc_1401A2161
0x1401a21b0  cmp     edx, 103h
0x1401a21b6  jz      short loc_1401A2161
0x1401a21b8  xor     ecx, ecx
0x1401a21ba  mov     r8d, 0A0508h
0x1401a21c0  call    NtfsStatusTraceAndDebugInternal
0x1401a21c5  jmp     short loc_1401A2161
0x1401a21c7  and     rax, 0FFFFFFFFFFFFFFFDh
0x1401a21cb  mov     [rbx+10h], rax
0x1401a21cf  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a21d6  mov     eax, [rbx+0Ch]
0x1401a21d9  test    al, 2
0x1401a21db  jz      loc_1401A227F
0x1401a21e1  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a21e8  test    al, al
0x1401a21ea  jnz     short loc_1401A2223
0x1401a21ec  mov     eax, edi
0x1401a21ee  not     eax
0x1401a21f0  shr     eax, 1Fh
0x1401a21f3  mov     r9b, 1
0x1401a21f6  xor     edx, edx
0x1401a21f8  mov     dword ptr [rsp+248h+Context], eax
0x1401a21fc  mov     r8d, edi
0x1401a21ff  mov     rcx, rbx
0x1401a2202  call    NtfsExtendedCompleteRequestInternal
0x1401a2207  jmp     loc_1401A214F
0x1401a220c  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2213  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a221a  mov     [rsp+248h+var_1E8], edi
0x1401a221e  jmp     loc_1401A2047
0x1401a2223  test    edi, edi
0x1401a2225  jz      short loc_1401A21EC
0x1401a2227  cmp     edi, 126h
0x1401a222d  jz      short loc_1401A21EC
0x1401a222f  lea     eax, [rdi-12Ah]
0x1401a2235  cmp     eax, 1
0x1401a2238  jbe     short loc_1401A21EC
0x1401a223a  cmp     edi, 0FFFFFFEDh
0x1401a223d  jnb     short loc_1401A21EC
0x1401a223f  cmp     edi, 0C00000D8h
0x1401a2245  jz      short loc_1401A21EC
0x1401a2247  cmp     edi, 0C0000016h
0x1401a224d  jz      short loc_1401A21EC
0x1401a224f  cmp     edi, 0C0000011h
0x1401a2255  jz      short loc_1401A21EC
0x1401a2257  lea     eax, [rdi+7FFFFFFBh]
0x1401a225d  cmp     eax, 1
0x1401a2260  jbe     short loc_1401A21EC
0x1401a2262  cmp     edi, 103h
0x1401a2268  jz      short loc_1401A21EC
0x1401a226a  mov     r8d, 0A6010h
0x1401a2270  mov     edx, edi
0x1401a2272  mov     rcx, rbx
0x1401a2275  call    NtfsStatusTraceAndDebugInternal
0x1401a227a  jmp     loc_1401A21EC
0x1401a227f  cmp     [rsp+248h+var_D0], 0
0x1401a2288  jnz     loc_1401A21E1
0x1401a228e  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2295  test    al, al
0x1401a2297  jnz     loc_1401A2349
0x1401a229d  mov     eax, edi
0x1401a229f  not     eax
0x1401a22a1  shr     eax, 1Fh
0x1401a22a4  test    r13, r13
0x1401a22a7  setnz   r9b
0x1401a22ab  mov     rdx, rsi
0x1401a22ae  mov     dword ptr [rsp+248h+Context], eax
0x1401a22b2  mov     r8d, edi
0x1401a22b5  mov     rcx, rbx
0x1401a22b8  call    NtfsExtendedCompleteRequestInternal
0x1401a22bd  jmp     loc_1401A214F
0x1401a22c2  cmp     edi, 0C0000017h
0x1401a22c8  mov     eax, 0C000009Ah
0x1401a22cd  cmovz   edi, eax
0x1401a22d0  mov     r9d, edi
0x1401a22d3  mov     r8, rsi
0x1401a22d6  lea     rdx, [rsp+248h+var_158]
0x1401a22de  mov     rcx, rbx
0x1401a22e1  call    NtfsCompleteCreateRequest
0x1401a22e6  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a22ed  test    al, al
0x1401a22ef  jz      loc_1401A2168
0x1401a22f5  cmp     edi, 0FFFFFFEDh
0x1401a22f8  jnb     loc_1401A2168
0x1401a22fe  cmp     edi, 0C0000016h
0x1401a2304  jz      loc_1401A2168
0x1401a230a  cmp     edi, 0C0000011h
0x1401a2310  jz      loc_1401A2168
0x1401a2316  lea     eax, [rdi+7FFFFFFBh]
0x1401a231c  cmp     eax, 1
0x1401a231f  jbe     loc_1401A2168
0x1401a2325  cmp     edi, 0C00000D8h
0x1401a232b  jz      loc_1401A2168
0x1401a2331  mov     r8d, 0A04E7h
0x1401a2337  mov     edx, edi
0x1401a2339  xor     ecx, ecx
0x1401a233b  call    NtfsStatusTraceAndDebugInternal
0x1401a2340  mov     [rsp+248h+var_1E8], edi
0x1401a2344  jmp     loc_1401A2047
0x1401a2349  test    edi, edi
0x1401a234b  jz      loc_1401A229D
0x1401a2351  cmp     edi, 126h
0x1401a2357  jz      loc_1401A229D
0x1401a235d  lea     eax, [rdi-12Ah]
  ... truncated ...
```
