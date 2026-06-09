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
  unsigned int v6; // r9d
  struct _SCB *v8; // rbx
  unsigned int v9; // r8d
  unsigned int v10; // edx
  ULONG Length; // r12d
  __int64 *v12; // rsi
  __int64 *v13; // r15
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  __int64 ULong64FromUser; // r12
  PNAMED_PIPE_CREATE_PARAMETERS v16; // rax
  __int64 v17; // rsi
  struct _FAST_MUTEX *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  char v22; // cl
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 v26; // rsi
  __int64 v27; // rdi
  __int64 v28; // rcx
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rsi
  unsigned __int8 v33; // r8
  int v34; // r9d
  BOOLEAN CanFileBeTruncated; // di
  __int64 v36; // rax
  char IsRangeAllocated; // al
  unsigned __int64 v38; // rdi
  char v39; // al
  __int64 *v40; // r8
  __int64 v41; // rdx
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rdx
  __int64 *v44; // rcx
  int v45; // eax
  char v46; // cl
  struct _FAST_MUTEX *v47; // rdi
  bool v48; // cc
  struct _FAST_MUTEX *v49; // rcx
  __int64 v50; // rax
  __int64 *v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rsi
  __int64 *v55; // rdi
  __int64 v56; // rax
  unsigned int v57; // r8d
  char v58; // [rsp+41h] [rbp-127h]
  unsigned int Status; // [rsp+44h] [rbp-124h]
  __int64 *v60; // [rsp+48h] [rbp-120h]
  __int64 v61; // [rsp+50h] [rbp-118h]
  unsigned __int64 v62; // [rsp+58h] [rbp-110h] BYREF
  __int64 v63; // [rsp+60h] [rbp-108h]
  __int64 v64; // [rsp+68h] [rbp-100h]
  ULONG v65; // [rsp+70h] [rbp-F8h]
  unsigned __int64 v66; // [rsp+78h] [rbp-F0h]
  unsigned __int64 v67; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v68; // [rsp+88h] [rbp-E0h]
  struct _SCB *v69; // [rsp+90h] [rbp-D8h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp-D0h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-C8h]
  __int64 v72; // [rsp+A8h] [rbp-C0h]
  __int64 v73; // [rsp+B0h] [rbp-B8h]
  __int64 v74; // [rsp+B8h] [rbp-B0h]
  __int64 v75; // [rsp+C0h] [rbp-A8h]
  __int64 v76; // [rsp+C8h] [rbp-A0h]
  struct _SCB *v77; // [rsp+D0h] [rbp-98h]
  __int64 v78; // [rsp+D8h] [rbp-90h]
  struct _SCB *v79; // [rsp+E0h] [rbp-88h]
  __int128 v80; // [rsp+F0h] [rbp-78h]
  __int128 v81; // [rsp+100h] [rbp-68h]
  __int128 v82; // [rsp+110h] [rbp-58h] BYREF
  __int128 v83[4]; // [rsp+120h] [rbp-48h] BYREF
  __int64 v85; // [rsp+178h] [rbp+10h] BYREF
  struct _FCB *v86; // [rsp+180h] [rbp+18h] BYREF
  __int64 v87; // [rsp+188h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v87 = 0;
  v86 = 0;
  v69 = 0;
  v85 = 0;
  Irp->IoStatus.Information = 0;
  *((_QWORD *)a1 + 1) |= 1uLL;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, CurrentStackLocation->FileObject, &v87, &v86, &v69, &v85, 0) != 2 )
  {
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v6 = 10940;
LABEL_16:
    RefsStatusDebug(-1073741811, 0, "FsCtrl.c", v6);
    return 3221225485LL;
  }
  if ( v85 && (*(_DWORD *)(v85 + 4) & 0x2000) != 0 )
  {
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 265, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v6 = 10953;
    goto LABEL_16;
  }
  LOBYTE(v5) = *((_BYTE *)a1 + 8) & 1;
  v8 = v69;
  v77 = v69;
  if ( !(unsigned __int8)RefsAcquirePagingResourceShared(a1, v69, v5) )
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
    RefsRaiseStatusInternal(a1, (*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608, v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 274, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225704LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592, a1, "FsCtrl.c", 0x2CC3u);
    RefsRaiseStatusInternal(a1, -1073741592, v57);
    JUMPOUT(0x1402B3DA6LL);
  }
  Status = (*((_DWORD *)v8 + 75) & 0x4000) != 0 ? 0xC000026E : 0;
  if ( (*((_DWORD *)v8 + 75) & 0x4000) != 0 )
    goto LABEL_183;
  if ( !RefsIsFileOpen(v86) )
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
    goto LABEL_183;
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
    goto LABEL_183;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  LODWORD(v86) = Length;
  v65 = Length;
  v12 = (__int64 *)RefsMapUserBuffer(Irp, v10);
  v60 = v12;
  v13 = v12 - 2;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( Irp->RequestorMode )
  {
    ProbeForRead(Parameters, CurrentStackLocation->Parameters.Create.Options, 4u);
    ProbeForWrite(v12, Length, 4u);
  }
  else if ( Parameters != (PNAMED_PIPE_CREATE_PARAMETERS)(((unsigned __int64)&Parameters->NamedPipeType + 3)
                                                        & 0xFFFFFFFFFFFFFFFCuLL)
         || v12 != (__int64 *)(((unsigned __int64)v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
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
    goto LABEL_53;
  }
  if ( Irp->RequestorMode )
    ULong64FromUser = RtlReadULong64FromUser(CurrentStackLocation->Parameters.CreatePipe.Parameters);
  else
    ULong64FromUser = *(_QWORD *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v76 = ULong64FromUser;
  v16 = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( Irp->RequestorMode )
    v17 = RtlReadULong64FromUser(&v16->CompletionMode);
  else
    v17 = *(_QWORD *)&v16->CompletionMode;
  v85 = v17;
  if ( v17 < 0 || ULong64FromUser < 0 || v17 > 0x7FFFFFFFFFFFFFFFLL - ULong64FromUser )
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
    goto LABEL_52;
  }
  if ( !v17 )
    goto LABEL_52;
  v18 = (struct _FAST_MUTEX *)*((_QWORD *)v8 + 6);
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe(v18);
  _InterlockedIncrement((volatile signed __int32 *)v8 + 43);
  v19 = *((_QWORD *)v8 + 4);
  if ( ULong64FromUser >= v19 )
  {
    ++*((_DWORD *)v8 + 43);
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v8 + 6));
    KeLeaveGuardedRegion();
    goto LABEL_52;
  }
  v20 = v19 - ULong64FromUser;
  if ( v20 < v17 )
    v17 = v20;
  v77 = (struct _SCB *)v17;
  v85 = v17;
  ++*((_DWORD *)v8 + 43);
  ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v8 + 6));
  KeLeaveGuardedRegion();
  if ( *((__int16 *)v8 + 128) >= 0 || (v21 = *((_DWORD *)v8 + 38), (v21 & 8) != 0) && (v21 & 0x40) == 0 )
  {
    if ( (unsigned int)v86 >= 0x10 )
    {
      v13 += 2;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v13, ULong64FromUser);
      else
        *v13 = ULong64FromUser;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v13 + 1, v17);
      else
        v13[1] = v17;
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
LABEL_52:
    LODWORD(v12) = (_DWORD)v60;
    goto LABEL_53;
  }
  v73 = -1;
  v22 = *(_BYTE *)(v87 + 552);
  v61 = ULong64FromUser >> v22;
  v74 = ULong64FromUser >> v22;
  v23 = *(unsigned int *)(v87 + 272);
  v24 = ULong64FromUser + v17;
  if ( ULong64FromUser + v17 >= (__int64)(0x8000000000000000uLL - v23) )
  {
    v63 = v24 >> v22;
    v25 = (v24 >> v22)
        + ((__int64)((unsigned int)v23 + (*(_DWORD *)(v87 + 544) & ((_DWORD)ULong64FromUser + (_DWORD)v17)) - 1) >> v22);
  }
  else
  {
    v25 = (v17 + ULong64FromUser + v23 - 1) >> v22;
  }
  v26 = ULong64FromUser >> v22;
  v27 = v25 - v61;
  v63 = v27;
  v78 = 0x2000000000LL >> v22;
  RefsBindMinstoreTransaction(a1);
  while ( 2 )
  {
    v75 = v78;
    v28 = v78;
    if ( v78 > v27 )
      v28 = v27;
    v68 = v28;
    v75 = v28;
    v76 = v27 - v28;
    v63 = v27 - v28;
    if ( (*((_BYTE *)v8 + 4) & 0x20) != 0
      && (*((_DWORD *)v8 + 75) & 0x1000) != 0
      && *(_QWORD *)(*((_QWORD *)v8 + 31) + 8LL) )
    {
      v67 = 0;
      v66 = 0;
      v29 = v28;
      v71 = v28;
      FileOffset.QuadPart = 0;
      v72 = v26;
      v64 = 0;
      v85 = 0x80000000LL >> *(_BYTE *)(v87 + 552);
      while ( 1 )
      {
        *(_QWORD *)&v80 = v26;
        *((_QWORD *)&v80 + 1) = v29;
        v82 = v80;
        if ( !(unsigned __int8)RefsIsRangeAllocated(a1, v8, &v82, &v67) )
        {
          v30 = v67;
          v66 = v67;
          v64 = v26;
          RefsCheckpointCurrentTransaction(a1);
          v31 = v26;
          while ( v30 )
          {
            v32 = v30;
            if ( v30 > v85 )
              v32 = v85;
            FileOffset.QuadPart = v31 << *(_BYTE *)(v87 + 552);
            CcCoherencyFlushAndPurgeCache(
              (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v8 + 31) + 8LL),
              &FileOffset,
              v32 << *(_BYTE *)(v87 + 552),
              &Irp->IoStatus,
              3u);
            RefsNormalizeAndCleanupTransaction(a1, (int *)&Irp->IoStatus.0, v33, v34);
            v30 = v66 - v32;
            v66 -= v32;
            v31 = v32 + v64;
            v64 += v32;
          }
          RefsBindMinstoreTransaction(a1);
          v29 = v71;
          v26 = v72;
        }
        if ( v29 <= v67 )
          break;
        v29 -= v67;
        v71 = v29;
        v26 += v67;
        v72 = v26;
      }
      v26 = v61;
    }
    CanFileBeTruncated = MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v8 + 31) + 8LL), 0);
    LOBYTE(v85) = CanFileBeTruncated;
    v36 = v68;
    while ( 1 )
    {
      if ( (v62 = 0,
            *(_QWORD *)&v81 = v26,
            *((_QWORD *)&v81 + 1) = v36,
            v83[0] = v81,
            IsRangeAllocated = RefsIsRangeAllocated(a1, v8, v83, &v62),
            v58 = IsRangeAllocated,
            CanFileBeTruncated)
        && (*((_BYTE *)v8 + 4) & 0x20) != 0
        || IsRangeAllocated
        || !RefsCheckForReservedClusters(v8, v26, &v62) )
      {
        v38 = v62;
      }
      else
      {
        v38 = v62;
        if ( !v62 )
        {
          v39 = 1;
          v38 = 1;
          v62 = 1;
          goto LABEL_88;
        }
      }
      v39 = v58;
LABEL_88:
      if ( v39 )
      {
        if ( v73 == v26 )
        {
          v40 = v13 + 1;
          if ( Irp->RequestorMode )
          {
            v41 = RtlReadULong64FromUser(v13 + 1);
            v40 = v13 + 1;
          }
          else
          {
            v41 = *v40;
          }
          v42 = v38 << *(_BYTE *)(v87 + 552);
          if ( !Irp->RequestorMode )
          {
            *v40 = v42 + v41;
LABEL_104:
            v26 += v38;
            v74 = v26;
            v73 = v26;
            goto LABEL_122;
          }
          v43 = v42 + v41;
          v44 = v40;
        }
        else
        {
          v45 = (int)v86;
          if ( (unsigned int)v86 < 0x10 )
          {
            v12 = v60;
            if ( v13 + 2 == v60 )
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
            v63 = 0;
            goto LABEL_129;
          }
          LODWORD(v86) = (_DWORD)v86 - 16;
          v65 = v45 - 16;
          v13 += 2;
          v46 = *(_BYTE *)(v87 + 552);
          if ( Irp->RequestorMode )
            RtlWriteULong64ToUser(v13, v26 << v46);
          else
            *v13 = v26 << v46;
          v44 = v13 + 1;
          if ( !Irp->RequestorMode )
          {
            *v44 = v38 << *(_BYTE *)(v87 + 552);
            goto LABEL_104;
          }
          v43 = v38 << *(_BYTE *)(v87 + 552);
        }
        RtlWriteULong64ToUser(v44, v43);
        goto LABEL_104;
      }
      v26 += v38;
      v74 = v26;
LABEL_122:
      v61 = v26;
      v47 = (struct _FAST_MUTEX *)*((_QWORD *)v8 + 6);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v47);
      _InterlockedIncrement((volatile signed __int32 *)v8 + 43);
      v48 = v26 << *(_BYTE *)(v87 + 552) < *((_QWORD *)v8 + 4);
      ++*((_DWORD *)v8 + 43);
      v49 = (struct _FAST_MUTEX *)*((_QWORD *)v8 + 6);
      if ( !v48 )
      {
        ExReleaseFastMutexUnsafe(v49);
        KeLeaveGuardedRegion();
        v27 = 0;
        v63 = 0;
        goto LABEL_127;
      }
      ExReleaseFastMutexUnsafe(v49);
      KeLeaveGuardedRegion();
      v36 = v68 - v62;
      v68 = v36;
      v75 = v36;
      if ( v36 <= 0 )
        break;
      CanFileBeTruncated = v85;
    }
    v27 = v76;
