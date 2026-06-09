# RefsDuplicateExtents(_IRP_CONTEXT *,_IRP *,uchar)

- ea: `0x1400ec8a4`
- end: `0x1400ee62f`
- name: `?RefsDuplicateExtents@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@E@Z`
- size: `7563`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, unsigned __int8)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x1400298a0`
- `0x140036e90`
- `0x140037820`
- `0x140037e00`
- `0x14005dbd0`
- `0x140075c94`
- `0x140076060`
- `0x140076ad0`
- `0x14007cdb0`
- `0x1400801d0`
- `0x1400862c0`
- `0x140086690`
- `0x140089680`
- `0x14008ad80`
- `0x140095370`
- `0x140096ed0`
- `0x140097fe0`
- `0x14009c360`
- `0x1400cbfe4`
- `0x1400cf1bc`
- `0x1400d0fd8`
- `0x1400e8190`
- `0x1400ec8a4`
- `0x1400f192c`
- `0x1400f3d34`
- `0x1400f3f34`
- `0x140118ec4`
- `0x1401f3fc0`
- `0x14028debc`
- `0x1402deb6c`
- `0x140302e10`
- `0x140304230`
- `0x140306290`
- `0x14032cb40`
- `0x14033439c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400ee2f2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f669c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ee2f2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f669c`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400ed5f2`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400ed5f2`
- `ntoskrnl!IoCancelIrp` at `0x1400ed61b`
- `ntoskrnl!IoCancelIrp` at `0x1400ed61b`
- `ntoskrnl!IoIs32bitProcess` at `0x1400eca47`
- `ntoskrnl!IoIs32bitProcess` at `0x1400eca47`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ecf9b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ecf9b`
- `ntoskrnl!IoFileObjectType` at `0x1400ecf83`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400edcc1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400eded2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400edcc1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400eded2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400edcd0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400edee1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400edcd0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400edee1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400ed5be`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400ed5be`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400edd51`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400eddd9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400edf60`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400edd51`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400eddd9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400edf60`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edd5d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edde5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edf6c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edd5d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edde5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400edf6c`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed585`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed585`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400ed7f5`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400eddb3`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400ed7f5`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400eddb3`
- `HAL!KeQueryPerformanceCounter` at `0x1400ec985`
- `HAL!KeQueryPerformanceCounter` at `0x1400ee2b0`
- `HAL!KeQueryPerformanceCounter` at `0x1401f665c`
- `HAL!KeQueryPerformanceCounter` at `0x1400ec985`
- `HAL!KeQueryPerformanceCounter` at `0x1400ee2b0`
- `HAL!KeQueryPerformanceCounter` at `0x1401f665c`

## pseudocode

```c
__int64 __fastcall RefsDuplicateExtents(struct _IRP_CONTEXT *a1, struct _IRP *a2, char a3)
{
  unsigned int v6; // ebx
  LARGE_INTEGER PerformanceCounter; // rdi
  PFILE_OBJECT FileObject; // r13
  unsigned int v9; // r9d
  BOOLEAN v10; // al
  unsigned int Options; // ecx
  unsigned int v12; // r9d
  struct _IRP *v13; // rcx
  struct _IRP *MasterIrp; // rcx
  unsigned int v15; // r9d
  struct _DUPLICATE_EXTENTS_DATA_EX *v16; // rdx
  __int64 QuadPart; // r9
  struct _IRP *v18; // rcx
  __int64 v19; // r11
  int v20; // r8d
  __int64 v21; // r10
  LARGE_INTEGER SourceFileOffset; // r8
  LARGE_INTEGER TargetFileOffset; // rdx
  PMRX_NET_ROOT pNetRoot; // rcx
  __int64 v25; // rdx
  LARGE_INTEGER v26; // rsi
  char v27; // al
  LARGE_INTEGER v28; // rsi
  int v29; // ecx
  _QWORD *v30; // rcx
  char v31; // al
  IRP *v32; // rsi
  struct _IRP *v33; // rdx
  _QWORD *p_DataSectionObject; // rax
  __int64 v35; // r13
  struct _IRP *v36; // rdx
  struct _FCB *v37; // r10
  LARGE_INTEGER v38; // rsi
  char v39; // cl
  __int64 v40; // r8
  LARGE_INTEGER AllocationSize; // rdx
  unsigned int v42; // r8d
  struct _CC_FILE_SIZES *v43; // rdx
  PMRX_NET_ROOT v44; // rcx
  PVOID Context; // r8
  __int64 v46; // r11
  PVOID v47; // r9
  struct _MRX_SRV_CALL_ *v48; // rax
  struct _DUPLICATE_EXTENTS_DATA_EX *v49; // r11
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // r8
  __int64 v53; // r9
  struct _IRP *v54; // rdx
  __int64 v55; // r8
  char v56; // cl
  __int64 v57; // rdx
  __int64 v58; // rsi
  unsigned int v59; // r8d
  __int64 v60; // r13
  unsigned int v61; // r8d
  int v62; // esi
  struct _FAST_MUTEX *FastMutex; // rsi
  char v64; // cl
  ULONGLONG ActualAllocationLength; // rcx
  struct _FAST_MUTEX *v66; // rsi
  __int64 v67; // r13
  struct _FCB *v68; // rdx
  unsigned int v69; // ebx
  unsigned int v70; // r8d
  unsigned int v71; // r8d
  LARGE_INTEGER v72; // r13
  int v73; // esi
  LARGE_INTEGER FileSize; // rdx
  struct _IRP *v75; // rsi
  __int64 v76; // rax
  unsigned __int8 Object; // [rsp+58h] [rbp-248h]
  unsigned __int8 Objecta; // [rsp+58h] [rbp-248h]
  int v80; // [rsp+68h] [rbp-238h]
  int Status; // [rsp+78h] [rbp-228h]
  struct _FCB *v82; // [rsp+80h] [rbp-220h] BYREF
  struct _DUPLICATE_EXTENTS_DATA_EX *v83; // [rsp+88h] [rbp-218h] BYREF
  struct _IRP *v84; // [rsp+90h] [rbp-210h] BYREF
  char v85; // [rsp+98h] [rbp-208h] BYREF
  struct _VCB *v86; // [rsp+A0h] [rbp-200h] BYREF
  PIRP Irp; // [rsp+A8h] [rbp-1F8h]
  struct _FCB *v88; // [rsp+B0h] [rbp-1F0h] BYREF
  unsigned __int8 v89[8]; // [rsp+B8h] [rbp-1E8h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+C0h] [rbp-1E0h]
  __int16 v91; // [rsp+C8h] [rbp-1D8h]
  LARGE_INTEGER v92; // [rsp+D0h] [rbp-1D0h] BYREF
  PVOID v93; // [rsp+D8h] [rbp-1C8h] BYREF
  __int64 v94[2]; // [rsp+E0h] [rbp-1C0h] BYREF
  struct _FCB *v95; // [rsp+F0h] [rbp-1B0h]
  _QWORD v96[3]; // [rsp+F8h] [rbp-1A8h] BYREF
  __int128 v97; // [rsp+110h] [rbp-190h] BYREF
  __int128 v98; // [rsp+120h] [rbp-180h]
  __int128 v99; // [rsp+130h] [rbp-170h]
  struct _FCB *v100; // [rsp+150h] [rbp-150h] BYREF
  __int128 v101; // [rsp+158h] [rbp-148h] BYREF
  __int128 v102; // [rsp+168h] [rbp-138h] BYREF
  __int64 v103; // [rsp+178h] [rbp-128h] BYREF
  __int64 v104; // [rsp+180h] [rbp-120h]
  _BYTE v105[224]; // [rsp+188h] [rbp-118h] BYREF
  struct _RANGE_LOCK_STATE *v106; // [rsp+268h] [rbp-38h]

  Irp = a2;
  v96[2] = a1;
  *(_QWORD *)v105 = a2;
  v86 = 0;
  v88 = 0;
  v82 = 0;
  v94[0] = 0;
  v93 = 0;
  v96[0] = 0;
  v84 = 0;
  *(_QWORD *)v89 = 0;
  v83 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  memset(&v105[56], 0, 24);
  v92.QuadPart = 0;
  v102 = 0;
  v101 = 0;
  v6 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v96[1] = PerformanceCounter.QuadPart;
  *((_QWORD *)a1 + 1) |= 1uLL;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, FileObject, &v86, &v88, &v82, v94, 1) != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 13873;
