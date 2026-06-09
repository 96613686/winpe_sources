# NatUnloadDriver

- ea: `0x140007ca0`
- end: `0x140008a15`
- name: `NatUnloadDriver`
- size: `3445`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001030`
- `0x14000218c`
- `0x1400021bc`
- `0x140005300`
- `0x140006918`
- `0x140006e18`
- `0x140007ca0`
- `0x14000bc50`
- `0x14000d66c`
- `0x140011624`
- `0x140016524`
- `0x1400292ac`
- `0x14002c238`
- `0x14002c710`
- `0x1400420c0`
- `0x140042168`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400083e8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000866d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400086de`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400087c5`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400083e8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000866d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400086de`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400087c5`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400082ce`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400082ce`
- `ntoskrnl!KeCancelTimer` at `0x1400082e1`
- `ntoskrnl!KeCancelTimer` at `0x1400082e1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400080a7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400084b9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000859e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000888e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400080a7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400084b9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000859e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000888e`
- `ntoskrnl!IoDeleteDevice` at `0x140008260`
- `ntoskrnl!IoDeleteDevice` at `0x140008260`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000815b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000815b`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140008947`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140008947`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140007de8`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140007de8`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400081c4`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400081c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008250`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008250`
- `ntoskrnl!IofCompleteRequest` at `0x140008093`
- `ntoskrnl!IofCompleteRequest` at `0x140008093`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000823b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008652`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008960`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000823b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008652`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008960`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000811d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000813b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008169`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400084cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400085b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400087b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000811d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000813b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008169`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400084cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400085b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400087b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088a9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008077`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400084a2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008587`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008877`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008077`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400084a2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008587`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008877`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008006`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008103`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008379`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000845c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008541`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000874f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008839`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008006`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008103`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008379`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000845c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008541`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000874f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008839`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140007ed5`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140007ed5`
- `NETIO!NmrDeregisterClient` at `0x140007d6c`
- `NETIO!NmrDeregisterClient` at `0x140007d6c`

## pseudocode

```c
__int64 __fastcall NatUnloadDriver(__int64 a1)
{
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  __int64 v4; // rbx
  __int64 v5; // rcx
  ULONG MaximumProcessorCount; // ebp
  ULONG v7; // esi
  __int64 i; // rdi
  __int64 v9; // rcx
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  KIRQL v12; // di
  __int64 v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rax
  KIRQL v17; // al
  bool v18; // zf
  NTSTATUS v19; // eax
  KIRQL v20; // bl
  PVOID v21; // rcx
  _QWORD *v22; // rax
  PVOID *v23; // rdx
  KIRQL v24; // di
  PKDPC BufferChainingDpc; // rbx
  struct _SINGLE_LIST_ENTRY *v26; // rcx
  struct _SINGLE_LIST_ENTRY *Next; // rdx
  KIRQL v28; // di
  struct _SINGLE_LIST_ENTRY *v29; // rbx
  struct _SINGLE_LIST_ENTRY *v30; // rcx
  struct _SINGLE_LIST_ENTRY *v31; // rdx
  PVOID v32; // rcx
  _QWORD *v33; // rax
  PVOID *v34; // rdx
  KIRQL v35; // bl
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  KIRQL v39; // di
  PVOID v40; // rbx
  _QWORD *v41; // rcx
  PVOID *v42; // rdx
  _BYTE *v43; // rbx
  unsigned int v44; // edi
  unsigned __int64 v45; // rcx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    }
  }
  NatDeregisterCallout(ReservePort);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
  }
  v2 = 0;
  if ( gNatNsiHandle )
  {
    v3 = NmrDeregisterClient(gNatNsiHandle);
    v2 = v3;
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_23;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_a039967293013d6e0a781349d74ce0cf_Traceguids,
          (unsigned int)v3);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids, v2);
  }
LABEL_23:
  v4 = NatShimPool;
  if ( NatShimPool )
  {
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v7 = 0;
    for ( i = v4 + 64; v7 < MaximumProcessorCount; i += 64 )
    {
      FsbpFreeList(v5, i);
      FsbpFreeList(v9, i + 16);
      ++v7;
    }
    ExFreePoolWithTag(*(PVOID *)(v4 + 24), 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
      }
    }
  }
  v10 = 0;
  if ( !gNatNsiHandle )
    goto LABEL_54;
  v11 = NmrWaitForClientDeregisterComplete(gNatNsiHandle);
  v10 = v11;
  if ( v11 >= 0 )
    goto LABEL_45;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_a039967293013d6e0a781349d74ce0cf_Traceguids,
        (unsigned int)v11);
