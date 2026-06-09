# RefsQueryAllocatedRanges(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402b2ec0`
- end: `0x1402b3da6`
- name: `?RefsQueryAllocatedRanges@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `3814`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140320e78`

## callees

- `0x14000cd70`
- `0x140041b40`
- `0x140080b90`
- `0x140081670`
- `0x140087ee0`
- `0x14008dbd0`
- `0x14008e060`
- `0x14008e360`
- `0x1400913a0`
- `0x140096fd0`
- `0x1400ca788`
- `0x1400f9854`
- `0x14028d9b0`
- `0x14028daac`
- `0x14028db38`
- `0x14028df04`
- `0x1402b2ec0`
- `0x1402fec90`
- `0x1403021e0`

## import_xrefs

- `ntoskrnl!MmCanFileBeTruncated` at `0x1402b3624`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1402b3624`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1402b359b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1402b359b`
- `ntoskrnl!ProbeForRead` at `0x1402b31c9`
- `ntoskrnl!ProbeForRead` at `0x1402b31c9`
- `ntoskrnl!ProbeForWrite` at `0x1402b31e1`
- `ntoskrnl!ProbeForWrite` at `0x1402b31e1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b3291`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b38e4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b3291`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b38e4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b32a0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b38f3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b32a0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b38f3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b32ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b333d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b3933`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b397d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b32ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b333d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b3933`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b397d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b32da`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b3349`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b393f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b3989`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b32da`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b3349`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b393f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b3989`

## pseudocode

```c
__int64 __fastcall RefsQueryAllocatedRanges(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v5; // r8
  struct _SCB *v7; // rbx
  unsigned int v8; // r8d
  unsigned int v9; // edx
  ULONG Length; // r12d
  __int64 *v11; // rsi
  __int64 *v12; // r15
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  __int64 ULong64FromUser; // r12
  PNAMED_PIPE_CREATE_PARAMETERS v15; // rax
  __int64 v16; // rsi
  struct _FAST_MUTEX *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // ecx
  char v21; // cl
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rsi
  __int64 v26; // rdi
  __int64 v27; // rcx
  unsigned __int64 v28; // rdi
  unsigned __int64 v29; // rdi
  __int64 v30; // rax
  unsigned __int64 v31; // rsi
  unsigned __int8 v32; // r8
  int v33; // r9d
  BOOLEAN CanFileBeTruncated; // di
  __int64 v35; // rax
  char IsRangeAllocated; // al
  unsigned __int64 v37; // rdi
  char v38; // al
  __int64 *v39; // r8
  __int64 v40; // rdx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rdx
  __int64 *v43; // rcx
  int v44; // eax
  char v45; // cl
  struct _FAST_MUTEX *v46; // rdi
  bool v47; // cc
  struct _FAST_MUTEX *v48; // rcx
  __int64 v49; // rax
  __int64 *v50; // rdi
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rsi
  __int64 *v54; // rdi
  __int64 v55; // rax
  unsigned int v56; // r8d
  char v57; // [rsp+41h] [rbp-127h]
  unsigned int Status; // [rsp+44h] [rbp-124h]
  __int64 *v59; // [rsp+48h] [rbp-120h]
  __int64 v60; // [rsp+50h] [rbp-118h]
  unsigned __int64 v61; // [rsp+58h] [rbp-110h] BYREF
  __int64 v62; // [rsp+60h] [rbp-108h]
  __int64 v63; // [rsp+68h] [rbp-100h]
  ULONG v64; // [rsp+70h] [rbp-F8h]
  unsigned __int64 v65; // [rsp+78h] [rbp-F0h]
  unsigned __int64 v66; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v67; // [rsp+88h] [rbp-E0h]
  struct _SCB *v68; // [rsp+90h] [rbp-D8h]
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp-D0h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-C8h]
  __int64 v71; // [rsp+A8h] [rbp-C0h]
  __int64 v72; // [rsp+B0h] [rbp-B8h]
  __int64 v73; // [rsp+B8h] [rbp-B0h]
  __int64 v74; // [rsp+C0h] [rbp-A8h]
  __int64 v75; // [rsp+C8h] [rbp-A0h]
  struct _SCB *v76; // [rsp+D0h] [rbp-98h]
  __int64 v77; // [rsp+D8h] [rbp-90h]
  struct _SCB *v78; // [rsp+E0h] [rbp-88h]
  __int128 v79; // [rsp+F0h] [rbp-78h]
  __int128 v80; // [rsp+100h] [rbp-68h]
  __int128 v81; // [rsp+110h] [rbp-58h] BYREF
  __int128 v82[4]; // [rsp+120h] [rbp-48h] BYREF
  unsigned __int64 v84; // [rsp+178h] [rbp+10h]
  BOOLEAN v85; // [rsp+178h] [rbp+10h]
  __int64 v86; // [rsp+178h] [rbp+10h]
  __int64 v87; // [rsp+178h] [rbp+10h]
  struct _FCB *v88; // [rsp+180h] [rbp+18h] BYREF
  __int64 v89; // [rsp+188h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v89 = 0;
  v88 = 0;
  v68 = 0;
  Irp->IoStatus.Information = 0;
  *((_QWORD *)a1 + 1) |= 1uLL;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, CurrentStackLocation->FileObject, &v89, &v88) != 2 )
  {
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", 0x2ABCu);
    return 3221225485LL;
  }
  LOBYTE(v5) = *((_BYTE *)a1 + 8) & 1;
  v7 = v68;
  v76 = v68;
  if ( !(unsigned __int8)RefsAcquirePagingResourceShared(a1, v68, v5) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        266,
        WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
        (*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug((*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608, a1, "FsCtrl.c", 0x2ADDu);
    RefsRaiseStatusInternal(a1, (*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 274, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225704LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592, a1, "FsCtrl.c", 0x2CC3u);
    RefsRaiseStatusInternal(a1, -1073741592, v56);
    JUMPOUT(0x1402B3DA6LL);
  }
  Status = (*((_DWORD *)v68 + 75) & 0x4000) != 0 ? 0xC000026E : 0;
  if ( (*((_DWORD *)v68 + 75) & 0x4000) != 0 )
    goto LABEL_175;
  if ( !RefsIsFileOpen(v88) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 267, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, 0, "FsCtrl.c", 0x2AEFu);
    Status = -1073741528;
    goto LABEL_175;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 268, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", 0x2AFAu);
    Status = -1073741811;
    goto LABEL_175;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  LODWORD(v88) = Length;
  v64 = Length;
  v11 = (__int64 *)RefsMapUserBuffer(Irp, v9);
  v59 = v11;
  v12 = v11 - 2;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( Irp->RequestorMode )
  {
    ProbeForRead(Parameters, CurrentStackLocation->Parameters.Create.Options, 4u);
    ProbeForWrite(v11, Length, 4u);
  }
  else if ( Parameters != (PNAMED_PIPE_CREATE_PARAMETERS)(((unsigned __int64)&Parameters->NamedPipeType + 3)
                                                        & 0xFFFFFFFFFFFFFFFCuLL)
         || v11 != (__int64 *)(((unsigned __int64)v11 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 269, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225704LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592, 0, "FsCtrl.c", 0x2B20u);
    Status = -1073741592;
    goto LABEL_45;
  }
  if ( Irp->RequestorMode )
    ULong64FromUser = RtlReadULong64FromUser(CurrentStackLocation->Parameters.CreatePipe.Parameters);
  else
    ULong64FromUser = *(_QWORD *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v75 = ULong64FromUser;
  v15 = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( Irp->RequestorMode )
    v16 = RtlReadULong64FromUser(&v15->CompletionMode);
  else
    v16 = *(_QWORD *)&v15->CompletionMode;
  if ( v16 < 0 || ULong64FromUser < 0 || v16 > 0x7FFFFFFFFFFFFFFFLL - ULong64FromUser )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 270, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", 0x2B3Bu);
    Status = -1073741811;
    goto LABEL_44;
  }
  if ( !v16 )
    goto LABEL_44;
  v17 = (struct _FAST_MUTEX *)*((_QWORD *)v68 + 6);
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe(v17);
  _InterlockedIncrement((volatile signed __int32 *)v68 + 43);
  v18 = *((_QWORD *)v68 + 4);
  if ( ULong64FromUser >= v18 )
  {
    ++*((_DWORD *)v68 + 43);
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v7 + 6));
    KeLeaveGuardedRegion();
    goto LABEL_44;
  }
  v19 = v18 - ULong64FromUser;
  if ( v19 < v16 )
    v16 = v19;
  v76 = (struct _SCB *)v16;
  ++*((_DWORD *)v68 + 43);
  ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v7 + 6));
  KeLeaveGuardedRegion();
  if ( *((__int16 *)v7 + 128) >= 0 || (v20 = *((_DWORD *)v7 + 38), (v20 & 8) != 0) && (v20 & 0x40) == 0 )
  {
    if ( (unsigned int)v88 >= 0x10 )
    {
      v12 += 2;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v12, ULong64FromUser);
      else
        *v12 = ULong64FromUser;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v12 + 1, v16);
      else
        v12[1] = v16;
      Irp->IoStatus.Information = 16;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 271, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225507LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x2B62u);
      Status = -1073741789;
    }
