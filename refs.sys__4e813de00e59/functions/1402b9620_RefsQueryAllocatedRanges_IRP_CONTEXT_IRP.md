# RefsQueryAllocatedRanges(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402b9620`
- end: `0x1402ba506`
- name: `?RefsQueryAllocatedRanges@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `3814`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x14000e0e0`
- `0x1400298a0`
- `0x140075ff0`
- `0x140076ad0`
- `0x14007cdb0`
- `0x1400862c0`
- `0x140086690`
- `0x140088990`
- `0x14008ad80`
- `0x140090c50`
- `0x1400d0fd8`
- `0x1400fe714`
- `0x140294944`
- `0x140294a40`
- `0x140294acc`
- `0x140294e98`
- `0x1402b9620`
- `0x140302e10`
- `0x140306290`

## import_xrefs

- `ntoskrnl!MmCanFileBeTruncated` at `0x1402b9d84`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1402b9d84`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1402b9cfb`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1402b9cfb`
- `ntoskrnl!ProbeForRead` at `0x1402b9929`
- `ntoskrnl!ProbeForRead` at `0x1402b9929`
- `ntoskrnl!ProbeForWrite` at `0x1402b9941`
- `ntoskrnl!ProbeForWrite` at `0x1402b9941`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b99f1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402ba044`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402b99f1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402ba044`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b9a00`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402ba053`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b9a00`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402ba053`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b9a2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b9a9d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ba093`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ba0dd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b9a2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b9a9d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ba093`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ba0dd`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b9a3a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b9aa9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ba09f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ba0e9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b9a3a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402b9aa9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ba09f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ba0e9`

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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 258, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v6 = 10705;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 259, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v6 = 10718;
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
        260,
        WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
        (*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug((*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608, a1, "FsCtrl.c", 0x29F2u);
    RefsRaiseStatusInternal(a1, (*((_BYTE *)a1 + 8) & 1) != 0 ? -1073741823 : -1073741608, v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 268, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225704LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592, a1, "FsCtrl.c", 0x2BD8u);
    RefsRaiseStatusInternal(a1, -1073741592, v57);
    JUMPOUT(0x1402BA506LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 261, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, 0, "FsCtrl.c", 0x2A04u);
    Status = -1073741528;
    goto LABEL_183;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", 0x2A0Fu);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 263, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225704LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592, 0, "FsCtrl.c", 0x2A35u);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", 0x2A50u);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 265, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225507LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x2A77u);
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
                  266,
                  WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
                  3221225507LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x2B71u);
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
                  267,
                  WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
                  2147483653LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-2147483643, 0, "FsCtrl.c", 0x2B75u);
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
  RefsReleasePagingResource(a1, v8);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, Status);
  return Status;
}

```

## disassembly

