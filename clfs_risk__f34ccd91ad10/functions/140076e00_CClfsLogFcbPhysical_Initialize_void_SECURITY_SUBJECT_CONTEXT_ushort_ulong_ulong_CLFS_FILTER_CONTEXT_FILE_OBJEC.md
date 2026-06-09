# CClfsLogFcbPhysical::Initialize(void *,_SECURITY_SUBJECT_CONTEXT &,ushort,ulong,ulong,_CLFS_FILTER_CONTEXT *,_FILE_OBJECT *,ulong)

- ea: `0x140076e00`
- end: `0x1400777f7`
- name: `?Initialize@CClfsLogFcbPhysical@@QEAAJPEAXAEAU_SECURITY_SUBJECT_CONTEXT@@GKKPEAU_CLFS_FILTER_CONTEXT@@PEAU_FILE_OBJECT@@K@Z`
- size: `2551`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, void *@<rdx>, struct _SECURITY_SUBJECT_CONTEXT *@<r8>, unsigned __int16@<r9w>, ACCESS_MASK DesiredAccess, ULONG DesiredShareAccess, struct _CLFS_FILTER_CONTEXT *, struct _FILE_OBJECT *, unsigned int)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006d048`

## callees

- `0x140003590`
- `0x140005840`
- `0x140005f00`
- `0x140006ebc`
- `0x140007470`
- `0x1400075b0`
- `0x14000a8e0`
- `0x14000dfa4`
- `0x14000e46c`
- `0x14000ed64`
- `0x14000f1f0`
- `0x14000fa48`
- `0x1400121e4`
- `0x140017f20`
- `0x140018280`
- `0x1400374cc`
- `0x14005ed70`
- `0x140062980`
- `0x140062a30`
- `0x140062df0`
- `0x140063c24`
- `0x140066e00`
- `0x140067060`
- `0x1400677b8`
- `0x140073dd0`
- `0x140075704`
- `0x140075cd4`
- `0x140075e08`
- `0x140076c00`
- `0x140076e00`
- `0x140078034`
- `0x1400787ec`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140077161`
- `ntoskrnl!ExInitializeResourceLite` at `0x140077161`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140076ea4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140076ea4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140076fff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140076fff`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400774cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400774cd`
- `ntoskrnl!KeClearEvent` at `0x14007718e`
- `ntoskrnl!KeClearEvent` at `0x14007718e`
- `ntoskrnl!KeInitializeEvent` at `0x140077310`
- `ntoskrnl!KeInitializeEvent` at `0x140077310`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140077046`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140077046`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077231`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007728e`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400772c0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077231`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007728e`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400772c0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400771b9`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400771b9`
- `ntoskrnl!IoCheckShareAccess` at `0x14007764c`
- `ntoskrnl!IoCheckShareAccess` at `0x14007764c`
- `ntoskrnl!IoSetShareAccess` at `0x140077678`
- `ntoskrnl!IoSetShareAccess` at `0x140077678`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007759a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400777c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c981`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007759a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400777c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c981`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140076fb8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077142`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400771e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077212`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077245`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007726f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400772a1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400772d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077513`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140076fb8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077142`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400771e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077212`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077245`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007726f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400772a1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400772d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140077513`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::Initialize(
        CClfsLogFcbPhysical *this,
        void *a2,
        struct _SECURITY_SUBJECT_CONTEXT *a3,
        __int16 a4,
        ACCESS_MASK DesiredAccess,
        ULONG DesiredShareAccess,
        struct _CLFS_FILTER_CONTEXT *a7,
        struct _FILE_OBJECT *FileObject,
        unsigned int a9)
{
  union _CLS_LSN *v11; // r14
  NTSTATUS EventObject; // ebx
  struct _FILE_OBJECT *v13; // r13
  int v14; // r8d
  SIZE_T v15; // rax
  PVOID PoolWithTag; // rax
  size_t v17; // r8
  volatile signed __int32 *v18; // rax
  int v19; // eax
  unsigned int v20; // eax
  struct _ERESOURCE *v21; // rax
  enum _EVENT_TYPE v22; // ecx
  PDEVICE_OBJECT DeviceObject; // rax
  PIO_WORKITEM WorkItem; // rax
  _QWORD *v25; // rax
  KSPIN_LOCK *v26; // rax
  _QWORD *v27; // rax
  KSPIN_LOCK *v28; // rax
  KSPIN_LOCK *v29; // rax
  struct _KEVENT *v30; // rax
  CClfsBaseFilePersisted *v31; // rdi
  char v32; // al
  CLFS_LSN *v33; // rcx
  ULONG v34; // ebx
  CLFS_CONTAINER_ID v35; // eax
  unsigned __int8 *v36; // rax
  union _CLS_LSN *v37; // rax
  unsigned int v38; // r8d
  unsigned int v39; // r8d
  char v41; // [rsp+54h] [rbp-94h]
  BOOLEAN v42; // [rsp+55h] [rbp-93h]
  char v43; // [rsp+56h] [rbp-92h]
  char v44; // [rsp+57h] [rbp-91h]
  struct _CLFS_CLIENT_CONTEXT *v45; // [rsp+60h] [rbp-88h] BYREF
  UNICODE_STRING Destination; // [rsp+68h] [rbp-80h] BYREF
  unsigned int v47; // [rsp+78h] [rbp-70h] BYREF
  unsigned __int64 v48; // [rsp+80h] [rbp-68h] BYREF
  char *v49; // [rsp+88h] [rbp-60h]
  __int128 v50; // [rsp+90h] [rbp-58h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-48h]
  struct _SECURITY_SUBJECT_CONTEXT *v53; // [rsp+100h] [rbp+18h] BYREF

  v53 = a3;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  v48 = 0;
  v11 = 0;
  v45 = 0;
  v50 = 0;
  v51 = 0;
  v47 = 0;
  v44 = 0;
  v43 = 0;
  LOBYTE(v53) = 0;
  v41 = 0;
  if ( a7 )
  {
    v50 = *(_OWORD *)a7;
    v51 = *((_QWORD *)a7 + 2);
  }
  v49 = (char *)this + 200;
  v42 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  if ( (a4 & 6) != 0 )
  {
    EventObject = -1073741811;
    v13 = FileObject;
    goto LABEL_59;
  }
  v14 = *((_DWORD *)this + 91);
  if ( (v14 & 0x1000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        17,
        (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
        (unsigned int)"CClfsLogFcbPhysical::Initialize",
        153,
        v14);
    }
    EventObject = -1072037845;
    v13 = FileObject;
    goto LABEL_59;
  }
  v13 = FileObject;
  EventObject = CClfsLogFcbPhysical::Open(this, FileObject);
  if ( EventObject < 0 )
    goto LABEL_59;
  if ( (*((_BYTE *)this + 364) & 1) == 0 )
  {
    EventObject = -1073741771;
    goto LABEL_59;
  }
  if ( *((_QWORD *)this + 6) && !*((_QWORD *)this + 41) )
  {
    v15 = 2 * ((unsigned __int64)*((unsigned __int16 *)this + 20) >> 1);
    if ( !is_mul_ok((unsigned __int64)*((unsigned __int16 *)this + 20) >> 1, 2u) )
      v15 = -1;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v15, 0x73666C43u);
    *((_QWORD *)this + 41) = PoolWithTag;
    if ( !PoolWithTag )
      goto LABEL_18;
    v17 = *((unsigned __int16 *)this + 20);
    *((_WORD *)this + 160) = v17;
    *((_WORD *)this + 161) = v17;
    memset(PoolWithTag, 0, v17);
    RtlCopyUnicodeString((PUNICODE_STRING)this + 20, (PCUNICODE_STRING)((char *)this + 40));
    _InterlockedExchange64((volatile __int64 *)this + 6, *((_QWORD *)this + 41));
  }
  EventObject = CClfsLogFcbPhysical::CreateBaseFileName((PCUNICODE_STRING)((char *)this + 40), &Destination);
  if ( EventObject < 0 )
    goto LABEL_59;
  v18 = (volatile signed __int32 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceExtension);
  if ( v18 )
    v18 = (volatile signed __int32 *)CClfsBaseFilePersisted::CClfsBaseFilePersisted(
                                       (CClfsBaseFilePersisted *)v18,
                                       v13->DeviceObject);
  *((_QWORD *)this + 89) = v18;
  if ( !v18 )
    goto LABEL_18;
  v44 = 1;
  _InterlockedIncrement(v18 + 2);
  EventObject = CClfsBaseFilePersisted::CreateImage(
                  *((CClfsBaseFilePersisted **)this + 89),
                  &Destination,
                  0x10000u,
                  (a4 & 0x100) == 0,
                  (const struct _CLFS_FILTER_CONTEXT *)&v50,
                  a2,
                  a9,
                  (unsigned __int8 *)&v53);
  if ( EventObject < 0 )
    goto LABEL_59;
  v43 = 1;
  v19 = *((_DWORD *)this + 91);
  if ( (_BYTE)v53 )
    v20 = v19 | 0x800;
  else
    v20 = v19 & 0xFFFFF7FF;
  *((_DWORD *)this + 91) = v20;
  *((_BYTE *)this + 689) = CClfsBaseFile::GetUsn(*((CClfsBaseFile **)this + 89));
  *((_WORD *)this + 188) = a4;
  if ( (a9 & 0x200) != 0 )
    *((_WORD *)this + 188) = a4 | 2;
  v21 = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x68u, 0x73666C43u);
  *((_QWORD *)this + 176) = v21;
  if ( !v21 )
    goto LABEL_18;
  ExInitializeResourceLite(v21);
  EventObject = ClfsCreateEventObject(v22, (struct _KEVENT **)this + 170);
  if ( EventObject < 0 )
    goto LABEL_59;
  KeClearEvent(*((PRKEVENT *)this + 170));
  DeviceObject = v13->DeviceObject;
  *((_QWORD *)this + 70) = DeviceObject;
  *((_DWORD *)this + 329) = *((_DWORD *)DeviceObject->DeviceExtension + 36);
  WorkItem = IoAllocateWorkItem(v13->DeviceObject);
  *((_QWORD *)this + 174) = WorkItem;
  if ( !WorkItem )
    goto LABEL_18;
  v25 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x73666C43u);
  *((_QWORD *)this + 119) = v25;
  if ( !v25 )
    goto LABEL_18;
  v25[1] = v25;
  *v25 = v25;
  v26 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 120) = v26;
  if ( !v26 )
    goto LABEL_18;
  KeInitializeSpinLock(v26);
  v27 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x73666C43u);
  *((_QWORD *)this + 705) = v27;
  if ( !v27 )
    goto LABEL_18;
  v27[1] = v27;
  *v27 = v27;
  v28 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 706) = v28;
  if ( !v28 )
    goto LABEL_18;
  KeInitializeSpinLock(v28);
  v29 = (KSPIN_LOCK *)ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x73666C43u);
  *((_QWORD *)this + 124) = v29;
  if ( !v29 )
    goto LABEL_18;
  KeInitializeSpinLock(v29);
  v30 = (struct _KEVENT *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x38u, 0x73666C43u);
  *((_QWORD *)this + 136) = v30;
  if ( !v30 )
    goto LABEL_18;
  v30->Header.LockNV = 1;
  v30->Header.WaitListHead.Flink = 0;
  LODWORD(v30->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(v30 + 1, SynchronizationEvent, 0);
  v31 = (CClfsBaseFilePersisted *)*((_QWORD *)this + 89);
  v32 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 76) + 64LL))((char *)this + 608);
  EventObject = CClfsBaseFilePersisted::LoadContainerQ(
                  v31,
                  (unsigned int *const)this + 356,
                  0x400u,
                  (*((_BYTE *)this + 376) & 2) != 0,
                  v32,
                  CLFS_LSN_INVALID,
                  (unsigned int *)this + 355,
                  (unsigned int *)this + 354,
                  &v48);
  if ( EventObject < 0 )
    goto LABEL_59;
  v41 = 1;
  CClfsBaseFile::AcquireClientContext(*((CClfsBaseFile **)this + 89), 0, &v45);
  v33 = (CLFS_LSN *)v45;
  if ( !v45 )
  {
    EventObject = -1072037875;
    goto LABEL_59;
  }
  *((_WORD *)v45 + 5) = *((_WORD *)this + 188);
  v33[4] = *(CLFS_LSN *)((char *)this + 432);
  v33[5] = *(CLFS_LSN *)((char *)this + 440);
  v33[6] = *(CLFS_LSN *)((char *)this + 448);
  v33[7] = *(CLFS_LSN *)((char *)this + 1384);
  v33[8] = *(CLFS_LSN *)((char *)this + 496);
  v33[9] = *(CLFS_LSN *)((char *)this + 488);
  v33[10] = *(CLFS_LSN *)((char *)this + 504);
  v33[11] = *(CLFS_LSN *)((char *)this + 512);
  v33[12] = CLFS_LSN_INVALID;
  v33[1].offset.cidContainer = *((_DWORD *)this + 329);
  v33[2].offset.idxRecord = *((_DWORD *)this + 95);
  *((_QWORD *)this + 171) = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, struct _CLFS_FILTER_CONTEXT **))(*(_QWORD *)this + 352LL))(
                                         this,
                                         &a7);
  if ( ClfsLsnRecordSequence((const CLFS_LSN *)this + 171) )
  {
    v34 = ClfsLsnBlockOffset((const CLFS_LSN *)this + 171);
    v35 = ClfsLsnContainer((const CLFS_LSN *)this + 171);
    *((CLFS_LSN *)this + 171) = ClfsLsnCreate(v35, v34, 0);
  }
  CClfsBaseFile::ReleaseClientContext(*((CClfsBaseFile **)this + 89), &v45);
  if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
  {
    v36 = (unsigned __int8 *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
    *((_QWORD *)this + 88) = v36;
    if ( v36 )
    {
      ClfsInitializeOwnerPage(v36, *(_DWORD *)(*((_QWORD *)this + 89) + 144LL));
      *((_DWORD *)this + 328) = 1016;
      v37 = (union _CLS_LSN *)ExAllocatePoolWithTag(PagedPool, 0x3E0u, 0x73666C43u);
      v11 = v37;
      if ( v37 )
      {
        EventObject = CClfsBaseFile::LoadClientBaseLsn(*((CClfsBaseFile **)this + 89), v37, v38, &v47);
        if ( EventObject < 0 )
          goto LABEL_59;
        EventObject = CDynamicLsnQ::Initialize((CClfsLogFcbPhysical *)((char *)this + 5576), v11, v39);
        if ( EventObject < 0 )
          goto LABEL_59;
        if ( *((_DWORD *)this + 1396) )
          *((_QWORD *)this + 61) = *(_QWORD *)CDynamicLsnQ::TopLsn((CClfsLogFcbPhysical *)((char *)this + 5576)).ullOffset;
        ExFreePoolWithTag(v11, 0);
        goto LABEL_52;
      }
    }
LABEL_18:
    EventObject = -1073741670;
    goto LABEL_59;
  }
LABEL_52:
  a7 = (struct _CLFS_FILTER_CONTEXT *)(*((_QWORD *)this + 87)
                                     * CClfsBaseFile::ContainerCount(*((CClfsBaseFile **)this + 89)));
  v45 = (struct _CLFS_CLIENT_CONTEXT *)CClfsLogFcbPhysical::LsnToCacheOffset(this, (const union _CLS_LSN *)this + 60);
  EventObject = CClfsLogFcbPhysical::SetCacheFileSizes(this, v13, (const __int64 *)&v45, (const __int64 *)&a7);
  v11 = 0;
  if ( EventObject >= 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 344LL))(this)
      && (*((_DWORD *)this + 91) & 6) != 0 )
    {
      EventObject = IoCheckShareAccess(DesiredAccess, DesiredShareAccess, v13, (PSHARE_ACCESS)this + 12, 1u);
    }
    else
    {
      IoSetShareAccess(DesiredAccess, DesiredShareAccess, v13, (PSHARE_ACCESS)this + 12);
      EventObject = 0;
    }
    if ( EventObject >= 0 )
      EventObject = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 112LL))(this);
  }