LABEL_45:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
    }
  }
  ReleaseComponentReference();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
  }
  gNatNsiHandle = 0;
LABEL_54:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids, v10);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
      }
    }
  }
  v12 = KeAcquireSpinLockRaiseToDpc(&NotificationLock);
  while ( (__int64 *)NotificationList != &NotificationList )
  {
    v13 = NotificationList - 168;
    v14 = (_QWORD *)NotificationList;
    v15 = *(_QWORD *)NotificationList;
    if ( *(_QWORD *)(*(_QWORD *)NotificationList + 8LL) != NotificationList
      || (v16 = *(_QWORD **)(v13 + 176), *v16 != NotificationList) )
    {
LABEL_193:
      __fastfail(3u);
    }
    *v16 = v15;
    *(_QWORD *)(v15 + 8) = v16;
    *(_QWORD *)(v13 + 176) = v14;
    *v14 = v14;
    if ( _InterlockedExchange64((volatile __int64 *)(v13 + 104), 0) )
    {
      KeReleaseSpinLockFromDpcLevel(&NotificationLock);
      *(_DWORD *)(v13 + 48) = -1073741536;
      *(_QWORD *)(v13 + 56) = 0;
      IofCompleteRequest((PIRP)v13, 0);
      ReleaseComponentReference();
      KeAcquireSpinLockAtDpcLevel(&NotificationLock);
    }
  }
  KeReleaseSpinLock(&NotificationLock, v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  if ( WPP_MAIN_CB.StackSize )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v17);
  }
  else
  {
    v18 = WPP_MAIN_CB.DeviceType-- == 1;
    WPP_MAIN_CB.StackSize = 1;
    if ( v18 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v17);
      ((void (*)(void))WPP_MAIN_CB.Queue.Wcb.DeviceRoutine)();
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v17);
      KeWaitForSingleObject(&WPP_MAIN_CB.Queue, Executive, 0, 0, 0);
    }
  }
  NatDeleteExternalNaming();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
  }
  v19 = IoWMIRegistrationControl(NatDeviceObject, 2u);
  if ( v19 >= 0 )
    goto LABEL_90;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        63,
        WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids,
        (unsigned int)v19);