LABEL_272:
    RefsStatusDebug(-1073741811, 0, "DevIoSup.c", v9);
LABEL_273:
    Status = -1073741811;
    goto LABEL_274;
  }
  v10 = IoIs32bitProcess(Irp);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v10 )
  {
    if ( a3 )
    {
      if ( Options < 0x28 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            130,
            WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
            3221225507LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_18;
        v12 = 13905;
        goto LABEL_17;
      }
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      if ( *(_DWORD *)&MasterIrp->Type != 40 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            131,
            WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
            3221225659LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_35;
        v15 = 13912;
        goto LABEL_34;
      }
      *(_QWORD *)&v97 = 48;
      *((_QWORD *)&v97 + 1) = *(int *)(&MasterIrp->Size + 1);
      v98 = *(_OWORD *)&MasterIrp->MdlAddress;
      *(_QWORD *)&v99 = MasterIrp->AssociatedIrp.MasterIrp;
      DWORD2(v99) = MasterIrp->ThreadListEntry.Flink;
    }
    else
    {
      if ( Options < 0x20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            129,
            WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
            3221225507LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_18;
        v12 = 13885;
LABEL_17:
        RefsStatusDebug(-1073741789, 0, "DevIoSup.c", v12);
LABEL_18:
        Status = -1073741789;
        goto LABEL_274;
      }
      v13 = Irp->AssociatedIrp.MasterIrp;
      *(_QWORD *)&v97 = 48;
      *((_QWORD *)&v97 + 1) = *(int *)&v13->Type;
      v98 = *(_OWORD *)&v13->MdlAddress;
      *(_QWORD *)&v99 = v13->AssociatedIrp.MasterIrp;
      DWORD2(v99) = 0;
    }
    v16 = (struct _DUPLICATE_EXTENTS_DATA_EX *)&v97;
    v83 = (struct _DUPLICATE_EXTENTS_DATA_EX *)&v97;
  }
  else if ( a3 )
  {
    if ( Options < 0x30 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_18;
      v12 = 13953;
      goto LABEL_17;
    }
    v16 = (struct _DUPLICATE_EXTENTS_DATA_EX *)Irp->AssociatedIrp.MasterIrp;
    v83 = v16;
    if ( v16->Size != 48 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_35;
      v15 = 13960;
      goto LABEL_34;
    }
  }
  else
  {
    if ( Options < 0x20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_18;
      v12 = 13935;
      goto LABEL_17;
    }
    v18 = Irp->AssociatedIrp.MasterIrp;
    *(_QWORD *)&v97 = 48;
    *((_QWORD *)&v97 + 1) = *(_QWORD *)&v18->Type;
    v98 = *(_OWORD *)&v18->MdlAddress;
    *(_QWORD *)&v99 = v18->AssociatedIrp.MasterIrp;
    DWORD2(v99) = 0;
    v83 = (struct _DUPLICATE_EXTENTS_DATA_EX *)&v97;
    v16 = (struct _DUPLICATE_EXTENTS_DATA_EX *)&v97;
  }
  QuadPart = v16->ByteCount.QuadPart;
  if ( !QuadPart )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 0);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(0, 0, "DevIoSup.c", 0x368Fu);
    Status = 0;
    goto LABEL_274;
  }
  v19 = v16->TargetFileOffset.QuadPart;
  v94[0] = v19;
  if ( v19 < 0 || v16->SourceFileOffset.QuadPart < 0 || QuadPart < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 13979;
    goto LABEL_272;
  }
  v20 = *((_DWORD *)v86 + 136);
  if ( (((unsigned int)v19 | v16->SourceFileOffset.LowPart) & v20) != 0 || (v20 & v16->ByteCount.LowPart) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225659LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_35;
    v15 = 13991;
    goto LABEL_34;
  }
  if ( !a3 && v16->ByteCount.HighPart || v16->ByteCount.HighPart >= 0x2000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14005;
    goto LABEL_272;
  }
  Status = RtlLongLongAdd(v19, QuadPart, &v92);
  if ( Status < 0 )
    goto LABEL_274;
  Status = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RtlLongLongAdd)(
             (LARGE_INTEGER)v83->SourceFileOffset.QuadPart,
             (LARGE_INTEGER)v83->ByteCount.QuadPart,
             &v100);
  if ( Status < 0 )
    goto LABEL_274;
  Status = ObReferenceObjectByHandle(
             v83->FileHandle,
             0x81u,
             (POBJECT_TYPE)IoFileObjectType,
             *(_BYTE *)(v21 + 64),
             &v93,
             0);
  if ( Status < 0 )
    goto LABEL_274;
  if ( FileObject->DeviceObject != (PDEVICE_OBJECT)*((_QWORD *)v93 + 1) || FileObject->Vpb != (PVPB)*((_QWORD *)v93 + 2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14052;
    goto LABEL_272;
  }
  LOBYTE(v80) = 0;
  if ( (unsigned __int8)RefsDecodeFileObject(0, v93, &v86, v96, &v84, v89, v80) != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14058;
    goto LABEL_272;
  }
  if ( v84 == (struct _IRP *)v82 )
  {
    if ( (TargetFileOffset = v83->TargetFileOffset,
          SourceFileOffset = v83->SourceFileOffset,
          SourceFileOffset.QuadPart == TargetFileOffset.QuadPart)
      || SourceFileOffset.QuadPart < TargetFileOffset.QuadPart
      && SourceFileOffset.QuadPart + v83->ByteCount.QuadPart > TargetFileOffset.QuadPart
      || TargetFileOffset.QuadPart < SourceFileOffset.QuadPart
      && TargetFileOffset.QuadPart + v83->ByteCount.QuadPart > SourceFileOffset.QuadPart )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_35;
      v15 = 14075;
LABEL_34:
      RefsStatusDebug(-1073741637, 0, "DevIoSup.c", v15);
LABEL_35:
      Status = -1073741637;
      goto LABEL_274;
    }
  }
  if ( (*((_DWORD *)v86 + 6) & 0x2000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids, 3221225634LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741662, 0, "DevIoSup.c", 0x3700u);
    Status = -1073741662;
    goto LABEL_274;
  }
  if ( (*(unsigned __int8 *)(*((_QWORD *)&v82->1 + 18) + 793LL)
      | (*(unsigned __int8 *)(*((_QWORD *)&v82->1 + 18) + 792LL) << 8)) >= 0x30Bu )
  {
    RefsConvertToNonResident(a1, (struct _SCB *)v84);
    RefsConvertToNonResident(a1, (struct _SCB *)v82);
  }
  pNetRoot = v88->pNetRoot;
  v25 = *(_QWORD *)(v96[0] + 88LL);
  if ( pNetRoot[2].Context == *(PVOID *)(v25 + 256) && pNetRoot[2].pSrvCall == *(PMRX_SRV_CALL *)(v25 + 248) )
  {
    if ( FileObject->SectionObjectPointer->DataSectionObject )
      goto LABEL_129;
    v26 = v92;
    if ( v92.QuadPart > v82->LastWriteTime.QuadPart
      || (*((_DWORD *)&v82->1 + 38) & 0x10) != 0
      && (*(_QWORD *)(v82->ActualAllocationLength + 8) & 0x40000100LL) == 0x40000000 )
    {
      goto LABEL_129;
    }
    v100 = v82;
    LOBYTE(SourceFileOffset.LowPart) = 1;
    v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsAcquirePagingResourceShared)(
            a1,
            v82,
            (LARGE_INTEGER)SourceFileOffset.QuadPart);
    v6 = 2 * (v27 & 1);
    if ( (v27 & 1) != 0
      && (FileObject->SectionObjectPointer->DataSectionObject
       || v26.QuadPart > v82->LastWriteTime.QuadPart
       || (*((_DWORD *)&v82->1 + 38) & 0x10) != 0 && _FCB::HasPurgeableEAs((_FCB *)v82->ActualAllocationLength)) )
    {
      *(_QWORD *)v89 = v82;
      RefsReleasePagingResource(a1, v82);
LABEL_129:
      RefsAcquireExclusivePagingIo(a1, v88, 1u);
      v6 = 6;
    }
  }
  else
  {
    do
    {
      if ( FileObject->SectionObjectPointer->DataSectionObject
        || (v28 = v92, v92.QuadPart > v82->LastWriteTime.QuadPart)
        || (*((_DWORD *)&v82->1 + 38) & 0x10) != 0
        && (*(_QWORD *)(v82->ActualAllocationLength + 8) & 0x40000100LL) == 0x40000000 )
      {
        RefsAcquireExclusivePagingIo(a1, v88, 1u);
        v6 = (v6 | 2) ^ (((unsigned __int8)v6 | 2) ^ (unsigned __int8)(2 * (v6 | 2))) & 4;
      }
      else
      {
        v95 = v82;
        LOBYTE(SourceFileOffset.LowPart) = 1;
        v29 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsAcquirePagingResourceShared)(
                a1,
                v82,
                (LARGE_INTEGER)SourceFileOffset.QuadPart)
            & 1;
        v6 = (2 * v29) & 0xFFFFFFFB | v6 & 0xFFFFFFF9;
        if ( v29
          && (FileObject->SectionObjectPointer->DataSectionObject
           || v28.QuadPart > v82->LastWriteTime.QuadPart
           || (*((_DWORD *)&v82->1 + 38) & 0x10) != 0 && _FCB::HasPurgeableEAs((_FCB *)v82->ActualAllocationLength)) )
        {
          *(_QWORD *)&v105[128] = v82;
          RefsReleasePagingResource(a1, v82);
          v6 &= ~2u;
          if ( (v6 & 1) != 0 )
          {
            MsReleaseFastResource((char *)v86 + 1312);
            v6 &= ~1u;
          }
        }
      }
      if ( (v6 & 2) != 0 )
      {
        v30 = (_QWORD *)*((_QWORD *)v93 + 5);
        LOBYTE(SourceFileOffset.LowPart) = v6 & 1;
        if ( *v30 )
        {
          *(_QWORD *)&v105[160] = v84;
          v31 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsAcquirePagingResourceExclusive)(
                  v30,
                  v84,
                  (LARGE_INTEGER)SourceFileOffset.QuadPart);
        }
        else
        {
          *(_QWORD *)&v105[168] = v84;
          v31 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsAcquirePagingResourceShared)(
                  a1,
                  v84,
                  (LARGE_INTEGER)SourceFileOffset.QuadPart);
        }
        v6 ^= ((unsigned __int8)v6 ^ (unsigned __int8)(32 * v31)) & 0x20;
      }
      if ( ((v6 >> 1) & 1) == 0 || (v6 & 0x20) == 0 )
      {
        if ( ((v6 >> 1) & 1) != 0 )
        {
          if ( (v6 & 4) != 0 )
          {
            *(_QWORD *)&v105[176] = v88;
            RefsReleasePagingResource(a1, v88);
            *((_QWORD *)a1 + 7) = 0;
          }
          else
          {
            *(_QWORD *)&v105[184] = v82;
            RefsReleasePagingResource(a1, v82);
          }
          v6 &= 0xFFFFFFF9;
        }
        if ( (v6 & 0x20) != 0 )
        {
          *(_QWORD *)&v105[136] = v84;
          RefsReleasePagingResource(a1, v84);
          v6 &= ~0x20u;
        }
        if ( (v6 & 1) == 0 )
          v6 = v6 & 0xFFFFFFFE | RefsAcquireExclusiveVcb(a1, v86, 1u) & 1;
      }
    }
    while ( (v6 & 0x22) != 0x22 );
  }
  *(_QWORD *)&v105[80] = &v82;
  *(_QWORD *)&v105[88] = &v84;
  *(_QWORD *)&v105[96] = &v86;
  *(_QWORD *)&v105[104] = &v88;
  *(_QWORD *)&v105[112] = v96;
  *(_QWORD *)&v105[120] = &v83;
  Status = RefsDuplicateExtents_::_4_::_lambda_1_::operator()(&v105[80]);
  if ( Status < 0 )
    goto LABEL_274;
  KeInitializeEvent((PRKEVENT)&v105[56], NotificationEvent, 0);
  v32 = Irp;
  Status = FsRtlCheckOplockEx((POPLOCK)&v82->pNetRoot, Irp, 0, &v105[56], RefspOplockCompletion, 0);
  if ( Status == 259 )
  {
    CurrentStackLocation->Control &= ~1u;
    Status = FsRtlCancellableWaitForSingleObject(&v105[56], 0, v32);
    if ( Status == -1073741536 || Status == -1073741749 )
    {
      IoCancelIrp(v32);
      goto LABEL_274;
    }
  }
  if ( Status >= 0 )
  {
    p_DataSectionObject = &FileObject->SectionObjectPointer->DataSectionObject;
    v35 = v94[0];
    if ( *p_DataSectionObject )
      RefsCacheCoherencyFlush(a1, v33, (struct _SCB *)v82, v94[0], v83->ByteCount.QuadPart, 1u, 0);
    v36 = v84;
    if ( v84[1].ThreadListEntry.Blink->Blink )
    {
      RefsCacheCoherencyFlush(
        a1,
        v84,
        (struct _SCB *)v84,
        v83->SourceFileOffset.QuadPart,
        v83->ByteCount.QuadPart,
        0,
        0);
      v36 = v84;
    }
    v37 = v82;
    v38 = v92;
    if ( v92.QuadPart > v82->Header.AllocationSize.QuadPart )
    {
      RefsAcquireExclusiveScb(a1, v82, 0);
      v37 = v82;
      if ( v35 > v82->Header.AllocationSize.QuadPart )
      {
        RefsSnapshotScb(a1, v82, 0);
        if ( SLOWORD(v82->FcbTableEntry.HashLinks.Blink) >= 0 )
        {
          v103 = 0;
          v104 = 0;
          RefsBindMinstoreTransaction(a1);
          v39 = *((_BYTE *)v86 + 552);
          v40 = *((unsigned int *)v86 + 136);
          AllocationSize = v82->Header.AllocationSize;
          v103 = (AllocationSize.QuadPart + v40) >> v39;
          v104 = (v35 + v40 - AllocationSize.QuadPart) >> v39;
          Status = MsAddAllocation(*((_QWORD *)a1 + 3), v82->LastChangeTime.QuadPart, (unsigned int)&v103, 0x2000, 0);
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                143,
                WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x3878u);
            RefsRaiseStatusInternal(a1, Status, v42);
LABEL_296:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                144,
                WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
                3221225760LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741536, a1, "DevIoSup.c", 0x3967u);
            RefsRaiseStatusInternal(a1, -1073741536, v59);
LABEL_303:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                145,
                WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x3975u);
            RefsRaiseStatusInternal(a1, Status, v61);
LABEL_310:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                146,
                WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
                3221225688LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741608, a1, "DevIoSup.c", 0x39D9u);
            RefsRaiseStatusInternal(a1, -1073741608, v70);
