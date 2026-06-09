# RefsDuplicateExtents(_IRP_CONTEXT *,_IRP *,uchar)

- ea: `0x1400e785c`
- end: `0x1400e95e7`
- name: `?RefsDuplicateExtents@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@E@Z`
- size: `7563`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, unsigned __int8)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140320e78`

## callees

- `0x140008c10`
- `0x14000a500`
- `0x14000b324`
- `0x14000bcc0`
- `0x14000cd70`
- `0x14000f3f0`
- `0x140080834`
- `0x140080c00`
- `0x140081670`
- `0x140087ee0`
- `0x14008a460`
- `0x14008dbd0`
- `0x14008e060`
- `0x140090040`
- `0x1400913a0`
- `0x14009bb80`
- `0x14009ccb0`
- `0x1400a12b0`
- `0x1400c4c68`
- `0x1400c8a14`
- `0x1400ca788`
- `0x1400e3140`
- `0x1400e785c`
- `0x1400ec8dc`
- `0x1400ee9f8`
- `0x1400eebf4`
- `0x140113b50`
- `0x1401e9ce0`
- `0x140286ebc`
- `0x1402d9f34`
- `0x1402fec90`
- `0x1403000b0`
- `0x1403021e0`
- `0x14032b940`
- `0x1403326dc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400e92aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ec56c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e92aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ec56c`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400e85aa`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x1400e85aa`
- `ntoskrnl!IoCancelIrp` at `0x1400e85d3`
- `ntoskrnl!IoCancelIrp` at `0x1400e85d3`
- `ntoskrnl!IoIs32bitProcess` at `0x1400e79ff`
- `ntoskrnl!IoIs32bitProcess` at `0x1400e79ff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e7f53`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e7f53`
- `ntoskrnl!IoFileObjectType` at `0x1400e7f3b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400e8c79`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400e8e8a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400e8c79`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400e8e8a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400e8c88`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400e8e99`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400e8c88`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400e8e99`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400e8576`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400e8576`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8d09`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8d91`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8f18`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8d09`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8d91`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400e8f18`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8d15`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8d9d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8f24`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8d15`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8d9d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400e8f24`
- `ntoskrnl!KeInitializeEvent` at `0x1400e853d`
- `ntoskrnl!KeInitializeEvent` at `0x1400e853d`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400e87ad`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400e8d6b`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400e87ad`
- `ntoskrnl!CcSetFileSizesEx` at `0x1400e8d6b`
- `HAL!KeQueryPerformanceCounter` at `0x1400e793d`
- `HAL!KeQueryPerformanceCounter` at `0x1400e9268`
- `HAL!KeQueryPerformanceCounter` at `0x1401ec52c`
- `HAL!KeQueryPerformanceCounter` at `0x1400e793d`
- `HAL!KeQueryPerformanceCounter` at `0x1400e9268`
- `HAL!KeQueryPerformanceCounter` at `0x1401ec52c`

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
  __int64 v39; // r9
  char v40; // cl
  __int64 v41; // r8
  LARGE_INTEGER AllocationSize; // rdx
  unsigned int v43; // r8d
  struct _CC_FILE_SIZES *v44; // rdx
  PMRX_NET_ROOT v45; // rcx
  PVOID Context; // r8
  __int64 v47; // r11
  PVOID v48; // r9
  struct _MRX_SRV_CALL_ *v49; // rax
  struct _DUPLICATE_EXTENTS_DATA_EX *v50; // r11
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // r8
  __int64 v54; // r9
  struct _IRP *v55; // rdx
  __int64 v56; // r8
  char v57; // cl
  __int64 v58; // rdx
  __int64 v59; // rsi
  unsigned int v60; // r8d
  __int64 v61; // r13
  unsigned int v62; // r8d
  int v63; // esi
  struct _FAST_MUTEX *FastMutex; // rsi
  char v65; // cl
  ULONGLONG ActualAllocationLength; // rcx
  struct _FAST_MUTEX *v67; // rsi
  __int64 v68; // r13
  struct _FCB *v69; // rdx
  unsigned int v70; // ebx
  unsigned int v71; // r8d
  unsigned int v72; // r8d
  LARGE_INTEGER v73; // r13
  int v74; // esi
  LARGE_INTEGER FileSize; // rdx
  struct _IRP *v76; // rsi
  __int64 v77; // rax
  unsigned __int8 Object; // [rsp+58h] [rbp-248h]
  unsigned __int8 Objecta; // [rsp+58h] [rbp-248h]
  int Status; // [rsp+78h] [rbp-228h]
  struct _FCB *v82; // [rsp+80h] [rbp-220h] BYREF
  struct _DUPLICATE_EXTENTS_DATA_EX *v83; // [rsp+88h] [rbp-218h] BYREF
  struct _IRP *v84; // [rsp+90h] [rbp-210h] BYREF
  char v85; // [rsp+98h] [rbp-208h] BYREF
  struct _VCB *v86; // [rsp+A0h] [rbp-200h] BYREF
  PIRP Irp; // [rsp+A8h] [rbp-1F8h]
  struct _FCB *v88; // [rsp+B0h] [rbp-1F0h] BYREF
  unsigned __int8 v89[8]; // [rsp+B8h] [rbp-1E8h]
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
  if ( (unsigned __int8)RefsDecodeFileObject(a1, FileObject, &v86, &v88) != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14467;
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
            135,
            WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
            3221225507LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_18;
        v12 = 14499;
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
            136,
            WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
            3221225659LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_35;
        v15 = 14506;
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
            134,
            WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
            3221225507LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_18;
        v12 = 14479;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_18;
      v12 = 14547;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_35;
      v15 = 14554;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_18;
      v12 = 14529;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 0);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(0, 0, "DevIoSup.c", 0x38E1u);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14573;
    goto LABEL_272;
  }
  v20 = *((_DWORD *)v86 + 136);
  if ( (((unsigned int)v19 | v16->SourceFileOffset.LowPart) & v20) != 0 || (v20 & v16->ByteCount.LowPart) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225659LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_35;
    v15 = 14585;
    goto LABEL_34;
  }
  if ( !a3 && v16->ByteCount.HighPart || v16->ByteCount.HighPart >= 0x2000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14599;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14646;
    goto LABEL_272;
  }
  if ( (unsigned __int8)RefsDecodeFileObject(0, v93, &v86, v96) != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_273;
    v9 = 14652;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_35;
      v15 = 14669;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids, 3221225634LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741662, 0, "DevIoSup.c", 0x3952u);
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
        RefsSnapshotScb(a1, v82, 0, v39);
        if ( SLOWORD(v82->FcbTableEntry.HashLinks.Blink) >= 0 )
        {
          v103 = 0;
          v104 = 0;
          RefsBindMinstoreTransaction(a1);
          v40 = *((_BYTE *)v86 + 552);
          v41 = *((unsigned int *)v86 + 136);
          AllocationSize = v82->Header.AllocationSize;
          v103 = (AllocationSize.QuadPart + v41) >> v40;
          v104 = (v35 + v41 - AllocationSize.QuadPart) >> v40;
          Status = MsAddAllocation(*((_QWORD *)a1 + 3), v82->LastChangeTime.QuadPart, (unsigned int)&v103, 0x2000, 0);
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                148,
                WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x3ACAu);
            RefsRaiseStatusInternal(a1, Status, v43);
