# ndisPnPIrpRemoveDevice(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *,uchar *,uchar *)

- ea: `0x140149880`
- end: `0x140149b3c`
- name: `?ndisPnPIrpRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@PEAE3@Z`
- size: `700`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, struct _NDIS_MINIPORT_BLOCK *@<rdx>, PIRP Irp@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14003e640`
- `0x14006b450`

## callees

- `0x14000dbe0`
- `0x140010d20`
- `0x140017510`
- `0x14001ddf0`
- `0x14001ded0`
- `0x14003dec0`
- `0x14003f590`
- `0x140052740`
- `0x140053280`
- `0x140070890`
- `0x140079f80`
- `0x140087620`
- `0x140087b14`
- `0x140088a2c`
- `0x14008c71c`
- `0x14009db0c`
- `0x1400a2ecc`
- `0x1400b9768`
- `0x1400e935c`
- `0x140149880`
- `0x14014d440`
- `0x14015d480`
- `0x140180350`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140149b0b`
- `ntoskrnl!IoDeleteDevice` at `0x140149b0b`
- `ntoskrnl!IofCallDriver` at `0x140149ae7`
- `ntoskrnl!IofCallDriver` at `0x140149ae7`
- `ntoskrnl!IoDetachDevice` at `0x140149afc`
- `ntoskrnl!IoDetachDevice` at `0x140149afc`
- `ntoskrnl!KeInitializeEvent` at `0x14014997b`
- `ntoskrnl!KeInitializeEvent` at `0x14014997b`

## pseudocode