LABEL_317:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                147,
                WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x39E6u);
            RefsRaiseStatusInternal(a1, Status, v71);
            __debugbreak();
            JUMPOUT(0x1400EE62FLL);
          }
        }
        RefsWriteFileSizes(a1, (struct _SCB *)v82, 0, 1u, Object);
        v82->Header.AllocationSize.QuadPart = v35;
        v43 = (struct _CC_FILE_SIZES *)v82;
        v35 = v94[0];
        if ( v82->Header.NodeTypeCode == 2053 )
        {
          v82->LastWriteTime.QuadPart = v94[0];
          v43 = (struct _CC_FILE_SIZES *)v82;
        }
        if ( *(_QWORD *)(v43[10].FileSize.QuadPart + 16) )
        {
          CurrentStackLocation = (struct _IO_STACK_LOCATION *)(v43[10].FileSize.QuadPart + 8);
          CcSetFileSizesEx((PFILE_OBJECT)&v85, v43 + 1);
        }
        RefsCheckpointCurrentTransaction(a1);
        RefsReleaseFcb(a1, (struct _FCB *)v82->ActualAllocationLength);
        v37 = v82;
      }
      v6 |= 0x10u;
      v36 = v84;
    }
    if ( v38.QuadPart > v37->LastWriteTime.QuadPart )
    {
      v37->LastWriteTime = v38;
      v37 = v82;
      v36 = v84;
    }
    if ( (v6 & 1) != 0 )
    {
      MsReleaseFastResource((char *)v86 + 1312);
      v6 &= ~1u;
      v37 = v82;
      v36 = v84;
    }
    v44 = v88->pNetRoot;
    Context = v44[2].Context;
    v46 = *(_QWORD *)(v96[0] + 88LL);
    v47 = *(PVOID *)(v46 + 256);
    if ( Context <= v47 )
    {
      if ( Context != v47 )
        goto LABEL_199;
      v48 = *(struct _MRX_SRV_CALL_ **)(v46 + 248);
      if ( v44[2].pSrvCall <= v48 )
      {
        if ( Context == v47 && v44[2].pSrvCall == v48 )
        {
          v49 = v83;
          v50 = v83->TargetFileOffset.QuadPart;
          if ( v83->SourceFileOffset.QuadPart < v50 && v37 == (struct _FCB *)v36 || v36 < (struct _IRP *)v37 )
          {
            if ( _bittest16((const signed __int16 *)&v36[1].IoStatus, 0xDu)
              && (*(_DWORD *)(*((_QWORD *)v36->Tail.Overlay.DriverContext[3] + 14) + 3396LL) & 0x800000) != 0 )
            {
              RefsSetDuplicateInProgress(
                a1,
                (struct _SCB *)v36,
                v83->SourceFileOffset.QuadPart,
                v83->ByteCount.QuadPart);
              v6 |= 0x80u;
              v37 = v82;
              v36 = v84;
              v49 = v83;
            }
            if ( (*((_DWORD *)&v36->Tail.CompletionKey + 8) & 0x80u) == 0 )
            {
              RefsAcquireRangeLock(
                a1,
                (struct _SCB_NONPAGED *)v36[1].ThreadListEntry.Blink,
                v49->SourceFileOffset.QuadPart,
                v49->ByteCount.QuadPart,
                0,
                (struct _RANGE_LOCK_STATE *)&v101);
              v6 |= 0x40u;
              v37 = v82;
              v49 = v83;
            }
            v51 = v49->ByteCount.QuadPart;
            v52 = v49->TargetFileOffset.QuadPart;
LABEL_197:
            RefsAcquireRangeLock(
              a1,
              (struct _SCB_NONPAGED *)v37->FcbTableEntry.HashLinks.Flink,
              v52,
              v51,
              1,
              (struct _RANGE_LOCK_STATE *)&v102);
            v6 |= 8u;
            goto LABEL_211;
          }
          v53 = v83->ByteCount.QuadPart;
LABEL_206:
          RefsAcquireRangeLock(
            a1,
            (struct _SCB_NONPAGED *)v37->FcbTableEntry.HashLinks.Flink,
            v50,
            v53,
            1,
            (struct _RANGE_LOCK_STATE *)&v102);
          v6 |= 8u;
          v54 = v84;
          if ( _bittest16((const signed __int16 *)&v84[1].IoStatus, 0xDu)
            && (*(_DWORD *)(*((_QWORD *)v84->Tail.Overlay.DriverContext[3] + 14) + 3396LL) & 0x800000) != 0 )
          {
            RefsSetDuplicateInProgress(a1, (struct _SCB *)v84, v83->SourceFileOffset.QuadPart, v83->ByteCount.QuadPart);
            v6 |= 0x80u;
            v54 = v84;
          }
          if ( (*((_DWORD *)&v54->Tail.CompletionKey + 8) & 0x80u) == 0 )
          {
            RefsAcquireRangeLock(
              a1,
              (struct _SCB_NONPAGED *)v54[1].ThreadListEntry.Blink,
              v83->SourceFileOffset.QuadPart,
              v83->ByteCount.QuadPart,
              0,
              (struct _RANGE_LOCK_STATE *)&v101);
            v6 |= 0x40u;
          }
LABEL_211:
          if ( v82->Header.FileSize.QuadPart > v35 )
            RefsPostUsnChange(a1, v82, 1u, 0);
          v55 = *((_QWORD *)a1 + 18);
          v56 = *((_BYTE *)v86 + 552);
          v57 = *((unsigned int *)v86 + 136);
          v58 = ((v57 + v83->ByteCount.QuadPart) >> v56) - v55;
          *(_QWORD *)&v105[32] = v58;
          CurrentStackLocation = (struct _IO_STACK_LOCATION *)(v55 + ((v57 + v83->SourceFileOffset.QuadPart) >> v56));
          *(_QWORD *)&v105[48] = CurrentStackLocation;
          *(_QWORD *)v89 = v55 + ((v57 + v83->TargetFileOffset.QuadPart) >> v56);
          *(_QWORD *)&v105[24] = *(_QWORD *)v89;
          v91 = LOWORD(v82->FcbTableEntry.HashLinks.Blink) >> 15;
          while ( v58 > 0 )
          {
            v85 = 0;
            RefsBindMinstoreTransaction(a1);
            if ( Irp->Cancel )
              goto LABEL_296;
            v60 = (*(unsigned int *)(*((_QWORD *)&v82->1 + 18) + 544LL) + 0x40000000LL) >> *(_BYTE *)(*((_QWORD *)&v82->1 + 18) + 552LL);
            if ( v58 < v60 )
              v60 = v58;
            Status = MsDuplicateExtents(
                       *((struct CmsTransactionContext **)a1 + 3),
                       (CmsStream *)v82->LastChangeTime.QuadPart,
                       v89[0],
                       v60,
                       v91);
            if ( Status < 0 )
              goto LABEL_303;
            CurrentStackLocation = (struct _IO_STACK_LOCATION *)((char *)CurrentStackLocation + v60);
            *(_QWORD *)&v105[48] = CurrentStackLocation;
            *(_QWORD *)v89 += v60;
            *(_QWORD *)&v105[24] = *(_QWORD *)v89;
            v100 = (struct _FCB *)(v58 - v60);
            *(_QWORD *)&v105[32] = v58 - v60;
            v62 = (v6 >> 4) & 1;
            LODWORD(v95) = v62;
            if ( v62 )
            {
              FastMutex = v82->Header.FastMutex;
              KeEnterGuardedRegion();
              ExAcquireFastMutexUnsafe(FastMutex);
              _InterlockedAdd((volatile signed __int32 *)&v82->1 + 43, 1u);
              *(_OWORD *)&v105[192] = *(_OWORD *)&v82->spacer.AllocationSize.LowPart;
              *(_QWORD *)&v105[208] = v82->Header.ValidDataLength.QuadPart;
              v64 = *((_BYTE *)v86 + 552);
              if ( *(__int64 *)&v105[192] >= *(_QWORD *)v89 << v64 )
              {
                ++*((_DWORD *)&v82->1 + 43);
                ExReleaseFastMutexUnsafe(v82->Header.FastMutex);
                KeLeaveGuardedRegion();
              }
              else
              {
                *(_QWORD *)&v105[192] = *(_QWORD *)v89 << v64;
                v85 = 1;
                ++*((_DWORD *)&v82->1 + 43);
                ExReleaseFastMutexUnsafe(v82->Header.FastMutex);
                KeLeaveGuardedRegion();
                RefsWriteFileSizes(a1, (struct _SCB *)v82, (struct _CC_FILE_SIZES *)&v105[192], 1u, Objecta);
                if ( v82->FcbTableEntry.HashLinks.Flink[1].Flink )
                {
                  *(_QWORD *)&v105[40] = &v82->FcbTableEntry.HashLinks.Flink->Blink;
                  CcSetFileSizesEx((PFILE_OBJECT)v105, (PCC_FILE_SIZES)&v105[192]);
                }
              }
              v62 = (int)v95;
            }
            if ( SLOWORD(v82->FcbTableEntry.HashLinks.Blink) < 0 && (*((_DWORD *)&v82->1 + 38) & 0x10) != 0 )
            {
              memset(&v105[192], 0, 32);
              v106 = 0;
              RefsGetStreamSummary(a1, (struct _SCB *)v82, (struct _SmsStreamSummary *)&v105[192]);
              ActualAllocationLength = v82->ActualAllocationLength;
              if ( *(struct _RANGE_LOCK_STATE **)(ActualAllocationLength + 136) != v106 )
              {
                *(_QWORD *)(ActualAllocationLength + 136) = v106;
                *(_DWORD *)(v82->ActualAllocationLength + 172) |= 0x40000000u;
                *(_QWORD *)(v82->ActualAllocationLength + 8) |= 0x10uLL;
              }
            }
            RefsCheckpointCurrentTransaction(a1);
            if ( (v83->Flags & 1) == 0 || (*((_DWORD *)&v84->Tail.CompletionKey + 8) & 0x80u) != 0 )
              *((_QWORD *)a1 + 18) += v60;
            if ( v62 && v85 )
            {
              v66 = v82->Header.FastMutex;
              KeEnterGuardedRegion();
              ExAcquireFastMutexUnsafe(v66);
              _InterlockedAdd((volatile signed __int32 *)&v82->1 + 43, 1u);
              v67 = *(_QWORD *)v89;
              v82->Header.AllocationSize.QuadPart = *(_QWORD *)v89 << *((_BYTE *)v86 + 552);
              v68 = v82;
              if ( v82->Header.NodeTypeCode == 2053 )
              {
                v82->LastWriteTime.QuadPart = v67 << *((_BYTE *)v86 + 552);
                v68 = v82;
              }
              ++*((_DWORD *)&v68->1 + 43);
              ExReleaseFastMutexUnsafe(v82->Header.FastMutex);
              KeLeaveGuardedRegion();
            }
            v58 = (__int64)v100;
            if ( (__int64)v100 > 0 && (*((_DWORD *)&v84->Tail.CompletionKey + 8) & 0x80u) != 0 )
            {
              *(_QWORD *)&v105[144] = v84;
              RefsReleasePagingResource(a1, v84);
              v69 = v6 & 0xFFFFFFDF;
              *(_QWORD *)&v105[152] = v84;
              if ( !(unsigned __int8)RefsAcquirePagingResourceShared(a1, v84, 0) )
                goto LABEL_310;
              v6 = v69 | 0x20;
              Status = RefsDuplicateExtents_::_4_::_lambda_1_::operator()(&v105[80]);
              if ( Status < 0 )
                goto LABEL_317;
            }
          }
          v72 = v92;
          if ( v82->Header.FileSize.QuadPart < v92.QuadPart )
          {
            RefsReleaseRangeLock(
              (struct _SCB_NONPAGED *)v82->FcbTableEntry.HashLinks.Flink,
              v83->TargetFileOffset.QuadPart,
              v83->ByteCount.QuadPart,
              1,
              (struct _RANGE_LOCK_STATE *)&v102);
            v6 &= ~8u;
            if ( (v6 & 0x40) != 0 )
            {
              RefsReleaseRangeLock(
                (struct _SCB_NONPAGED *)v84[1].ThreadListEntry.Blink,
                v83->SourceFileOffset.QuadPart,
                v83->ByteCount.QuadPart,
                0,
                (struct _RANGE_LOCK_STATE *)&v101);
              v6 &= ~0x40u;
            }
            v73 = (v6 >> 2) & 1;
            if ( !v73 )
              RefsAcquireEofLockForRead(a1, (struct _SCB *)v82);
            FileSize = v82->Header.FileSize;
            if ( FileSize.QuadPart < v72.QuadPart && FileSize.QuadPart > v94[0] )
            {
              *(_OWORD *)v94 = 0;
              if ( !v73 )
              {
                RefsAcquireRangeLock(
                  a1,
                  (struct _SCB_NONPAGED *)v82->FcbTableEntry.HashLinks.Flink,
                  FileSize.QuadPart & *((int *)v86 + 137),
                  1LL << *((_BYTE *)v86 + 552),
                  1,
                  (struct _RANGE_LOCK_STATE *)v94);
                *((_DWORD *)a1 + 1) |= 0x40u;
              }
              RefsZeroEndOfClusterStraddlingEof(a1, (struct _SCB *)v82, Irp);
              RefsCheckpointCurrentTransaction(a1);
              if ( !v73 )
              {
                RefsReleaseRangeLock(
                  (struct _SCB_NONPAGED *)v82->FcbTableEntry.HashLinks.Flink,
                  v82->Header.FileSize.QuadPart & *((int *)v86 + 137),
                  1LL << *((_BYTE *)v86 + 552),
                  1,
                  (struct _RANGE_LOCK_STATE *)v94);
                *((_DWORD *)a1 + 1) &= ~0x40u;
              }
            }
          }
          RefsFlushForWriteThrough(a1, v82, 0);
          goto LABEL_274;
        }
LABEL_199:
        if ( _bittest16((const signed __int16 *)&v36[1].IoStatus, 0xDu)
          && (*(_DWORD *)(*((_QWORD *)v36->Tail.Overlay.DriverContext[3] + 14) + 3396LL) & 0x800000) != 0 )
        {
          RefsSetDuplicateInProgress(a1, (struct _SCB *)v36, v83->SourceFileOffset.QuadPart, v83->ByteCount.QuadPart);
          v6 |= 0x80u;
          v37 = v82;
          v36 = v84;
        }
        if ( (*((_DWORD *)&v36->Tail.CompletionKey + 8) & 0x80u) == 0 )
        {
          RefsAcquireRangeLock(
            a1,
            (struct _SCB_NONPAGED *)v36[1].ThreadListEntry.Blink,
            v83->SourceFileOffset.QuadPart,
            v83->ByteCount.QuadPart,
            0,
            (struct _RANGE_LOCK_STATE *)&v101);
          v6 |= 0x40u;
          v37 = v82;
        }
        v51 = v83->ByteCount.QuadPart;
        v52 = v83->TargetFileOffset.QuadPart;
        goto LABEL_197;
      }
    }
    v53 = v83->ByteCount.QuadPart;
    v50 = v83->TargetFileOffset.QuadPart;
    goto LABEL_206;
  }