LABEL_296:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                149,
                WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
                3221225760LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741536, a1, "DevIoSup.c", 0x3BB9u);
            RefsRaiseStatusInternal(a1, -1073741536, v60);
LABEL_303:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                150,
                WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x3BC7u);
            RefsRaiseStatusInternal(a1, Status, v62);
LABEL_310:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                151,
                WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
                3221225688LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741608, a1, "DevIoSup.c", 0x3C2Bu);
            RefsRaiseStatusInternal(a1, -1073741608, v71);
LABEL_317:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                152,
                WPP_99ddc213b05f39bbd3789163ea155869_Traceguids,
                (unsigned int)Status);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(Status, a1, "DevIoSup.c", 0x3C38u);
            RefsRaiseStatusInternal(a1, Status, v72);
            __debugbreak();
            JUMPOUT(0x1400E95E7LL);
          }
        }
        RefsWriteFileSizes(a1, (struct _SCB *)v82, 0, 1u, Object);
        v82->Header.AllocationSize.QuadPart = v35;
        v44 = (struct _CC_FILE_SIZES *)v82;
        v35 = v94[0];
        if ( v82->Header.NodeTypeCode == 2053 )
        {
          v82->LastWriteTime.QuadPart = v94[0];
          v44 = (struct _CC_FILE_SIZES *)v82;
        }
        if ( *(_QWORD *)(v44[10].FileSize.QuadPart + 16) )
        {
          CurrentStackLocation = (struct _IO_STACK_LOCATION *)(v44[10].FileSize.QuadPart + 8);
          CcSetFileSizesEx((PFILE_OBJECT)&v85, v44 + 1);
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
    v45 = v88->pNetRoot;
    Context = v45[2].Context;
    v47 = *(_QWORD *)(v96[0] + 88LL);
    v48 = *(PVOID *)(v47 + 256);
    if ( Context <= v48 )
    {
      if ( Context != v48 )
        goto LABEL_199;
      v49 = *(struct _MRX_SRV_CALL_ **)(v47 + 248);
      if ( v45[2].pSrvCall <= v49 )
      {
        if ( Context == v48 && v45[2].pSrvCall == v49 )
        {
          v50 = v83;
          v51 = v83->TargetFileOffset.QuadPart;
          if ( v83->SourceFileOffset.QuadPart < v51 && v37 == (struct _FCB *)v36 || v36 < (struct _IRP *)v37 )
          {
            if ( _bittest16((const signed __int16 *)&v36[1].IoStatus, 0xDu)
              && (*(_DWORD *)(*((_QWORD *)v36->Tail.Overlay.DriverContext[3] + 14) + 3460LL) & 0x800000) != 0 )
            {
              RefsSetDuplicateInProgress(
                a1,
                (struct _SCB *)v36,
                v83->SourceFileOffset.QuadPart,
                v83->ByteCount.QuadPart);
              v6 |= 0x80u;
              v37 = v82;
              v36 = v84;
              v50 = v83;
            }
            if ( (*((_DWORD *)&v36->Tail.CompletionKey + 8) & 0x80u) == 0 )
            {
              RefsAcquireRangeLock(
                a1,
                (struct _SCB_NONPAGED *)v36[1].ThreadListEntry.Blink,
                v50->SourceFileOffset.QuadPart,
                v50->ByteCount.QuadPart,
                0,
                (struct _RANGE_LOCK_STATE *)&v101);
              v6 |= 0x40u;
              v37 = v82;
              v50 = v83;
            }
            v52 = v50->ByteCount.QuadPart;
            v53 = v50->TargetFileOffset.QuadPart;
LABEL_197:
            RefsAcquireRangeLock(
              a1,
              (struct _SCB_NONPAGED *)v37->FcbTableEntry.HashLinks.Flink,
              v53,
              v52,
              1,
              (struct _RANGE_LOCK_STATE *)&v102);
            v6 |= 8u;
            goto LABEL_211;
          }
          v54 = v83->ByteCount.QuadPart;
LABEL_206:
          RefsAcquireRangeLock(
            a1,
            (struct _SCB_NONPAGED *)v37->FcbTableEntry.HashLinks.Flink,
            v51,
            v54,
            1,
            (struct _RANGE_LOCK_STATE *)&v102);
          v6 |= 8u;
          v55 = v84;
          if ( _bittest16((const signed __int16 *)&v84[1].IoStatus, 0xDu)
            && (*(_DWORD *)(*((_QWORD *)v84->Tail.Overlay.DriverContext[3] + 14) + 3460LL) & 0x800000) != 0 )
          {
            RefsSetDuplicateInProgress(a1, (struct _SCB *)v84, v83->SourceFileOffset.QuadPart, v83->ByteCount.QuadPart);
            v6 |= 0x80u;
            v55 = v84;
          }
          if ( (*((_DWORD *)&v55->Tail.CompletionKey + 8) & 0x80u) == 0 )
          {
            RefsAcquireRangeLock(
              a1,
              (struct _SCB_NONPAGED *)v55[1].ThreadListEntry.Blink,
              v83->SourceFileOffset.QuadPart,
              v83->ByteCount.QuadPart,
              0,
              (struct _RANGE_LOCK_STATE *)&v101);
            v6 |= 0x40u;
          }
LABEL_211:
          if ( v82->Header.FileSize.QuadPart > v35 )
            RefsPostUsnChange(a1, v82, 1u, 0);
          v56 = *((_QWORD *)a1 + 18);
          v57 = *((_BYTE *)v86 + 552);
          v58 = *((unsigned int *)v86 + 136);
          v59 = ((v58 + v83->ByteCount.QuadPart) >> v57) - v56;
          *(_QWORD *)&v105[32] = v59;
          CurrentStackLocation = (struct _IO_STACK_LOCATION *)(v56 + ((v58 + v83->SourceFileOffset.QuadPart) >> v57));
          *(_QWORD *)&v105[48] = CurrentStackLocation;
          *(_QWORD *)v89 = v56 + ((v58 + v83->TargetFileOffset.QuadPart) >> v57);
          *(_QWORD *)&v105[24] = *(_QWORD *)v89;
          v91 = LOWORD(v82->FcbTableEntry.HashLinks.Blink) >> 15;
          while ( v59 > 0 )
          {
            v85 = 0;
            RefsBindMinstoreTransaction(a1);
            if ( Irp->Cancel )
              goto LABEL_296;
            v61 = (*(unsigned int *)(*((_QWORD *)&v82->1 + 18) + 544LL) + 0x40000000LL) >> *(_BYTE *)(*((_QWORD *)&v82->1 + 18) + 552LL);
            if ( v59 < v61 )
              v61 = v59;
            Status = MsDuplicateExtents(
                       *((struct CmsTransactionContext **)a1 + 3),
                       (CmsStream *)v82->LastChangeTime.QuadPart,
                       v89[0],
                       v61,
                       v91);
            if ( Status < 0 )
              goto LABEL_303;
            CurrentStackLocation = (struct _IO_STACK_LOCATION *)((char *)CurrentStackLocation + v61);
            *(_QWORD *)&v105[48] = CurrentStackLocation;
            *(_QWORD *)v89 += v61;
            *(_QWORD *)&v105[24] = *(_QWORD *)v89;
            v100 = (struct _FCB *)(v59 - v61);
            *(_QWORD *)&v105[32] = v59 - v61;
            v63 = (v6 >> 4) & 1;
            LODWORD(v95) = v63;
            if ( v63 )
            {
              FastMutex = v82->Header.FastMutex;
              KeEnterGuardedRegion();
              ExAcquireFastMutexUnsafe(FastMutex);
              _InterlockedAdd((volatile signed __int32 *)&v82->1 + 43, 1u);
              *(_OWORD *)&v105[192] = *(_OWORD *)&v82->spacer.AllocationSize.LowPart;
              *(_QWORD *)&v105[208] = v82->Header.ValidDataLength.QuadPart;
              v65 = *((_BYTE *)v86 + 552);
              if ( *(__int64 *)&v105[192] >= *(_QWORD *)v89 << v65 )
              {
                ++*((_DWORD *)&v82->1 + 43);
                ExReleaseFastMutexUnsafe(v82->Header.FastMutex);
                KeLeaveGuardedRegion();
              }
              else
              {
                *(_QWORD *)&v105[192] = *(_QWORD *)v89 << v65;
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
              v63 = (int)v95;
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
              *((_QWORD *)a1 + 18) += v61;
            if ( v63 && v85 )
            {
              v67 = v82->Header.FastMutex;
              KeEnterGuardedRegion();
              ExAcquireFastMutexUnsafe(v67);
              _InterlockedAdd((volatile signed __int32 *)&v82->1 + 43, 1u);
              v68 = *(_QWORD *)v89;
              v82->Header.AllocationSize.QuadPart = *(_QWORD *)v89 << *((_BYTE *)v86 + 552);
              v69 = v82;
              if ( v82->Header.NodeTypeCode == 2053 )
              {
                v82->LastWriteTime.QuadPart = v68 << *((_BYTE *)v86 + 552);
                v69 = v82;
              }
              ++*((_DWORD *)&v69->1 + 43);
              ExReleaseFastMutexUnsafe(v82->Header.FastMutex);
              KeLeaveGuardedRegion();
            }
            v59 = (__int64)v100;
            if ( (__int64)v100 > 0 && (*((_DWORD *)&v84->Tail.CompletionKey + 8) & 0x80u) != 0 )
            {
              *(_QWORD *)&v105[144] = v84;
              RefsReleasePagingResource(a1, v84);
              v70 = v6 & 0xFFFFFFDF;
              *(_QWORD *)&v105[152] = v84;
              if ( !(unsigned __int8)RefsAcquirePagingResourceShared(a1, v84, 0) )
                goto LABEL_310;
              v6 = v70 | 0x20;
              Status = RefsDuplicateExtents_::_4_::_lambda_1_::operator()(&v105[80]);
              if ( Status < 0 )
                goto LABEL_317;
            }
          }
          v73 = v92;
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
            v74 = (v6 >> 2) & 1;
            if ( !v74 )
              RefsAcquireEofLockForRead(a1, (struct _SCB *)v82);
            FileSize = v82->Header.FileSize;
            if ( FileSize.QuadPart < v73.QuadPart && FileSize.QuadPart > v94[0] )
            {
              *(_OWORD *)v94 = 0;
              if ( !v74 )
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
              if ( !v74 )
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
          && (*(_DWORD *)(*((_QWORD *)v36->Tail.Overlay.DriverContext[3] + 14) + 3460LL) & 0x800000) != 0 )
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
        v52 = v83->ByteCount.QuadPart;
        v53 = v83->TargetFileOffset.QuadPart;
        goto LABEL_197;
      }
    }
    v54 = v83->ByteCount.QuadPart;
    v51 = v83->TargetFileOffset.QuadPart;
    goto LABEL_206;
  }
LABEL_274:
  v76 = Irp;
  v77 = *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart;
  RefsTelemetryDuplicateExtentsToFile(v86, (struct _SCB *)v82, (struct _SCB *)v84, v83, v77, Status);
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
  RefsCompleteFileSystemControlRequest(a1, v76, Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400e785c  mov     r11, rsp
0x1400e785f  mov     [r11+18h], rbx
0x1400e7863  mov     [r11+20h], rsi
0x1400e7867  push    rdi
0x1400e7868  push    r12
0x1400e786a  push    r13
0x1400e786c  push    r14
0x1400e786e  push    r15
0x1400e7870  sub     rsp, 240h
0x1400e7877  mov     rax, cs:__security_cookie
0x1400e787e  xor     rax, rsp
0x1400e7881  mov     qword ptr [rsp+268h+var_30], rax
0x1400e7889  mov     sil, r8b
0x1400e788c  mov     r13, rdx
0x1400e788f  mov     [rsp+268h+Irp], rdx
0x1400e7894  mov     r15, rcx
0x1400e7897  mov     [rsp+268h+var_198], rcx
0x1400e789f  mov     [rsp+268h+var_118], rdx
0x1400e78a7  mov     [rsp+268h+Status], 0C000000Dh
0x1400e78af  xor     r14d, r14d
0x1400e78b2  mov     [rsp+268h+var_200], r14
0x1400e78b7  mov     [rsp+268h+var_1F0], r14
0x1400e78bc  mov     [rsp+268h+var_220], r14
0x1400e78c1  mov     [r11-1C0h], r14
0x1400e78c8  mov     [r11-1C8h], r14
0x1400e78cf  mov     [r11-1A8h], r14
0x1400e78d6  mov     [rsp+268h+var_210], r14
0x1400e78db  mov     [r11-1E8h], r14
0x1400e78e2  mov     [rsp+268h+var_218], r14
0x1400e78e7  xorps   xmm0, xmm0
0x1400e78ea  movups  [rsp+268h+var_190], xmm0
0x1400e78f2  movups  [rsp+268h+var_180], xmm0
0x1400e78fa  movups  [rsp+268h+var_170], xmm0
0x1400e7902  xor     eax, eax
0x1400e7904  movups  xmmword ptr [rsp+268h+Event.Header], xmm0
0x1400e790c  mov     [r11-0D0h], rax
0x1400e7913  mov     [r11-1D0h], r14
0x1400e791a  movups  [rsp+268h+var_138], xmm0
0x1400e7922  xorps   xmm1, xmm1
0x1400e7925  movups  [rsp+268h+var_148], xmm1
0x1400e792d  mov     [r11-1A0h], r14
0x1400e7934  mov     ebx, r14d
0x1400e7937  mov     [rsp+268h+var_224], ebx
0x1400e793b  xor     ecx, ecx; PerformanceFrequency
0x1400e793d  call    cs:__imp_KeQueryPerformanceCounter
0x1400e7944  nop     dword ptr [rax+rax+00h]
0x1400e7949  mov     rdi, rax
0x1400e794c  mov     [rsp+268h+var_1A0], rax
0x1400e7954  lea     r12d, [r14+1]
0x1400e7958  or      [r15+8], r12
0x1400e795c  mov     rax, [r13+0B8h]
0x1400e7963  mov     [rsp+268h+var_1E0], rax
0x1400e796b  mov     r13, [rax+30h]
0x1400e796f  mov     [rsp+268h+var_238], r12b
0x1400e7974  lea     rax, [rsp+268h+var_1C0]
0x1400e797c  mov     [rsp+268h+HandleInformation], rax
0x1400e7981  lea     rax, [rsp+268h+var_220]
0x1400e7986  mov     [rsp+268h+Object], rax
0x1400e798b  lea     r9, [rsp+268h+var_1F0]
0x1400e7990  lea     r8, [rsp+268h+var_200]
0x1400e7995  mov     rdx, r13
0x1400e7998  mov     rcx, r15
0x1400e799b  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1400e79a0  cmp     al, 2
0x1400e79a2  jz      short loc_1400E79FA
0x1400e79a4  lea     rax, WPP_GLOBAL_Control
0x1400e79ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e79b2  cmp     rcx, rax
0x1400e79b5  jz      short loc_1400E79E1
0x1400e79b7  test    dword ptr [rcx+2Ch], 100h
0x1400e79be  jz      short loc_1400E79E1
0x1400e79c0  cmp     byte ptr [rcx+29h], 4
0x1400e79c4  jb      short loc_1400E79E1
0x1400e79c6  mov     edx, 85h
0x1400e79cb  mov     r9d, 0C000000Dh
0x1400e79d1  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e79d8  mov     rcx, [rcx+18h]
0x1400e79dc  call    WPP_SF_d
0x1400e79e1  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e79e7  test    al, al
0x1400e79e9  jz      loc_1400E9235
0x1400e79ef  mov     r9d, 3883h
0x1400e79f5  jmp     loc_1400E9222
0x1400e79fa  mov     rcx, [rsp+268h+Irp]; Irp
0x1400e79ff  call    cs:__imp_IoIs32bitProcess
0x1400e7a06  nop     dword ptr [rax+rax+00h]
0x1400e7a0b  mov     rcx, [rsp+268h+var_1E0]
0x1400e7a13  mov     ecx, [rcx+10h]
0x1400e7a16  test    al, al
0x1400e7a18  jz      loc_1400E7C8E
0x1400e7a1e  test    sil, sil
0x1400e7a21  jnz     loc_1400E7AEA
0x1400e7a27  cmp     ecx, 20h ; ' '
0x1400e7a2a  jnb     short loc_1400E7A99
0x1400e7a2c  lea     rax, WPP_GLOBAL_Control
0x1400e7a33  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7a3a  cmp     rcx, rax
0x1400e7a3d  jz      short loc_1400E7A69
0x1400e7a3f  test    dword ptr [rcx+2Ch], 100h
0x1400e7a46  jz      short loc_1400E7A69
0x1400e7a48  cmp     byte ptr [rcx+29h], 4
0x1400e7a4c  jb      short loc_1400E7A69
0x1400e7a4e  mov     edx, 86h
0x1400e7a53  mov     r9d, 0C0000023h
0x1400e7a59  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7a60  mov     rcx, [rcx+18h]
0x1400e7a64  call    WPP_SF_d
0x1400e7a69  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7a6f  test    al, al
0x1400e7a71  jz      short loc_1400E7A8C
0x1400e7a73  mov     r9d, 388Fh; unsigned int
0x1400e7a79  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400e7a80  xor     edx, edx; struct _IRP_CONTEXT *
0x1400e7a82  mov     ecx, 0C0000023h; Status
0x1400e7a87  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400e7a8c  mov     [rsp+268h+Status], 0C0000023h
0x1400e7a94  jmp     loc_1400E923D
0x1400e7a99  mov     rax, [rsp+268h+Irp]
0x1400e7a9e  mov     rcx, [rax+18h]
0x1400e7aa2  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400e7aae  movsxd  rax, dword ptr [rcx]
0x1400e7ab1  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400e7ab9  mov     rax, [rcx+8]
0x1400e7abd  mov     qword ptr [rsp+268h+var_180], rax
0x1400e7ac5  mov     rax, [rcx+10h]
0x1400e7ac9  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400e7ad1  mov     rax, [rcx+18h]
0x1400e7ad5  mov     qword ptr [rsp+268h+var_170], rax
0x1400e7add  mov     dword ptr [rsp+268h+var_170+8], r14d
0x1400e7ae5  jmp     loc_1400E7C06
0x1400e7aea  cmp     ecx, 28h ; '('
0x1400e7aed  jnb     short loc_1400E7B45
0x1400e7aef  lea     rax, WPP_GLOBAL_Control
0x1400e7af6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7afd  cmp     rcx, rax
0x1400e7b00  jz      short loc_1400E7B2C
0x1400e7b02  test    dword ptr [rcx+2Ch], 100h
0x1400e7b09  jz      short loc_1400E7B2C
0x1400e7b0b  cmp     byte ptr [rcx+29h], 4
0x1400e7b0f  jb      short loc_1400E7B2C
0x1400e7b11  mov     edx, 87h
0x1400e7b16  mov     r9d, 0C0000023h
0x1400e7b1c  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7b23  mov     rcx, [rcx+18h]
0x1400e7b27  call    WPP_SF_d
0x1400e7b2c  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7b32  test    al, al
0x1400e7b34  jz      loc_1400E7A8C
0x1400e7b3a  mov     r9d, 38A3h
0x1400e7b40  jmp     loc_1400E7A79
0x1400e7b45  mov     rax, [rsp+268h+Irp]
0x1400e7b4a  mov     rcx, [rax+18h]
0x1400e7b4e  cmp     dword ptr [rcx], 28h ; '('
0x1400e7b51  jz      short loc_1400E7BC0
0x1400e7b53  lea     rax, WPP_GLOBAL_Control
0x1400e7b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7b61  cmp     rcx, rax
0x1400e7b64  jz      short loc_1400E7B90
0x1400e7b66  test    dword ptr [rcx+2Ch], 100h
0x1400e7b6d  jz      short loc_1400E7B90
0x1400e7b6f  cmp     byte ptr [rcx+29h], 4
0x1400e7b73  jb      short loc_1400E7B90
0x1400e7b75  mov     edx, 88h
0x1400e7b7a  mov     r9d, 0C00000BBh
0x1400e7b80  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7b87  mov     rcx, [rcx+18h]
0x1400e7b8b  call    WPP_SF_d
0x1400e7b90  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7b96  test    al, al
0x1400e7b98  jz      short loc_1400E7BB3
0x1400e7b9a  mov     r9d, 38AAh; unsigned int
0x1400e7ba0  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400e7ba7  xor     edx, edx; struct _IRP_CONTEXT *
0x1400e7ba9  mov     ecx, 0C00000BBh; Status
0x1400e7bae  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400e7bb3  mov     [rsp+268h+Status], 0C00000BBh
0x1400e7bbb  jmp     loc_1400E923D
0x1400e7bc0  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400e7bcc  movsxd  rax, dword ptr [rcx+4]
0x1400e7bd0  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400e7bd8  mov     rax, [rcx+8]
0x1400e7bdc  mov     qword ptr [rsp+268h+var_180], rax
0x1400e7be4  mov     rax, [rcx+10h]
0x1400e7be8  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400e7bf0  mov     rax, [rcx+18h]
0x1400e7bf4  mov     qword ptr [rsp+268h+var_170], rax
0x1400e7bfc  mov     eax, [rcx+20h]
0x1400e7bff  mov     dword ptr [rsp+268h+var_170+8], eax
0x1400e7c06  lea     rax, [rsp+268h+var_190]
0x1400e7c0e  lea     rdx, [rsp+268h+var_190]
0x1400e7c16  mov     [rsp+268h+var_218], rax
0x1400e7c1b  mov     r10, [rsp+268h+Irp]
0x1400e7c20  mov     r9, [rdx+20h]
0x1400e7c24  test    r9, r9
0x1400e7c27  jnz     loc_1400E7E21
0x1400e7c2d  lea     rax, WPP_GLOBAL_Control
0x1400e7c34  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7c3b  cmp     rcx, rax
0x1400e7c3e  jz      short loc_1400E7C64
0x1400e7c40  test    dword ptr [rcx+2Ch], 100h
0x1400e7c47  jz      short loc_1400E7C64
0x1400e7c49  cmp     byte ptr [rcx+29h], 5
0x1400e7c4d  jb      short loc_1400E7C64
0x1400e7c4f  mov     edx, 8Ch
0x1400e7c54  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7c5b  mov     rcx, [rcx+18h]
0x1400e7c5f  call    WPP_SF_d
0x1400e7c64  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7c6a  test    al, al
0x1400e7c6c  jz      short loc_1400E7C84
0x1400e7c6e  mov     r9d, 38E1h; unsigned int
0x1400e7c74  lea     r8, aDeviosupC; "DevIoSup.c"
0x1400e7c7b  xor     edx, edx; struct _IRP_CONTEXT *
0x1400e7c7d  xor     ecx, ecx; Status
0x1400e7c7f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400e7c84  mov     [rsp+268h+Status], r14d
0x1400e7c89  jmp     loc_1400E923D
0x1400e7c8e  test    sil, sil
0x1400e7c91  jnz     loc_1400E7D58
0x1400e7c97  cmp     ecx, 20h ; ' '
0x1400e7c9a  jnb     short loc_1400E7CF2
0x1400e7c9c  lea     rax, WPP_GLOBAL_Control
0x1400e7ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7caa  cmp     rcx, rax
0x1400e7cad  jz      short loc_1400E7CD9
0x1400e7caf  test    dword ptr [rcx+2Ch], 100h
0x1400e7cb6  jz      short loc_1400E7CD9
0x1400e7cb8  cmp     byte ptr [rcx+29h], 4
0x1400e7cbc  jb      short loc_1400E7CD9
0x1400e7cbe  mov     edx, 89h
0x1400e7cc3  mov     r9d, 0C0000023h
0x1400e7cc9  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7cd0  mov     rcx, [rcx+18h]
0x1400e7cd4  call    WPP_SF_d
0x1400e7cd9  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7cdf  test    al, al
0x1400e7ce1  jz      loc_1400E7A8C
0x1400e7ce7  mov     r9d, 38C1h
0x1400e7ced  jmp     loc_1400E7A79
0x1400e7cf2  mov     r10, [rsp+268h+Irp]
0x1400e7cf7  mov     rcx, [r10+18h]
0x1400e7cfb  mov     qword ptr [rsp+268h+var_190], 30h ; '0'
0x1400e7d07  mov     rax, [rcx]
0x1400e7d0a  mov     qword ptr [rsp+268h+var_190+8], rax
0x1400e7d12  mov     rax, [rcx+8]
0x1400e7d16  mov     qword ptr [rsp+268h+var_180], rax
0x1400e7d1e  mov     rax, [rcx+10h]
0x1400e7d22  mov     qword ptr [rsp+268h+var_180+8], rax
0x1400e7d2a  mov     rax, [rcx+18h]
0x1400e7d2e  mov     qword ptr [rsp+268h+var_170], rax
0x1400e7d36  mov     dword ptr [rsp+268h+var_170+8], r14d
0x1400e7d3e  lea     rax, [rsp+268h+var_190]
0x1400e7d46  mov     [rsp+268h+var_218], rax
0x1400e7d4b  lea     rdx, [rsp+268h+var_190]
0x1400e7d53  jmp     loc_1400E7C20
0x1400e7d58  cmp     ecx, 30h ; '0'
0x1400e7d5b  jnb     short loc_1400E7DB3
0x1400e7d5d  lea     rax, WPP_GLOBAL_Control
0x1400e7d64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7d6b  cmp     rcx, rax
0x1400e7d6e  jz      short loc_1400E7D9A
0x1400e7d70  test    dword ptr [rcx+2Ch], 100h
0x1400e7d77  jz      short loc_1400E7D9A
0x1400e7d79  cmp     byte ptr [rcx+29h], 4
0x1400e7d7d  jb      short loc_1400E7D9A
0x1400e7d7f  mov     edx, 8Ah
0x1400e7d84  mov     r9d, 0C0000023h
0x1400e7d8a  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7d91  mov     rcx, [rcx+18h]
0x1400e7d95  call    WPP_SF_d
0x1400e7d9a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7da0  test    al, al
0x1400e7da2  jz      loc_1400E7A8C
0x1400e7da8  mov     r9d, 38D3h
0x1400e7dae  jmp     loc_1400E7A79
0x1400e7db3  mov     r10, [rsp+268h+Irp]
0x1400e7db8  mov     rdx, [r10+18h]
0x1400e7dbc  mov     [rsp+268h+var_218], rdx
0x1400e7dc1  cmp     qword ptr [rdx], 30h ; '0'
0x1400e7dc5  jz      loc_1400E7C20
0x1400e7dcb  lea     rax, WPP_GLOBAL_Control
0x1400e7dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e7dd9  cmp     rcx, rax
0x1400e7ddc  jz      short loc_1400E7E08
0x1400e7dde  test    dword ptr [rcx+2Ch], 100h
0x1400e7de5  jz      short loc_1400E7E08
0x1400e7de7  cmp     byte ptr [rcx+29h], 4
0x1400e7deb  jb      short loc_1400E7E08
0x1400e7ded  mov     edx, 8Bh
0x1400e7df2  mov     r9d, 0C00000BBh
0x1400e7df8  lea     r8, WPP_99ddc213b05f39bbd3789163ea155869_Traceguids
0x1400e7dff  mov     rcx, [rcx+18h]
0x1400e7e03  call    WPP_SF_d
0x1400e7e08  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400e7e0e  test    al, al
0x1400e7e10  jz      loc_1400E7BB3
0x1400e7e16  mov     r9d, 38DAh
0x1400e7e1c  jmp     loc_1400E7BA0
0x1400e7e21  mov     r11, [rdx+18h]
0x1400e7e25  mov     [rsp+268h+var_1C0], r11
  ... truncated ...
```
