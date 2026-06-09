# ndisDeviceControlHandler(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *)

- ea: `0x1400115c0`
- end: `0x140012607`
- name: `?ndisDeviceControlHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@@Z`
- size: `4167`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _NDIS_MINIPORT_BLOCK *, struct _IRP *)`
- caller_count: `2`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005bf70`
- `0x14007a490`

## callees

- `0x140009320`
- `0x14000b820`
- `0x1400100f0`
- `0x140010860`
- `0x1400110b0`
- `0x1400114b0`
- `0x1400115c0`
- `0x140012610`
- `0x140014e40`
- `0x140017220`
- `0x140017510`
- `0x140019dd0`
- `0x140041760`
- `0x14005b730`
- `0x140082c40`
- `0x140084440`
- `0x140084660`
- `0x140088a2c`
- `0x140088cc0`
- `0x140089820`
- `0x1400eb460`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x1400ebce0`
- `0x14013df20`
- `0x14013e9c0`
- `0x14014a750`
- `0x140165f10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001243e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001243e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011f60`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001237d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400123a9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400ed99a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011f60`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001237d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400123a9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400ed99a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012331`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012331`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140011efd`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400ed97e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400ed9ef`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140011efd`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400ed97e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400ed9ef`
- `ntoskrnl!KeSetTimer` at `0x140012314`
- `ntoskrnl!KeSetTimer` at `0x140012314`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400119d0`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400119d0`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400119e6`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140011c9f`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400121b7`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14001245b`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400119e6`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140011c9f`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400121b7`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14001245b`
- `ntoskrnl!MmLockPagableSectionByHandle` at `0x140011654`
- `ntoskrnl!MmLockPagableSectionByHandle` at `0x140011654`
- `ntoskrnl!IofCompleteRequest` at `0x140011d7b`
- `ntoskrnl!IofCompleteRequest` at `0x140012197`
- `ntoskrnl!IofCompleteRequest` at `0x140011d7b`
- `ntoskrnl!IofCompleteRequest` at `0x140012197`
- `ntoskrnl!KeSetEvent` at `0x140011b2f`
- `ntoskrnl!KeSetEvent` at `0x140011da1`
- `ntoskrnl!KeSetEvent` at `0x140011b2f`
- `ntoskrnl!KeSetEvent` at `0x140011da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001259f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400125e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001259f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400125e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001172c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011743`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012062`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400121e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001250b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ed93a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001172c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011743`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012062`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400121e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001250b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ed93a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011752`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011752`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b78`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400122fa`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400122fa`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001190f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011f11`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400124b0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001190f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011f11`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400124b0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001195d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011f4f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001234e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001236c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001195d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011f4f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001234e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001236c`

## pseudocode

```c
__int64 __fastcall ndisDeviceControlHandler(
        struct _DEVICE_OBJECT *a1,
        struct _NDIS_MINIPORT_BLOCK *a2,
        struct _IRP *a3)
{
  struct _IRP *v3; // r14
  struct _NDIS_MINIPORT_BLOCK *v4; // r12
  signed __int32 v6; // eax
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  _FILE_OBJECT *FileObject; // rax
  _NDIS_MINIPORT_BLOCK *v9; // r15
  __int128 *FsContext; // rbx
  unsigned int v11; // r14d
  KIRQL v12; // al
  struct _NDIS_M_DRIVER_BLOCK *v13; // r13
  KIRQL v14; // di
  KSPIN_LOCK *p_SpinLock; // rsi
  __int64 v16; // rdx
  KIRQL v17; // bl
  unsigned __int16 ReferenceCount; // cx
  KIRQL v19; // al
  _NDIS_MINIPORT_BLOCK *MiniportQueue; // rbx
  struct _NDIS_MINIPORT_BLOCK *v21; // rsi
  _NDIS_BIND_PATHS *BindPaths; // rdx
  KIRQL v23; // al
  struct _NDIS_M_DRIVER_BLOCK *NextDriver; // rbx
  __int64 v25; // rax
  unsigned int LowPart; // r8d
  unsigned int v27; // esi
  _NDIS_BIND_PATHS *v28; // rcx
  struct _NDIS_MINIPORT_BLOCK *v29; // rcx
  unsigned int *p_Number; // rax
  unsigned __int8 v31; // r8
  unsigned int HardwareInfo; // eax
  int RdmaCapabilities; // eax
  char v34; // r13
  KIRQL v35; // di
  ULONG_PTR NsiRefCountTracker; // r8
  __int64 v37; // r9
  unsigned __int8 m; // cl
  _BYTE *v39; // rdx
  char v40; // al
  struct _KEVENT *NsiRequestsCompletedEvent; // rcx
  int v43; // edx
  KIRQL v44; // al
  int v45; // edx
  ULONG_PTR RefCountTracker; // rcx
  KIRQL v47; // r14
  __int64 v48; // r9
  unsigned __int8 ii; // dl
  _BYTE *v50; // r8
  char v51; // al
  unsigned int v52; // edi
  int v53; // edx
  int v54; // edx
  struct _KEVENT *RemoveReadyEvent; // rcx
  int v57; // eax
  unsigned int v58; // r8d
  unsigned int v59; // r8d
  _IO_STACK_LOCATION *v60; // rdx
  _IO_STACK_LOCATION *v61; // rdx
  __int64 (__fastcall *v62)(struct _DEVICE_OBJECT *, struct _IRP *); // rax
  int v63; // edx
  KSPIN_LOCK *p_Lock; // rbx
  struct _NDIS_LOG *Log; // rdi
  _IO_STACK_LOCATION *v66; // rdx
  _IO_STACK_LOCATION *v67; // rdx
  _IO_STACK_LOCATION *v68; // rbx
  _IRP::<unnamed_type_AssociatedIrp> v69; // rdi
  struct _NDIS_PD_BLOCK *PDBlock; // rdx
  unsigned int v71; // esi
  KIRQL v72; // dl
  _IO_STACK_LOCATION *v73; // rax
  unsigned int v74; // edx
  ULONG_PTR v75; // r14
  int v76; // ecx
  struct _NDIS_REFCOUNT_STACK_BLOCK *k; // r12
  ULONG_PTR v78; // rdi
  unsigned int v79; // r8d
  int v80; // edx
  struct _NDIS_REFCOUNT_STACK_BLOCK *n; // r12
  _MDL *MdlAddress; // rcx
  ULONG ByteCount; // r12d
  char *MappedSystemVa; // r13
  __int64 v85; // rcx
  ULONG v86; // eax
  char *v87; // rdx
  size_t v88; // r8
  char *v89; // rcx
  KSPIN_LOCK *v90; // r14
  int v91; // edi
  KIRQL v92; // dl
  int v93; // eax
  _NDIS_SRIOV_CAPABILITIES *SriovCurrentCapabilities; // rax
  __int64 v95; // rcx
  __int64 v96; // r9
  unsigned int v97; // eax
  unsigned int v98; // ecx
  _IRP *MasterIrp; // rbx
  int v100; // ecx
  int v101; // ecx
  int v102; // ecx
  struct _NDIS_PCW_DATA_BLOCK *MiniportDataBlock; // rdi
  unsigned int i; // ebx
  unsigned __int64 Length; // rcx
  _IRP::<unnamed_type_AssociatedIrp> v106; // rbx
  unsigned int v107; // edi
  unsigned int v108; // edx
  unsigned int v109; // r8d
  _IO_STATUS_BLOCK *p_IoStatus; // rsi
  struct _NDIS_PCW_DATA_BLOCK *v111; // rax
  struct _NDIS_PCW_DATA_BLOCK *v112; // r10
  unsigned int j; // r9d
  _IO_STATUS_BLOCK *v114; // rax
  _IO_STATUS_BLOCK *v115; // rcx
  __int64 v116; // rdx
  _IO_STATUS_BLOCK v117; // xmm0
  KIRQL v118; // dl
  _NDIS_SRIOV_CAPABILITIES *v119; // rax
  _NDIS_SRIOV_CAPABILITIES *v120; // rax
  int v121; // ebx
  _IRP::<unnamed_type_AssociatedIrp> v122; // rcx
  char Priority; // [rsp+28h] [rbp-D8h]
  KIRQL Irql[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _NDIS_MINIPORT_BLOCK *v125; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v126; // [rsp+50h] [rbp-B0h] BYREF
  _IO_STACK_LOCATION *v127; // [rsp+58h] [rbp-A8h]
  __int128 *v128; // [rsp+60h] [rbp-A0h]
  __int128 v129; // [rsp+70h] [rbp-90h] BYREF
  __int128 v130; // [rsp+80h] [rbp-80h]
  __int128 v131; // [rsp+90h] [rbp-70h]
  __int128 v132; // [rsp+A0h] [rbp-60h]
  __int128 v133; // [rsp+B0h] [rbp-50h]
  __int128 v134; // [rsp+C0h] [rbp-40h]
  struct _KTIMER Timer; // [rsp+D0h] [rbp-30h] BYREF
  struct _NDIS_MINIPORT_BLOCK *v136; // [rsp+158h] [rbp+58h]
  char v138; // [rsp+168h] [rbp+68h]

  v136 = a2;
  v126 = 0;
  v3 = a3;
  v129 = 0;
  v4 = a2;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    Priority = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      11,
      21,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      Priority,
      (char)a3);
  }
  v6 = _InterlockedIncrement((volatile signed __int32 *)&ndisPkgs);
  if ( !ImageSectionHandle )
  {
    if ( v6 == 1 )
    {
      ImageSectionHandle = MmLockPagableDataSection(AddressWithinSection);
      MmUnlockPagableImageSection(ImageSectionHandle);
    }
    else
    {
      do
      {
        memset(&Timer, 0, sizeof(Timer));
        KeInitializeTimerEx(&Timer, SynchronizationTimer);
        KeSetTimer(&Timer, (LARGE_INTEGER)-500LL, 0);
        KeWaitForSingleObject(&Timer, Executive, 0, 0, 0);
      }
      while ( !ImageSectionHandle );
    }
  }
  MmLockPagableSectionByHandle(ImageSectionHandle);
  CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
  v3->IoStatus.Status = 259;
  v3->IoStatus.Information = 0;
  v127 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( !FileObject )
  {
    v27 = -1073741823;
    MmUnlockPagableImageSection(ImageSectionHandle);
    _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
    v34 = (char)v136;
LABEL_95:
    v3->IoStatus.Status = v27;
    IofCompleteRequest(v3, 2);
    goto LABEL_89;
  }
  if ( v4->Header.Type != 17 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(CurrentStackLocation) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)CurrentStackLocation,
        11,
        32,
        (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
        (char)a1,
        (char)v3);
    }
    v61 = v3->Tail.Overlay.CurrentStackLocation;
    if ( v4->Header.Type == 17 )
    {
      v27 = 0;
      if ( v61->MajorFunction != 18 )
        v27 = -1073741637;
    }
    else
    {
      if ( v4->Header.Type == 9 )
      {
        v62 = (__int64 (__fastcall *)(struct _DEVICE_OBJECT *, struct _IRP *))*((_QWORD *)&v4->Reserved28
                                                                              + v61->MajorFunction);
        if ( v62 )
        {
          v27 = v62(a1, v3);
LABEL_147:
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v63) = 4;
            WPP_RECORDER_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v63,
              11,
              33,
              (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
              (char)a1,
              (char)v3);
          }
          MmUnlockPagableImageSection(ImageSectionHandle);
          _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
          v34 = (char)v136;
          goto LABEL_89;
        }
      }
      v27 = -1073741637;
    }
    v3->IoStatus.Status = v27;
    IofCompleteRequest(v3, 2);
    goto LABEL_147;
  }
  v9 = 0;
  FsContext = (__int128 *)FileObject->FsContext;
  v128 = FsContext;
  v138 = 1;
  if ( v4->BindPaths )
  {
    v125 = 0;
    v11 = 1;
    v12 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
    v13 = ndisMiniDriverList;
    v14 = v12;
    if ( ndisMiniDriverList )
    {
      while ( 1 )
      {
        p_SpinLock = &v13->Ref.SpinLock;
        v17 = KeAcquireSpinLockRaiseToDpc(&v13->Ref.SpinLock);
        if ( !v13->Ref.Closing )
        {
          ReferenceCount = v13->Ref.ReferenceCount;
          if ( ReferenceCount < 0xFFEBu )
          {
            LOBYTE(v16) = 8;
            v13->Ref.ReferenceCount = ReferenceCount + 1;
            NdisReferenceWithTag(v13->Ref.RefCountTracker, v16);
            KeReleaseSpinLock(&v13->Ref.SpinLock, v17);
            KeReleaseSpinLock(&ndisMiniDriverListLock, v14);
            v19 = KeAcquireSpinLockRaiseToDpc(&v13->Ref.SpinLock);
            MiniportQueue = v13->MiniportQueue;
            Irql[0] = v19;
            if ( MiniportQueue )
            {
              v21 = v125;
              do
              {
                BindPaths = MiniportQueue->BindPaths;
                if ( BindPaths )
                {
                  if ( BindPaths->Number >= v11 )
                  {
                    v28 = v4->BindPaths;
                    if ( v28->Paths[0].Length == BindPaths->Paths[0].Length
                      && !memcmp(v28->Paths[0].Buffer, BindPaths->Paths[0].Buffer, v28->Paths[0].Length) )
                    {
                      KeAcquireSpinLockAtDpcLevel(&MiniportQueue->Lock);
                      MiniportQueue->MiniportThread = KeGetCurrentThread();
                      if ( !MINIPORT_TEST_FLAG(MiniportQueue, 0x80200020)
                        && (MiniportQueue->PnPFlags & 0x1084110) == 0
                        && MiniportQueue->PnPDeviceState == NdisPnPDeviceStarted
                        && MiniportQueue->CurrentDevicePowerState == PowerDeviceD0
                        && ndisReferenceMiniport(v29, MPREF_UM_IOCTL) )
                      {
                        v21 = v9;
                        NdisReferenceWithTag(MiniportQueue->NsiRefCountTracker, 0);
                        p_Number = &MiniportQueue->BindPaths->Number;
                        v9 = MiniportQueue;
                        ++MiniportQueue->NsiOpenReferences;
                        v11 = *p_Number;
                      }
                      MiniportQueue->MiniportThread = 0;
                      KeReleaseSpinLockFromDpcLevel(&MiniportQueue->Lock);
                      if ( v21 )
                      {
                        ndisDereferenceMiniportForNsi(v21, NSIREF_IOCTL, MPREF_UM_IOCTL);
                        v21 = 0;
                      }
                    }
                  }
                }
                MiniportQueue = MiniportQueue->NextMiniport;
              }
              while ( MiniportQueue );
              v19 = Irql[0];
              v125 = v21;
              p_SpinLock = &v13->Ref.SpinLock;
            }
            KeReleaseSpinLock(p_SpinLock, v19);
            v23 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
            NextDriver = v13->NextDriver;
            v14 = v23;
            ndisDereferenceDriver(v13, 1u, MDRVREF_MPREFT);
            goto LABEL_17;
          }
          ndisRefCountReferenceCountOverflow = 1;
        }
        KeReleaseSpinLock(&v13->Ref.SpinLock, v17);
        NextDriver = v13->NextDriver;
LABEL_17:
        v13 = NextDriver;
        if ( !NextDriver )
        {
          FsContext = v128;
          break;
        }
      }
    }
    KeReleaseSpinLock(&ndisMiniDriverListLock, v14);
    v3 = a3;
    CurrentStackLocation = v127;
    if ( v9 )
    {
      v136 = v9;
      *(_QWORD *)&v129 = 0;
      *((_QWORD *)&v129 + 1) = v9;
      v4 = v9;
      v130 = 0;
      v131 = 0;
      v132 = 0;
      v133 = 0;
      v134 = 0;
      *(_QWORD *)&v130 = v9->OidList;
      BYTE8(v130) = *((_BYTE *)FsContext + 24);
      v25 = *(_QWORD *)FsContext;
      FsContext = &v129;
      *(_QWORD *)&v129 = v25;
    }
  }
  if ( (v4->PnPFlags & 0x4010) != 0 )
  {
    v34 = (char)v136;
    v27 = -1073741436;
    goto LABEL_47;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 2252876 )
  {
    if ( *((_BYTE *)v3->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 24) )
    {
      if ( ndisSystemSupportsSriov )
      {
        SriovCurrentCapabilities = v4->SriovCurrentCapabilities;
        if ( SriovCurrentCapabilities )
        {
          if ( (SriovCurrentCapabilities->SriovCapabilities & 3) == 3 )
          {
            v27 = 0;
LABEL_235:
            v3->IoStatus.Information = 0;
            goto LABEL_44;
          }
        }
      }
LABEL_243:
      v27 = -1073741637;
      goto LABEL_44;
    }
  }
  else
  {
    if ( LowPart <= 0x226044 )
    {
      if ( LowPart != 2252868 )
      {
        switch ( LowPart )
        {
          case 0x170002u:
          case 0x170006u:
          case 0x17000Eu:
          case 0x170028u:
          case 0x17002Cu:
          case 0x170030u:
          case 0x17003Eu:
          case 0x17009Cu:
            v57 = ndisMiniportOidIoctl(
                    v4,
                    (struct _NDIS_USER_OPEN_CONTEXT *)FsContext,
                    LowPart,
                    CurrentStackLocation->Parameters.Create.Options,
                    CurrentStackLocation->Parameters.Read.Length,
                    (unsigned __int8 *)v3->AssociatedIrp.MasterIrp,
                    v3->MdlAddress,
                    &v126);
            v27 = v57;
            if ( !v57 || v57 == -2147483643 )
              v3->IoStatus.Information = v126;
            v138 = 1;
            goto LABEL_44;
          case 0x17001Eu:
            if ( !v3->MdlAddress )
            {
              v34 = (char)v136;
              v27 = -1073741811;
              goto LABEL_47;
            }
            Irql[0] = 0;
            IoAcquireCancelSpinLock(Irql);
            p_Lock = &v4->Lock;
            KeAcquireSpinLockAtDpcLevel(&v4->Lock);
            v27 = -1073741823;
            Log = v4->Log;
            v4->MiniportThread = KeGetCurrentThread();
            if ( !Log )
            {
              v4->MiniportThread = 0;
              KeReleaseSpinLockFromDpcLevel(&v4->Lock);
              IoReleaseCancelSpinLock(Irql[0]);
              goto LABEL_44;
            }
            v90 = (KSPIN_LOCK *)((char *)Log + 8);
            KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)Log + 1);
            ByteCount = *((_DWORD *)Log + 7);
            if ( ByteCount )
            {
              MdlAddress = a3->MdlAddress;
              if ( MdlAddress->ByteCount <= ByteCount )
                ByteCount = MdlAddress->ByteCount;
              if ( (MdlAddress->MdlFlags & 5) != 0 )
                MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
              else
                MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
              if ( MappedSystemVa )
              {
                v85 = *((unsigned int *)Log + 9);
                v86 = *((_DWORD *)Log + 6) - v85;
                v87 = (char *)Log + v85 + 40;
                if ( v86 < ByteCount )
                {
                  memmove(MappedSystemVa, v87, v86);
                  v95 = *((unsigned int *)Log + 6);
                  v87 = (char *)Log + 40;
                  v96 = *((unsigned int *)Log + 9);
                  v88 = (unsigned int)v96 + ByteCount - (_DWORD)v95;
                  v89 = &MappedSystemVa[v95 - v96];
                }
                else
                {
                  v88 = ByteCount;
                  v89 = MappedSystemVa;
                }
                memmove(v89, v87, v88);
                *((_DWORD *)Log + 9) += ByteCount;
                *((_DWORD *)Log + 7) -= ByteCount;
                v97 = *((_DWORD *)Log + 9);
                v98 = *((_DWORD *)Log + 6);
                if ( v97 >= v98 )
                  *((_DWORD *)Log + 9) = v97 - v98;
                v91 = 0;
                a3->IoStatus.Information = ByteCount;
              }
              else
              {
                v91 = -1073741670;
              }
            }
            else if ( *((_QWORD *)Log + 2) )
            {
              v91 = -1073741823;
            }
            else
            {
              _InterlockedExchange64((volatile __int64 *)&a3->CancelRoutine, (__int64)ndisCancelLogIrp);
              *((_QWORD *)Log + 2) = a3;
              v91 = 259;
            }
            KeReleaseSpinLockFromDpcLevel(v90);
            v34 = (char)v136;
            v136->MiniportThread = 0;
            KeReleaseSpinLockFromDpcLevel(p_Lock);
            IoReleaseCancelSpinLock(Irql[0]);
            if ( v91 == 259 )
            {
              v27 = 259;
            }
            else if ( !v91 )
            {
              v27 = 0;
            }
            break;
          case 0x170068u:
            v66 = v3->Tail.Overlay.CurrentStackLocation;
            if ( !*((_BYTE *)v66->FileObject->FsContext + 24) )
              goto LABEL_41;
            if ( v66->Parameters.Create.Options < 0x14 )
              goto LABEL_41;
            MasterIrp = v3->AssociatedIrp.MasterIrp;
            v100 = (int)MasterIrp->MdlAddress;
            if ( (unsigned int)(v100 - 1) > 2 )
              goto LABEL_41;
            v101 = v100 - 1;
            if ( v101 )
            {
              v102 = v101 - 1;
              if ( v102 )
              {
                if ( v102 == 1 )
                {
                  MiniportDataBlock = ndisPcwGetMiniportDataBlock(v4);
                  if ( MiniportDataBlock )
                  {
                    for ( i = 0; i < ndisMaxNumberOfProcessors; ++i )
                      memset(
                        (char *)MiniportDataBlock + ndisPcwPerCpuDataStride * i + ndisPcwOffsetToPerCpuData,
                        0,
                        0x130u);
                  }
                  v4->NumberOfIndirectionTableChanges = 0;
                }
              }
              else
              {
                v4->PcwDatapathEventMask = 0;
                v4->PcwDatapathCycleMask = 0;
              }
            }
            else if ( ndisPcwGetMiniportDataBlock(v4) )
            {
              v4->PcwDatapathEventMask = HIDWORD(MasterIrp->MdlAddress);
              v4->PcwDatapathCycleMask = MasterIrp->Flags;
            }
            v3->IoStatus.Information = 0;
            v27 = 0;
            goto LABEL_44;
          case 0x17006Cu:
            v67 = v3->Tail.Overlay.CurrentStackLocation;
            if ( !*((_BYTE *)v67->FileObject->FsContext + 24) )
              goto LABEL_41;
            Length = v67->Parameters.Read.Length;
            if ( (unsigned int)Length < 0x30 )
              goto LABEL_41;
            v106.MasterIrp = (_IRP *)v3->AssociatedIrp;
            v107 = 48;
            *(_OWORD *)&v106.MasterIrp->Type = 0;
            *(_OWORD *)&v106.MasterIrp->Flags = 0;
            v106.MasterIrp->ThreadListEntry = 0;
            *(_DWORD *)&v106.MasterIrp->Type = 3146112;
            v106.MasterIrp->Reserved2 = ndisMaxNumberOfProcessors;
            v106.MasterIrp->AssociatedIrp.MasterIrp = (_IRP *)v4->NumberOfIndirectionTableChanges;
            HIDWORD(v106.MasterIrp->MdlAddress) = v4->PcwDatapathEventMask;
            v106.MasterIrp->Flags = v4->PcwDatapathCycleMask;
            v108 = ndisMaxNumberOfProcessors;
            v109 = 304 * ndisMaxNumberOfProcessors + 48;
            if ( (unsigned int)Length < v109 )
            {
              LODWORD(v106.MasterIrp->ThreadListEntry.Flink) = Length / 0x130;
              if ( (unsigned int)(Length / 0x130) )
              {
                HIDWORD(v106.MasterIrp->ThreadListEntry.Flink) = 48;
                p_IoStatus = &v106.MasterIrp->IoStatus;
                LODWORD(v106.MasterIrp->ThreadListEntry.Blink) = 304;
                v107 = 304 * (Length / 0x130) + 48;
              }
              else
              {
                p_IoStatus = 0;
              }
            }
            else
            {
              HIDWORD(v106.MasterIrp->ThreadListEntry.Flink) = 48;
              p_IoStatus = &v106.MasterIrp->IoStatus;
              v107 = v109;
              LODWORD(v106.MasterIrp->ThreadListEntry.Flink) = v108;
              LODWORD(v106.MasterIrp->ThreadListEntry.Blink) = 304;
            }
            LODWORD(v106.MasterIrp->MdlAddress) = v109;
            v111 = ndisPcwGetMiniportDataBlock(v4);
            v112 = v111;
            if ( p_IoStatus )
            {
              if ( v111 )
              {
                for ( j = 0; j < LODWORD(v106.MasterIrp->ThreadListEntry.Flink); v114[2] = v115[2] )
                {
                  v114 = &p_IoStatus[19 * j];
                  v115 = (_IO_STATUS_BLOCK *)((char *)v112 + ndisPcwPerCpuDataStride * j + ndisPcwOffsetToPerCpuData);
                  v116 = 2;
                  do
                  {
                    v114 += 8;
                    v117 = *v115;
                    v115 += 8;
                    v114[-8] = v117;
                    v114[-7] = v115[-7];
                    v114[-6] = v115[-6];
                    v114[-5] = v115[-5];
                    v114[-4] = v115[-4];
                    v114[-3] = v115[-3];
                    v114[-2] = v115[-2];
                    v114[-1] = v115[-1];
                    --v116;
                  }
                  while ( v116 );
                  ++j;
                  *v114 = *v115;
                  v114[1] = v115[1];
                }
              }
            }
            v27 = 0;
            v3->IoStatus.Information = v107;
            goto LABEL_44;
          case 0x170070u:
            LODWORD(v125) = 0;
            HardwareInfo = ndisGetHardwareInfo(v4, v3, (int *)&v125);
            goto LABEL_43;
          case 0x170078u:
            LODWORD(v125) = 0;
            HardwareInfo = ndisGetPowerInfo(v4, v3, (int *)&v125);
            goto LABEL_43;
          case 0x170090u:
            RdmaCapabilities = ndisGetRdmaCapabilities(v4, v3);
            if ( RdmaCapabilities )
              goto LABEL_158;
            v27 = 0;
            goto LABEL_44;
          case 0x170094u:
            LODWORD(v125) = 0;
            HardwareInfo = ndisGetAdapterHardwareInfo(v4, v3, (int *)&v125);
            goto LABEL_43;
          case 0x170098u:
            v31 = *((_BYTE *)FsContext + 24);
            LODWORD(v125) = 0;
            HardwareInfo = ndisGetAdapterRssInfo(v4, v3, v31, (int *)&v125);
LABEL_43:
            v27 = HardwareInfo;
            RdmaCapabilities = (int)v125;
            if ( !(_DWORD)v125 )
              goto LABEL_44;
LABEL_158:
            if ( RdmaCapabilities == -1073676268 )
              goto LABEL_185;
            v27 = -1073741823;
            if ( RdmaCapabilities == -1073741637 )
              v27 = -1073741637;
            goto LABEL_44;
          case 0x1700A8u:
            if ( !*((_BYTE *)FsContext + 24) )
              goto LABEL_41;
            ndisMiniportFatalError(v4, NdisMEventErr_Min);
            v27 = 0;
            goto LABEL_44;
          case 0x1700B0u:
            v68 = v3->Tail.Overlay.CurrentStackLocation;
            Irql[0] = 0;
            if ( !*((_BYTE *)v68->FileObject->FsContext + 24)
              || v68->Parameters.Create.Options
              || v68->Parameters.Read.Length < 0x18 )
            {
              goto LABEL_41;
            }
            v69.MasterIrp = (_IRP *)v3->AssociatedIrp;
            *(_DWORD *)&v69.MasterIrp->Type = 1573248;
            NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(v4, Irql);
            PDBlock = v4->PDBlock;
            if ( PDBlock && (v71 = *((_DWORD *)PDBlock + 8) + 24, v71 >= 0x18) )
            {
              *(_DWORD *)&v69.MasterIrp->AllocationProcessorNumber = v71;
              if ( v68->Parameters.Read.Length >= v71 )
              {
                v69.MasterIrp->Reserved2 = *((_DWORD *)PDBlock + 2);
                LOBYTE(v69.MasterIrp->Flags) = *((_BYTE *)PDBlock + 20);
                LODWORD(v69.MasterIrp->MdlAddress) = 24;
                HIDWORD(v69.MasterIrp->MdlAddress) = *((_DWORD *)PDBlock + 8);
                memmove(&v69.MasterIrp->AssociatedIrp, *((const void **)PDBlock + 3), *((unsigned int *)PDBlock + 8));
                v118 = Irql[0];
                v3->IoStatus.Information = v71;
                v4->MiniportThread = 0;
                KeReleaseSpinLock(&v4->Lock, v118);
                v27 = 0;
              }
              else
              {
                v92 = Irql[0];
                v3->IoStatus.Information = 24;
                v4->MiniportThread = 0;
                KeReleaseSpinLock(&v4->Lock, v92);
LABEL_185:
                v27 = -2147483643;
              }
            }
            else
            {
              v72 = Irql[0];
              v4->MiniportThread = 0;
              KeReleaseSpinLock(&v4->Lock, v72);
              v27 = -1073741823;
            }
            goto LABEL_44;
          default:
            goto LABEL_131;
        }
        goto LABEL_45;
      }
      v73 = v3->Tail.Overlay.CurrentStackLocation;
      Irql[0] = 0;
      if ( !*((_BYTE *)v73->FileObject->FsContext + 24) )
      {
        v27 = -1073741823;
        goto LABEL_44;
      }
      if ( ndisSystemSupportsSriov )
      {
        v119 = v4->SriovCurrentCapabilities;
        if ( v119 )
        {
          if ( (v119->SriovCapabilities & 3) == 3 )
          {
            IoAcquireCancelSpinLock(Irql);
            _InterlockedExchange64((volatile __int64 *)&v3->CancelRoutine, (__int64)ndisIovCancelIoctlNotification);
            IoReleaseCancelSpinLock(Irql[0]);
            v138 = 0;
            v27 = 259;
            goto LABEL_235;
          }
        }
      }
      goto LABEL_243;
    }
    v58 = LowPart - 2252872;
    if ( !v58 || (v59 = v58 - 8) == 0 )
    {
      v93 = ndisIovIoctlDetach(v4, v3);
      if ( v93 != 259 )
      {
        v27 = ndisConvertNdisStatusToNtStatusForIoctl(v93, v93, 0);
        goto LABEL_44;
      }
      goto LABEL_168;
    }
    if ( v59 != 4 )
    {
LABEL_131:
      v34 = (char)v136;
      v27 = -1073741822;
      goto LABEL_47;
    }
    v60 = v3->Tail.Overlay.CurrentStackLocation;
    Irql[0] = 0;
    if ( *((_BYTE *)v60->FileObject->FsContext + 24) && v60->Parameters.Read.Length >= 0x10 )
    {
      if ( !ndisSystemSupportsSriov )
        goto LABEL_243;
      v120 = v4->SriovCurrentCapabilities;
      if ( !v120 || (v120->SriovCapabilities & 3) != 3 )
        goto LABEL_243;
      IoAcquireCancelSpinLock(Irql);
      if ( v4->InvalidateBlockMask )
      {
        v121 = 0;
        v122.MasterIrp = (_IRP *)v3->AssociatedIrp;
        v122.MasterIrp->Type = v4->InvalidateVfId;
        v122.MasterIrp->MdlAddress = (_MDL *)v4->InvalidateBlockMask;
        v3->IoStatus.Information = 16;
        v4->InvalidateBlockMask = 0;
      }
      else
      {
        v4->InvalidateBlockIoctlPf = v3;
        v121 = 259;
        v3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        _InterlockedExchange64((volatile __int64 *)&v3->CancelRoutine, (__int64)ndisIovCancelIoctlInvalidate);
      }
      IoReleaseCancelSpinLock(Irql[0]);
      if ( v121 != 259 )
      {
        v27 = 0;
        goto LABEL_44;
      }
LABEL_168:
      v138 = 0;
      v27 = 259;
      goto LABEL_44;
    }
  }
