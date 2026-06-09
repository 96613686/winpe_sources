# NtfsFsdCreate

- ea: `0x1401a1dc0`
- end: `0x1401a2b37`
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
- `0x140059370`
- `0x1400596c0`
- `0x1400cb6b0`
- `0x14013ad80`
- `0x140185070`
- `0x1401a0b50`
- `0x1401a0dd0`
- `0x1401a1dc0`
- `0x1401a2b40`
- `0x1401a2cb0`
- `0x1401e7ab0`
- `0x140206dc0`
- `0x14024f78c`
- `0x14026f774`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x1401a1fb9`
- `ntoskrnl!IoGetStackLimits` at `0x1401a27fe`
- `ntoskrnl!IoGetStackLimits` at `0x1401a1fb9`
- `ntoskrnl!IoGetStackLimits` at `0x1401a27fe`
- `ntoskrnl!KeSetEvent` at `0x1401a2a48`
- `ntoskrnl!KeSetEvent` at `0x1401a2a48`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1e9a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2642`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402cae7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1e9a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2642`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402cae7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a24da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2717`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cafe2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a24da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2717`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cafe2`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2728`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2948`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2728`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401a2948`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401a20c7`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401a20c7`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2935`
- `ntoskrnl!IofCompleteRequest` at `0x1401a2935`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401a24c7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401a24c7`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1401a26b1`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1401a26b1`
- `ntoskrnl!IoCancelIrp` at `0x1401a2a30`
- `ntoskrnl!IoCancelIrp` at `0x1401a2a30`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1401a1e5c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1401a1e5c`
- `ntoskrnl!KeClearEvent` at `0x1401a26dd`
- `ntoskrnl!KeClearEvent` at `0x1401a26dd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a2a69`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a2a69`
- `ntoskrnl!KeInitializeEvent` at `0x1401a1ef4`
- `ntoskrnl!KeInitializeEvent` at `0x1401a1ef4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a268c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a268c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cafd6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cafd6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401a24a9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401a24a9`
- `HAL!KeQueryPerformanceCounter` at `0x1401a1eca`
- `HAL!KeQueryPerformanceCounter` at `0x1401a1eca`

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
0x1401a1dc0  mov     r11, rsp
0x1401a1dc3  mov     [r11+10h], rdx
0x1401a1dc7  mov     [r11+8], rcx
0x1401a1dcb  push    rbx
0x1401a1dcc  push    rsi
0x1401a1dcd  push    rdi
0x1401a1dce  push    r12
0x1401a1dd0  push    r13
0x1401a1dd2  push    r14
0x1401a1dd4  push    r15
0x1401a1dd6  sub     rsp, 210h
0x1401a1ddd  mov     rsi, rdx
0x1401a1de0  mov     r15, rcx
0x1401a1de3  xorps   xmm0, xmm0
0x1401a1de6  xor     eax, eax
0x1401a1de8  movups  xmmword ptr [r11-68h], xmm0
0x1401a1ded  movups  xmmword ptr [r11-58h], xmm0
0x1401a1df2  mov     [r11-48h], rax
0x1401a1df6  xor     r12d, r12d
0x1401a1df9  mov     [r11+18h], r12
0x1401a1dfd  xor     edx, edx; Val
0x1401a1dff  mov     r8d, 0F0h; Size
0x1401a1e05  lea     rcx, [r11-158h]; void *
0x1401a1e0c  call    memset
0x1401a1e11  xorps   xmm0, xmm0
0x1401a1e14  movups  xmmword ptr [rsp+248h+Event], xmm0
0x1401a1e1c  movups  xmmword ptr [rsp+248h+Event+10h], xmm0
0x1401a1e24  mov     eax, 150h
0x1401a1e29  mov     rcx, rsi; Irp
0x1401a1e2c  cmp     [r15+2], ax
0x1401a1e31  jz      loc_1401A2927
0x1401a1e37  call    NtfsGetVcbFromIrp
0x1401a1e3c  mov     r8, rax
0x1401a1e3f  xor     edx, edx
0x1401a1e41  lea     rcx, [rsp+248h+var_68]
0x1401a1e49  call    NtfsInitializeTopLevelIrp
0x1401a1e4e  mov     rbx, rax
0x1401a1e51  mov     [rsp+248h+var_180], rax
0x1401a1e59  mov     rcx, rsi; Irp
0x1401a1e5c  call    cs:__imp_IoIsOperationSynchronous
0x1401a1e63  nop     dword ptr [rax+rax+00h]
0x1401a1e68  lea     r9, [rsp+248h+arg_10]
0x1401a1e70  xor     r8d, r8d
0x1401a1e73  mov     dl, 1
0x1401a1e75  mov     rcx, rsi; Irp
0x1401a1e78  call    NtfsInitializeIrpContextInternal
0x1401a1e7d  mov     edi, eax
0x1401a1e7f  test    eax, eax
0x1401a1e81  js      loc_1401A2969
0x1401a1e87  mov     r13, rsi
0x1401a1e8a  mov     [rsp+248h+var_188], rsi
0x1401a1e92  xor     r14b, r14b
0x1401a1e95  mov     [rsp+248h+var_1F8], r14b
0x1401a1e9a  call    cs:__imp_KeEnterCriticalRegion
0x1401a1ea1  nop     dword ptr [rax+rax+00h]
0x1401a1ea6  mov     rdx, rbx
0x1401a1ea9  mov     rbx, [rsp+248h+arg_10]
0x1401a1eb1  mov     rcx, rbx
0x1401a1eb4  call    NtfsUpdateIrpContextWithTopLevel
0x1401a1eb9  mov     rax, [rbx+68h]
0x1401a1ebd  movzx   ecx, byte ptr [rax+2900h]
0x1401a1ec4  test    cl, cl
0x1401a1ec6  jz      short loc_1401A1EE7
0x1401a1ec8  xor     ecx, ecx; PerformanceFrequency
0x1401a1eca  call    cs:__imp_KeQueryPerformanceCounter
0x1401a1ed1  nop     dword ptr [rax+rax+00h]
0x1401a1ed6  mov     [rbx+1F0h], rax
0x1401a1edd  mov     dword ptr [rbx+1F8h], 1Bh
0x1401a1ee7  xor     r8d, r8d; State
0x1401a1eea  xor     edx, edx; Type
0x1401a1eec  lea     rcx, [rsp+248h+Event+8]; Event
0x1401a1ef4  call    cs:__imp_KeInitializeEvent
0x1401a1efb  nop     dword ptr [rax+rax+00h]
0x1401a1f00  xor     edx, edx; Val
0x1401a1f02  mov     r8d, 0F0h; Size
0x1401a1f08  lea     rcx, [rsp+248h+var_158]; void *
0x1401a1f10  call    memset
0x1401a1f15  lea     rax, [rsi+0B8h]
0x1401a1f1c  mov     [rsp+248h+arg_18], rax
0x1401a1f24  mov     rax, [rax]
0x1401a1f27  mov     [rsp+248h+var_A8], rax
0x1401a1f2f  cmp     edi, 0C0000188h
0x1401a1f35  jz      loc_1401A2391
0x1401a1f3b  test    rbx, rbx
0x1401a1f3e  jz      short loc_1401A1F4A
0x1401a1f40  mov     edx, edi
0x1401a1f42  mov     rcx, rbx
0x1401a1f45  call    NtfsPreRequestProcessingExtend
0x1401a1f4a  lea     rax, [rsp+248h+Event]
0x1401a1f52  mov     [rsp+248h+var_120], rax
0x1401a1f5a  or      dword ptr [rbx+0Ch], 10002h
0x1401a1f61  mov     rcx, rbx
0x1401a1f64  test    dword ptr [rbx+0Ch], 200h
0x1401a1f6b  jnz     loc_1401A2061
0x1401a1f71  lea     rdx, [rsp+248h+var_158]
0x1401a1f79  call    TxfMarshalTransactionForCreate
0x1401a1f7e  mov     rdx, [rsp+248h+arg_18]
0x1401a1f86  mov     rax, [rdx]
0x1401a1f89  test    byte ptr [rax+2], 10h
0x1401a1f8d  movzx   r14d, r14b
0x1401a1f91  mov     eax, 1
0x1401a1f96  cmovnz  r14d, eax
0x1401a1f9a  mov     [rsp+248h+var_1F8], r14b
0x1401a1f9f  mov     [rsp+248h+HighLimit], r12
0x1401a1fa7  mov     [rsp+248h+LowLimit], r12
0x1401a1fac  lea     rdx, [rsp+248h+HighLimit]; HighLimit
0x1401a1fb4  lea     rcx, [rsp+248h+LowLimit]; LowLimit
0x1401a1fb9  call    cs:__imp_IoGetStackLimits
0x1401a1fc0  nop     dword ptr [rax+rax+00h]
0x1401a1fc5  lea     rax, [rsp+248h+HighLimit]
0x1401a1fcd  sub     rax, [rsp+248h+LowLimit]
0x1401a1fd2  cmp     rax, 4800h
0x1401a1fd8  jbe     loc_1401A2074
0x1401a1fde  lea     r8, [rsp+248h+var_158]
0x1401a1fe6  mov     rdx, rsi; Irp
0x1401a1fe9  mov     rcx, rbx; int
0x1401a1fec  call    NtfsCommonCreate
0x1401a1ff1  mov     edi, eax
0x1401a1ff3  mov     [rsp+248h+var_1E8], eax
0x1401a1ff7  cmp     edi, 367h
0x1401a1ffd  jnz     loc_1401A239E
0x1401a2003  or      dword ptr [rbx+4], 400h
0x1401a200a  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2011  test    al, al
0x1401a2013  jnz     loc_1401A2379
0x1401a2019  mov     dword ptr [rsp+248h+Context], 1
0x1401a2021  xor     r9d, r9d
0x1401a2024  xor     edx, edx
0x1401a2026  mov     r8d, 367h
0x1401a202c  mov     rcx, rbx
0x1401a202f  call    NtfsExtendedCompleteRequestInternal
0x1401a2034  mov     r9, [rsp+248h+var_120]
0x1401a203c  add     r9, 8
0x1401a2040  mov     dword ptr [rsp+248h+var_220], 1
0x1401a2048  mov     rdx, rsi
0x1401a204b  call    NtfsWaitForOplockCompletionEvent
0x1401a2050  mov     rax, [rsp+248h+var_A8]
0x1401a2058  and     byte ptr [rax+3], 0FEh
0x1401a205c  jmp     loc_1401A239E
0x1401a2061  mov     rdx, rsi
0x1401a2064  call    NtfsCommonVolumeOpen
0x1401a2069  mov     edi, eax
0x1401a206b  mov     [rsp+248h+var_1E8], eax
0x1401a206f  jmp     loc_1401A239E
0x1401a2074  xorps   xmm0, xmm0
0x1401a2077  xor     eax, eax
0x1401a2079  movups  [rsp+248h+Parameter], xmm0
0x1401a207e  movups  [rsp+248h+var_1C8], xmm0
0x1401a2086  mov     qword ptr [rsp+248h+var_1B8], rax
0x1401a208e  mov     qword ptr [rsp+248h+Parameter], rbx
0x1401a2093  mov     qword ptr [rsp+248h+Parameter+8], rsi
0x1401a2098  lea     rax, [rsp+248h+var_158]
0x1401a20a0  mov     qword ptr [rsp+248h+var_1C8], rax
0x1401a20a8  or      qword ptr [rbx+10h], 1
0x1401a20ad  mov     [rsp+248h+Context], r12; Context
0x1401a20b2  xor     r9d, r9d; Wait
0x1401a20b5  mov     r8d, 6000h; Size
0x1401a20bb  lea     rdx, [rsp+248h+Parameter]; Parameter
0x1401a20c0  lea     rcx, NtfsCommonCreateCallout; Callout
0x1401a20c7  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1401a20ce  nop     dword ptr [rax+rax+00h]
0x1401a20d3  mov     edi, eax
0x1401a20d5  test    eax, eax
0x1401a20d7  js      short loc_1401A20EA
0x1401a20d9  cmp     dword ptr [rsp+248h+var_1B8], 103h
0x1401a20e4  jz      loc_1401A21BC
0x1401a20ea  and     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFEh
0x1401a20ef  mov     rax, [rbx+10h]
0x1401a20f3  test    edi, edi
0x1401a20f5  js      loc_1401A2272
0x1401a20fb  test    al, 2
0x1401a20fd  jnz     short loc_1401A2177
0x1401a20ff  mov     edx, dword ptr [rsp+248h+var_1B8]
0x1401a2106  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a210d  test    al, al
0x1401a210f  jnz     short loc_1401A2121
0x1401a2111  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a2118  mov     [rsp+248h+var_1E8], edi
0x1401a211c  jmp     loc_1401A1FF7
0x1401a2121  test    edx, edx
0x1401a2123  jz      short loc_1401A2111
0x1401a2125  cmp     edx, 126h
0x1401a212b  jz      short loc_1401A2111
0x1401a212d  lea     eax, [rdx-12Ah]
0x1401a2133  cmp     eax, 1
0x1401a2136  jbe     short loc_1401A2111
0x1401a2138  cmp     edx, 0FFFFFFEDh
0x1401a213b  jnb     short loc_1401A2111
0x1401a213d  cmp     edx, 0C00000D8h
0x1401a2143  jz      short loc_1401A2111
0x1401a2145  cmp     edx, 0C0000016h
0x1401a214b  jz      short loc_1401A2111
0x1401a214d  cmp     edx, 0C0000011h
0x1401a2153  jz      short loc_1401A2111
0x1401a2155  lea     eax, [rdx+7FFFFFFBh]
0x1401a215b  cmp     eax, 1
0x1401a215e  jbe     short loc_1401A2111
0x1401a2160  cmp     edx, 103h
0x1401a2166  jz      short loc_1401A2111
0x1401a2168  xor     ecx, ecx
0x1401a216a  mov     r8d, 0A0508h
0x1401a2170  call    NtfsStatusTraceAndDebugInternal
0x1401a2175  jmp     short loc_1401A2111
0x1401a2177  and     rax, 0FFFFFFFFFFFFFFFDh
0x1401a217b  mov     [rbx+10h], rax
0x1401a217f  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a2186  mov     eax, [rbx+0Ch]
0x1401a2189  test    al, 2
0x1401a218b  jz      loc_1401A222F
0x1401a2191  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2198  test    al, al
0x1401a219a  jnz     short loc_1401A21D3
0x1401a219c  mov     eax, edi
0x1401a219e  not     eax
0x1401a21a0  shr     eax, 1Fh
0x1401a21a3  mov     r9b, 1
0x1401a21a6  xor     edx, edx
0x1401a21a8  mov     dword ptr [rsp+248h+Context], eax
0x1401a21ac  mov     r8d, edi
0x1401a21af  mov     rcx, rbx
0x1401a21b2  call    NtfsExtendedCompleteRequestInternal
0x1401a21b7  jmp     loc_1401A20FF
0x1401a21bc  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a21c3  mov     edi, dword ptr [rsp+248h+var_1B8]
0x1401a21ca  mov     [rsp+248h+var_1E8], edi
0x1401a21ce  jmp     loc_1401A1FF7
0x1401a21d3  test    edi, edi
0x1401a21d5  jz      short loc_1401A219C
0x1401a21d7  cmp     edi, 126h
0x1401a21dd  jz      short loc_1401A219C
0x1401a21df  lea     eax, [rdi-12Ah]
0x1401a21e5  cmp     eax, 1
0x1401a21e8  jbe     short loc_1401A219C
0x1401a21ea  cmp     edi, 0FFFFFFEDh
0x1401a21ed  jnb     short loc_1401A219C
0x1401a21ef  cmp     edi, 0C00000D8h
0x1401a21f5  jz      short loc_1401A219C
0x1401a21f7  cmp     edi, 0C0000016h
0x1401a21fd  jz      short loc_1401A219C
0x1401a21ff  cmp     edi, 0C0000011h
0x1401a2205  jz      short loc_1401A219C
0x1401a2207  lea     eax, [rdi+7FFFFFFBh]
0x1401a220d  cmp     eax, 1
0x1401a2210  jbe     short loc_1401A219C
0x1401a2212  cmp     edi, 103h
0x1401a2218  jz      short loc_1401A219C
0x1401a221a  mov     r8d, 0A6010h
0x1401a2220  mov     edx, edi
0x1401a2222  mov     rcx, rbx
0x1401a2225  call    NtfsStatusTraceAndDebugInternal
0x1401a222a  jmp     loc_1401A219C
0x1401a222f  cmp     [rsp+248h+var_D0], 0
0x1401a2238  jnz     loc_1401A2191
0x1401a223e  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a2245  test    al, al
0x1401a2247  jnz     loc_1401A22F9
0x1401a224d  mov     eax, edi
0x1401a224f  not     eax
0x1401a2251  shr     eax, 1Fh
0x1401a2254  test    r13, r13
0x1401a2257  setnz   r9b
0x1401a225b  mov     rdx, rsi
0x1401a225e  mov     dword ptr [rsp+248h+Context], eax
0x1401a2262  mov     r8d, edi
0x1401a2265  mov     rcx, rbx
0x1401a2268  call    NtfsExtendedCompleteRequestInternal
0x1401a226d  jmp     loc_1401A20FF
0x1401a2272  cmp     edi, 0C0000017h
0x1401a2278  mov     eax, 0C000009Ah
0x1401a227d  cmovz   edi, eax
0x1401a2280  mov     r9d, edi
0x1401a2283  mov     r8, rsi
0x1401a2286  lea     rdx, [rsp+248h+var_158]
0x1401a228e  mov     rcx, rbx
0x1401a2291  call    NtfsCompleteCreateRequest
0x1401a2296  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a229d  test    al, al
0x1401a229f  jz      loc_1401A2118
0x1401a22a5  cmp     edi, 0FFFFFFEDh
0x1401a22a8  jnb     loc_1401A2118
0x1401a22ae  cmp     edi, 0C0000016h
0x1401a22b4  jz      loc_1401A2118
0x1401a22ba  cmp     edi, 0C0000011h
0x1401a22c0  jz      loc_1401A2118
0x1401a22c6  lea     eax, [rdi+7FFFFFFBh]
0x1401a22cc  cmp     eax, 1
0x1401a22cf  jbe     loc_1401A2118
0x1401a22d5  cmp     edi, 0C00000D8h
0x1401a22db  jz      loc_1401A2118
0x1401a22e1  mov     r8d, 0A04E7h
0x1401a22e7  mov     edx, edi
0x1401a22e9  xor     ecx, ecx
0x1401a22eb  call    NtfsStatusTraceAndDebugInternal
0x1401a22f0  mov     [rsp+248h+var_1E8], edi
0x1401a22f4  jmp     loc_1401A1FF7
0x1401a22f9  test    edi, edi
0x1401a22fb  jz      loc_1401A224D
0x1401a2301  cmp     edi, 126h
0x1401a2307  jz      loc_1401A224D
0x1401a230d  lea     eax, [rdi-12Ah]
  ... truncated ...
```