LABEL_127:
    if ( v27 )
      continue;
    break;
  }
  v12 = v60;
LABEL_129:
  if ( v13 != v12 - 2 )
  {
    if ( Irp->RequestorMode )
      v50 = RtlReadULong64FromUser(v12);
    else
      v50 = *v12;
    v85 = v50;
    v51 = v12 + 1;
    if ( Irp->RequestorMode )
      v52 = RtlReadULong64FromUser(v12 + 1);
    else
      v52 = *v51;
    if ( v85 < ULong64FromUser )
    {
      v53 = v52 - ULong64FromUser + v85;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v12 + 1, v53);
      else
        *v51 = v53;
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v12, ULong64FromUser);
      else
        *v12 = ULong64FromUser;
    }
    if ( Irp->RequestorMode )
    {
      v54 = RtlReadULong64FromUser(v13);
      v85 = v54;
    }
    else
    {
      v54 = *v13;
      v85 = *v13;
    }
    v55 = v13 + 1;
    if ( Irp->RequestorMode )
      v56 = RtlReadULong64FromUser(v13 + 1);
    else
      v56 = *v55;
    if ( v56 + v54 > (__int64)v77 + ULong64FromUser )
    {
      if ( Irp->RequestorMode )
        RtlWriteULong64ToUser(v13 + 1, (char *)v77 + ULong64FromUser - v85);
      else
        *v55 = (__int64)v77 + ULong64FromUser - v85;
    }
    goto LABEL_52;
  }
LABEL_53:
  Irp->IoStatus.Information = (unsigned int)((_DWORD)v13 - (_DWORD)v12 + 16);
  RefsCheckpointCurrentTransaction(a1);
  RefsFlushForWriteThrough(a1, v8, 0);
LABEL_183:
  v79 = v8;
  RefsReleasePagingResource(a1);
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