LABEL_41:
  v27 = -1073741823;
LABEL_44:
  v34 = (char)v136;
LABEL_45:
  if ( (v27 & 0xC0230000) == 0xC0230000 )
    v27 = (unsigned __int16)v27 | 0xC0010000;
LABEL_47:
  if ( !v9 )
    goto LABEL_88;
  v35 = KeAcquireSpinLockRaiseToDpc(&v9->Lock);
  NsiRefCountTracker = (ULONG_PTR)v9->NsiRefCountTracker;
  v9->MiniportThread = KeGetCurrentThread();
  if ( NsiRefCountTracker - 2 > 1 )
  {
    if ( NsiRefCountTracker < 2 )
      ndisBugCheckEx(0x1Eu, 3u, NsiRefCountTracker, 0);
    if ( !*(_BYTE *)(NsiRefCountTracker + 2) )
      ndisBugCheckEx(0x1Eu, 2u, NsiRefCountTracker, 0);
    if ( *(_BYTE *)(NsiRefCountTracker + 1) )
    {
      if ( *(_BYTE *)(NsiRefCountTracker + 1) == 1 )
      {
        v74 = *(_DWORD *)(NsiRefCountTracker + 64);
        v75 = NsiRefCountTracker + 8;
        v76 = (unsigned __int16)v74 >> 1;
        if ( v74 >> 17 < 0x3FFE && v76 == (v74 >> 17) + 1 )
        {
          for ( k = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v75;
                *(_QWORD *)v75;
                k = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v75 )
          {
            *(_QWORD *)v75 = k->Next;
            ndisFreeRefCountStacksInBlock(k);
            ExFreePoolWithTag(k, 0);
          }
          ndisFreeRefCountStacksInBlock((struct _NDIS_REFCOUNT_STACK_BLOCK *)v75);
          *(_DWORD *)(v75 + 56) &= 0x10001u;
        }
        else
        {
          if ( v76 == 0 && (v74 & 1) == 0 )
LABEL_55:
            ndisReportRefcountImbalance(NsiRefCountTracker, 0);
          ndisReferenceWithTagStackTrace((struct _NDIS_REFCOUNT_WITH_STACK *)(NsiRefCountTracker + 8), 0);
        }
      }
    }
    else
    {
      v37 = *(_QWORD *)(NsiRefCountTracker + 8);
      if ( v37 )
      {
        for ( m = 0; ; ++m )
        {
          if ( m >= *(_BYTE *)(NsiRefCountTracker + 3) )
            goto LABEL_54;
          v39 = (_BYTE *)(v37 + 2LL * m);
          if ( !*v39 )
          {
            v40 = v39[1];
            if ( v40 )
              break;
          }
        }
        v39[1] = v40 - 1;
      }
      else
      {
LABEL_54:
        if ( !_bittestandreset((signed __int32 *)(NsiRefCountTracker + 16), 0) )
          goto LABEL_55;
      }
    }
  }
  if ( v9->NsiOpenReferences-- == 1 )
  {
    NsiRequestsCompletedEvent = v9->NsiRequestsCompletedEvent;
    if ( NsiRequestsCompletedEvent )
      KeSetEvent(NsiRequestsCompletedEvent, 0, 0);
  }
  v9->MiniportThread = 0;
  KeReleaseSpinLock(&v9->Lock, v35);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v43) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v43,
      20,
      25,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      (char)v9);
  }
  v44 = KeAcquireSpinLockRaiseToDpc(&v9->Ref.SpinLock);
  RefCountTracker = (ULONG_PTR)v9->RefCountTracker;
  v47 = v44;
  if ( (RefCountTracker & 0xFFFFFFFFFFFFFFFCuLL) == 0 && RefCountTracker != 1 )
    goto LABEL_83;
  if ( RefCountTracker == 1 )
    ndisBugCheckEx(0x1Eu, 3u, 1u, 0);
  if ( *(_BYTE *)(RefCountTracker + 2) <= 0x57u )
    ndisBugCheckEx(0x1Eu, 2u, (ULONG_PTR)v9->RefCountTracker, 0x57u);
  v45 = *(unsigned __int8 *)(RefCountTracker + 1);
  if ( *(_BYTE *)(RefCountTracker + 1) )
  {
    if ( v45 != 1 )
      goto LABEL_83;
    v78 = RefCountTracker + 5576;
    v79 = *(_DWORD *)(RefCountTracker + 5632);
    v80 = (unsigned __int16)v79 >> 1;
    if ( v79 >> 17 < 0x3FFE && v80 == (v79 >> 17) + 1 )
    {
      for ( n = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v78; *(_QWORD *)v78; n = *(struct _NDIS_REFCOUNT_STACK_BLOCK **)v78 )
      {
        *(_QWORD *)v78 = n->Next;
        ndisFreeRefCountStacksInBlock(n);
        ExFreePoolWithTag(n, 0);
      }
      ndisFreeRefCountStacksInBlock((struct _NDIS_REFCOUNT_STACK_BLOCK *)v78);
      *(_DWORD *)(v78 + 56) &= 0x10001u;
      goto LABEL_83;
    }
    if ( v80 != 0 || (v79 & 1) != 0 )
    {
      ndisReferenceWithTagStackTrace((struct _NDIS_REFCOUNT_WITH_STACK *)(RefCountTracker + 5576), 0);
      goto LABEL_83;
    }
LABEL_76:
    ndisReportRefcountImbalance(RefCountTracker, 0x57u);
  }
  v48 = *(_QWORD *)(RefCountTracker + 8);
  if ( v48 )
  {
    for ( ii = 0; ; ++ii )
    {
      if ( ii >= *(_BYTE *)(RefCountTracker + 3) )
        goto LABEL_75;
      v50 = (_BYTE *)(v48 + 2LL * ii);
      if ( *v50 == 87 )
      {
        v51 = v50[1];
        if ( v51 )
          break;
      }
    }
    v50[1] = v51 - 1;
    goto LABEL_83;
  }