```c
__int64 __fastcall ndisPnPIrpRemoveDevice(
        PDEVICE_OBJECT DeviceObject,
        struct _NDIS_MINIPORT_BLOCK *a2,
        PIRP Irp,
        unsigned __int8 *a4,
        unsigned __int8 *a5)
{
  unsigned int v5; // esi
  unsigned int InterlockedFlags; // eax
  unsigned int v11; // ett
  bool v12; // zf
  unsigned int v13; // eax
  unsigned int v14; // ett
  _NDIS_M_DRIVER_BLOCK *DriverHandle; // rax
  _NDIS_SG_DMA_BLOCK *MiniportSGDmaBlock; // rax
  __int64 result; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  v5 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      9,
      35,
      (struct _GUID *)&WPP_a0375633690b3eae5e161e1c8b2d1e08_Traceguids,
      (char)a2,
      (__int64)a2->pAdapterInstanceName);
  ndisLogMiniportEvent(a2, NdisMEvent_DeviceRemove);
  _m_prefetchw(&a2->InterlockedFlags);
  InterlockedFlags = a2->InterlockedFlags;
  do
  {
    v11 = InterlockedFlags;
    InterlockedFlags = _InterlockedCompareExchange(
                         (volatile signed __int32 *)&a2->InterlockedFlags,
                         InterlockedFlags,
                         InterlockedFlags);
  }
  while ( v11 != InterlockedFlags );
  if ( (InterlockedFlags & 0x200) == 0 )
  {
    NdisTraceLoggingDeviceRemoved(a2, 4);
    ndisPowerSaveStop(a2, 2);
    ndisWaitForKernelObject(&a2->PowerD0CompleteEvent);
    if ( (a2->PnPFlags & 0x100) == 0 && a2->CurrentDevicePowerState > PowerDeviceD0 )
      v5 = ndisWakeUpDevice(a2);
    ndisReferenceMiniportNoCheck(a2, MPREF_PNP_REMOVING);
  }
  if ( !a2->Ref.ReferenceCount )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v12 = a2->PnPDeviceState == NdisPnPDeviceRemoved;
  a2->RemoveReadyEvent = &Event;
  if ( !v12 )
    ndisPnPRemoveDeviceEx(a2);
  if ( Irp )
    Irp->IoStatus.Status = v5;
  if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( MINIPORT_TEST_FLAG(a2, 0x80u) )
    {
      _m_prefetchw(&a2->InterlockedFlags);
      v13 = a2->InterlockedFlags;
      do
      {
        v14 = v13;
        v13 = _InterlockedCompareExchange((volatile signed __int32 *)&a2->InterlockedFlags, v13, v13);
      }
      while ( v14 != v13 );
      if ( (v13 & 0x200) != 0 )
        ndisMiniportRevokeOpenHandles(a2);
    }
  }
  ndisDereferenceMiniport(a2, MPREF_PNP_REMOVING);
  ndisWaitForKernelObject(&Event);
  DriverHandle = a2->DriverHandle;
  a2->RemoveReadyEvent = 0;
  if ( DriverHandle->HookType == NdisMiniportHookDriverTypeWdi && !ndisBugCheckOnReenumerationTimeout )
    ndisDisarmWatchdog(a2->ReenumerateWatchdog.m_ptr);
  MiniportSGDmaBlock = a2->MiniportSGDmaBlock;
  if ( MiniportSGDmaBlock && MiniportSGDmaBlock->DmaAdapterRefCount == 1 && MINIPORT_TEST_FLAG(a2, 0x40u) )
  {
    a2->MiniportSGDmaBlock->DmaResourcesReleasedEvent = 0;
    ndisDereferenceDmaAdapter(a2->MiniportSGDmaBlock);
    MINIPORT_CLEAR_FLAG(a2, 0x40u);
  }
  if ( ndisIsMiniportStarted(a2) )
  {
    ndisDeQueueMiniportOnDriver(a2, a2->DriverHandle);
    ndisDereferenceDriver(a2->DriverHandle, 0, MDRVREF_MINIPORT);
    if ( MINIPORT_TEST_FLAG(a2, 0x20000u) )
      ndisDereferencePackage((struct _PKG_REF *)&dword_140120018);
  }
  ndisRemoveMiniportFromGlobalList(a2);
  if ( Irp )
  {
    ++Irp->CurrentLocation;
    ++Irp->Tail.Overlay.CurrentStackLocation;
    v5 = IofCallDriver(a2->NextDeviceObject, Irp);
    IoDetachDevice(a2->NextDeviceObject);
    IoDeleteDevice(DeviceObject);
  }
  ndisMDeleteMiniportBlockOnRemove(a2);
  *a5 = 0;
  result = v5;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x140149880  mov     r11, rsp
0x140149883  push    rbx
0x140149884  push    rbp
0x140149885  push    rsi
0x140149886  push    rdi
0x140149887  push    r14
0x140149889  sub     rsp, 60h
0x14014988d  xor     esi, esi
0x14014988f  xorps   xmm0, xmm0
0x140149892  xor     eax, eax
0x140149894  mov     r14, r9
0x140149897  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14014989c  mov     [r11-38h], rax
0x1401498a0  mov     rdi, r8
0x1401498a3  mov     rbx, rdx
0x1401498a6  mov     rbp, rcx
0x1401498a9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401498b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401498b7  jz      short loc_1401498EB
0x1401498b9  mov     rax, [rdx+0F10h]
0x1401498c0  lea     r9d, [rsi+23h]; int
0x1401498c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401498cb  lea     r8d, [rsi+9]; int
0x1401498cf  mov     [r11-58h], rax
0x1401498d3  lea     rax, WPP_a0375633690b3eae5e161e1c8b2d1e08_Traceguids
0x1401498da  mov     [r11-60h], rdx
0x1401498de  mov     [r11-68h], rax
0x1401498e2  mov     rcx, [rcx+40h]; int
0x1401498e6  call    WPP_RECORDER_SF_qZ
0x1401498eb  mov     edx, 23h ; '#'; enum _NDIS_MINIPORT_EVENT
0x1401498f0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401498f3  call    ?ndisLogMiniportEvent@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MINIPORT_EVENT@@@Z; ndisLogMiniportEvent(_NDIS_MINIPORT_BLOCK *,_NDIS_MINIPORT_EVENT)
0x1401498f8  prefetchw byte ptr [rbx+1148h]
0x1401498ff  mov     eax, [rbx+1148h]
0x140149905  mov     ecx, eax
0x140149907  lock cmpxchg [rbx+1148h], ecx
0x14014990f  jnz     short loc_140149905
0x140149911  bt      eax, 9
0x140149915  jb      short loc_140149963
0x140149917  mov     edx, 4
0x14014991c  mov     rcx, rbx
0x14014991f  call    ?NdisTraceLoggingDeviceRemoved@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_TRACEFORMAT_REMOVAL_REASON@@@Z; NdisTraceLoggingDeviceRemoved(_NDIS_MINIPORT_BLOCK *,_NDIS_TRACEFORMAT_REMOVAL_REASON)
0x140149924  mov     edx, 2
0x140149929  mov     rcx, rbx
0x14014992c  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x140149931  lea     rcx, [rbx+1078h]; void *
0x140149938  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14014993d  test    dword ptr [rbx+7Ch], 100h
0x140149944  jnz     short loc_140149959
0x140149946  cmp     dword ptr [rbx+0F1Ch], 1
0x14014994d  jle     short loc_140149959
0x14014994f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149952  call    ?ndisWakeUpDevice@@YAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisWakeUpDevice(_NDIS_MINIPORT_BLOCK *)
0x140149957  mov     esi, eax
0x140149959  mov     dl, 1Eh; enum _NDIS_MP_REFTAG
0x14014995b  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14014995e  call    ?ndisReferenceMiniportNoCheck@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniportNoCheck(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140149963  cmp     dword ptr [rbx+1158h], 0
0x14014996a  ja      short loc_140149971
0x14014996c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Miniport->Ref.ReferenceCount > 0")
0x140149971  xor     r8d, r8d; State
0x140149974  lea     rcx, [rsp+88h+Event]; Event
0x140149979  xor     edx, edx; Type
0x14014997b  call    cs:__imp_KeInitializeEvent
0x140149982  nop     dword ptr [rax+rax+00h]
0x140149987  cmp     dword ptr [rbx+5F0h], 5
0x14014998e  lea     rax, [rsp+88h+Event]
0x140149993  mov     [rbx+648h], rax
0x14014999a  jz      short loc_1401499A4
0x14014999c  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14014999f  call    ?ndisPnPRemoveDeviceEx@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPnPRemoveDeviceEx(_NDIS_MINIPORT_BLOCK *)
0x1401499a4  test    rdi, rdi
0x1401499a7  jz      short loc_1401499AC
0x1401499a9  mov     [rdi+30h], esi
0x1401499ac  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x1401499b1  test    eax, eax
0x1401499b3  jz      short loc_1401499ED
0x1401499b5  mov     edx, 80h; unsigned int
0x1401499ba  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401499bd  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1401499c2  test    al, al
0x1401499c4  jz      short loc_1401499ED
0x1401499c6  prefetchw byte ptr [rbx+1148h]
0x1401499cd  mov     eax, [rbx+1148h]
0x1401499d3  mov     ecx, eax
0x1401499d5  lock cmpxchg [rbx+1148h], ecx
0x1401499dd  jnz     short loc_1401499D3
0x1401499df  bt      eax, 9
0x1401499e3  jnb     short loc_1401499ED
0x1401499e5  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401499e8  call    ?ndisMiniportRevokeOpenHandles@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMiniportRevokeOpenHandles(_NDIS_MINIPORT_BLOCK *)
0x1401499ed  mov     dl, 1Eh; enum _NDIS_MP_REFTAG
0x1401499ef  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401499f2  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x1401499f7  lea     rcx, [rsp+88h+Event]; void *
0x1401499fc  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140149a01  mov     rax, [rbx+0EB0h]
0x140149a08  mov     qword ptr [rbx+648h], 0
0x140149a13  cmp     dword ptr [rax+380h], 1
0x140149a1a  jnz     short loc_140149A31
0x140149a1c  cmp     cs:?ndisBugCheckOnReenumerationTimeout@@3KA, 0; ulong ndisBugCheckOnReenumerationTimeout
0x140149a23  jnz     short loc_140149A31
0x140149a25  mov     rcx, [rbx+1568h]; struct NDISWATCHDOG__ *
0x140149a2c  call    ?ndisDisarmWatchdog@@YAXPEAUNDISWATCHDOG__@@@Z; ndisDisarmWatchdog(NDISWATCHDOG__ *)
0x140149a31  mov     rax, [rbx+1F8h]
0x140149a38  test    rax, rax
0x140149a3b  jz      short loc_140149A7C
0x140149a3d  cmp     dword ptr [rax+58h], 1
0x140149a41  jnz     short loc_140149A7C
0x140149a43  mov     edx, 40h ; '@'; unsigned int
0x140149a48  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149a4b  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140149a50  test    al, al
0x140149a52  jz      short loc_140149A7C
0x140149a54  mov     rax, [rbx+1F8h]
0x140149a5b  mov     qword ptr [rax+60h], 0
0x140149a63  mov     rcx, [rbx+1F8h]; struct _NDIS_SG_DMA_BLOCK *
0x140149a6a  call    ?ndisDereferenceDmaAdapter@@YAXPEAU_NDIS_SG_DMA_BLOCK@@@Z; ndisDereferenceDmaAdapter(_NDIS_SG_DMA_BLOCK *)
0x140149a6f  mov     edx, 40h ; '@'; unsigned int
0x140149a74  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149a77  call    ?MINIPORT_CLEAR_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_CLEAR_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x140149a7c  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149a7f  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140149a84  test    al, al
0x140149a86  jz      short loc_140149AC5
0x140149a88  mov     rdx, [rbx+0EB0h]; struct _NDIS_M_DRIVER_BLOCK *
0x140149a8f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149a92  call    ?ndisDeQueueMiniportOnDriver@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_M_DRIVER_BLOCK@@@Z; ndisDeQueueMiniportOnDriver(_NDIS_MINIPORT_BLOCK *,_NDIS_M_DRIVER_BLOCK *)
0x140149a97  mov     rcx, [rbx+0EB0h]; struct _NDIS_M_DRIVER_BLOCK *
0x140149a9e  mov     r8b, 2; enum _NDIS_MDRV_REFTAG
0x140149aa1  xor     edx, edx; unsigned __int8
0x140149aa3  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x140149aa8  mov     edx, 20000h; unsigned int
0x140149aad  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149ab0  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140149ab5  test    al, al
0x140149ab7  jz      short loc_140149AC5
0x140149ab9  lea     rcx, dword_140120018; struct _PKG_REF *
0x140149ac0  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140149ac5  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140149ac8  call    ?ndisRemoveMiniportFromGlobalList@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisRemoveMiniportFromGlobalList(_NDIS_MINIPORT_BLOCK *)
0x140149acd  test    rdi, rdi
0x140149ad0  jz      short loc_140149B17
0x140149ad2  inc     byte ptr [rdi+43h]
0x140149ad5  mov     rdx, rdi; Irp
0x140149ad8  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140149ae0  mov     rcx, [rbx+0F00h]; DeviceObject
0x140149ae7  call    cs:__imp_IofCallDriver
0x140149aee  nop     dword ptr [rax+rax+00h]
0x140149af3  mov     rcx, [rbx+0F00h]; TargetDevice
0x140149afa  mov     esi, eax
0x140149afc  call    cs:__imp_IoDetachDevice
0x140149b03  nop     dword ptr [rax+rax+00h]
0x140149b08  mov     rcx, rbp; DeviceObject
0x140149b0b  call    cs:__imp_IoDeleteDevice
0x140149b12  nop     dword ptr [rax+rax+00h]
0x140149b17  mov     rcx, rbx; this
0x140149b1a  call    ?ndisMDeleteMiniportBlockOnRemove@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMDeleteMiniportBlockOnRemove(_NDIS_MINIPORT_BLOCK *)
0x140149b1f  mov     rax, [rsp+88h+arg_20]
0x140149b27  mov     byte ptr [rax], 0
0x140149b2a  mov     eax, esi
0x140149b2c  mov     byte ptr [r14], 0
0x140149b30  add     rsp, 60h
0x140149b34  pop     r14
0x140149b36  pop     rdi
0x140149b37  pop     rsi
0x140149b38  pop     rbp
0x140149b39  pop     rbx
0x140149b3a  retn
```