```asm
0x1402b9620  mov     r11, rsp
0x1402b9623  mov     [r11+8], rcx
0x1402b9627  push    rbx
0x1402b9628  push    rsi
0x1402b9629  push    rdi
0x1402b962a  push    r12
0x1402b962c  push    r13
0x1402b962e  push    r14
0x1402b9630  push    r15
0x1402b9632  sub     rsp, 130h
0x1402b9639  mov     r14, rdx
0x1402b963c  mov     r13, rcx
0x1402b963f  mov     rdi, [rdx+0B8h]
0x1402b9646  xor     esi, esi
0x1402b9648  mov     [r11+20h], rsi
0x1402b964c  mov     [r11+18h], rsi
0x1402b9650  mov     [r11-0D8h], rsi
0x1402b9657  mov     [r11+10h], rsi
0x1402b965b  mov     [rdx+38h], rsi
0x1402b965f  or      qword ptr [rcx+8], 1
0x1402b9664  mov     [rsp+168h+var_138], sil
0x1402b9669  lea     rax, [r11+10h]
0x1402b966d  mov     [rsp+168h+var_140], rax
0x1402b9672  lea     rax, [r11-0D8h]
0x1402b9679  mov     qword ptr [rsp+168h+Flags], rax
0x1402b967e  lea     r9, [r11+18h]
0x1402b9682  lea     r8, [r11+20h]
0x1402b9686  mov     rdx, [rdi+30h]
0x1402b968a  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402b968f  cmp     al, 2
0x1402b9691  jz      short loc_1402B96F9
0x1402b9693  mov     edi, 0C000000Dh
0x1402b9698  mov     r8d, edi; Status
0x1402b969b  mov     rdx, r14; Irp
0x1402b969e  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b96a1  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b96a6  lea     rax, WPP_GLOBAL_Control
0x1402b96ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b96b4  cmp     rcx, rax
0x1402b96b7  jz      short loc_1402B96E0
0x1402b96b9  test    dword ptr [rcx+2Ch], 100h
0x1402b96c0  jz      short loc_1402B96E0
0x1402b96c2  cmp     byte ptr [rcx+29h], 4
0x1402b96c6  jb      short loc_1402B96E0
0x1402b96c8  mov     edx, 102h
0x1402b96cd  mov     r9d, edi
0x1402b96d0  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b96d7  mov     rcx, [rcx+18h]
0x1402b96db  call    WPP_SF_d
0x1402b96e0  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b96e6  test    al, al
0x1402b96e8  jz      loc_1402B9789
0x1402b96ee  mov     r9d, 29D1h
0x1402b96f4  jmp     loc_1402B9779
0x1402b96f9  mov     [rsp+168h+var_126], sil
0x1402b96fe  mov     rax, [rsp+168h+arg_8]
0x1402b9706  test    rax, rax
0x1402b9709  jz      loc_1402B979F
0x1402b970f  mov     eax, [rax+4]
0x1402b9712  bt      eax, 0Dh
0x1402b9716  jnb     loc_1402B979F
0x1402b971c  mov     edi, 0C000000Dh
0x1402b9721  mov     r8d, edi; Status
0x1402b9724  mov     rdx, r14; Irp
0x1402b9727  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b972a  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b972f  lea     rax, WPP_GLOBAL_Control
0x1402b9736  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b973d  cmp     rcx, rax
0x1402b9740  jz      short loc_1402B9769
0x1402b9742  test    dword ptr [rcx+2Ch], 100h
0x1402b9749  jz      short loc_1402B9769
0x1402b974b  cmp     byte ptr [rcx+29h], 4
0x1402b974f  jb      short loc_1402B9769
0x1402b9751  mov     edx, 103h
0x1402b9756  mov     r9d, edi
0x1402b9759  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b9760  mov     rcx, [rcx+18h]
0x1402b9764  call    WPP_SF_d
0x1402b9769  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b976f  test    cl, cl
0x1402b9771  jz      short loc_1402B9789
0x1402b9773  mov     r9d, 29DEh; unsigned int
0x1402b9779  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b9780  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b9782  mov     ecx, edi; Status
0x1402b9784  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b9789  mov     eax, edi
0x1402b978b  add     rsp, 130h
0x1402b9792  pop     r15
0x1402b9794  pop     r14
0x1402b9796  pop     r13
0x1402b9798  pop     r12
0x1402b979a  pop     rdi
0x1402b979b  pop     rsi
0x1402b979c  pop     rbx
0x1402b979d  retn
0x1402b979f  mov     r8b, [r13+8]
0x1402b97a3  and     r8b, 1
0x1402b97a7  mov     rbx, [rsp+168h+var_D8]
0x1402b97af  mov     [rsp+168h+var_98], rbx
0x1402b97b7  mov     rdx, rbx
0x1402b97ba  mov     rcx, r13
0x1402b97bd  call    ?RefsAcquirePagingResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x1402b97c2  test    al, al
0x1402b97c4  jz      loc_1402BA3EB
0x1402b97ca  mov     [rsp+168h+var_126], 1
0x1402b97cf  mov     edx, [rbx+12Ch]
0x1402b97d5  and     edx, 4000h
0x1402b97db  mov     eax, edx
0x1402b97dd  neg     eax
0x1402b97df  sbb     ecx, ecx
0x1402b97e1  and     ecx, 0C000026Eh
0x1402b97e7  mov     [rsp+168h+Status], ecx
0x1402b97eb  test    edx, edx
0x1402b97ed  jnz     loc_1402BA3BF
0x1402b97f3  mov     rcx, [rsp+168h+arg_10]; struct _FCB *
0x1402b97fb  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402b9800  test    al, al
0x1402b9802  jnz     short loc_1402B9871
0x1402b9804  lea     rax, WPP_GLOBAL_Control
0x1402b980b  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b9812  cmp     rcx, rax
0x1402b9815  jz      short loc_1402B9841
0x1402b9817  mov     eax, [rcx+2Ch]
0x1402b981a  bt      eax, 8
0x1402b981e  jnb     short loc_1402B9841
0x1402b9820  cmp     byte ptr [rcx+29h], 4
0x1402b9824  jb      short loc_1402B9841
0x1402b9826  mov     edx, 105h
0x1402b982b  mov     r9d, 0C0000128h
0x1402b9831  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b9838  mov     rcx, [rcx+18h]
0x1402b983c  call    WPP_SF_d
0x1402b9841  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b9847  test    al, al
0x1402b9849  jz      short loc_1402B9864
0x1402b984b  mov     r9d, 2A04h; unsigned int
0x1402b9851  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b9858  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b985a  mov     ecx, 0C0000128h; Status
0x1402b985f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b9864  mov     [rsp+168h+Status], 0C0000128h
0x1402b986c  jmp     loc_1402BA3BF
0x1402b9871  cmp     dword ptr [rdi+10h], 10h
0x1402b9875  jnb     short loc_1402B98E6
0x1402b9877  lea     rax, WPP_GLOBAL_Control
0x1402b987e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b9885  cmp     rcx, rax
0x1402b9888  jz      short loc_1402B98B8
0x1402b988a  mov     eax, [rcx+2Ch]
0x1402b988d  bt      eax, 8
0x1402b9891  jnb     short loc_1402B98B8
0x1402b9893  cmp     byte ptr [rcx+29h], 4
0x1402b9897  jb      short loc_1402B98B8
0x1402b9899  mov     edx, 106h
0x1402b989e  mov     edi, 0C000000Dh
0x1402b98a3  mov     r9d, edi
0x1402b98a6  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b98ad  mov     rcx, [rcx+18h]
0x1402b98b1  call    WPP_SF_d
0x1402b98b6  jmp     short loc_1402B98BD
0x1402b98b8  mov     edi, 0C000000Dh
0x1402b98bd  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b98c3  test    al, al
0x1402b98c5  jz      short loc_1402B98DD
0x1402b98c7  mov     r9d, 2A0Fh; unsigned int
0x1402b98cd  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b98d4  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b98d6  mov     ecx, edi; Status
0x1402b98d8  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b98dd  mov     [rsp+168h+Status], edi
0x1402b98e1  jmp     loc_1402BA3BF
0x1402b98e6  mov     [rsp+168h+var_128], 1
0x1402b98eb  mov     r12d, [rdi+8]
0x1402b98ef  mov     dword ptr [rsp+168h+arg_10], r12d
0x1402b98f7  mov     [rsp+168h+var_F8], r12d
0x1402b98fc  mov     rcx, r14; struct _IRP *
0x1402b98ff  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402b9904  mov     rsi, rax
0x1402b9907  mov     [rsp+168h+var_120], rax
0x1402b990c  lea     r15, [rax-10h]
0x1402b9910  mov     [rsp+168h+var_118], r15
0x1402b9915  mov     rcx, [rdi+20h]; Address
0x1402b9919  cmp     byte ptr [r14+40h], 0
0x1402b991e  jz      short loc_1402B994F
0x1402b9920  mov     edx, [rdi+10h]; Length
0x1402b9923  mov     r8d, 4; Alignment
0x1402b9929  call    cs:__imp_ProbeForRead
0x1402b9930  nop     dword ptr [rax+rax+00h]
0x1402b9935  mov     edx, r12d; Length
0x1402b9938  mov     r8d, 4; Alignment
0x1402b993e  mov     rcx, rsi; Address
0x1402b9941  call    cs:__imp_ProbeForWrite
0x1402b9948  nop     dword ptr [rax+rax+00h]
0x1402b994d  jmp     short loc_1402B9971
0x1402b994f  lea     rax, [rcx+3]
0x1402b9953  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402b9957  cmp     rcx, rax
0x1402b995a  jnz     loc_1402BA352
0x1402b9960  lea     rax, [rsi+3]
0x1402b9964  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402b9968  cmp     rsi, rax
0x1402b996b  jnz     loc_1402BA352
0x1402b9971  mov     r12, [rdi+20h]
0x1402b9975  cmp     byte ptr [r14+40h], 0
0x1402b997a  jz      short loc_1402B9989
0x1402b997c  mov     rcx, r12
0x1402b997f  call    RtlReadULong64FromUser
0x1402b9984  mov     r12, rax
0x1402b9987  jmp     short loc_1402B998D
0x1402b9989  mov     r12, [r12]
0x1402b998d  mov     [rsp+168h+var_A0], r12
0x1402b9995  mov     rax, [rdi+20h]
0x1402b9999  xor     edi, edi
0x1402b999b  cmp     [r14+40h], dil
0x1402b999f  jz      short loc_1402B99AF
0x1402b99a1  lea     rcx, [rax+8]
0x1402b99a5  call    RtlReadULong64FromUser
0x1402b99aa  mov     rsi, rax
0x1402b99ad  jmp     short loc_1402B99B3
0x1402b99af  mov     rsi, [rax+8]
0x1402b99b3  mov     [rsp+168h+arg_8], rsi
0x1402b99bb  mov     [rsp+168h+var_128], dil
0x1402b99c0  test    rsi, rsi
0x1402b99c3  js      loc_1402BA2E3
0x1402b99c9  test    r12, r12
0x1402b99cc  js      loc_1402BA2E3
0x1402b99d2  mov     rax, 7FFFFFFFFFFFFFFFh
0x1402b99dc  sub     rax, r12
0x1402b99df  cmp     rsi, rax
0x1402b99e2  jg      loc_1402BA2E3
0x1402b99e8  test    rsi, rsi
0x1402b99eb  jz      short loc_1402B9A46
0x1402b99ed  mov     rdi, [rbx+30h]
0x1402b99f1  call    cs:__imp_KeEnterGuardedRegion
0x1402b99f8  nop     dword ptr [rax+rax+00h]
0x1402b99fd  mov     rcx, rdi; FastMutex
0x1402b9a00  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1402b9a07  nop     dword ptr [rax+rax+00h]
0x1402b9a0c  lock inc dword ptr [rbx+0ACh]
0x1402b9a13  mov     rax, [rbx+20h]
0x1402b9a17  cmp     r12, rax
0x1402b9a1a  jl      short loc_1402B9A71
0x1402b9a1c  mov     eax, [rbx+0ACh]
0x1402b9a22  inc     eax
0x1402b9a24  mov     [rbx+0ACh], eax
0x1402b9a2a  mov     rcx, [rbx+30h]; FastMutex
0x1402b9a2e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402b9a35  nop     dword ptr [rax+rax+00h]
0x1402b9a3a  call    cs:__imp_KeLeaveGuardedRegion
0x1402b9a41  nop     dword ptr [rax+rax+00h]
0x1402b9a46  mov     rsi, [rsp+168h+var_120]
0x1402b9a4b  sub     r15d, esi
0x1402b9a4e  lea     eax, [r15+10h]
0x1402b9a52  mov     [r14+38h], rax
0x1402b9a56  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402b9a59  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x1402b9a5e  xor     r8d, r8d
0x1402b9a61  mov     rdx, rbx
0x1402b9a64  mov     rcx, r13
0x1402b9a67  call    ?RefsFlushForWriteThrough@@YAXPEAU_IRP_CONTEXT@@PEAXW4REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS@@@Z; RefsFlushForWriteThrough(_IRP_CONTEXT *,void *,REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS)
0x1402b9a6c  jmp     loc_1402BA3BF
0x1402b9a71  sub     rax, r12
0x1402b9a74  cmp     rax, rsi
0x1402b9a77  cmovl   rsi, rax
0x1402b9a7b  mov     [rsp+168h+var_98], rsi
0x1402b9a83  mov     [rsp+168h+arg_8], rsi
0x1402b9a8b  mov     eax, [rbx+0ACh]
0x1402b9a91  inc     eax
0x1402b9a93  mov     [rbx+0ACh], eax
0x1402b9a99  mov     rcx, [rbx+30h]; FastMutex
0x1402b9a9d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402b9aa4  nop     dword ptr [rax+rax+00h]
0x1402b9aa9  call    cs:__imp_KeLeaveGuardedRegion
0x1402b9ab0  nop     dword ptr [rax+rax+00h]
0x1402b9ab5  xor     edi, edi
0x1402b9ab7  cmp     [rbx+100h], di
0x1402b9abe  jge     loc_1402BA223
0x1402b9ac4  mov     ecx, [rbx+98h]
0x1402b9aca  mov     eax, ecx
0x1402b9acc  and     eax, 8
0x1402b9acf  jz      short loc_1402B9ADA
0x1402b9ad1  and     ecx, 40h
0x1402b9ad4  jz      loc_1402BA223
0x1402b9ada  mov     [rsp+168h+var_B8], 0FFFFFFFFFFFFFFFFh
0x1402b9ae6  mov     r9, [rsp+168h+arg_18]
0x1402b9aee  movsx   ecx, byte ptr [r9+228h]
0x1402b9af6  mov     rax, r12
0x1402b9af9  sar     rax, cl
0x1402b9afc  mov     [rsp+168h+var_118], rax
0x1402b9b01  mov     [rsp+168h+var_B0], rax
0x1402b9b09  mov     r8d, [r9+110h]
0x1402b9b10  lea     rdx, [r12+rsi]
0x1402b9b14  mov     rax, 8000000000000000h
0x1402b9b1e  sub     rax, r8
0x1402b9b21  cmp     rdx, rax
0x1402b9b24  jge     short loc_1402B9B35
0x1402b9b26  lea     rdi, [r8-1]
0x1402b9b2a  add     rdi, r12
  ... truncated ...
```