LABEL_90:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
  {
    ExFreePoolWithTag(*(PVOID *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, 0);
    RtlInitUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DeviceContext, 0);
  }
  IoDeleteDevice(*(PDEVICE_OBJECT *)(a1 + 8));
  NatShutdownPptpManagement();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
    }
  }
  KeFlushQueuedDpcs();
  KeCancelTimer(&TimerObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
      }
    }
  }
  v20 = KeAcquireSpinLockRaiseToDpc(&MappingLock);
  while ( 1 )
  {
    v21 = MappingList;
    if ( MappingList == &MappingList )
      break;
    v22 = *(_QWORD **)MappingList;
    if ( *(PVOID *)(*(_QWORD *)MappingList + 8LL) != MappingList )
      goto LABEL_193;
    v23 = (PVOID *)*((_QWORD *)MappingList + 1);
    if ( *v23 != MappingList )
      goto LABEL_193;
    *v23 = v22;
    v22[1] = v23;
    NatCleanupMapping(v21);
  }
  MappingTree = 0;
  KeReleaseSpinLock(&MappingLock, v20);
  ExDeleteNPagedLookasideList(&MappingLookasideList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
    }
  }
  v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  while ( 1 )
  {
    BufferChainingDpc = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
    if ( (PKDPC *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc == &WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
      break;
    v26 = *(struct _SINGLE_LIST_ENTRY **)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
    if ( *(PKDPC *)(*(_QWORD *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc + 8LL) != WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
      goto LABEL_193;
    Next = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc->DpcListEntry.Next;
    if ( Next->Next != (struct _SINGLE_LIST_ENTRY *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
      goto LABEL_193;
    Next->Next = v26;
    v26[1].Next = Next;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
    NatCleanupEditor(BufferChainingDpc);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, v24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
    }
  }
  v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  while ( 1 )
  {
    v29 = WPP_MAIN_CB.Dpc.DpcListEntry.Next;
    if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next == &WPP_MAIN_CB.Dpc.DpcListEntry )
      break;
    v30 = WPP_MAIN_CB.Dpc.DpcListEntry.Next->Next;
    if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next->Next[1].Next != WPP_MAIN_CB.Dpc.DpcListEntry.Next )
      goto LABEL_193;
    v31 = WPP_MAIN_CB.Dpc.DpcListEntry.Next[1].Next;
    if ( v31->Next != WPP_MAIN_CB.Dpc.DpcListEntry.Next )
      goto LABEL_193;
    v31->Next = v30;
    v30[1].Next = v31;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
    NatCleanupDirector(v29);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine, v28);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
    }
  }
  while ( 1 )
  {
    v32 = DynamicTicketList;
    if ( DynamicTicketList == &DynamicTicketList )
      break;
    v33 = *(_QWORD **)DynamicTicketList;
    if ( *(PVOID *)(*(_QWORD *)DynamicTicketList + 8LL) != DynamicTicketList )
      goto LABEL_193;
    v34 = (PVOID *)*((_QWORD *)DynamicTicketList + 1);
    if ( *v34 != DynamicTicketList )
      goto LABEL_193;
    *v34 = v33;
    v33[1] = v34;
    ExFreePoolWithTag(v32, 0);
  }
  DynamicTicketCount = 0;
  ExDeleteNPagedLookasideList(&TicketLookasideList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids);
    }
  }
  ExDeleteNPagedLookasideList(&IpLookasideList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
    }
  }
  v35 = KeAcquireSpinLockRaiseToDpc(&IcmpMappingLock);
  while ( 1 )
  {
    v36 = qword_14003E4B0;
    if ( (__int64 *)qword_14003E4B0 == &qword_14003E4B0 )
      break;
    v37 = *(_QWORD *)qword_14003E4B0;
    if ( *(_QWORD *)(*(_QWORD *)qword_14003E4B0 + 8LL) != qword_14003E4B0 )
      goto LABEL_193;
    v38 = *(_QWORD **)(qword_14003E4B0 + 8);
    if ( *v38 != qword_14003E4B0 )
      goto LABEL_193;
    *v38 = v37;
    *(_QWORD *)(v37 + 8) = v38;
    NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, (PVOID)(v36 - 16));
  }
  KeReleaseSpinLock(&IcmpMappingLock, v35);
  ExDeleteNPagedLookasideList(&IcmpLookasideList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    }
  }
  v39 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  while ( 1 )
  {
    v40 = InterfaceList;
    if ( InterfaceList == &InterfaceList )
      break;
    v41 = *(_QWORD **)InterfaceList;
    if ( *(PVOID *)(*(_QWORD *)InterfaceList + 8LL) != InterfaceList )
      goto LABEL_193;
    v42 = (PVOID *)*((_QWORD *)InterfaceList + 1);
    if ( *v42 != InterfaceList )
      goto LABEL_193;
    *v42 = v41;
    v41[1] = v42;
    KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
    NatCleanupInterface(v40);
    KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
  }
  KeReleaseSpinLock(&InterfaceLock, v39);
  InterfaceCount = 0;
  TicketCount = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    }
  }
  v43 = NatDbgBufPool;
  if ( NatDbgBufPool )
  {
    v44 = *(_DWORD *)NatDbgBufPool;
    while ( (--v44 & 0x80000000) == 0 )
    {
      v45 = (unsigned __int64)v44 << 7;
      if ( v43[v45 + 176] )
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v43[v45 + 64]);
    }
    ExFreePoolWithTag(v43, 0x6372544Eu);
  }
  McGenEventUnregister_EtwUnregister();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
    }
  }
  result = WppCleanupKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140007ca0  push    rbx