LABEL_274:
  v75 = Irp;
  v76 = *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart;
  RefsTelemetryDuplicateExtentsToFile(v86, (struct _SCB *)v82, (struct _SCB *)v84, v83, v76, Status);
  if ( v93 )
    ObfDereferenceObject(v93);
  if ( (v6 & 8) != 0 )
    RefsReleaseRangeLock(
      (struct _SCB_NONPAGED *)v82->FcbTableEntry.HashLinks.Flink,
      v83->TargetFileOffset.QuadPart,
      v83->ByteCount.QuadPart,
      1,
      (struct _RANGE_LOCK_STATE *)&v102);
  if ( (v6 & 0x80u) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)&v84[1].Tail.CompletionKey + 5);
  if ( (v6 & 0x40) != 0 )
    RefsReleaseRangeLock(
      (struct _SCB_NONPAGED *)v84[1].ThreadListEntry.Blink,
      v83->SourceFileOffset.QuadPart,
      v83->ByteCount.QuadPart,
      0,
      (struct _RANGE_LOCK_STATE *)&v101);
  if ( (v6 & 6) == 2 )
  {
    *(_QWORD *)&v105[8] = v82;
    RefsReleasePagingResource(a1, v82);
    LOBYTE(v6) = v6 & 0xFD;
  }
  if ( (v6 & 0x20) != 0 )
  {
    *(_QWORD *)&v105[16] = v84;
    RefsReleasePagingResource(a1, v84);
    LOBYTE(v6) = v6 & 0xDF;
  }
  if ( (v6 & 1) != 0 )
    MsReleaseFastResource((char *)v86 + 1312);
  RefsCompleteFileSystemControlRequest(a1, v75, Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400ec8a4  mov     r11, rsp
0x1400ec8a7  mov     [r11+18h], rbx
0x1400ec8ab  mov     [r11+20h], rsi
0x1400ec8af  push    rdi
0x1400ec8b0  push    r12
0x1400ec8b2  push    r13
0x1400ec8b4  push    r14
0x1400ec8b6  push    r15
0x1400ec8b8  sub     rsp, 240h
0x1400ec8bf  mov     rax, cs:__security_cookie
0x1400ec8c6  xor     rax, rsp
0x1400ec8c9  mov     qword ptr [rsp+268h+var_30], rax
0x1400ec8d1  mov     sil, r8b
0x1400ec8d4  mov     r13, rdx
0x1400ec8d7  mov     [rsp+268h+Irp], rdx
0x1400ec8dc  mov     r15, rcx
0x1400ec8df  mov     [rsp+268h+var_198], rcx
0x1400ec8e7  mov     [rsp+268h+var_118], rdx
0x1400ec8ef  mov     [rsp+268h+Status], 0C000000Dh
0x1400ec8f7  xor     r14d, r14d
0x1400ec8fa  mov     [rsp+268h+var_200], r14
0x1400ec8ff  mov     [rsp+268h+var_1F0], r14
0x1400ec904  mov     [rsp+268h+var_220], r14
0x1400ec909  mov     [r11-1C0h], r14
0x1400ec910  mov     [r11-1C8h], r14
0x1400ec917  mov     [r11-1A8h], r14
0x1400ec91e  mov     [rsp+268h+var_210], r14
0x1400ec923  mov     [r11-1E8h], r14
0x1400ec92a  mov     [rsp+268h+var_218], r14
0x1400ec92f  xorps   xmm0, xmm0
0x1400ec932  movups  [rsp+268h+var_190], xmm0
0x1400ec93a  movups  [rsp+268h+var_180], xmm0
0x1400ec942  movups  [rsp+268h+var_170], xmm0
0x1400ec94a  xor     eax, eax
0x1400ec94c  movups  xmmword ptr [rsp+268h+Event.Header], xmm0
0x1400ec954  mov     [r11-0D0h], rax
0x1400ec95b  mov     [r11-1D0h], r14
0x1400ec962  movups  [rsp+268h+var_138], xmm0
0x1400ec96a  xorps   xmm1, xmm1
0x1400ec96d  movups  [rsp+268h+var_148], xmm1
0x1400ec975  mov     [r11-1A0h], r14
0x1400ec97c  mov     ebx, r14d
0x1400ec97f  mov     [rsp+268h+var_224], ebx
0x1400ec983  xor     ecx, ecx; PerformanceFrequency
0x1400ec985  call    cs:__imp_KeQueryPerformanceCounter
0x1400ec98c  nop     dword ptr [rax+rax+00h]
0x1400ec991  mov     rdi, rax
0x1400ec994  mov     [rsp+268h+var_1A0], rax
0x1400ec99c  lea     r12d, [r14+1]
0x1400ec9a0  or      [r15+8], r12
0x1400ec9a4  mov     rax, [r13+0B8h]
0x1400ec9ab  mov     [rsp+268h+var_1E0], rax
0x1400ec9b3  mov     r13, [rax+30h]
0x1400ec9b7  mov     byte ptr [rsp+268h+var_238], r12b
0x1400ec9bc  lea     rax, [rsp+268h+var_1C0]
0x1400ec9c4  mov     [rsp+268h+HandleInformation], rax
0x1400ec9c9  lea     rax, [rsp+268h+var_220]
0x1400ec9ce  mov     [rsp+268h+Object], rax
0x1400ec9d3  lea     r9, [rsp+268h+var_1F0]
0x1400ec9d8  lea     r8, [rsp+268h+var_200]
0x1400ec9dd  mov     rdx, r13
0x1400ec9e0  mov     rcx, r15
0x1400ec9e3  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1400ec9e8  cmp     al, 2
0x1400ec9ea  jz      short loc_1400ECA42
0x1400ec9ec  lea     rax, WPP_GLOBAL_Control
0x1400ec9f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec9fa  cmp     rcx, rax
0x1400ec9fd  jz      short loc_1400ECA29
0x1400ec9ff  test    dword ptr [rcx+2Ch], 100h
0x1400eca06  jz      short loc_1400ECA29
0x1400eca08  cmp     byte ptr [rcx+29h], 4
0x1400eca0c  jb      short loc_1400ECA29
0x1400eca0e  lea     edx, [r12+7Fh]
0x1400eca13  mov     r9d, 0C000000Dh
0x1400eca19  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400eca20  mov     rcx, [rcx+18h]
0x1400eca24  call    WPP_SF_d
0x1400eca29  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400eca2f  test    al, al
0x1400eca31  jz      loc_1400EE27D
0x1400eca37  mov     r9d, 3631h
0x1400eca3d  jmp     loc_1400EE26A
0x1400eca42  mov     rcx, [rsp+268h+Irp]; Irp
0x1400eca47  call    cs:__imp_IoIs32bitProcess
0x1400eca4e  nop     dword ptr [rax+rax+00h]
0x1400eca53  mov     rcx, [rsp+268h+var_1E0]
0x1400eca5b  mov     ecx, [rcx+10h]
0x1400eca5e  test    al, al
0x1400eca60  jz      loc_1400ECCD6
0x1400eca66  test    sil, sil
0x1400eca69  jnz     loc_1400ECB32
0x1400eca6f  cmp     ecx, 20h ; ' '
0x1400eca72  jnb     short loc_1400ECAE1
0x1400eca74  lea     rax, WPP_GLOBAL_Control
0x1400eca7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eca82  cmp     rcx, rax
0x1400eca85  jz      short loc_1400ECAB1
0x1400eca87  test    dword ptr [rcx+2Ch], 100h
0x1400eca8e  jz      short loc_1400ECAB1
0x1400eca90  cmp     byte ptr [rcx+29h], 4
0x1400eca94  jb      short loc_1400ECAB1
0x1400eca96  mov     edx, 81h
0x1400eca9b  mov     r9d, 0C0000023h
0x1400ecaa1  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecaa8  mov     rcx, [rcx+18h]
0x1400ecaac  call    WPP_SF_d
0x1400ecab1  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ecab7  test    al, al
0x1400ecab9  jz      short loc_1400ECAD4
0x1400ecabb  mov     r9d, 363Dh; unsigned int
0x1400ecac1  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400ecac8  xor     edx, edx; struct _IRP_CONTEXT *
0x1400ecaca  mov     ecx, 0C0000023h; Status
0x1400ecacf  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400ecad4  mov     [rsp+268h+Status], 0C0000023h
0x1400ecadc  jmp     loc_1400EE285
0x1400ecae1  mov     rax, [rsp+268h+Irp]
0x1400ecae6  mov     rcx, [rax+18h]
0x1400ecaea  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400ecaf6  movsxd  rax, dword ptr [rcx]
0x1400ecaf9  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400ecb01  mov     rax, [rcx+8]
0x1400ecb05  mov     qword ptr [rsp+268h+var_180], rax
0x1400ecb0d  mov     rax, [rcx+10h]
0x1400ecb11  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400ecb19  mov     rax, [rcx+18h]
0x1400ecb1d  mov     qword ptr [rsp+268h+var_170], rax
0x1400ecb25  mov     dword ptr [rsp+268h+var_170+8], r14d
0x1400ecb2d  jmp     loc_1400ECC4E
0x1400ecb32  cmp     ecx, 28h ; '('
0x1400ecb35  jnb     short loc_1400ECB8D
0x1400ecb37  lea     rax, WPP_GLOBAL_Control
0x1400ecb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ecb45  cmp     rcx, rax
0x1400ecb48  jz      short loc_1400ECB74
0x1400ecb4a  test    dword ptr [rcx+2Ch], 100h
0x1400ecb51  jz      short loc_1400ECB74
0x1400ecb53  cmp     byte ptr [rcx+29h], 4
0x1400ecb57  jb      short loc_1400ECB74
0x1400ecb59  mov     edx, 82h
0x1400ecb5e  mov     r9d, 0C0000023h
0x1400ecb64  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecb6b  mov     rcx, [rcx+18h]
0x1400ecb6f  call    WPP_SF_d
0x1400ecb74  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ecb7a  test    al, al
0x1400ecb7c  jz      loc_1400ECAD4
0x1400ecb82  mov     r9d, 3651h
0x1400ecb88  jmp     loc_1400ECAC1
0x1400ecb8d  mov     rax, [rsp+268h+Irp]
0x1400ecb92  mov     rcx, [rax+18h]
0x1400ecb96  cmp     dword ptr [rcx], 28h ; '('
0x1400ecb99  jz      short loc_1400ECC08
0x1400ecb9b  lea     rax, WPP_GLOBAL_Control
0x1400ecba2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ecba9  cmp     rcx, rax
0x1400ecbac  jz      short loc_1400ECBD8
0x1400ecbae  test    dword ptr [rcx+2Ch], 100h
0x1400ecbb5  jz      short loc_1400ECBD8
0x1400ecbb7  cmp     byte ptr [rcx+29h], 4
0x1400ecbbb  jb      short loc_1400ECBD8
0x1400ecbbd  mov     edx, 83h
0x1400ecbc2  mov     r9d, 0C00000BBh
0x1400ecbc8  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecbcf  mov     rcx, [rcx+18h]
0x1400ecbd3  call    WPP_SF_d
0x1400ecbd8  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ecbde  test    al, al
0x1400ecbe0  jz      short loc_1400ECBFB
0x1400ecbe2  mov     r9d, 3658h; unsigned int
0x1400ecbe8  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400ecbef  xor     edx, edx; struct _IRP_CONTEXT *
0x1400ecbf1  mov     ecx, 0C00000BBh; Status
0x1400ecbf6  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400ecbfb  mov     [rsp+268h+Status], 0C00000BBh
0x1400ecc03  jmp     loc_1400EE285
0x1400ecc08  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400ecc14  movsxd  rax, dword ptr [rcx+4]
0x1400ecc18  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400ecc20  mov     rax, [rcx+8]
0x1400ecc24  mov     qword ptr [rsp+268h+var_180], rax
0x1400ecc2c  mov     rax, [rcx+10h]
0x1400ecc30  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400ecc38  mov     rax, [rcx+18h]
0x1400ecc3c  mov     qword ptr [rsp+268h+var_170], rax
0x1400ecc44  mov     eax, [rcx+20h]
0x1400ecc47  mov     dword ptr [rsp+268h+var_170+8], eax
0x1400ecc4e  lea     rax, [rsp+268h+var_190]
0x1400ecc56  lea     rdx, [rsp+268h+var_190]
0x1400ecc5e  mov     [rsp+268h+var_218], rax
0x1400ecc63  mov     r10, [rsp+268h+Irp]
0x1400ecc68  mov     r9, [rdx+20h]
0x1400ecc6c  test    r9, r9
0x1400ecc6f  jnz     loc_1400ECE69
0x1400ecc75  lea     rax, WPP_GLOBAL_Control
0x1400ecc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ecc83  cmp     rcx, rax
0x1400ecc86  jz      short loc_1400ECCAC
0x1400ecc88  test    dword ptr [rcx+2Ch], 100h
0x1400ecc8f  jz      short loc_1400ECCAC
0x1400ecc91  cmp     byte ptr [rcx+29h], 5
0x1400ecc95  jb      short loc_1400ECCAC
0x1400ecc97  mov     edx, 87h
0x1400ecc9c  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecca3  mov     rcx, [rcx+18h]
0x1400ecca7  call    WPP_SF_d
0x1400eccac  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400eccb2  test    al, al
0x1400eccb4  jz      short loc_1400ECCCC
0x1400eccb6  mov     r9d, 368Fh; unsigned int
0x1400eccbc  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400eccc3  xor     edx, edx; struct _IRP_CONTEXT *
0x1400eccc5  xor     ecx, ecx; Status
0x1400eccc7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400ecccc  mov     [rsp+268h+Status], r14d
0x1400eccd1  jmp     loc_1400EE285
0x1400eccd6  test    sil, sil
0x1400eccd9  jnz     loc_1400ECDA0
0x1400eccdf  cmp     ecx, 20h ; ' '
0x1400ecce2  jnb     short loc_1400ECD3A
0x1400ecce4  lea     rax, WPP_GLOBAL_Control
0x1400ecceb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eccf2  cmp     rcx, rax
0x1400eccf5  jz      short loc_1400ECD21
0x1400eccf7  test    dword ptr [rcx+2Ch], 100h
0x1400eccfe  jz      short loc_1400ECD21
0x1400ecd00  cmp     byte ptr [rcx+29h], 4
0x1400ecd04  jb      short loc_1400ECD21
0x1400ecd06  mov     edx, 84h
0x1400ecd0b  mov     r9d, 0C0000023h
0x1400ecd11  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecd18  mov     rcx, [rcx+18h]
0x1400ecd1c  call    WPP_SF_d
0x1400ecd21  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ecd27  test    al, al
0x1400ecd29  jz      loc_1400ECAD4
0x1400ecd2f  mov     r9d, 366Fh
0x1400ecd35  jmp     loc_1400ECAC1
0x1400ecd3a  mov     r10, [rsp+268h+Irp]
0x1400ecd3f  mov     rcx, [r10+18h]
0x1400ecd43  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400ecd4f  mov     rax, [rcx]
0x1400ecd52  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400ecd5a  mov     rax, [rcx+8]
0x1400ecd5e  mov     qword ptr [rsp+268h+var_180], rax
0x1400ecd66  mov     rax, [rcx+10h]
0x1400ecd6a  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400ecd72  mov     rax, [rcx+18h]
0x1400ecd76  mov     qword ptr [rsp+268h+var_170], rax
0x1400ecd7e  mov     dword ptr [rsp+268h+var_170+8], r14d
0x1400ecd86  lea     rax, [rsp+268h+var_190]
0x1400ecd8e  mov     [rsp+268h+var_218], rax
0x1400ecd93  lea     rdx, [rsp+268h+var_190]
0x1400ecd9b  jmp     loc_1400ECC68
0x1400ecda0  cmp     ecx, 30h ; '0'
0x1400ecda3  jnb     short loc_1400ECDFB
0x1400ecda5  lea     rax, WPP_GLOBAL_Control
0x1400ecdac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ecdb3  cmp     rcx, rax
0x1400ecdb6  jz      short loc_1400ECDE2
0x1400ecdb8  test    dword ptr [rcx+2Ch], 100h
0x1400ecdbf  jz      short loc_1400ECDE2
0x1400ecdc1  cmp     byte ptr [rcx+29h], 4
0x1400ecdc5  jb      short loc_1400ECDE2
0x1400ecdc7  mov     edx, 85h
0x1400ecdcc  mov     r9d, 0C0000023h
0x1400ecdd2  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ecdd9  mov     rcx, [rcx+18h]
0x1400ecddd  call    WPP_SF_d
0x1400ecde2  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ecde8  test    al, al
0x1400ecdea  jz      loc_1400ECAD4
0x1400ecdf0  mov     r9d, 3681h
0x1400ecdf6  jmp     loc_1400ECAC1
0x1400ecdfb  mov     r10, [rsp+268h+Irp]
0x1400ece00  mov     rdx, [r10+18h]
0x1400ece04  mov     [rsp+268h+var_218], rdx
0x1400ece09  cmp     qword ptr [rdx], 30h ; '0'
0x1400ece0d  jz      loc_1400ECC68
0x1400ece13  lea     rax, WPP_GLOBAL_Control
0x1400ece1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ece21  cmp     rcx, rax
0x1400ece24  jz      short loc_1400ECE50
0x1400ece26  test    dword ptr [rcx+2Ch], 100h
0x1400ece2d  jz      short loc_1400ECE50
0x1400ece2f  cmp     byte ptr [rcx+29h], 4
0x1400ece33  jb      short loc_1400ECE50
0x1400ece35  mov     edx, 86h
0x1400ece3a  mov     r9d, 0C00000BBh
0x1400ece40  lea     r8, WPP_9c60aa4d8ddb36935dafcdfba0977da1_Traceguids
0x1400ece47  mov     rcx, [rcx+18h]
0x1400ece4b  call    WPP_SF_d
0x1400ece50  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400ece56  test    al, al
0x1400ece58  jz      loc_1400ECBFB
0x1400ece5e  mov     r9d, 3688h
0x1400ece64  jmp     loc_1400ECBE8
0x1400ece69  mov     r11, [rdx+18h]
0x1400ece6d  mov     [rsp+268h+var_1C0], r11
  ... truncated ...
```