LABEL_59:
  if ( EventObject < 0 )
  {
    if ( EventObject == -1073741202 )
    {
      *((_DWORD *)this + 91) |= 0x41000u;
      if ( !*((_DWORD *)this + 149) )
      {
        *((_DWORD *)this + 149) = 2;
        *((_DWORD *)this + 150) = -1073741202;
      }
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slid(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          18,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::Initialize",
          191,
          (char)this,
          110);
      }
    }
    if ( v43 )
      CClfsBaseFilePersisted::RemoveImage(*((CClfsBaseFilePersisted **)this + 89));
    if ( v44 )
    {
      if ( v41 )
        CClfsLogFcbPhysical::CloseContainers(this);
      CClfsBaseFile::Release(*((CClfsBaseFile **)this + 89));
      *((_QWORD *)this + 89) = 0;
    }
    if ( (char *)this + 56 == v13->FsContext )
      CClfsLogFcbPhysical::TearDownOpen(this, v13);
  }
  else
  {
    CClfsLogFcbCommon::AddHandleRef(this);
    *((_DWORD *)this + 91) = *((_DWORD *)this + 91) & 0xFFFFFFFC | 2;
  }
  if ( Destination.Buffer )
    CClfsLogFcbPhysical::DestroyBaseFileName(&Destination);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v42 )
    ClfsReleaseResourceLite(v49);
  return (unsigned int)EventObject;
}

