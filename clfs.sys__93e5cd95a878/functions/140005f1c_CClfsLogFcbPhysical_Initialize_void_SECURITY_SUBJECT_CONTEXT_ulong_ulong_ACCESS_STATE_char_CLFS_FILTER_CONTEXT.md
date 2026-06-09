# CClfsLogFcbPhysical::Initialize(void *,_SECURITY_SUBJECT_CONTEXT &,ulong,ulong,_ACCESS_STATE *,char,_CLFS_FILTER_CONTEXT *,_FILE_OBJECT *,ulong)

- ea: `0x140005f1c`
- end: `0x140006eb4`
- name: `?Initialize@CClfsLogFcbPhysical@@QEAAJPEAXAEAU_SECURITY_SUBJECT_CONTEXT@@KKPEAU_ACCESS_STATE@@DPEAU_CLFS_FILTER_CONTEXT@@PEAU_FILE_OBJECT@@K@Z`
- size: `3992`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, void *@<rdx>, struct _SECURITY_SUBJECT_CONTEXT *@<r8>, unsigned int@<r9d>, ULONG DesiredShareAccess, struct _ACCESS_STATE *, char, struct _CLFS_FILTER_CONTEXT *, struct _FILE_OBJECT *, unsigned int)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006d048`

## callees

- `0x140003590`
- `0x140005840`
- `0x140005868`
- `0x140005f00`
- `0x140005f1c`
- `0x140006ebc`
- `0x140006fa4`
- `0x1400072f8`
- `0x140007470`
- `0x140007550`
- `0x1400075b0`
- `0x14000a8e0`
- `0x14000dcd8`
- `0x14000dfa4`
- `0x14000e46c`
- `0x14000ed64`
- `0x14000f1f0`
- `0x14000fa48`
- `0x1400121e4`
- `0x140017f20`
- `0x140018280`
- `0x1400187a0`
- `0x14005ed70`
- `0x140062980`
- `0x140062a30`
- `0x140062df0`
- `0x1400632d4`
- `0x140063c24`
- `0x140066e00`
- `0x140067060`
- `0x140067458`
- `0x140067608`
- `0x1400677b8`
- `0x1400683b8`
- `0x140073758`
- `0x140073dd0`
- `0x140075704`
- `0x140075cd4`
- `0x140075e08`
- `0x140076c00`
- `0x140077800`
- `0x1400787ec`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018c56`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140018c56`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000620b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000620b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005fc5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005fc5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000694b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000694b`
- `ntoskrnl!ObfDereferenceObject` at `0x140006d89`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cf1`
- `ntoskrnl!ObfDereferenceObject` at `0x140006d89`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cf1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140006a73`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140006a73`
- `ntoskrnl!KeClearEvent` at `0x140006238`
- `ntoskrnl!KeClearEvent` at `0x140006238`
- `ntoskrnl!KeBugCheckEx` at `0x14000686e`
- `ntoskrnl!KeBugCheckEx` at `0x14000699c`
- `ntoskrnl!KeBugCheckEx` at `0x1400069df`
- `ntoskrnl!KeBugCheckEx` at `0x140006a60`
- `ntoskrnl!KeBugCheckEx` at `0x14000686e`
- `ntoskrnl!KeBugCheckEx` at `0x14000699c`
- `ntoskrnl!KeBugCheckEx` at `0x1400069df`
- `ntoskrnl!KeBugCheckEx` at `0x140006a60`
- `ntoskrnl!KeInitializeEvent` at `0x140006438`
- `ntoskrnl!KeInitializeEvent` at `0x140006438`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006130`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006130`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000635d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400063bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400063ef`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000635d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400063bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400063ef`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000625b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000625b`
- `ntoskrnl!IoCheckShareAccess` at `0x1400060b2`
- `ntoskrnl!IoCheckShareAccess` at `0x1400060b2`
- `ntoskrnl!IoSetShareAccess` at `0x140006cb9`
- `ntoskrnl!IoSetShareAccess` at `0x140006cb9`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14000652f`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14000652f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006e8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006e8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ded`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400061ec`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000630e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000633e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006372`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000639d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400063d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006404`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000690b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006ab8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400061ec`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000630e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000633e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006372`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000639d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400063d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006404`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000690b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006ab8`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::Initialize(
        CClfsLogFcbPhysical *this,
        __int64 a2,
        struct _SECURITY_SUBJECT_CONTEXT *a3,
        ACCESS_MASK a4,
        ULONG DesiredShareAccess,
        struct _ACCESS_STATE *a6,
        char a7,
        struct _CLFS_FILTER_CONTEXT *a8,
        struct _FILE_OBJECT *FileObject,
        unsigned int a10)
{
  union _CLS_LSN *v11; // r15
  struct _CLFS_FILTER_CONTEXT *v12; // rdi
  _BYTE *v13; // r12
  int v14; // r8d
  NTSTATUS EventObject; // ebx
  struct _FILE_OBJECT *v16; // r13
  char v17; // al
  ACCESS_MASK v18; // edi
  char v19; // al
  struct _SHARE_ACCESS *v20; // r9
  struct _FILE_OBJECT *v21; // r12
  CClfsBaseFilePersisted *v22; // rax
  CClfsBaseFile *v23; // rax
  int v24; // eax
  unsigned int v25; // eax
  struct _ERESOURCE *v26; // rax
  enum _EVENT_TYPE v27; // ecx
  struct _FILE_OBJECT *v28; // rcx
  PIO_WORKITEM WorkItem; // rax
  struct _CLFS_CLIENT_CONTEXT *v30; // rcx
  __int16 v31; // dx
  struct _CLFS_CLIENT_CONTEXT *v32; // rbx
  _QWORD *v33; // rax
  KSPIN_LOCK *v34; // rax
  _QWORD *v35; // rax
  KSPIN_LOCK *v36; // rax
  KSPIN_LOCK *v37; // rax
  struct _KEVENT *v38; // rax
  unsigned int v39; // eax
  __int64 v40; // r13
  CClfsBaseFilePersisted *v41; // rdi
  union _CLS_LSN v42; // rbx
  char v43; // al
  struct _FILE_OBJECT *StreamFileObjectLite; // rdi
  struct _CLFS_CLIENT_CONTEXT *v45; // rcx
  CLFS_LSN *v46; // rdi
  SIZE_T v48; // rax
  PVOID PoolWithTag; // rax
  size_t v50; // r8
  ULONG v51; // ebx
  CLFS_CONTAINER_ID v52; // eax
  ULONG_PTR v53; // r8
  unsigned __int8 *v54; // rax
  union _CLS_LSN *v55; // rax
  unsigned int v56; // r8d
  unsigned int v57; // r8d
  ULONG v58; // ebx
  CLFS_CONTAINER_ID v59; // eax
  unsigned __int8 v60; // r9
  ULONG v61; // ebx
  CLFS_CONTAINER_ID v62; // eax
  __int64 v63; // rcx
  char v64; // bl
  unsigned int v65; // eax
  int v67; // [rsp+80h] [rbp-F0h]
  int v68; // [rsp+88h] [rbp-E8h]
  char v69; // [rsp+ACh] [rbp-C4h]
  char v70; // [rsp+ADh] [rbp-C3h]
  struct _FILE_OBJECT *Object; // [rsp+B0h] [rbp-C0h]
  char v72; // [rsp+B8h] [rbp-B8h]
  char v73; // [rsp+BAh] [rbp-B6h]
  struct _CLFS_CLIENT_CONTEXT *v74; // [rsp+C8h] [rbp-A8h] BYREF
  char v75; // [rsp+D0h] [rbp-A0h]
  UNICODE_STRING Destination; // [rsp+D8h] [rbp-98h] BYREF
  unsigned int v77[2]; // [rsp+E8h] [rbp-88h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-80h] BYREF
  unsigned __int64 v79; // [rsp+F8h] [rbp-78h] BYREF
  unsigned int *v80; // [rsp+100h] [rbp-70h]
  __int64 v81; // [rsp+108h] [rbp-68h] BYREF
  char *v82; // [rsp+110h] [rbp-60h]
  __int128 v83; // [rsp+118h] [rbp-58h] BYREF
  __int64 v84; // [rsp+128h] [rbp-48h]
  __int64 v85; // [rsp+180h] [rbp+10h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT *v86; // [rsp+188h] [rbp+18h]
  ACCESS_MASK DesiredAccess; // [rsp+190h] [rbp+20h]

  DesiredAccess = a4;
  v86 = a3;
  v85 = a2;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  v79 = 0;
  v83 = 0;
  v84 = 0;
  v11 = 0;
  v74 = 0;
  Object = 0;
  v77[0] = 0;
  v73 = 0;
  v72 = 0;
  LOBYTE(v85) = 0;
  v69 = 0;
  v70 = 0;
  v12 = a8;
  if ( a8 )
  {
    v83 = *(_OWORD *)a8;
    v84 = *((_QWORD *)a8 + 2);
  }
  v82 = (char *)this + 200;
  LOBYTE(a8) = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  if ( *((_DWORD *)this + 236) )
    KeBugCheckEx(0xC1F5u, 0x2Cu, (ULONG_PTR)this, 0, 0);
  v13 = (char *)this + 364;
  v78 = (__int64)this + 364;
  v80 = (unsigned int *)((char *)this + 364);
  v14 = *((_DWORD *)this + 91);
  if ( (v14 & 0x1000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        15,
        (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
        (unsigned int)"CClfsLogFcbPhysical::Initialize",
        203,
        v14);
    }
    EventObject = -1072037845;
    goto LABEL_78;
  }
  EventObject = CClfsLogFcbPhysical::Open(this, FileObject);
  if ( EventObject < 0 )
    goto LABEL_78;
  if ( (*v13 & 1) == 0 )
  {
    if ( v12 )
    {
      v63 = *((_QWORD *)this + 89);
      v64 = 0;
      if ( *(_QWORD *)(v63 + 176) == *(_QWORD *)v12 )
      {
        v65 = *(_DWORD *)(v63 + 192);
        if ( v65 == *((_DWORD *)v12 + 4)
          && (!v65 || !memcmp(*(const void **)(v63 + 184), *((const void **)v12 + 1), v65)) )
        {
          v64 = 1;
        }
      }
      if ( !v64 )
      {
        EventObject = -1073741496;
        goto LABEL_78;
      }
    }
    v16 = 0;
    goto LABEL_9;
  }
  if ( *((_QWORD *)this + 6) && !*((_QWORD *)this + 41) )
  {
    v48 = 2 * ((unsigned __int64)*((unsigned __int16 *)this + 20) >> 1);
    if ( !is_mul_ok((unsigned __int64)*((unsigned __int16 *)this + 20) >> 1, 2u) )
      v48 = -1;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v48, 0x73666C43u);
    *((_QWORD *)this + 41) = PoolWithTag;
    if ( !PoolWithTag )
      goto LABEL_77;
    v50 = *((unsigned __int16 *)this + 20);
    *((_WORD *)this + 160) = v50;
    *((_WORD *)this + 161) = v50;
    memset(PoolWithTag, 0, v50);
    RtlCopyUnicodeString((PUNICODE_STRING)this + 20, (PCUNICODE_STRING)((char *)this + 40));
    _InterlockedExchange64((volatile __int64 *)this + 6, *((_QWORD *)this + 41));
  }
  EventObject = CClfsLogFcbPhysical::CreateBaseFileName((PCUNICODE_STRING)((char *)this + 40), &Destination);
  if ( EventObject < 0 )
    goto LABEL_78;
  if ( *((_QWORD *)this + 89) )
    KeBugCheckEx(0xC1F5u, 0x2Du, (ULONG_PTR)this, 0, 0);
  v22 = (CClfsBaseFilePersisted *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceExtension);
  if ( v22 )
    v23 = CClfsBaseFilePersisted::CClfsBaseFilePersisted(v22, FileObject->DeviceObject);
  else
    v23 = 0;
  *((_QWORD *)this + 89) = v23;
  if ( !v23 )
    goto LABEL_77;
  v72 = 1;
  CClfsBaseFile::AddRef(v23);
  EventObject = CClfsBaseFilePersisted::OpenImage(
                  *((CClfsBaseFilePersisted **)this + 89),
                  &Destination,
                  (const struct _CLFS_FILTER_CONTEXT *)&v83,
                  a10,
                  (unsigned __int8 *)&v85);
  if ( EventObject < 0 )
  {
LABEL_78:
    v16 = 0;
    goto LABEL_13;
  }
  v24 = *(_DWORD *)v13;
  if ( (_BYTE)v85 )
    v25 = v24 | 0x800;
  else
    v25 = v24 & 0xFFFFF7FF;
  *(_DWORD *)v13 = v25;
  *((_BYTE *)this + 689) = CClfsBaseFile::GetUsn(*((CClfsBaseFile **)this + 89));
  v26 = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x68u, 0x73666C43u);
  *((_QWORD *)this + 176) = v26;
  if ( !v26 )
  {
LABEL_77:
    EventObject = -1073741670;
    goto LABEL_78;
  }
  ExInitializeResourceLite(v26);
  EventObject = ClfsCreateEventObject(v27, (struct _KEVENT **)this + 170);
  if ( EventObject < 0 )
    goto LABEL_78;
  KeClearEvent(*((PRKEVENT *)this + 170));
  v28 = FileObject;
  *((_QWORD *)this + 70) = FileObject->DeviceObject;
  WorkItem = IoAllocateWorkItem(v28->DeviceObject);
  *((_QWORD *)this + 174) = WorkItem;
  if ( !WorkItem )
    goto LABEL_77;
  CClfsBaseFile::AcquireClientContext(*((CClfsBaseFile **)this + 89), 0, &v74);
  if ( !v74 )
  {
    EventObject = -1072037875;
    goto LABEL_78;
  }
  v30 = v74;
  v31 = *((_WORD *)v74 + 5);
  *((_WORD *)this + 188) = v31;
  *((_DWORD *)this + 329) = *((_DWORD *)v30 + 3);
  if ( (a10 & 0x200) != 0 )
    *((_WORD *)this + 188) = v31 | 2;
  v32 = v74;
  if ( (*((_BYTE *)v74 + 120) & 0x20) == 0
    || (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
  {
    v45 = v74;
    *((_QWORD *)this + 54) = *((_QWORD *)v74 + 4);
    *((_QWORD *)this + 55) = *((_QWORD *)v45 + 5);
    *((_QWORD *)this + 56) = *((_QWORD *)v45 + 6);
    *((_QWORD *)this + 59) = 0;
    *((_QWORD *)this + 173) = *((_QWORD *)v45 + 7);
    *((_QWORD *)this + 62) = *((_QWORD *)v45 + 8);
    *((_QWORD *)this + 61) = *((_QWORD *)v45 + 9);
    *((_QWORD *)this + 63) = *((_QWORD *)v45 + 10);
    *((_QWORD *)this + 64) = *((_QWORD *)v45 + 11);
    *((_DWORD *)this + 95) = *((_DWORD *)v45 + 4);
    v73 = *((_BYTE *)v32 + 120);
    v75 = v73;
    v46 = (CLFS_LSN *)((char *)this + 1368);
    if ( this == (CClfsLogFcbPhysical *)-1368LL || CLFS_LSN_INVALID.ullOffset != v46->ullOffset )
      KeBugCheckEx(0xC1F5u, 0x2Eu, *((unsigned int *)this + 343), v46->offset.idxRecord, (ULONG_PTR)this);
    *v46 = *(CLFS_LSN *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, __int64 *))(*(_QWORD *)this + 352LL))(
                          this,
                          &v85);
    if ( ClfsLsnRecordSequence((const CLFS_LSN *)this + 171) )
    {
      v51 = ClfsLsnBlockOffset((const CLFS_LSN *)this + 171);
      v52 = ClfsLsnContainer((const CLFS_LSN *)this + 171);
      *v46 = ClfsLsnCreate(v52, v51, 0);
    }
  }
  else
  {
    CClfsLogFcbPhysical::ResetLog(this);
    *(_DWORD *)v13 |= 0x40u;
  }
  CClfsBaseFile::ReleaseClientContext(*((CClfsBaseFile **)this + 89), &v74);
  v33 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x73666C43u);
  *((_QWORD *)this + 119) = v33;
  if ( !v33 )
    goto LABEL_77;
  v33[1] = v33;
  *v33 = v33;
  v34 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 120) = v34;
  if ( !v34 )
    goto LABEL_77;
  KeInitializeSpinLock(v34);
  v35 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x73666C43u);
  *((_QWORD *)this + 705) = v35;
  if ( !v35 )
    goto LABEL_77;
  v35[1] = v35;
  *v35 = v35;
  v36 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 706) = v36;
  if ( !v36 )
    goto LABEL_77;
  KeInitializeSpinLock(v36);
  v37 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 124) = v37;
  if ( !v37 )
    goto LABEL_77;
  KeInitializeSpinLock(v37);
  v38 = (struct _KEVENT *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x38u, 0x73666C43u);
  *((_QWORD *)this + 136) = v38;
  if ( !v38 )
    goto LABEL_77;
  v38->Header.LockNV = 1;
  v38->Header.WaitListHead.Flink = 0;
  LODWORD(v38->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(v38 + 1, SynchronizationEvent, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
    goto LABEL_39;
  v53 = *((_QWORD *)this + 88);
  if ( v53 )
    KeBugCheckEx(0xC1F5u, 0x2Fu, v53, (ULONG_PTR)this, 0);
  v54 = (unsigned __int8 *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
  *((_QWORD *)this + 88) = v54;
  if ( !v54 )
    goto LABEL_77;
  ClfsInitializeOwnerPage(v54, *(_DWORD *)(*((_QWORD *)this + 89) + 144LL));
  *((_DWORD *)this + 328) = 1016;
  v55 = (union _CLS_LSN *)ExAllocatePoolWithTag(PagedPool, 0x3E0u, 0x73666C43u);
  v11 = v55;
  if ( !v55 )
    goto LABEL_77;
  EventObject = CClfsBaseFile::LoadClientBaseLsn(*((CClfsBaseFile **)this + 89), v55, v56, v77);
  if ( EventObject < 0 )
    goto LABEL_48;
  EventObject = CDynamicLsnQ::Initialize((CClfsLogFcbPhysical *)((char *)this + 5576), v11, v57);
  if ( EventObject < 0 )
    goto LABEL_48;
  ExFreePoolWithTag(v11, 0);
  v11 = 0;
  if ( *((_DWORD *)this + 1396) )
    *((_QWORD *)this + 61) = *(_QWORD *)CDynamicLsnQ::TopLsn((CClfsLogFcbPhysical *)((char *)this + 5576)).ullOffset;
LABEL_39:
  FileObject->FsContext = (char *)this + 56;
  v39 = CClfsBaseFile::ContainerCount(*((CClfsBaseFile **)this + 89));
  v40 = v39;
  LODWORD(v85) = v39;
  v41 = (CClfsBaseFilePersisted *)*((_QWORD *)this + 89);
  v42 = *(union _CLS_LSN *)((char *)this + 512);
  v43 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 76) + 64LL))((char *)this + 608);
  EventObject = CClfsBaseFilePersisted::LoadContainerQ(
                  v41,
                  (unsigned int *const)this + 356,
                  0x400u,
                  (*((_BYTE *)this + 376) & 2) != 0,
                  v43,
                  v42,
                  (unsigned int *)this + 355,
                  (unsigned int *)this + 354,
                  &v79);
  if ( EventObject < 0 )
    goto LABEL_48;
  if ( (_DWORD)v40 )
  {
    v69 = 1;
    *((_QWORD *)this + 87) = v79;
  }
  if ( (v73 & 8) != 0 )
  {
    CClfsLogFcbPhysical::DeleteBaseFileAndContainers(this);
    v69 = 0;
    EventObject = -1073741533;
    goto LABEL_78;
  }
  if ( (_DWORD)v40 )
  {
    StreamFileObjectLite = IoCreateStreamFileObjectLite(0, *((PDEVICE_OBJECT *)this + 70));
    Object = StreamFileObjectLite;
    CClfsLogFcbCommon::SetFileObject(this, StreamFileObjectLite, 0);
    (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 64LL))(this);
    EventObject = (**(__int64 (__fastcall ***)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, CClfsLogFcbPhysical *))this)(
                    this,
                    StreamFileObjectLite,
                    this);
    if ( EventObject < 0 )
      goto LABEL_48;
    v70 = 1;
    v85 = *((_QWORD *)this + 87) * v40;
    v78 = v85;
    EventObject = CClfsLogFcbPhysical::SetCacheFileSizes(this, StreamFileObjectLite, &v78, &v85);
    if ( EventObject < 0 )
      goto LABEL_48;
    EventObject = CClfsLogFcbPhysical::RecoverTruncateLog(this, StreamFileObjectLite);
    if ( EventObject < 0 )
      goto LABEL_48;
    if ( !(*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
    {
      if ( (*(_DWORD *)v13 & 0x40) == 0 )
      {
        EventObject = CClfsLogFcbPhysical::FindEndOfLog(this, StreamFileObjectLite, (const union _CLS_LSN *)this + 61);
        if ( EventObject < 0 )
          goto LABEL_48;
      }
      *((_QWORD *)this + 171) = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, __int64 *))(*(_QWORD *)this + 352LL))(
                                             this,
                                             &v85);
      if ( ClfsLsnRecordSequence((const CLFS_LSN *)this + 171) )
      {
        v58 = ClfsLsnBlockOffset((const CLFS_LSN *)this + 171);
        v59 = ClfsLsnContainer((const CLFS_LSN *)this + 171);
        *((CLFS_LSN *)this + 171) = ClfsLsnCreate(v59, v58, 0);
      }
      goto LABEL_56;
    }
    EventObject = CClfsLogFcbPhysical::RebuildOwnerPage(this, StreamFileObjectLite);
    if ( EventObject >= 0 )
    {
      *((_QWORD *)this + 171) = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, __int64 *))(*(_QWORD *)this + 352LL))(
                                             this,
                                             &v85);
      if ( ClfsLsnRecordSequence((const CLFS_LSN *)this + 171) )
      {
        v61 = ClfsLsnBlockOffset((const CLFS_LSN *)this + 171);
        v62 = ClfsLsnContainer((const CLFS_LSN *)this + 171);
        *((CLFS_LSN *)this + 171) = ClfsLsnCreate(v62, v61, 0);
      }
      CClfsLogFcbPhysical::PurgeCacheSection(this, (CLFS_LSN *)&CLFS_LSN_NULL, (CLFS_LSN *)&CLFS_LSN_NULL, v60);
LABEL_56:
      *((_QWORD *)this + 57) = *((_QWORD *)this + 87) * v40;
      *((_QWORD *)this + 58) = CClfsLogFcbPhysical::CalculateAvailableFreeSpace(this);
      *(_QWORD *)v77 = *((_QWORD *)this + 87) * v40;
      v81 = CClfsLogFcbPhysical::LsnToCacheOffset(this, (const union _CLS_LSN *)this + 60);
      v16 = StreamFileObjectLite;
      EventObject = CClfsLogFcbPhysical::SetCacheFileSizes(this, StreamFileObjectLite, &v81, (const __int64 *)v77);
      if ( EventObject < 0 )
        goto LABEL_13;
      goto LABEL_57;
    }
LABEL_48:
    v16 = Object;
    goto LABEL_13;
  }
  v16 = 0;
LABEL_57:
  if ( !CClfsLogFcbCommon::IsReadOnly(this) && (*(_DWORD *)v13 & 0x40) != 0 )
  {
    EventObject = (*(__int64 (**)(void))(*(_QWORD *)this + 112LL))();
    if ( EventObject < 0 )
      goto LABEL_13;
    *(_DWORD *)v13 &= ~0x40u;
  }
LABEL_9:
  v17 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 76) + 64LL))((char *)this + 608);
  v18 = DesiredAccess;
  if ( v17 )
  {
    LOBYTE(v68) = 1;
    LOBYTE(v67) = a7;
    EventObject = (*(__int64 (__fastcall **)(char *, struct _SECURITY_SUBJECT_CONTEXT *, _QWORD, _QWORD, struct _ACCESS_STATE *, int, int))(*((_QWORD *)this + 76) + 400LL))(
                    (char *)this + 608,
                    v86,
                    DesiredAccess,
                    a6->PreviouslyGrantedAccess,
                    a6,
                    v67,
                    v68);
    v11 = 0;
    if ( EventObject < 0 )
      goto LABEL_13;
  }
  if ( CClfsLogFcbCommon::IsReadOnly(this) && (v18 & 0x10006) != 0 )
  {
    EventObject = -1073741790;
    v11 = 0;
    goto LABEL_13;
  }
  v19 = (*(__int64 (**)(void))(*(_QWORD *)this + 344LL))();
  v20 = (struct _SHARE_ACCESS *)((char *)this + 336);
  if ( v19 )
  {
    EventObject = IoCheckShareAccess(v18, DesiredShareAccess, FileObject, v20, 0);
    v11 = 0;
LABEL_13:
    v21 = FileObject;
    goto LABEL_110;
  }
  v21 = FileObject;
  IoSetShareAccess(v18, DesiredShareAccess, FileObject, v20);
  EventObject = 0;
  v11 = 0;
LABEL_110:
  if ( EventObject >= 0 )
    CClfsLogFcbCommon::AddHandleRef(this);
  if ( Destination.Buffer )
    CClfsLogFcbPhysical::DestroyBaseFileName(&Destination);
  if ( EventObject >= 0 )
    (**(void (__fastcall ***)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, CClfsLogFcbPhysical *))this)(
      this,
      v21,
      this);
  if ( v16 )
  {
    if ( v70 )
      (*(void (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *))(*(_QWORD *)this + 8LL))(this, v16);
    ObfDereferenceObject(v16);
  }
  if ( EventObject < 0 )
  {
    if ( EventObject == -1073741202 )
    {
      *v80 |= 0x41000u;
      if ( !*((_DWORD *)this + 149) )
      {
        *((_DWORD *)this + 149) = 1;
        *((_DWORD *)this + 150) = -1073741202;
      }
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slid(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          16,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::Initialize",
          207,
          (char)this,
          110);
      }
    }
    if ( v72 )
    {
      if ( v69 )
        CClfsLogFcbPhysical::CloseContainers(this);
      CClfsBaseFile::Release(*((CClfsBaseFile **)this + 89));
      *((_QWORD *)this + 89) = 0;
    }
    if ( (char *)this + 56 == v21->FsContext )
      CClfsLogFcbPhysical::TearDownOpen(this, v21);
  }
  else
  {
    *v80 = *v80 & 0xFFFFFFFA | 4;
  }
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v74 )
    CClfsBaseFile::ReleaseClientContext(*((CClfsBaseFile **)this + 89), &v74);
  if ( (_BYTE)a8 )
    ClfsReleaseResourceLite(v82);
  return (unsigned int)EventObject;
}

```