LABEL_44:
    LODWORD(v11) = (_DWORD)v59;
    goto LABEL_45;
  }
  v72 = -1;
  v21 = *(_BYTE *)(v89 + 552);
  v60 = ULong64FromUser >> v21;
  v73 = ULong64FromUser >> v21;
  v22 = *(unsigned int *)(v89 + 272);
  v23 = ULong64FromUser + v16;
  if ( ULong64FromUser + v16 >= (__int64)(0x8000000000000000uLL - v22) )
  {
    v62 = v23 >> v21;
    v24 = (v23 >> v21)
        + ((__int64)((unsigned int)v22 + (*(_DWORD *)(v89 + 544) & ((_DWORD)ULong64FromUser + (_DWORD)v16)) - 1) >> v21);
  }
  else
  {
    v24 = (v16 + ULong64FromUser + v22 - 1) >> v21;
  }
  v25 = ULong64FromUser >> v21;
  v26 = v24 - v60;
  v62 = v26;
  v77 = 0x2000000000LL >> v21;
  RefsBindMinstoreTransaction(a1);
  while ( 2 )
  {
    v74 = v77;
    v27 = v77;
    if ( v77 > v26 )
      v27 = v26;
    v67 = v27;
    v74 = v27;
    v75 = v26 - v27;
    v62 = v26 - v27;
    if ( (*((_BYTE *)v7 + 4) & 0x20) != 0
      && (*((_DWORD *)v7 + 75) & 0x1000) != 0
      && *(_QWORD *)(*((_QWORD *)v7 + 31) + 8LL) )
    {
      v66 = 0;
      v65 = 0;
      v28 = v27;
      v70 = v27;
      FileOffset.QuadPart = 0;
      v71 = v25;
      v63 = 0;
      v84 = 0x80000000LL >> *(_BYTE *)(v89 + 552);
      while ( 1 )
      {
        *(_QWORD *)&v79 = v25;
        *((_QWORD *)&v79 + 1) = v28;
        v81 = v79;
        if ( !(unsigned __int8)RefsIsRangeAllocated(a1, v7, &v81, &v66) )
        {
          v29 = v66;
          v65 = v66;
          v63 = v25;
          RefsCheckpointCurrentTransaction(a1);
          v30 = v25;
          while ( v29 )
          {
            v31 = v29;
            if ( v29 > v84 )
              v31 = v84;
            FileOffset.QuadPart = v30 << *(_BYTE *)(v89 + 552);
            CcCoherencyFlushAndPurgeCache(
              (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v7 + 31) + 8LL),
              &FileOffset,
              v31 << *(_BYTE *)(v89 + 552),
              &Irp->IoStatus,
              3u);
            RefsNormalizeAndCleanupTransaction(a1, (int *)&Irp->IoStatus.0, v32, v33);
            v29 = v65 - v31;
            v65 -= v31;
            v30 = v31 + v63;
            v63 += v31;
          }
          RefsBindMinstoreTransaction(a1);
          v28 = v70;
          v25 = v71;
        }
        if ( v28 <= v66 )
          break;
        v28 -= v66;
        v70 = v28;
        v25 += v66;
        v71 = v25;
      }
      v25 = v60;
    }
    CanFileBeTruncated = MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v7 + 31) + 8LL), 0);
    v85 = CanFileBeTruncated;
    v35 = v67;
    while ( 1 )
    {
      if ( (v61 = 0,
            *(_QWORD *)&v80 = v25,
            *((_QWORD *)&v80 + 1) = v35,
            v82[0] = v80,
            IsRangeAllocated = RefsIsRangeAllocated(a1, v7, v82, &v61),
            v57 = IsRangeAllocated,
            CanFileBeTruncated)
        && (*((_BYTE *)v7 + 4) & 0x20) != 0
        || IsRangeAllocated
        || !RefsCheckForReservedClusters(v7, v25, &v61) )
      {
        v37 = v61;
      }
      else
      {
        v37 = v61;
        if ( !v61 )
        {
          v38 = 1;
          v37 = 1;
          v61 = 1;
          goto LABEL_80;
        }
      }
      v38 = v57;
LABEL_80:
      if ( v38 )
      {
        if ( v72 == v25 )
        {
          v39 = v12 + 1;
          if ( Irp->RequestorMode )
          {
            v40 = RtlReadULong64FromUser(v12 + 1);
            v39 = v12 + 1;
          }
          else
          {
            v40 = *v39;
          }
          v41 = v37 << *(_BYTE *)(v89 + 552);
          if ( !Irp->RequestorMode )
          {
            *v39 = v41 + v40;
LABEL_96:
            v25 += v37;
            v73 = v25;
            v72 = v25;
            goto LABEL_114;
          }
          v42 = v41 + v40;
          v43 = v39;
        }
        else
        {
          v44 = (int)v88;
          if ( (unsigned int)v88 < 0x10 )
          {
            v11 = v59;
            if ( v12 + 2 == v59 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  272,
                  WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
                  3221225507LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x2C5Cu);
              Status = -1073741789;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  273,
                  WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
                  2147483653LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-2147483643, 0, "FsCtrl.c", 0x2C60u);
              Status = -2147483643;
            }
            v62 = 0;
            goto LABEL_121;
          }
          LODWORD(v88) = (_DWORD)v88 - 16;
          v64 = v44 - 16;
          v12 += 2;
          v45 = *(_BYTE *)(v89 + 552);
          if ( Irp->RequestorMode )
            RtlWriteULong64ToUser(v12, v25 << v45);
          else
            *v12 = v25 << v45;
          v43 = v12 + 1;
          if ( !Irp->RequestorMode )
          {
            *v43 = v37 << *(_BYTE *)(v89 + 552);
            goto LABEL_96;
          }
          v42 = v37 << *(_BYTE *)(v89 + 552);
        }
        RtlWriteULong64ToUser(v43, v42);
        goto LABEL_96;
      }
      v25 += v37;
      v73 = v25;