0x140007ca2  push    rbp
0x140007ca3  push    rsi
0x140007ca4  push    rdi
0x140007ca5  push    r12
0x140007ca7  push    r13
0x140007ca9  push    r14
0x140007cab  push    r15
0x140007cad  sub     rsp, 38h
0x140007cb1  mov     r14, rcx
0x140007cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007cbb  lea     r15, WPP_GLOBAL_Control
0x140007cc2  lea     rsi, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007cc9  mov     r13d, 1
0x140007ccf  mov     r12b, 6
0x140007cd2  cmp     rcx, r15
0x140007cd5  jz      short loc_140007D20
0x140007cd7  mov     eax, [rcx+2Ch]
0x140007cda  test    r13b, al
0x140007cdd  jz      short loc_140007CF5
0x140007cdf  cmp     [rcx+29h], r12b
0x140007ce3  jb      short loc_140007CF5
0x140007ce5  mov     rcx, [rcx+18h]
0x140007ce9  lea     edx, [r13+3Bh]
0x140007ced  mov     r8, rsi
0x140007cf0  call    WPP_SF_
0x140007cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140007cfc  cmp     rcx, r15
0x140007cff  jz      short loc_140007D20
0x140007d01  mov     eax, [rcx+2Ch]
0x140007d04  test    r13b, al
0x140007d07  jz      short loc_140007D20
0x140007d09  cmp     [rcx+29h], r12b
0x140007d0d  jb      short loc_140007D20
0x140007d0f  mov     rcx, [rcx+18h]
0x140007d13  mov     edx, 38h ; '8'
0x140007d18  mov     r8, rsi
0x140007d1b  call    WPP_SF_
0x140007d20  mov     ecx, cs:ReservePort
0x140007d26  call    NatDeregisterCallout
0x140007d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d32  lea     rdi, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x140007d39  cmp     rcx, r15
0x140007d3c  jz      short loc_140007D5C
0x140007d3e  mov     eax, [rcx+2Ch]
0x140007d41  test    al, 2
0x140007d43  jz      short loc_140007D5C
0x140007d45  cmp     [rcx+29h], r12b
0x140007d49  jb      short loc_140007D5C
0x140007d4b  mov     rcx, [rcx+18h]
0x140007d4f  mov     edx, 0Dh
0x140007d54  mov     r8, rdi
0x140007d57  call    WPP_SF_
0x140007d5c  mov     rcx, cs:gNatNsiHandle; NmrClientHandle
0x140007d63  xor     ebp, ebp
0x140007d65  mov     ebx, ebp
0x140007d67  test    rcx, rcx
0x140007d6a  jz      short loc_140007DAA
0x140007d6c  call    cs:__imp_NmrDeregisterClient
0x140007d73  nop     dword ptr [rax+rax+00h]
0x140007d78  mov     ebx, eax
0x140007d7a  test    eax, eax
0x140007d7c  jns     short loc_140007DAA
0x140007d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d85  cmp     rcx, r15
0x140007d88  jz      short loc_140007DD7
0x140007d8a  mov     edx, [rcx+2Ch]
0x140007d8d  test    dl, 2
0x140007d90  jz      short loc_140007DAA
0x140007d92  cmp     byte ptr [rcx+29h], 2
0x140007d96  jb      short loc_140007DAA
0x140007d98  mov     rcx, [rcx+18h]
0x140007d9c  lea     edx, [rbp+0Eh]
0x140007d9f  mov     r9d, eax
0x140007da2  mov     r8, rdi
0x140007da5  call    WPP_SF_d
0x140007daa  mov     rcx, cs:WPP_GLOBAL_Control
0x140007db1  cmp     rcx, r15
0x140007db4  jz      short loc_140007DD7
0x140007db6  mov     eax, [rcx+2Ch]
0x140007db9  test    al, 2
0x140007dbb  jz      short loc_140007DD7
0x140007dbd  cmp     [rcx+29h], r12b
0x140007dc1  jb      short loc_140007DD7
0x140007dc3  mov     rcx, [rcx+18h]
0x140007dc7  mov     edx, 0Fh
0x140007dcc  mov     r9d, ebx
0x140007dcf  mov     r8, rdi
0x140007dd2  call    WPP_SF_d
0x140007dd7  mov     rbx, cs:NatShimPool
0x140007dde  test    rbx, rbx
0x140007de1  jz      short loc_140007E43
0x140007de3  mov     ecx, 0FFFFh; GroupNumber
0x140007de8  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140007def  nop     dword ptr [rax+rax+00h]
0x140007df4  mov     ebp, eax
0x140007df6  test    rbx, rbx
0x140007df9  jz      short loc_140007E41
0x140007dfb  xor     esi, esi
0x140007dfd  lea     rdi, [rbx+40h]
0x140007e01  test    eax, eax
0x140007e03  jz      short loc_140007E21
0x140007e05  mov     rdx, rdi
0x140007e08  call    FsbpFreeList
0x140007e0d  lea     rdx, [rdi+10h]
0x140007e11  call    FsbpFreeList
0x140007e16  add     esi, r13d
0x140007e19  add     rdi, 40h ; '@'
0x140007e1d  cmp     esi, ebp
0x140007e1f  jb      short loc_140007E05
0x140007e21  mov     rcx, [rbx+18h]; P
0x140007e25  xor     edx, edx; Tag
0x140007e27  call    cs:__imp_ExFreePoolWithTag
0x140007e2e  nop     dword ptr [rax+rax+00h]
0x140007e33  lea     rdi, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x140007e3a  lea     rsi, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007e41  xor     ebp, ebp
0x140007e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e4a  cmp     rcx, r15
0x140007e4d  jz      short loc_140007EC3
0x140007e4f  mov     eax, [rcx+2Ch]
0x140007e52  test    r13b, al
0x140007e55  jz      short loc_140007E6E
0x140007e57  cmp     [rcx+29h], r12b
0x140007e5b  jb      short loc_140007E6E
0x140007e5d  mov     rcx, [rcx+18h]
0x140007e61  mov     edx, 39h ; '9'
0x140007e66  mov     r8, rsi
0x140007e69  call    WPP_SF_
0x140007e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e75  cmp     rcx, r15
0x140007e78  jz      short loc_140007EC3
0x140007e7a  mov     eax, [rcx+2Ch]
0x140007e7d  test    r13b, al
0x140007e80  jz      short loc_140007E99
0x140007e82  cmp     [rcx+29h], r12b
0x140007e86  jb      short loc_140007E99
0x140007e88  mov     rcx, [rcx+18h]
0x140007e8c  mov     edx, 3Ah ; ':'
0x140007e91  mov     r8, rsi
0x140007e94  call    WPP_SF_
0x140007e99  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ea0  cmp     rcx, r15
0x140007ea3  jz      short loc_140007EC3
0x140007ea5  mov     eax, [rcx+2Ch]
0x140007ea8  test    al, 2
0x140007eaa  jz      short loc_140007EC3
0x140007eac  cmp     [rcx+29h], r12b
0x140007eb0  jb      short loc_140007EC3
0x140007eb2  mov     rcx, [rcx+18h]
0x140007eb6  mov     edx, 12h
0x140007ebb  mov     r8, rdi
0x140007ebe  call    WPP_SF_
0x140007ec3  mov     rcx, cs:gNatNsiHandle; NmrClientHandle
0x140007eca  mov     ebx, ebp
0x140007ecc  test    rcx, rcx
0x140007ecf  jz      loc_140007F75
0x140007ed5  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140007edc  nop     dword ptr [rax+rax+00h]
0x140007ee1  mov     ebx, eax
0x140007ee3  test    eax, eax
0x140007ee5  jns     short loc_140007F15
0x140007ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x140007eee  cmp     rcx, r15
0x140007ef1  jz      short loc_140007F3F
0x140007ef3  mov     edx, [rcx+2Ch]
0x140007ef6  test    dl, 2
0x140007ef9  jz      short loc_140007F15
0x140007efb  cmp     byte ptr [rcx+29h], 2
0x140007eff  jb      short loc_140007F15
0x140007f01  mov     rcx, [rcx+18h]
0x140007f05  mov     edx, 13h
0x140007f0a  mov     r9d, eax
0x140007f0d  mov     r8, rdi
0x140007f10  call    WPP_SF_d
0x140007f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f1c  cmp     rcx, r15
0x140007f1f  jz      short loc_140007F3F
0x140007f21  mov     eax, [rcx+2Ch]
0x140007f24  test    al, 2
0x140007f26  jz      short loc_140007F3F
0x140007f28  cmp     [rcx+29h], r12b
0x140007f2c  jb      short loc_140007F3F
0x140007f2e  mov     rcx, [rcx+18h]
0x140007f32  mov     edx, 10h
0x140007f37  mov     r8, rdi
0x140007f3a  call    WPP_SF_
0x140007f3f  call    ReleaseComponentReference
0x140007f44  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f4b  cmp     rcx, r15
0x140007f4e  jz      short loc_140007F6E
0x140007f50  mov     eax, [rcx+2Ch]
0x140007f53  test    al, 2
0x140007f55  jz      short loc_140007F6E
0x140007f57  cmp     [rcx+29h], r12b
0x140007f5b  jb      short loc_140007F6E
0x140007f5d  mov     rcx, [rcx+18h]
0x140007f61  mov     edx, 11h
0x140007f66  mov     r8, rdi
0x140007f69  call    WPP_SF_
0x140007f6e  mov     cs:gNatNsiHandle, rbp
0x140007f75  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f7c  cmp     rcx, r15
0x140007f7f  jz      short loc_140007FFC
0x140007f81  mov     eax, [rcx+2Ch]
0x140007f84  test    al, 2
0x140007f86  jz      short loc_140007FA2
0x140007f88  cmp     [rcx+29h], r12b
0x140007f8c  jb      short loc_140007FA2
0x140007f8e  mov     rcx, [rcx+18h]
0x140007f92  mov     edx, 14h
0x140007f97  mov     r9d, ebx
0x140007f9a  mov     r8, rdi
0x140007f9d  call    WPP_SF_d
0x140007fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fa9  cmp     rcx, r15
0x140007fac  jz      short loc_140007FFC
0x140007fae  mov     eax, [rcx+2Ch]
0x140007fb1  test    r13b, al
0x140007fb4  jz      short loc_140007FCD
0x140007fb6  cmp     [rcx+29h], r12b
0x140007fba  jb      short loc_140007FCD
0x140007fbc  mov     rcx, [rcx+18h]
0x140007fc0  mov     edx, 3Bh ; ';'
0x140007fc5  mov     r8, rsi
0x140007fc8  call    WPP_SF_
0x140007fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fd4  cmp     rcx, r15
0x140007fd7  jz      short loc_140007FFC
0x140007fd9  mov     eax, [rcx+2Ch]
0x140007fdc  test    r13b, al
0x140007fdf  jz      short loc_140007FFC
0x140007fe1  cmp     [rcx+29h], r12b
0x140007fe5  jb      short loc_140007FFC
0x140007fe7  mov     rcx, [rcx+18h]
0x140007feb  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140007ff2  mov     edx, 22h ; '"'
0x140007ff7  call    WPP_SF_
0x140007ffc  lea     rsi, NotificationLock
0x140008003  mov     rcx, rsi; SpinLock
0x140008006  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000800d  nop     dword ptr [rax+rax+00h]
0x140008012  mov     dil, al
0x140008015  mov     rbx, cs:NotificationList
0x14000801c  lea     rax, NotificationList
0x140008023  cmp     rbx, rax
0x140008026  jz      loc_1400080B8
0x14000802c  add     rbx, 0FFFFFFFFFFFFFF58h
0x140008033  lea     rcx, [rbx+0A8h]
0x14000803a  mov     rdx, [rcx]
0x14000803d  cmp     [rdx+8], rcx
0x140008041  jnz     loc_14000889C
0x140008047  mov     rax, [rbx+0B0h]
0x14000804e  cmp     [rax], rcx
0x140008051  jnz     loc_14000889C
0x140008057  mov     [rax], rdx
0x14000805a  mov     [rdx+8], rax
0x14000805e  mov     rax, rbp
0x140008061  mov     [rbx+0B0h], rcx
0x140008068  mov     [rcx], rcx
0x14000806b  xchg    rax, [rbx+68h]
0x14000806f  test    rax, rax
0x140008072  jz      short loc_140008015
0x140008074  mov     rcx, rsi; SpinLock
0x140008077  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000807e  nop     dword ptr [rax+rax+00h]
0x140008083  xor     edx, edx; PriorityBoost
0x140008085  mov     dword ptr [rbx+30h], 0C0000120h
0x14000808c  mov     rcx, rbx; Irp
0x14000808f  mov     [rbx+38h], rbp
0x140008093  call    cs:__imp_IofCompleteRequest
0x14000809a  nop     dword ptr [rax+rax+00h]
0x14000809f  call    ReleaseComponentReference
0x1400080a4  mov     rcx, rsi; SpinLock
0x1400080a7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400080ae  nop     dword ptr [rax+rax+00h]
0x1400080b3  jmp     loc_140008015
0x1400080b8  mov     dl, dil; NewIrql
0x1400080bb  mov     rcx, rsi; SpinLock
0x1400080be  call    cs:__imp_KeReleaseSpinLock
0x1400080c5  nop     dword ptr [rax+rax+00h]
0x1400080ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080d1  cmp     rcx, r15
0x1400080d4  jz      short loc_1400080F9
0x1400080d6  mov     eax, [rcx+2Ch]
0x1400080d9  test    r13b, al
0x1400080dc  jz      short loc_1400080F9
0x1400080de  cmp     [rcx+29h], r12b
0x1400080e2  jb      short loc_1400080F9
0x1400080e4  mov     rcx, [rcx+18h]
0x1400080e8  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x1400080ef  mov     edx, 23h ; '#'
0x1400080f4  call    WPP_SF_
0x1400080f9  lea     rbx, WPP_MAIN_CB.DeviceExtension
0x140008100  mov     rcx, rbx; SpinLock
0x140008103  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000810a  nop     dword ptr [rax+rax+00h]
0x14000810f  cmp     cs:WPP_MAIN_CB.StackSize, bpl
0x140008116  mov     rcx, rbx; SpinLock
0x140008119  mov     dl, al; NewIrql
  ... truncated ...
```