## disassembly

```asm
0x140005f1c  mov     rax, rsp
0x140005f1f  mov     [rax+20h], r9d
0x140005f23  mov     [rax+18h], r8
0x140005f27  mov     [rax+10h], rdx
0x140005f2b  mov     [rax+8], rcx
0x140005f2f  push    rbx
0x140005f30  push    rsi
0x140005f31  push    rdi
0x140005f32  push    r12
0x140005f34  push    r13
0x140005f36  push    r14
0x140005f38  push    r15
0x140005f3a  sub     rsp, 0E0h
0x140005f41  mov     rsi, rcx
0x140005f44  xor     r14d, r14d
0x140005f47  mov     [rax-98h], r14
0x140005f4e  mov     [rax-90h], r14
0x140005f55  mov     [rax-78h], r14
0x140005f59  xorps   xmm0, xmm0
0x140005f5c  movdqu  xmmword ptr [rax-58h], xmm0
0x140005f61  mov     [rax-48h], r14
0x140005f65  mov     r15d, r14d
0x140005f68  mov     [rsp+118h+var_B0], r14
0x140005f6d  mov     [rsp+118h+var_A8], r14
0x140005f72  mov     [rsp+118h+Object], r14
0x140005f77  mov     [rsp+118h+var_C8], r14d
0x140005f7c  mov     [rax-88h], r14d
0x140005f83  mov     [rsp+118h+var_B6], r14b
0x140005f88  mov     [rsp+118h+var_B8], r14b
0x140005f8d  mov     [rsp+118h+var_B7], r14b
0x140005f92  mov     [rax+10h], r14b
0x140005f96  mov     [rsp+118h+var_C4], r14b
0x140005f9b  mov     [rsp+118h+var_C3], r14b
0x140005fa0  mov     rdi, [rsp+118h+arg_38]
0x140005fa8  test    rdi, rdi
0x140005fab  jnz     loc_140006D9A
0x140005fb1  lea     rax, [rcx+0C8h]
0x140005fb8  mov     [rsp+118h+var_60], rax
0x140005fc0  mov     dl, 1; Wait
0x140005fc2  mov     rcx, rax; Resource
0x140005fc5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005fcc  nop     dword ptr [rax+rax+00h]
0x140005fd1  mov     byte ptr [rsp+118h+arg_38], al
0x140005fd8  mov     [rsp+118h+var_B7], al
0x140005fdc  cmp     [rsi+3B0h], r14d
0x140005fe3  jnz     loc_14000685A
0x140005fe9  lea     r12, [rsi+16Ch]
0x140005ff0  mov     [rsp+118h+var_80], r12
0x140005ff8  mov     [rsp+118h+var_70], r12
0x140006000  mov     r8d, [r12]
0x140006004  bt      r8d, 0Ch
0x140006009  jb      loc_14000687A
0x14000600f  mov     rdx, [rsp+118h+FileObject]; struct _FILE_OBJECT *
0x140006017  mov     rcx, rsi; this
0x14000601a  call    ?Open@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@@Z; CClfsLogFcbPhysical::Open(_FILE_OBJECT *)
0x14000601f  mov     ebx, eax
0x140006021  mov     [rsp+118h+var_C8], eax
0x140006025  test    eax, eax
0x140006027  js      loc_140006977
0x14000602d  test    byte ptr [r12], 1
0x140006032  jnz     loc_1400060E8
0x140006038  test    rdi, rdi
0x14000603b  jnz     loc_140006C39
0x140006041  mov     r13, [rsp+118h+Object]
0x140006046  lea     rbx, [rsi+260h]
0x14000604d  mov     rax, [rbx]
0x140006050  mov     rax, [rax+40h]
0x140006054  mov     rcx, rbx
0x140006057  call    _guard_dispatch_icall
0x14000605c  mov     edi, [rsp+118h+DesiredAccess]
0x140006063  test    al, al
0x140006065  jnz     loc_140006617
0x14000606b  mov     rcx, rsi; this
0x14000606e  call    ?IsReadOnly@CClfsLogFcbCommon@@QEBAEXZ; CClfsLogFcbCommon::IsReadOnly(void)
0x140006073  test    al, al
0x140006075  jnz     loc_140006C8C
0x14000607b  lea     rbx, [rsi+150h]
0x140006082  mov     rax, [rsi]
0x140006085  mov     rax, [rax+158h]
0x14000608c  call    _guard_dispatch_icall
0x140006091  mov     r9, rbx; ShareAccess
0x140006094  mov     edx, [rsp+118h+DesiredShareAccess]; DesiredShareAccess
0x14000609b  mov     ecx, edi; DesiredAccess
0x14000609d  test    al, al
0x14000609f  jz      loc_140006CAE
0x1400060a5  mov     [rsp+118h+Update], r14b; Update
0x1400060aa  mov     r8, [rsp+118h+FileObject]; FileObject
0x1400060b2  call    cs:__imp_IoCheckShareAccess
0x1400060b9  nop     dword ptr [rax+rax+00h]
0x1400060be  mov     ebx, eax
0x1400060c0  mov     [rsp+118h+var_C8], eax
0x1400060c4  mov     r15, r14
0x1400060c7  mov     [rsp+118h+var_B0], r14
0x1400060cc  test    eax, eax
0x1400060ce  jns     loc_140006CA4
0x1400060d4  lea     rdi, WPP_GLOBAL_Control
0x1400060db  mov     r12, [rsp+118h+FileObject]
0x1400060e3  jmp     loc_140006CDB
0x1400060e8  cmp     [rsi+30h], r14
0x1400060ec  jnz     loc_1400068CD
0x1400060f2  mov     edi, 73666C43h
0x1400060f7  mov     r13d, 200h
0x1400060fd  lea     rcx, [rsi+28h]; Source
0x140006101  lea     rdx, [rsp+118h+Destination]; Destination
0x140006109  call    ?CreateBaseFileName@CClfsLogFcbPhysical@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsLogFcbPhysical::CreateBaseFileName(_UNICODE_STRING const &,_UNICODE_STRING &)
0x14000610e  mov     ebx, eax
0x140006110  mov     [rsp+118h+var_C8], eax
0x140006114  test    eax, eax
0x140006116  js      loc_140006977
0x14000611c  cmp     [rsi+2C8h], r14
0x140006123  jnz     loc_140006988
0x140006129  lea     rcx, WPP_MAIN_CB.DeviceExtension; Lookaside
0x140006130  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140006137  nop     dword ptr [rax+rax+00h]
0x14000613c  test    rax, rax
0x14000613f  jz      loc_140006670
0x140006145  mov     rcx, [rsp+118h+FileObject]
0x14000614d  mov     rdx, [rcx+8]; struct _DEVICE_OBJECT *
0x140006151  mov     rcx, rax; this
0x140006154  call    ??0CClfsBaseFilePersisted@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsBaseFilePersisted::CClfsBaseFilePersisted(_DEVICE_OBJECT *)
0x140006159  mov     [rsi+2C8h], rax
0x140006160  test    rax, rax
0x140006163  jz      loc_140006967
0x140006169  mov     [rsp+118h+var_B8], 1
0x14000616e  mov     rcx, rax; this
0x140006171  call    ?AddRef@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::AddRef(void)
0x140006176  lea     rcx, [rsp+118h+arg_8]
0x14000617e  mov     qword ptr [rsp+118h+Update], rcx; unsigned __int8 *
0x140006183  mov     r9d, [rsp+118h+arg_48]; unsigned int
0x14000618b  lea     r8, [rsp+118h+var_58]; struct _CLFS_FILTER_CONTEXT *
0x140006193  lea     rdx, [rsp+118h+Destination]; struct _UNICODE_STRING *
0x14000619b  mov     rcx, [rsi+2C8h]; this
0x1400061a2  call    ?OpenImage@CClfsBaseFilePersisted@@QEAAJPEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@KAEAE@Z; CClfsBaseFilePersisted::OpenImage(_UNICODE_STRING *,_CLFS_FILTER_CONTEXT const &,ulong,uchar &)
0x1400061a7  mov     ebx, eax
0x1400061a9  mov     [rsp+118h+var_C8], eax
0x1400061ad  test    eax, eax
0x1400061af  js      loc_140006977
0x1400061b5  mov     eax, [r12]
0x1400061b9  cmp     byte ptr [rsp+118h+arg_8], r14b
0x1400061c1  jz      loc_14000678B
0x1400061c7  bts     eax, 0Bh
0x1400061cb  mov     [r12], eax
0x1400061cf  mov     rcx, [rsi+2C8h]; this
0x1400061d6  call    ?GetUsn@CClfsBaseFile@@QEAAEXZ; CClfsBaseFile::GetUsn(void)
0x1400061db  mov     [rsi+2B1h], al
0x1400061e1  mov     r8d, edi; Tag
0x1400061e4  mov     edx, 68h ; 'h'; NumberOfBytes
0x1400061e9  mov     ecx, r13d; PoolType
0x1400061ec  call    cs:__imp_ExAllocatePoolWithTag
0x1400061f3  nop     dword ptr [rax+rax+00h]
0x1400061f8  mov     [rsi+580h], rax
0x1400061ff  test    rax, rax
0x140006202  jz      loc_140006967
0x140006208  mov     rcx, rax; Resource
0x14000620b  call    cs:__imp_ExInitializeResourceLite
0x140006212  nop     dword ptr [rax+rax+00h]
0x140006217  lea     rdx, [rsi+550h]; struct _KEVENT **
0x14000621e  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x140006223  mov     ebx, eax
0x140006225  mov     [rsp+118h+var_C8], eax
0x140006229  test    eax, eax
0x14000622b  js      loc_140006977
0x140006231  mov     rcx, [rsi+550h]; Event
0x140006238  call    cs:__imp_KeClearEvent
0x14000623f  nop     dword ptr [rax+rax+00h]
0x140006244  mov     rcx, [rsp+118h+FileObject]
0x14000624c  mov     rax, [rcx+8]
0x140006250  mov     [rsi+230h], rax
0x140006257  mov     rcx, [rcx+8]; DeviceObject
0x14000625b  call    cs:__imp_IoAllocateWorkItem
0x140006262  nop     dword ptr [rax+rax+00h]
0x140006267  mov     [rsi+570h], rax
0x14000626e  test    rax, rax
0x140006271  jz      loc_140006967
0x140006277  lea     r8, [rsp+118h+var_A8]; struct _CLFS_CLIENT_CONTEXT **
0x14000627c  xor     edx, edx; unsigned __int8
0x14000627e  mov     rcx, [rsi+2C8h]; this
0x140006285  call    ?AcquireClientContext@CClfsBaseFile@@QEAAJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::AcquireClientContext(uchar,_CLFS_CLIENT_CONTEXT * *)
0x14000628a  cmp     [rsp+118h+var_A8], r14
0x14000628f  jz      loc_1400069A8
0x140006295  mov     rcx, [rsp+118h+var_A8]
0x14000629a  movzx   edx, word ptr [rcx+0Ah]
0x14000629e  mov     [rsi+178h], dx
0x1400062a5  mov     eax, [rcx+0Ch]
0x1400062a8  mov     [rsi+524h], eax
0x1400062ae  test    [rsp+118h+arg_48], r13d
0x1400062b6  jnz     loc_1400069AF
0x1400062bc  mov     rbx, [rsp+118h+var_A8]
0x1400062c1  test    byte ptr [rbx+78h], 20h
0x1400062c5  jz      loc_1400067C0
0x1400062cb  mov     rax, [rsi]
0x1400062ce  mov     rax, [rax+138h]
0x1400062d5  mov     rcx, rsi
0x1400062d8  call    _guard_dispatch_icall
0x1400062dd  test    al, al
0x1400062df  jnz     loc_1400067C0
0x1400062e5  mov     rcx, rsi; this
0x1400062e8  call    ?ResetLog@CClfsLogFcbPhysical@@AEAAJXZ; CClfsLogFcbPhysical::ResetLog(void)
0x1400062ed  or      dword ptr [r12], 40h
0x1400062f2  lea     rdx, [rsp+118h+var_A8]; struct _CLFS_CLIENT_CONTEXT **
0x1400062f7  mov     rcx, [rsi+2C8h]; this
0x1400062fe  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x140006303  mov     r8d, edi; Tag
0x140006306  mov     edx, 10h; NumberOfBytes
0x14000630b  mov     ecx, r13d; PoolType
0x14000630e  call    cs:__imp_ExAllocatePoolWithTag
0x140006315  nop     dword ptr [rax+rax+00h]
0x14000631a  mov     [rsi+3B8h], rax
0x140006321  test    rax, rax
0x140006324  jz      loc_140006967
0x14000632a  mov     [rax+8], rax
0x14000632e  mov     [rax], rax
0x140006331  mov     r8d, edi; Tag
0x140006334  mov     ebx, 8
0x140006339  mov     edx, ebx; NumberOfBytes
0x14000633b  mov     ecx, r13d; PoolType
0x14000633e  call    cs:__imp_ExAllocatePoolWithTag
0x140006345  nop     dword ptr [rax+rax+00h]
0x14000634a  mov     [rsi+3C0h], rax
0x140006351  test    rax, rax
0x140006354  jz      loc_140006967
0x14000635a  mov     rcx, rax; SpinLock
0x14000635d  call    cs:__imp_KeInitializeSpinLock
0x140006364  nop     dword ptr [rax+rax+00h]
0x140006369  mov     r8d, edi; Tag
0x14000636c  lea     edx, [rbx+8]; NumberOfBytes
0x14000636f  mov     ecx, r13d; PoolType
0x140006372  call    cs:__imp_ExAllocatePoolWithTag
0x140006379  nop     dword ptr [rax+rax+00h]
0x14000637e  mov     [rsi+1608h], rax
0x140006385  test    rax, rax
0x140006388  jz      loc_140006967
0x14000638e  mov     [rax+8], rax
0x140006392  mov     [rax], rax
0x140006395  mov     r8d, edi; Tag
0x140006398  mov     edx, ebx; NumberOfBytes
0x14000639a  mov     ecx, r13d; PoolType
0x14000639d  call    cs:__imp_ExAllocatePoolWithTag
0x1400063a4  nop     dword ptr [rax+rax+00h]
0x1400063a9  mov     [rsi+1610h], rax
0x1400063b0  test    rax, rax
0x1400063b3  jz      loc_140006967
0x1400063b9  mov     rcx, rax; SpinLock
0x1400063bc  call    cs:__imp_KeInitializeSpinLock
0x1400063c3  nop     dword ptr [rax+rax+00h]
0x1400063c8  mov     r8d, edi; Tag
0x1400063cb  mov     edx, ebx; NumberOfBytes
0x1400063cd  mov     ecx, r13d; PoolType
0x1400063d0  call    cs:__imp_ExAllocatePoolWithTag
0x1400063d7  nop     dword ptr [rax+rax+00h]
0x1400063dc  mov     [rsi+3E0h], rax
0x1400063e3  test    rax, rax
0x1400063e6  jz      loc_140006967
0x1400063ec  mov     rcx, rax; SpinLock
0x1400063ef  call    cs:__imp_KeInitializeSpinLock
0x1400063f6  nop     dword ptr [rax+rax+00h]
0x1400063fb  mov     r8d, edi; Tag
0x1400063fe  lea     edx, [rbx+30h]; NumberOfBytes
0x140006401  mov     ecx, r13d; PoolType
0x140006404  call    cs:__imp_ExAllocatePoolWithTag
0x14000640b  nop     dword ptr [rax+rax+00h]
0x140006410  mov     [rsi+440h], rax
0x140006417  test    rax, rax
0x14000641a  jz      loc_140006967
0x140006420  mov     ebx, 1
0x140006425  mov     [rax], ebx
0x140006427  mov     [rax+8], r14
0x14000642b  mov     [rax+10h], r14d
0x14000642f  lea     rcx, [rax+18h]; Event
0x140006433  xor     r8d, r8d; State
0x140006436  mov     edx, ebx; Type
0x140006438  call    cs:__imp_KeInitializeEvent
0x14000643f  nop     dword ptr [rax+rax+00h]
0x140006444  mov     rax, [rsi]
0x140006447  mov     rax, [rax+138h]
0x14000644e  mov     rcx, rsi
0x140006451  call    _guard_dispatch_icall
0x140006456  test    al, al
0x140006458  jnz     loc_140006A42
0x14000645e  lea     rax, [rsi+38h]
0x140006462  mov     rcx, [rsp+118h+FileObject]
0x14000646a  mov     [rcx+18h], rax
0x14000646e  mov     rcx, [rsi+2C8h]; this
0x140006475  call    ?ContainerCount@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::ContainerCount(void)
0x14000647a  mov     r13d, eax
0x14000647d  mov     dword ptr [rsp+118h+arg_8], r13d
0x140006485  mov     rdi, [rsi+2C8h]
0x14000648c  mov     rbx, [rsi+200h]
0x140006493  lea     rcx, [rsi+260h]
0x14000649a  mov     rax, [rcx]
0x14000649d  mov     rax, [rax+40h]
0x1400064a1  call    _guard_dispatch_icall
0x1400064a6  mov     r10b, al
0x1400064a9  lea     rax, [rsi+588h]
0x1400064b0  lea     r8, [rsi+58Ch]
0x1400064b7  mov     r9b, [rsi+178h]
0x1400064be  shr     r9b, 1
0x1400064c1  and     r9b, 1; unsigned __int8
0x1400064c5  lea     rdx, [rsi+590h]; unsigned int *
0x1400064cc  lea     rcx, [rsp+118h+var_78]
  ... truncated ...
```