LABEL_114:
      v60 = v25;
      v46 = (struct _FAST_MUTEX *)*((_QWORD *)v7 + 6);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v46);
      _InterlockedIncrement((volatile signed __int32 *)v7 + 43);
      v47 = v25 << *(_BYTE *)(v89 + 552) < *((_QWORD *)v7 + 4);
      ++*((_DWORD *)v7 + 43);
      v48 = (struct _FAST_MUTEX *)*((_QWORD *)v7 + 6);
      if ( !v47 )
      {
        ExReleaseFastMutexUnsafe(v48);
        KeLeaveGuardedRegion();
        v26 = 0;
        v62 = 0;
        goto LABEL_119;
      }
      ExReleaseFastMutexUnsafe(v48);
      KeLeaveGuardedRegion();
      v35 = v67 - v61;
      v67 = v35;
      v74 = v35;
      if ( v35 <= 0 )
        break;
      CanFileBeTruncated = v85;
    }
    v26 = v75;
LABEL_119:
    if ( v26 )
      continue;
    break;
  }
  v11 = v59;
LABEL_121:
  if ( v12 != v11 - 2 )
  {
    if ( Irp->RequestorMode )
      v49 = RtlReadULong64FromUser(v11);
    else
      v49 = *v11;
    v86 = v49;
    v50 = v11 + 1;
    if ( Irp->RequestorMode )
      v51 = RtlReadULong64FromUser(v11 + 1);
    else
      v51 = *v50;
    if ( v86 < ULong64FromUser )
    {
      v52 = v51 - ULong64FromUser + v86;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v11 + 1, v52);
      else
        *v50 = v52;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v11, ULong64FromUser);
      else
        *v11 = ULong64FromUser;
    }
    if ( Irp->RequestorMode )
    {
      v53 = RtlReadULong64FromUser(v12);
      v87 = v53;
    }
    else
    {
      v53 = *v12;
      v87 = *v12;
    }
    v54 = v12 + 1;
    if ( Irp->RequestorMode )
      v55 = RtlReadULong64FromUser(v12 + 1);
    else
      v55 = *v54;
    if ( v55 + v53 > (__int64)v76 + ULong64FromUser )
    {
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v12 + 1, (char *)v76 + ULong64FromUser - v87);
      else
        *v54 = (__int64)v76 + ULong64FromUser - v87;
    }
    goto LABEL_44;
  }