```

## disassembly

```asm
0x140076e00  mov     r11, rsp
0x140076e03  mov     [r11+18h], r8
0x140076e07  mov     [r11+10h], rdx
0x140076e0b  mov     [r11+8], rcx
0x140076e0f  push    rbx
0x140076e10  push    rsi
0x140076e11  push    rdi
0x140076e12  push    r12
0x140076e14  push    r13
0x140076e16  push    r14
0x140076e18  push    r15
0x140076e1a  sub     rsp, 0B0h
0x140076e21  movzx   r12d, r9w
0x140076e25  mov     rsi, rcx
0x140076e28  xor     edi, edi
0x140076e2a  mov     [r11-80h], rdi
0x140076e2e  mov     [r11-78h], rdi
0x140076e32  mov     [r11-68h], rdi
0x140076e36  mov     r14d, edi
0x140076e39  mov     [rsp+0E8h+var_90], rdi
0x140076e3e  mov     [rsp+0E8h+var_88], rdi
0x140076e43  xorps   xmm0, xmm0
0x140076e46  movdqu  xmmword ptr [r11-58h], xmm0
0x140076e4c  mov     [r11-48h], rdi
0x140076e50  mov     [rsp+0E8h+var_98], edi
0x140076e54  mov     [rsp+0E8h+var_70], edi
0x140076e58  mov     [rsp+0E8h+var_91], dil
0x140076e5d  mov     [rsp+0E8h+var_92], dil
0x140076e62  mov     [rsp+0E8h+var_93], dil
0x140076e67  mov     [r11+18h], dil
0x140076e6b  mov     [rsp+0E8h+var_94], dil
0x140076e70  mov     rax, [rsp+0E8h+arg_30]
0x140076e78  test    rax, rax
0x140076e7b  jz      short loc_140076E90
0x140076e7d  movups  xmm0, xmmword ptr [rax]
0x140076e80  movups  xmmword ptr [r11-58h], xmm0
0x140076e85  movsd   xmm1, qword ptr [rax+10h]
0x140076e8a  movsd   qword ptr [r11-48h], xmm1
0x140076e90  lea     rax, [rcx+0C8h]
0x140076e97  mov     [rsp+0E8h+var_60], rax
0x140076e9f  mov     dl, 1; Wait
0x140076ea1  mov     rcx, rax; Resource
0x140076ea4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140076eab  nop     dword ptr [rax+rax+00h]
0x140076eb0  mov     [rsp+0E8h+var_93], al
0x140076eb4  test    r12b, 6
0x140076eb8  jz      short loc_140076ED0
0x140076eba  mov     ebx, 0C000000Dh
0x140076ebf  mov     [rsp+0E8h+var_98], ebx
0x140076ec3  mov     r13, [rsp+0E8h+FileObject]
0x140076ecb  jmp     loc_1400776AD
0x140076ed0  mov     r8d, [rsi+16Ch]
0x140076ed7  bt      r8d, 0Ch
0x140076edc  jnb     short loc_140076F39
0x140076ede  lea     rdi, WPP_GLOBAL_Control
0x140076ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x140076eec  cmp     rcx, rdi
0x140076eef  jz      short loc_140076F23
0x140076ef1  test    dword ptr [rcx+2Ch], 8000000h
0x140076ef8  jz      short loc_140076F23
0x140076efa  mov     edx, 11h
0x140076eff  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x140076f04  mov     dword ptr [rsp+0E8h+Update], 2C99h
0x140076f0c  lea     r9, aCclfslogfcbphy_3; "CClfsLogFcbPhysical::Initialize"
0x140076f13  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140076f1a  mov     rcx, [rcx+18h]
0x140076f1e  call    WPP_SF_slD
0x140076f23  mov     ebx, 0C01A002Bh
0x140076f28  mov     [rsp+0E8h+var_98], ebx
0x140076f2c  mov     r13, [rsp+0E8h+FileObject]
0x140076f34  jmp     loc_1400776B4
0x140076f39  mov     r13, [rsp+0E8h+FileObject]
0x140076f41  mov     rdx, r13; struct _FILE_OBJECT *
0x140076f44  mov     rcx, rsi; this
0x140076f47  call    ?Open@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@@Z; CClfsLogFcbPhysical::Open(_FILE_OBJECT *)
0x140076f4c  mov     ebx, eax
0x140076f4e  mov     [rsp+0E8h+var_98], eax
0x140076f52  test    eax, eax
0x140076f54  js      loc_1400776AD
0x140076f5a  test    byte ptr [rsi+16Ch], 1
0x140076f61  jnz     short loc_140076F71
0x140076f63  mov     ebx, 0C0000035h
0x140076f68  mov     [rsp+0E8h+var_98], ebx
0x140076f6c  jmp     loc_1400776AD
0x140076f71  cmp     [rsi+30h], rdi
0x140076f75  jz      loc_140077018
0x140076f7b  cmp     [rsi+148h], rdi
0x140076f82  jnz     loc_140077018
0x140076f88  lea     rbx, [rsi+28h]
0x140076f8c  movzx   ecx, word ptr [rbx]
0x140076f8f  shr     rcx, 1
0x140076f92  mov     eax, 2
0x140076f97  mul     rcx
0x140076f9a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140076fa1  cmovb   rax, rcx
0x140076fa5  mov     r15d, 73666C43h
0x140076fab  mov     r8d, r15d; Tag
0x140076fae  mov     rdx, rax; NumberOfBytes
0x140076fb1  mov     edi, 200h
0x140076fb6  mov     ecx, edi; PoolType
0x140076fb8  call    cs:__imp_ExAllocatePoolWithTag
0x140076fbf  nop     dword ptr [rax+rax+00h]
0x140076fc4  mov     [rsi+148h], rax
0x140076fcb  test    rax, rax
0x140076fce  jnz     short loc_140076FD7
0x140076fd0  mov     ebx, 0C000009Ah
0x140076fd5  jmp     short loc_140076F68
0x140076fd7  movzx   r8d, word ptr [rbx]; Size
0x140076fdb  mov     [rsi+140h], r8w
0x140076fe3  mov     [rsi+142h], r8w
0x140076feb  xor     edx, edx; Val
0x140076fed  mov     rcx, rax; void *
0x140076ff0  call    memset
0x140076ff5  mov     rdx, rbx; SourceString
0x140076ff8  lea     rcx, [rsi+140h]; DestinationString
0x140076fff  call    cs:__imp_RtlCopyUnicodeString
0x140077006  nop     dword ptr [rax+rax+00h]
0x14007700b  mov     rax, [rsi+148h]
0x140077012  xchg    rax, [rbx+8]
0x140077016  jmp     short loc_140077023
0x140077018  mov     edi, 200h
0x14007701d  mov     r15d, 73666C43h
0x140077023  lea     rcx, [rsi+28h]; Source
0x140077027  lea     rdx, [rsp+0E8h+Destination]; Destination
0x14007702c  call    ?CreateBaseFileName@CClfsLogFcbPhysical@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsLogFcbPhysical::CreateBaseFileName(_UNICODE_STRING const &,_UNICODE_STRING &)
0x140077031  mov     ebx, eax
0x140077033  mov     [rsp+0E8h+var_98], eax
0x140077037  test    eax, eax
0x140077039  js      loc_1400776AD
0x14007703f  lea     rcx, WPP_MAIN_CB.DeviceExtension; Lookaside
0x140077046  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007704d  nop     dword ptr [rax+rax+00h]
0x140077052  test    rax, rax
0x140077055  jz      short loc_140077063
0x140077057  mov     rdx, [r13+8]; struct _DEVICE_OBJECT *
0x14007705b  mov     rcx, rax; this
0x14007705e  call    ??0CClfsBaseFilePersisted@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsBaseFilePersisted::CClfsBaseFilePersisted(_DEVICE_OBJECT *)
0x140077063  mov     [rsi+2C8h], rax
0x14007706a  test    rax, rax
0x14007706d  jz      loc_140076FD0
0x140077073  mov     [rsp+0E8h+var_91], 1
0x140077078  lock inc dword ptr [rax+8]
0x14007707c  movzx   r9d, r12w
0x140077080  shr     r9w, 8
0x140077085  not     r9b
0x140077088  and     r9b, 1; unsigned __int8
0x14007708c  lea     rax, [rsp+0E8h+arg_10]
0x140077094  mov     [rsp+0E8h+var_B0], rax; unsigned __int8 *
0x140077099  mov     eax, [rsp+0E8h+arg_40]
0x1400770a0  mov     dword ptr [rsp+0E8h+var_B8], eax; unsigned int
0x1400770a4  mov     rax, [rsp+0E8h+arg_8]
0x1400770ac  mov     qword ptr [rsp+0E8h+var_C0], rax; void *
0x1400770b1  lea     rax, [rsp+0E8h+var_58]
0x1400770b9  mov     qword ptr [rsp+0E8h+Update], rax; struct _CLFS_FILTER_CONTEXT *
0x1400770be  mov     r8d, 10000h; unsigned int
0x1400770c4  lea     rdx, [rsp+0E8h+Destination]; struct _UNICODE_STRING *
0x1400770c9  mov     rcx, [rsi+2C8h]; this
0x1400770d0  call    ?CreateImage@CClfsBaseFilePersisted@@QEAAJPEAU_UNICODE_STRING@@KEAEBU_CLFS_FILTER_CONTEXT@@QEAXKAEAE@Z; CClfsBaseFilePersisted::CreateImage(_UNICODE_STRING *,ulong,uchar,_CLFS_FILTER_CONTEXT const &,void * const,ulong,uchar &)
0x1400770d5  mov     ebx, eax
0x1400770d7  mov     [rsp+0E8h+var_98], eax
0x1400770db  test    eax, eax
0x1400770dd  js      loc_1400776AD
0x1400770e3  mov     [rsp+0E8h+var_92], 1
0x1400770e8  mov     eax, [rsi+16Ch]
0x1400770ee  cmp     byte ptr [rsp+0E8h+arg_10], 0
0x1400770f6  jz      short loc_1400770FE
0x1400770f8  bts     eax, 0Bh
0x1400770fc  jmp     short loc_140077102
0x1400770fe  btr     eax, 0Bh
0x140077102  mov     [rsi+16Ch], eax
0x140077108  mov     rcx, [rsi+2C8h]; this
0x14007710f  call    ?GetUsn@CClfsBaseFile@@QEAAEXZ; CClfsBaseFile::GetUsn(void)
0x140077114  mov     [rsi+2B1h], al
0x14007711a  mov     [rsi+178h], r12w
0x140077122  test    [rsp+0E8h+arg_40], edi
0x140077129  jz      short loc_140077138
0x14007712b  or      r12w, 2
0x140077130  mov     [rsi+178h], r12w
0x140077138  mov     r8d, r15d; Tag
0x14007713b  mov     edx, 68h ; 'h'; NumberOfBytes
0x140077140  mov     ecx, edi; PoolType
0x140077142  call    cs:__imp_ExAllocatePoolWithTag
0x140077149  nop     dword ptr [rax+rax+00h]
0x14007714e  mov     [rsi+580h], rax
0x140077155  test    rax, rax
0x140077158  jz      loc_140076FD0
0x14007715e  mov     rcx, rax; Resource
0x140077161  call    cs:__imp_ExInitializeResourceLite
0x140077168  nop     dword ptr [rax+rax+00h]
0x14007716d  lea     r12, [rsi+550h]
0x140077174  mov     rdx, r12; struct _KEVENT **
0x140077177  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x14007717c  mov     ebx, eax
0x14007717e  mov     [rsp+0E8h+var_98], eax
0x140077182  test    eax, eax
0x140077184  js      loc_1400776AD
0x14007718a  mov     rcx, [r12]; Event
0x14007718e  call    cs:__imp_KeClearEvent
0x140077195  nop     dword ptr [rax+rax+00h]
0x14007719a  mov     rax, [r13+8]
0x14007719e  mov     [rsi+230h], rax
0x1400771a5  mov     rax, [rax+40h]
0x1400771a9  mov     ecx, [rax+90h]
0x1400771af  mov     [rsi+524h], ecx
0x1400771b5  mov     rcx, [r13+8]; DeviceObject
0x1400771b9  call    cs:__imp_IoAllocateWorkItem
0x1400771c0  nop     dword ptr [rax+rax+00h]
0x1400771c5  mov     [rsi+570h], rax
0x1400771cc  test    rax, rax
0x1400771cf  jz      loc_140076FD0
0x1400771d5  mov     r8d, r15d; Tag
0x1400771d8  mov     r12d, 10h
0x1400771de  mov     edx, r12d; NumberOfBytes
0x1400771e1  mov     ecx, edi; PoolType
0x1400771e3  call    cs:__imp_ExAllocatePoolWithTag
0x1400771ea  nop     dword ptr [rax+rax+00h]
0x1400771ef  mov     [rsi+3B8h], rax
0x1400771f6  test    rax, rax
0x1400771f9  jz      loc_140076FD0
0x1400771ff  mov     [rax+8], rax
0x140077203  mov     [rax], rax
0x140077206  mov     r8d, r15d; Tag
0x140077209  lea     ebx, [r12-8]
0x14007720e  mov     edx, ebx; NumberOfBytes
0x140077210  mov     ecx, edi; PoolType
0x140077212  call    cs:__imp_ExAllocatePoolWithTag
0x140077219  nop     dword ptr [rax+rax+00h]
0x14007721e  mov     [rsi+3C0h], rax
0x140077225  test    rax, rax
0x140077228  jz      loc_140076FD0
0x14007722e  mov     rcx, rax; SpinLock
0x140077231  call    cs:__imp_KeInitializeSpinLock
0x140077238  nop     dword ptr [rax+rax+00h]
0x14007723d  mov     r8d, r15d; Tag
0x140077240  mov     edx, r12d; NumberOfBytes
0x140077243  mov     ecx, edi; PoolType
0x140077245  call    cs:__imp_ExAllocatePoolWithTag
0x14007724c  nop     dword ptr [rax+rax+00h]
0x140077251  mov     [rsi+1608h], rax
0x140077258  test    rax, rax
0x14007725b  jz      loc_140076FD0
0x140077261  mov     [rax+8], rax
0x140077265  mov     [rax], rax
0x140077268  mov     r8d, r15d; Tag
0x14007726b  mov     edx, ebx; NumberOfBytes
0x14007726d  mov     ecx, edi; PoolType
0x14007726f  call    cs:__imp_ExAllocatePoolWithTag
0x140077276  nop     dword ptr [rax+rax+00h]
0x14007727b  mov     [rsi+1610h], rax
0x140077282  test    rax, rax
0x140077285  jz      loc_140076FD0
0x14007728b  mov     rcx, rax; SpinLock
0x14007728e  call    cs:__imp_KeInitializeSpinLock
0x140077295  nop     dword ptr [rax+rax+00h]
0x14007729a  mov     r8d, r15d; Tag
0x14007729d  mov     edx, ebx; NumberOfBytes
0x14007729f  mov     ecx, edi; PoolType
0x1400772a1  call    cs:__imp_ExAllocatePoolWithTag
0x1400772a8  nop     dword ptr [rax+rax+00h]
0x1400772ad  mov     [rsi+3E0h], rax
0x1400772b4  test    rax, rax
0x1400772b7  jz      loc_140076FD0
0x1400772bd  mov     rcx, rax; SpinLock
0x1400772c0  call    cs:__imp_KeInitializeSpinLock
0x1400772c7  nop     dword ptr [rax+rax+00h]
0x1400772cc  mov     r8d, r15d; Tag
0x1400772cf  lea     edx, [rbx+30h]; NumberOfBytes
0x1400772d2  mov     ecx, edi; PoolType
0x1400772d4  call    cs:__imp_ExAllocatePoolWithTag
0x1400772db  nop     dword ptr [rax+rax+00h]
0x1400772e0  mov     [rsi+440h], rax
0x1400772e7  test    rax, rax
0x1400772ea  jz      loc_140076FD0
0x1400772f0  lea     r12d, [rbx-7]
0x1400772f4  mov     [rax], r12d
0x1400772f7  mov     qword ptr [rax+8], 0
0x1400772ff  mov     dword ptr [rax+10h], 0
0x140077306  lea     rcx, [rax+18h]; Event
0x14007730a  xor     r8d, r8d; State
0x14007730d  mov     edx, r12d; Type
0x140077310  call    cs:__imp_KeInitializeEvent
0x140077317  nop     dword ptr [rax+rax+00h]
0x14007731c  mov     rdi, [rsi+2C8h]
0x140077323  mov     rbx, qword ptr cs:CLFS_LSN_INVALID
0x14007732a  lea     rcx, [rsi+260h]
0x140077331  mov     rax, [rcx]
0x140077334  mov     rax, [rax+40h]
0x140077338  call    _guard_dispatch_icall
0x14007733d  lea     r8, [rsi+588h]
0x140077344  lea     r10, [rsi+58Ch]
0x14007734b  mov     r9b, [rsi+178h]
0x140077352  shr     r9b, 1
0x140077355  and     r9b, r12b; unsigned __int8
0x140077358  lea     rdx, [rsi+590h]; unsigned int *
0x14007735f  lea     rcx, [rsp+0E8h+var_68]
0x140077367  mov     [rsp+0E8h+var_A8], rcx; unsigned __int64 *
0x14007736c  mov     [rsp+0E8h+var_B0], r8; unsigned int *
0x140077371  mov     [rsp+0E8h+var_B8], r10; unsigned int *
0x140077376  mov     qword ptr [rsp+0E8h+var_C0], rbx; union _CLS_LSN
0x14007737b  mov     [rsp+0E8h+Update], al; char
  ... truncated ...
```