LABEL_75:
  if ( !_bittestandreset((signed __int32 *)(RefCountTracker + 24), 0x17u) )
    goto LABEL_76;
LABEL_83:
  v52 = --v9->Ref.ReferenceCount;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v45) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v45,
      20,
      14,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      (char)v9,
      v9->Ref.ReferenceCount);
  }
  KeReleaseSpinLock(&v9->Ref.SpinLock, v47);
  if ( !v52 )
  {
    RemoveReadyEvent = v9->RemoveReadyEvent;
    if ( RemoveReadyEvent )
      KeSetEvent(RemoveReadyEvent, 0, 0);
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v53) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v53,
      20,
      26,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      (char)v9);
  }
LABEL_88:
  MmUnlockPagableImageSection(ImageSectionHandle);
  _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
  v3 = a3;
  if ( v138 && v27 != 259 )
    goto LABEL_95;
LABEL_89:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v54) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v54,
      11,
      22,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      v34,
      (char)v3);
  }
  return v27;
}

```

## disassembly

```asm
0x1400115c0  mov     [rsp-8+Irp], r8
0x1400115c5  mov     qword ptr [rsp-8+arg_8], rdx
0x1400115ca  push    rbp
0x1400115cb  push    rbx
0x1400115cc  push    rdi
0x1400115cd  push    r12
0x1400115cf  push    r13
0x1400115d1  push    r14
0x1400115d3  push    r15
0x1400115d5  lea     rbp, [rsp-10h]
0x1400115da  sub     rsp, 110h
0x1400115e1  xorps   xmm0, xmm0
0x1400115e4  xor     r13d, r13d
0x1400115e7  mov     [rsp+140h+var_F0], r13d
0x1400115ec  mov     r14, r8
0x1400115ef  movups  [rsp+140h+var_D0], xmm0
0x1400115f4  mov     r12, rdx
0x1400115f7  mov     rbx, rcx
0x1400115fa  movups  [rbp+40h+var_C0], xmm0
0x1400115fe  movups  [rbp+40h+var_B0], xmm0
0x140011602  movups  [rbp+40h+var_A0], xmm0
0x140011606  movups  [rbp+40h+var_90], xmm0
0x14001160a  movups  [rbp+40h+var_80], xmm0
0x14001160e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140011615  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001161c  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x140011623  jnz     loc_1400122A8
0x140011629  mov     eax, 1
0x14001162e  lock xadd cs:?ndisPkgs@@3PAU_PKG_REF@@A, eax; _PKG_REF near * ndisPkgs
0x140011636  inc     eax
0x140011638  cmp     cs:ImageSectionHandle, r13
0x14001163f  jz      loc_1400119C0
0x140011645  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x14001164c  mov     [rsp+140h+arg_0], rsi
0x140011654  call    cs:__imp_MmLockPagableSectionByHandle
0x14001165b  nop     dword ptr [rax+rax+00h]
0x140011660  mov     rdx, [r14+0B8h]
0x140011667  mov     dword ptr [r14+30h], 103h
0x14001166f  mov     [r14+38h], r13
0x140011673  mov     [rsp+140h+var_E8], rdx
0x140011678  mov     rax, [rdx+30h]
0x14001167c  test    rax, rax
0x14001167f  jz      loc_14001244F
0x140011685  cmp     byte ptr [r12], 11h
0x14001168a  jnz     loc_140011E8D
0x140011690  mov     r15, r13
0x140011693  mov     rbx, [rax+18h]
0x140011697  mov     [rsp+140h+var_E0], rbx
0x14001169c  mov     [rbp+40h+arg_18], 1
0x1400116a0  cmp     [r12+0EB8h], r13
0x1400116a8  jz      loc_140011858
0x1400116ae  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400116b5  mov     [rsp+140h+var_F8], r13
0x1400116ba  mov     r14d, 1
0x1400116c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400116c7  nop     dword ptr [rax+rax+00h]
0x1400116cc  mov     r13, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x1400116d3  movzx   edi, al
0x1400116d6  test    r13, r13
0x1400116d9  jz      loc_1400117E9
0x1400116df  lea     rsi, [r13+188h]
0x1400116e6  mov     rcx, rsi; SpinLock
0x1400116e9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400116f0  nop     dword ptr [rax+rax+00h]
0x1400116f5  cmp     byte ptr [rsi+0Ah], 0
0x1400116f9  movzx   ebx, al
0x1400116fc  jnz     loc_1400121DA
0x140011702  movzx   ecx, word ptr [rsi+8]
0x140011706  mov     eax, 0FFEBh
0x14001170b  cmp     cx, ax
0x14001170e  jnb     loc_1400121D3
0x140011714  inc     cx
0x140011717  mov     dl, 8
0x140011719  mov     [rsi+8], cx
0x14001171d  mov     rcx, [rsi+10h]
0x140011721  call    NdisReferenceWithTag
0x140011726  movzx   edx, bl; NewIrql
0x140011729  mov     rcx, rsi; SpinLock
0x14001172c  call    cs:__imp_KeReleaseSpinLock
0x140011733  nop     dword ptr [rax+rax+00h]
0x140011738  movzx   edx, dil; NewIrql
0x14001173c  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140011743  call    cs:__imp_KeReleaseSpinLock
0x14001174a  nop     dword ptr [rax+rax+00h]
0x14001174f  mov     rcx, rsi; SpinLock
0x140011752  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011759  nop     dword ptr [rax+rax+00h]
0x14001175e  mov     rbx, [r13+10h]
0x140011762  mov     [rsp+140h+Irql], al
0x140011766  test    rbx, rbx
0x140011769  jz      short loc_14001179F
0x14001176b  mov     rsi, [rsp+140h+var_F8]
0x140011770  mov     rdx, [rbx+0EB8h]
0x140011777  test    rdx, rdx
0x14001177a  jz      short loc_140011785
0x14001177c  cmp     [rdx], r14d
0x14001177f  jnb     loc_1400118DD
0x140011785  mov     rbx, [rbx+8]
0x140011789  test    rbx, rbx
0x14001178c  jnz     short loc_140011770
0x14001178e  movzx   eax, [rsp+140h+Irql]
0x140011793  mov     [rsp+140h+var_F8], rsi
0x140011798  lea     rsi, [r13+188h]
0x14001179f  movzx   edx, al; NewIrql
0x1400117a2  mov     rcx, rsi; SpinLock
0x1400117a5  call    cs:__imp_KeReleaseSpinLock
0x1400117ac  nop     dword ptr [rax+rax+00h]
0x1400117b1  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400117b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400117bf  nop     dword ptr [rax+rax+00h]
0x1400117c4  mov     rbx, [r13+8]
0x1400117c8  mov     r8b, 8; enum _NDIS_MDRV_REFTAG
0x1400117cb  mov     dl, 1; unsigned __int8
0x1400117cd  mov     rcx, r13; struct _NDIS_M_DRIVER_BLOCK *
0x1400117d0  movzx   edi, al
0x1400117d3  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x1400117d8  mov     r13, rbx
0x1400117db  test    rbx, rbx
0x1400117de  jnz     loc_1400116DF
0x1400117e4  mov     rbx, [rsp+140h+var_E0]
0x1400117e9  movzx   edx, dil; NewIrql
0x1400117ed  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400117f4  call    cs:__imp_KeReleaseSpinLock
0x1400117fb  nop     dword ptr [rax+rax+00h]
0x140011800  mov     r14, [rbp+40h+Irp]
0x140011804  xor     r13d, r13d
0x140011807  mov     rdx, [rsp+140h+var_E8]
0x14001180c  test    r15, r15
0x14001180f  jz      short loc_140011858
0x140011811  xorps   xmm0, xmm0
0x140011814  mov     qword ptr [rbp+40h+arg_8], r15
0x140011818  movups  [rsp+140h+var_D0], xmm0
0x14001181d  mov     qword ptr [rsp+140h+var_D0+8], r15
0x140011822  mov     r12, r15
0x140011825  movups  [rbp+40h+var_C0], xmm0
0x140011829  movups  [rbp+40h+var_B0], xmm0
0x14001182d  movups  [rbp+40h+var_A0], xmm0
0x140011831  movups  [rbp+40h+var_90], xmm0
0x140011835  movups  [rbp+40h+var_80], xmm0
0x140011839  mov     rax, [r15+6F0h]
0x140011840  mov     qword ptr [rbp+40h+var_C0], rax
0x140011844  movzx   eax, byte ptr [rbx+18h]
0x140011848  mov     byte ptr [rbp+40h+var_C0+8], al
0x14001184b  mov     rax, [rbx]
0x14001184e  lea     rbx, [rsp+140h+var_D0]
0x140011853  mov     qword ptr [rsp+140h+var_D0], rax
0x140011858  test    dword ptr [r12+7Ch], 4010h
0x140011861  jnz     loc_140011E7F
0x140011867  mov     r8d, [rdx+18h]; unsigned int
0x14001186b  cmp     r8d, 22604Ch
0x140011872  jz      loc_1400119F7
0x140011878  cmp     r8d, 226044h
0x14001187f  ja      loc_140011E3B
0x140011885  jz      loc_140012078
0x14001188b  lea     eax, [r8-170002h]; switch 175 cases
0x140011892  cmp     eax, 0AEh
0x140011897  ja      def_1400118B8; jumptable 00000001400118B8 default case, cases 1507331-1507333,1507335-1507341,1507343-1507357,1507359-1507367,1507369-1507371,1507373-1507375,1507377-1507389,1507391-1507431,1507433-1507435,1507437-1507439,1507441-1507447,1507449-1507471,1507473-1507475,1507477-1507479,1507481-1507483,1507485-1507495,1507497-1507503
0x14001189d  lea     r9, cs:140000000h
0x1400118a4  movzx   eax, ds:(byte_140103FEE - 140000000h)[r9+rax]
0x1400118ad  mov     ecx, ds:(jpt_1400118B8 - 140000000h)[r9+rax*4]
0x1400118b5  add     rcx, r9
0x1400118b8  jmp     rcx; switch jump
0x1400118be  cmp     byte ptr [rbx+18h], 0; jumptable 00000001400118B8 case 1507496
0x1400118c2  jz      loc_140011A10
0x1400118c8  mov     edx, 46h ; 'F'; enum _NDIS_MINIPORT_EVENT
0x1400118cd  mov     rcx, r12; struct _NDIS_MINIPORT_BLOCK *
0x1400118d0  call    ?ndisMiniportFatalError@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MINIPORT_EVENT@@@Z; ndisMiniportFatalError(_NDIS_MINIPORT_BLOCK *,_NDIS_MINIPORT_EVENT)
0x1400118d5  mov     esi, r13d
0x1400118d8  jmp     loc_140011A3F
0x1400118dd  mov     rcx, [r12+0EB8h]
0x1400118e5  movzx   eax, word ptr [rcx+8]
0x1400118e9  cmp     ax, [rdx+8]
0x1400118ed  jnz     loc_140011785
0x1400118f3  mov     rdx, [rdx+10h]; Buf2
0x1400118f7  mov     r8d, eax; Size
0x1400118fa  mov     rcx, [rcx+10h]; Buf1
0x1400118fe  call    memcmp
0x140011903  test    eax, eax
0x140011905  jnz     loc_140011785
0x14001190b  lea     rcx, [rbx+60h]; SpinLock
0x14001190f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140011916  nop     dword ptr [rax+rax+00h]
0x14001191b  mov     rax, gs:188h
0x140011924  mov     edx, 80200020h; unsigned int
0x140011929  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14001192c  mov     [rbx+208h], rax
0x140011933  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140011938  test    al, al
0x14001193a  jnz     short loc_14001194E
0x14001193c  test    dword ptr [rbx+7Ch], 1084110h
0x140011943  jnz     short loc_14001194E
0x140011945  cmp     dword ptr [rbx+5F0h], 1
0x14001194c  jz      short loc_140011986
0x14001194e  lea     rcx, [rbx+60h]; SpinLock
0x140011952  mov     qword ptr [rbx+208h], 0
0x14001195d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011964  nop     dword ptr [rax+rax+00h]
0x140011969  test    rsi, rsi
0x14001196c  jz      loc_140011785
0x140011972  mov     r8b, 57h ; 'W'; enum _NDIS_MP_REFTAG
0x140011975  xor     edx, edx; enum _NDIS_NSI_REFTAG
0x140011977  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14001197a  call    ?ndisDereferenceMiniportForNsi@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_NSI_REFTAG@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniportForNsi(_NDIS_MINIPORT_BLOCK *,_NDIS_NSI_REFTAG,_NDIS_MP_REFTAG)
0x14001197f  xor     esi, esi
0x140011981  jmp     loc_140011785
0x140011986  cmp     dword ptr [rbx+0F1Ch], 1
0x14001198d  jnz     short loc_14001194E
0x14001198f  mov     dl, 57h ; 'W'; enum _NDIS_MP_REFTAG
0x140011991  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140011996  test    al, al
0x140011998  jz      short loc_14001194E
0x14001199a  mov     rcx, [rbx+1328h]
0x1400119a1  xor     edx, edx
0x1400119a3  mov     rsi, r15
0x1400119a6  call    NdisReferenceWithTag
0x1400119ab  mov     rax, [rbx+0EB8h]
0x1400119b2  mov     r15, rbx
0x1400119b5  inc     dword ptr [rbx+0C34h]
0x1400119bb  mov     r14d, [rax]
0x1400119be  jmp     short loc_14001194E
0x1400119c0  cmp     eax, 1
0x1400119c3  jnz     loc_1400122E0
0x1400119c9  mov     rcx, cs:AddressWithinSection; AddressWithinSection
0x1400119d0  call    cs:__imp_MmLockPagableDataSection
0x1400119d7  nop     dword ptr [rax+rax+00h]
0x1400119dc  mov     rcx, rax; ImageSectionHandle
0x1400119df  mov     cs:ImageSectionHandle, rax
0x1400119e6  call    cs:__imp_MmUnlockPagableImageSection
0x1400119ed  nop     dword ptr [rax+rax+00h]
0x1400119f2  jmp     loc_140011645
0x1400119f7  mov     rax, [r14+0B8h]
0x1400119fe  mov     rcx, [rax+30h]
0x140011a02  mov     rax, [rcx+18h]
0x140011a06  cmp     byte ptr [rax+18h], 0
0x140011a0a  jnz     loc_140012557
0x140011a10  mov     esi, 0C0000001h
0x140011a15  jmp     short loc_140011A3F
0x140011a17  movzx   r8d, byte ptr [rbx+18h]; jumptable 00000001400118B8 case 1507480
0x140011a1c  lea     r9, [rsp+140h+var_F8]; int *
0x140011a21  mov     rdx, r14; struct _IRP *
0x140011a24  mov     dword ptr [rsp+140h+var_F8], r13d
0x140011a29  mov     rcx, r12; struct _NDIS_MINIPORT_BLOCK *
0x140011a2c  call    ?ndisGetAdapterRssInfo@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@EPEAH@Z; ndisGetAdapterRssInfo(_NDIS_MINIPORT_BLOCK *,_IRP *,uchar,int *)
0x140011a31  mov     esi, eax
0x140011a33  mov     eax, dword ptr [rsp+140h+var_F8]
0x140011a37  test    eax, eax
0x140011a39  jnz     loc_140012289
0x140011a3f  mov     r13, qword ptr [rbp+40h+arg_8]
0x140011a43  mov     eax, esi
0x140011a45  and     eax, 0C0230000h
0x140011a4a  cmp     eax, 0C0230000h
0x140011a4f  jnz     short loc_140011A5A
0x140011a51  movzx   esi, si
0x140011a54  or      esi, 0C0010000h
0x140011a5a  test    r15, r15
0x140011a5d  jz      loc_1400125FB
0x140011a63  lea     rcx, [r15+60h]; SpinLock
0x140011a67  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011a6e  nop     dword ptr [rax+rax+00h]
0x140011a73  movzx   edi, al
0x140011a76  mov     rax, gs:188h
0x140011a7f  mov     r8, [r15+1328h]; BugCheckParameter3
0x140011a86  mov     [r15+208h], rax
0x140011a8d  lea     rax, [r8-2]
0x140011a91  cmp     rax, 1
0x140011a95  jbe     short loc_140011B14
0x140011a97  cmp     r8, 2
0x140011a9b  jb      loc_14001223A
0x140011aa1  cmp     byte ptr [r8+2], 0
0x140011aa6  ja      short loc_140011ABB
0x140011aa8  xor     r9d, r9d; BugCheckParameter4
0x140011aab  mov     edx, 2; BugCheckParameter2
0x140011ab0  mov     ecx, 1Eh; BugCheckParameter1
0x140011ab5  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x140011abb  movzx   ecx, byte ptr [r8+1]
0x140011ac0  test    ecx, ecx
0x140011ac2  jnz     loc_1400120C9
0x140011ac8  mov     r9, [r8+8]
0x140011acc  test    r9, r9
0x140011acf  jnz     short loc_140011AE4
0x140011ad1  btr     dword ptr [r8+10h], 0
0x140011ad7  jb      short loc_140011B14
0x140011ad9  xor     edx, edx; unsigned __int8
0x140011adb  mov     rcx, r8; BugCheckParameter3
0x140011ade  call    ?ndisReportRefcountImbalance@@YAXPEAU_NDIS_REFCOUNT_BLOCK@@E@Z; ndisReportRefcountImbalance(_NDIS_REFCOUNT_BLOCK *,uchar)
0x140011ae4  movzx   r10d, byte ptr [r8+3]
0x140011ae9  xor     cl, cl
0x140011aeb  nop     dword ptr [rax+rax+00h]
0x140011af0  cmp     cl, r10b
0x140011af3  jnb     short loc_140011AD1
0x140011af5  movzx   eax, cl
0x140011af8  cmp     byte ptr [r9+rax*2], 0
0x140011afd  lea     rdx, [r9+rax*2]
0x140011b01  jz      short loc_140011B07
0x140011b03  inc     cl
0x140011b05  jmp     short loc_140011AF0
0x140011b07  movzx   eax, byte ptr [rdx+1]
0x140011b0b  test    al, al
0x140011b0d  jz      short loc_140011B03
0x140011b0f  dec     al
  ... truncated ...
```