LABEL_45:
  Irp->IoStatus.Information = (unsigned int)((_DWORD)v12 - (_DWORD)v11 + 16);
  RefsCheckpointCurrentTransaction(a1);
  RefsFlushForWriteThrough(a1, v7, 0);
LABEL_175:
  v78 = v7;
  RefsReleasePagingResource(a1, v7);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, Status);
  return Status;
}

```

## disassembly

```asm
0x1402b2ec0  mov     r11, rsp
0x1402b2ec3  mov     [r11+8], rcx
0x1402b2ec7  push    rbx
0x1402b2ec8  push    rsi
0x1402b2ec9  push    rdi
0x1402b2eca  push    r12
0x1402b2ecc  push    r13
0x1402b2ece  push    r14
0x1402b2ed0  push    r15
0x1402b2ed2  sub     rsp, 130h
0x1402b2ed9  mov     r14, rdx
0x1402b2edc  mov     r13, rcx
0x1402b2edf  mov     rdi, [rdx+0B8h]
0x1402b2ee6  xor     esi, esi
0x1402b2ee8  mov     [r11+20h], rsi
0x1402b2eec  mov     [r11+18h], rsi
0x1402b2ef0  mov     [r11-0D8h], rsi
0x1402b2ef7  mov     [r11+10h], rsi
0x1402b2efb  mov     [rdx+38h], rsi
0x1402b2eff  or      qword ptr [rcx+8], 1
0x1402b2f04  mov     [rsp+168h+var_138], sil
0x1402b2f09  lea     rax, [r11+10h]
0x1402b2f0d  mov     [rsp+168h+var_140], rax
0x1402b2f12  lea     rax, [r11-0D8h]
0x1402b2f19  mov     qword ptr [rsp+168h+Flags], rax
0x1402b2f1e  lea     r9, [r11+18h]
0x1402b2f22  lea     r8, [r11+20h]
0x1402b2f26  mov     rdx, [rdi+30h]
0x1402b2f2a  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402b2f2f  cmp     al, 2
0x1402b2f31  jz      short loc_1402B2F99
0x1402b2f33  mov     edi, 0C000000Dh
0x1402b2f38  mov     r8d, edi; Status
0x1402b2f3b  mov     rdx, r14; Irp
0x1402b2f3e  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b2f41  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b2f46  lea     rax, WPP_GLOBAL_Control
0x1402b2f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b2f54  cmp     rcx, rax
0x1402b2f57  jz      short loc_1402B2F80
0x1402b2f59  test    dword ptr [rcx+2Ch], 100h
0x1402b2f60  jz      short loc_1402B2F80
0x1402b2f62  cmp     byte ptr [rcx+29h], 4
0x1402b2f66  jb      short loc_1402B2F80
0x1402b2f68  mov     edx, 108h
0x1402b2f6d  mov     r9d, edi
0x1402b2f70  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402b2f77  mov     rcx, [rcx+18h]
0x1402b2f7b  call    WPP_SF_d
0x1402b2f80  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b2f86  test    al, al
0x1402b2f88  jz      loc_1402B3029
0x1402b2f8e  mov     r9d, 2ABCh
0x1402b2f94  jmp     loc_1402B3019
0x1402b2f99  mov     [rsp+168h+var_126], sil
0x1402b2f9e  mov     rax, [rsp+168h+arg_8]
0x1402b2fa6  test    rax, rax
0x1402b2fa9  jz      loc_1402B303F
0x1402b2faf  mov     eax, [rax+4]
0x1402b2fb2  bt      eax, 0Dh
0x1402b2fb6  jnb     loc_1402B303F
0x1402b2fbc  mov     edi, 0C000000Dh
0x1402b2fc1  mov     r8d, edi; Status
0x1402b2fc4  mov     rdx, r14; Irp
0x1402b2fc7  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b2fca  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b2fcf  lea     rax, WPP_GLOBAL_Control
0x1402b2fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b2fdd  cmp     rcx, rax
0x1402b2fe0  jz      short loc_1402B3009
0x1402b2fe2  test    dword ptr [rcx+2Ch], 100h
0x1402b2fe9  jz      short loc_1402B3009
0x1402b2feb  cmp     byte ptr [rcx+29h], 4
0x1402b2fef  jb      short loc_1402B3009
0x1402b2ff1  mov     edx, 109h
0x1402b2ff6  mov     r9d, edi
0x1402b2ff9  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402b3000  mov     rcx, [rcx+18h]
0x1402b3004  call    WPP_SF_d
0x1402b3009  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b300f  test    cl, cl
0x1402b3011  jz      short loc_1402B3029
0x1402b3013  mov     r9d, 2AC9h; unsigned int
0x1402b3019  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b3020  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b3022  mov     ecx, edi; Status
0x1402b3024  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b3029  mov     eax, edi
0x1402b302b  add     rsp, 130h
0x1402b3032  pop     r15
0x1402b3034  pop     r14
0x1402b3036  pop     r13
0x1402b3038  pop     r12
0x1402b303a  pop     rdi
0x1402b303b  pop     rsi
0x1402b303c  pop     rbx
0x1402b303d  retn
0x1402b303f  mov     r8b, [r13+8]
0x1402b3043  and     r8b, 1
0x1402b3047  mov     rbx, [rsp+168h+var_D8]
0x1402b304f  mov     [rsp+168h+var_98], rbx
0x1402b3057  mov     rdx, rbx
0x1402b305a  mov     rcx, r13
0x1402b305d  call    ?RefsAcquirePagingResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x1402b3062  test    al, al
0x1402b3064  jz      loc_1402B3C8B
0x1402b306a  mov     [rsp+168h+var_126], 1
0x1402b306f  mov     edx, [rbx+12Ch]
0x1402b3075  and     edx, 4000h
0x1402b307b  mov     eax, edx
0x1402b307d  neg     eax
0x1402b307f  sbb     ecx, ecx
0x1402b3081  and     ecx, 0C000026Eh
0x1402b3087  mov     [rsp+168h+Status], ecx
0x1402b308b  test    edx, edx
0x1402b308d  jnz     loc_1402B3C5F
0x1402b3093  mov     rcx, [rsp+168h+arg_10]; struct _FCB *
0x1402b309b  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402b30a0  test    al, al
0x1402b30a2  jnz     short loc_1402B3111
0x1402b30a4  lea     rax, WPP_GLOBAL_Control
0x1402b30ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b30b2  cmp     rcx, rax
0x1402b30b5  jz      short loc_1402B30E1
0x1402b30b7  mov     eax, [rcx+2Ch]
0x1402b30ba  bt      eax, 8
0x1402b30be  jnb     short loc_1402B30E1
0x1402b30c0  cmp     byte ptr [rcx+29h], 4
0x1402b30c4  jb      short loc_1402B30E1
0x1402b30c6  mov     edx, 10Bh
0x1402b30cb  mov     r9d, 0C0000128h
0x1402b30d1  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402b30d8  mov     rcx, [rcx+18h]
0x1402b30dc  call    WPP_SF_d
0x1402b30e1  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b30e7  test    al, al
0x1402b30e9  jz      short loc_1402B3104
0x1402b30eb  mov     r9d, 2AEFh; unsigned int
0x1402b30f1  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b30f8  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b30fa  mov     ecx, 0C0000128h; Status
0x1402b30ff  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b3104  mov     [rsp+168h+Status], 0C0000128h
0x1402b310c  jmp     loc_1402B3C5F
0x1402b3111  cmp     dword ptr [rdi+10h], 10h
0x1402b3115  jnb     short loc_1402B3186
0x1402b3117  lea     rax, WPP_GLOBAL_Control
0x1402b311e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b3125  cmp     rcx, rax
0x1402b3128  jz      short loc_1402B3158
0x1402b312a  mov     eax, [rcx+2Ch]
0x1402b312d  bt      eax, 8
0x1402b3131  jnb     short loc_1402B3158
0x1402b3133  cmp     byte ptr [rcx+29h], 4
0x1402b3137  jb      short loc_1402B3158
0x1402b3139  mov     edx, 10Ch
0x1402b313e  mov     edi, 0C000000Dh
0x1402b3143  mov     r9d, edi
0x1402b3146  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402b314d  mov     rcx, [rcx+18h]
0x1402b3151  call    WPP_SF_d
0x1402b3156  jmp     short loc_1402B315D
0x1402b3158  mov     edi, 0C000000Dh
0x1402b315d  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b3163  test    al, al
0x1402b3165  jz      short loc_1402B317D
0x1402b3167  mov     r9d, 2AFAh; unsigned int
0x1402b316d  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b3174  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b3176  mov     ecx, edi; Status
0x1402b3178  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b317d  mov     [rsp+168h+Status], edi
0x1402b3181  jmp     loc_1402B3C5F
0x1402b3186  mov     [rsp+168h+var_128], 1
0x1402b318b  mov     r12d, [rdi+8]
0x1402b318f  mov     dword ptr [rsp+168h+arg_10], r12d
0x1402b3197  mov     [rsp+168h+var_F8], r12d
0x1402b319c  mov     rcx, r14; struct _IRP *
0x1402b319f  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402b31a4  mov     rsi, rax
0x1402b31a7  mov     [rsp+168h+var_120], rax
0x1402b31ac  lea     r15, [rax-10h]
0x1402b31b0  mov     [rsp+168h+var_118], r15
0x1402b31b5  mov     rcx, [rdi+20h]; Address
0x1402b31b9  cmp     byte ptr [r14+40h], 0
0x1402b31be  jz      short loc_1402B31EF
0x1402b31c0  mov     edx, [rdi+10h]; Length
0x1402b31c3  mov     r8d, 4; Alignment
0x1402b31c9  call    cs:__imp_ProbeForRead
0x1402b31d0  nop     dword ptr [rax+rax+00h]
0x1402b31d5  mov     edx, r12d; Length
0x1402b31d8  mov     r8d, 4; Alignment
0x1402b31de  mov     rcx, rsi; Address
0x1402b31e1  call    cs:__imp_ProbeForWrite
0x1402b31e8  nop     dword ptr [rax+rax+00h]
0x1402b31ed  jmp     short loc_1402B3211
0x1402b31ef  lea     rax, [rcx+3]
0x1402b31f3  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402b31f7  cmp     rcx, rax
0x1402b31fa  jnz     loc_1402B3BF2
0x1402b3200  lea     rax, [rsi+3]
0x1402b3204  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402b3208  cmp     rsi, rax
0x1402b320b  jnz     loc_1402B3BF2
0x1402b3211  mov     r12, [rdi+20h]
0x1402b3215  cmp     byte ptr [r14+40h], 0
0x1402b321a  jz      short loc_1402B3229
0x1402b321c  mov     rcx, r12
0x1402b321f  call    RtlReadULong64FromUser
0x1402b3224  mov     r12, rax
0x1402b3227  jmp     short loc_1402B322D
0x1402b3229  mov     r12, [r12]
0x1402b322d  mov     [rsp+168h+var_A0], r12
0x1402b3235  mov     rax, [rdi+20h]
0x1402b3239  xor     edi, edi
0x1402b323b  cmp     [r14+40h], dil
0x1402b323f  jz      short loc_1402B324F
0x1402b3241  lea     rcx, [rax+8]
0x1402b3245  call    RtlReadULong64FromUser
0x1402b324a  mov     rsi, rax
0x1402b324d  jmp     short loc_1402B3253
0x1402b324f  mov     rsi, [rax+8]
0x1402b3253  mov     [rsp+168h+arg_8], rsi
0x1402b325b  mov     [rsp+168h+var_128], dil
0x1402b3260  test    rsi, rsi
0x1402b3263  js      loc_1402B3B83
0x1402b3269  test    r12, r12
0x1402b326c  js      loc_1402B3B83
0x1402b3272  mov     rax, 7FFFFFFFFFFFFFFFh
0x1402b327c  sub     rax, r12
0x1402b327f  cmp     rsi, rax
0x1402b3282  jg      loc_1402B3B83
0x1402b3288  test    rsi, rsi
0x1402b328b  jz      short loc_1402B32E6
0x1402b328d  mov     rdi, [rbx+30h]
0x1402b3291  call    cs:__imp_KeEnterGuardedRegion
0x1402b3298  nop     dword ptr [rax+rax+00h]
0x1402b329d  mov     rcx, rdi; FastMutex
0x1402b32a0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1402b32a7  nop     dword ptr [rax+rax+00h]
0x1402b32ac  lock inc dword ptr [rbx+0ACh]
0x1402b32b3  mov     rax, [rbx+20h]
0x1402b32b7  cmp     r12, rax
0x1402b32ba  jl      short loc_1402B3311
0x1402b32bc  mov     eax, [rbx+0ACh]
0x1402b32c2  inc     eax
0x1402b32c4  mov     [rbx+0ACh], eax
0x1402b32ca  mov     rcx, [rbx+30h]; FastMutex
0x1402b32ce  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402b32d5  nop     dword ptr [rax+rax+00h]
0x1402b32da  call    cs:__imp_KeLeaveGuardedRegion
0x1402b32e1  nop     dword ptr [rax+rax+00h]
0x1402b32e6  mov     rsi, [rsp+168h+var_120]
0x1402b32eb  sub     r15d, esi
0x1402b32ee  lea     eax, [r15+10h]
0x1402b32f2  mov     [r14+38h], rax
0x1402b32f6  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b32f9  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x1402b32fe  xor     r8d, r8d
0x1402b3301  mov     rdx, rbx
0x1402b3304  mov     rcx, r13
0x1402b3307  call    ?RefsFlushForWriteThrough@@YAXPEAU_IRP_CONTEXT@@PEAXW4REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS@@@Z; RefsFlushForWriteThrough(_IRP_CONTEXT *,void *,REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS)
0x1402b330c  jmp     loc_1402B3C5F
0x1402b3311  sub     rax, r12
0x1402b3314  cmp     rax, rsi
0x1402b3317  cmovl   rsi, rax
0x1402b331b  mov     [rsp+168h+var_98], rsi
0x1402b3323  mov     [rsp+168h+arg_8], rsi
0x1402b332b  mov     eax, [rbx+0ACh]
0x1402b3331  inc     eax
0x1402b3333  mov     [rbx+0ACh], eax
0x1402b3339  mov     rcx, [rbx+30h]; FastMutex
0x1402b333d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402b3344  nop     dword ptr [rax+rax+00h]
0x1402b3349  call    cs:__imp_KeLeaveGuardedRegion
0x1402b3350  nop     dword ptr [rax+rax+00h]
0x1402b3355  xor     edi, edi
0x1402b3357  cmp     [rbx+100h], di
0x1402b335e  jge     loc_1402B3AC3
0x1402b3364  mov     ecx, [rbx+98h]
0x1402b336a  mov     eax, ecx
0x1402b336c  and     eax, 8
0x1402b336f  jz      short loc_1402B337A
0x1402b3371  and     ecx, 40h
0x1402b3374  jz      loc_1402B3AC3
0x1402b337a  mov     [rsp+168h+var_B8], 0FFFFFFFFFFFFFFFFh
0x1402b3386  mov     r9, [rsp+168h+arg_18]
0x1402b338e  movsx   ecx, byte ptr [r9+228h]
0x1402b3396  mov     rax, r12
0x1402b3399  sar     rax, cl
0x1402b339c  mov     [rsp+168h+var_118], rax
0x1402b33a1  mov     [rsp+168h+var_B0], rax
0x1402b33a9  mov     r8d, [r9+110h]
0x1402b33b0  lea     rdx, [r12+rsi]
0x1402b33b4  mov     rax, 8000000000000000h
0x1402b33be  sub     rax, r8
0x1402b33c1  cmp     rdx, rax
0x1402b33c4  jge     short loc_1402B33D5
0x1402b33c6  lea     rdi, [r8-1]
0x1402b33ca  add     rdi, r12
  ... truncated ...
```
