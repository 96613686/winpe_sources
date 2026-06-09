# ndisPnPIrpRemoveDevice(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *,uchar *,uchar *)

- ea: `0x1401428e0`
- end: `0x140142b9c`
- name: `?ndisPnPIrpRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@PEAE3@Z`
- size: `700`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, struct _NDIS_MINIPORT_BLOCK *@<rdx>, PIRP Irp@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14003be90`
- `0x14003f5b0`

## callees

- `0x140014850`
- `0x140019b40`
- `0x14001cc80`
- `0x1400233b0`
- `0x140029d40`
- `0x140029e20`
- `0x14003cde0`
- `0x14004e050`
- `0x14006af10`
- `0x1400748a0`
- `0x14007f7c0`
- `0x1400823a0`
- `0x140082894`
- `0x1400837ac`
- `0x14008742c`
- `0x14009888c`
- `0x14009dc4c`
- `0x1400b4338`
- `0x1400e41ac`
- `0x1401428e0`
- `0x1401464a0`
- `0x1401564e0`
- `0x14017a380`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140142b6b`
- `ntoskrnl!IoDeleteDevice` at `0x140142b6b`
- `ntoskrnl!IofCallDriver` at `0x140142b47`
- `ntoskrnl!IofCallDriver` at `0x140142b47`
- `ntoskrnl!IoDetachDevice` at `0x140142b5c`
- `ntoskrnl!IoDetachDevice` at `0x140142b5c`
- `ntoskrnl!KeInitializeEvent` at `0x1401429db`
- `ntoskrnl!KeInitializeEvent` at `0x1401429db`

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
      ndisDereferencePackage((struct _PKG_REF *)&dword_14011A018);
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
0x1401428e0  mov     r11, rsp
0x1401428e3  push    rbx
0x1401428e4  push    rbp
0x1401428e5  push    rsi
0x1401428e6  push    rdi
0x1401428e7  push    r14
0x1401428e9  sub     rsp, 60h
0x1401428ed  xor     esi, esi
0x1401428ef  xorps   xmm0, xmm0
0x1401428f2  xor     eax, eax
0x1401428f4  mov     r14, r9
0x1401428f7  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x1401428fc  mov     [r11-38h], rax
0x140142900  mov     rdi, r8
0x140142903  mov     rbx, rdx
0x140142906  mov     rbp, rcx
0x140142909  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140142910  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140142917  jz      short loc_14014294B
0x140142919  mov     rax, [rdx+0F10h]
0x140142920  lea     r9d, [rsi+23h]; int
0x140142924  mov     rcx, cs:WPP_GLOBAL_Control
0x14014292b  lea     r8d, [rsi+9]; int
0x14014292f  mov     [r11-58h], rax
0x140142933  lea     rax, WPP_a0375633690b3eae5e161e1c8b2d1e08_Traceguids
0x14014293a  mov     [r11-60h], rdx
0x14014293e  mov     [r11-68h], rax
0x140142942  mov     rcx, [rcx+40h]; int
0x140142946  call    WPP_RECORDER_SF_qZ
0x14014294b  mov     edx, 23h ; '#'; enum _NDIS_MINIPORT_EVENT
0x140142950  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142953  call    ?ndisLogMiniportEvent@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MINIPORT_EVENT@@@Z; ndisLogMiniportEvent(_NDIS_MINIPORT_BLOCK *,_NDIS_MINIPORT_EVENT)
0x140142958  prefetchw byte ptr [rbx+1148h]
0x14014295f  mov     eax, [rbx+1148h]
0x140142965  mov     ecx, eax
0x140142967  lock cmpxchg [rbx+1148h], ecx
0x14014296f  jnz     short loc_140142965
0x140142971  bt      eax, 9
0x140142975  jb      short loc_1401429C3
0x140142977  mov     edx, 4
0x14014297c  mov     rcx, rbx
0x14014297f  call    ?NdisTraceLoggingDeviceRemoved@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_TRACEFORMAT_REMOVAL_REASON@@@Z; NdisTraceLoggingDeviceRemoved(_NDIS_MINIPORT_BLOCK *,_NDIS_TRACEFORMAT_REMOVAL_REASON)
0x140142984  mov     edx, 2
0x140142989  mov     rcx, rbx
0x14014298c  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x140142991  lea     rcx, [rbx+1078h]; void *
0x140142998  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14014299d  test    dword ptr [rbx+7Ch], 100h
0x1401429a4  jnz     short loc_1401429B9
0x1401429a6  cmp     dword ptr [rbx+0F1Ch], 1
0x1401429ad  jle     short loc_1401429B9
0x1401429af  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401429b2  call    ?ndisWakeUpDevice@@YAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisWakeUpDevice(_NDIS_MINIPORT_BLOCK *)
0x1401429b7  mov     esi, eax
0x1401429b9  mov     dl, 1Eh; enum _NDIS_MP_REFTAG
0x1401429bb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401429be  call    ?ndisReferenceMiniportNoCheck@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniportNoCheck(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x1401429c3  cmp     dword ptr [rbx+1158h], 0
0x1401429ca  ja      short loc_1401429D1
0x1401429cc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Miniport->Ref.ReferenceCount > 0")
0x1401429d1  xor     r8d, r8d; State
0x1401429d4  lea     rcx, [rsp+88h+Event]; Event
0x1401429d9  xor     edx, edx; Type
0x1401429db  call    cs:__imp_KeInitializeEvent
0x1401429e2  nop     dword ptr [rax+rax+00h]
0x1401429e7  cmp     dword ptr [rbx+5F0h], 5
0x1401429ee  lea     rax, [rsp+88h+Event]
0x1401429f3  mov     [rbx+648h], rax
0x1401429fa  jz      short loc_140142A04
0x1401429fc  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401429ff  call    ?ndisPnPRemoveDeviceEx@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPnPRemoveDeviceEx(_NDIS_MINIPORT_BLOCK *)
0x140142a04  test    rdi, rdi
0x140142a07  jz      short loc_140142A0C
0x140142a09  mov     [rdi+30h], esi
0x140142a0c  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x140142a11  test    eax, eax
0x140142a13  jz      short loc_140142A4D
0x140142a15  mov     edx, 80h; unsigned int
0x140142a1a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142a1d  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140142a22  test    al, al
0x140142a24  jz      short loc_140142A4D
0x140142a26  prefetchw byte ptr [rbx+1148h]
0x140142a2d  mov     eax, [rbx+1148h]
0x140142a33  mov     ecx, eax
0x140142a35  lock cmpxchg [rbx+1148h], ecx
0x140142a3d  jnz     short loc_140142A33
0x140142a3f  bt      eax, 9
0x140142a43  jnb     short loc_140142A4D
0x140142a45  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142a48  call    ?ndisMiniportRevokeOpenHandles@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMiniportRevokeOpenHandles(_NDIS_MINIPORT_BLOCK *)
0x140142a4d  mov     dl, 1Eh; enum _NDIS_MP_REFTAG
0x140142a4f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142a52  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140142a57  lea     rcx, [rsp+88h+Event]; void *
0x140142a5c  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140142a61  mov     rax, [rbx+0EB0h]
0x140142a68  mov     qword ptr [rbx+648h], 0
0x140142a73  cmp     dword ptr [rax+380h], 1
0x140142a7a  jnz     short loc_140142A91
0x140142a7c  cmp     cs:?ndisBugCheckOnReenumerationTimeout@@3KA, 0; ulong ndisBugCheckOnReenumerationTimeout
0x140142a83  jnz     short loc_140142A91
0x140142a85  mov     rcx, [rbx+1568h]; struct NDISWATCHDOG__ *
0x140142a8c  call    ?ndisDisarmWatchdog@@YAXPEAUNDISWATCHDOG__@@@Z; ndisDisarmWatchdog(NDISWATCHDOG__ *)
0x140142a91  mov     rax, [rbx+1F8h]
0x140142a98  test    rax, rax
0x140142a9b  jz      short loc_140142ADC
0x140142a9d  cmp     dword ptr [rax+58h], 1
0x140142aa1  jnz     short loc_140142ADC
0x140142aa3  mov     edx, 40h ; '@'; unsigned int
0x140142aa8  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142aab  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140142ab0  test    al, al
0x140142ab2  jz      short loc_140142ADC
0x140142ab4  mov     rax, [rbx+1F8h]
0x140142abb  mov     qword ptr [rax+60h], 0
0x140142ac3  mov     rcx, [rbx+1F8h]; struct _NDIS_SG_DMA_BLOCK *
0x140142aca  call    ?ndisDereferenceDmaAdapter@@YAXPEAU_NDIS_SG_DMA_BLOCK@@@Z; ndisDereferenceDmaAdapter(_NDIS_SG_DMA_BLOCK *)
0x140142acf  mov     edx, 40h ; '@'; unsigned int
0x140142ad4  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142ad7  call    ?MINIPORT_CLEAR_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_CLEAR_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x140142adc  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142adf  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140142ae4  test    al, al
0x140142ae6  jz      short loc_140142B25
0x140142ae8  mov     rdx, [rbx+0EB0h]; struct _NDIS_M_DRIVER_BLOCK *
0x140142aef  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142af2  call    ?ndisDeQueueMiniportOnDriver@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_M_DRIVER_BLOCK@@@Z; ndisDeQueueMiniportOnDriver(_NDIS_MINIPORT_BLOCK *,_NDIS_M_DRIVER_BLOCK *)
0x140142af7  mov     rcx, [rbx+0EB0h]; struct _NDIS_M_DRIVER_BLOCK *
0x140142afe  mov     r8b, 2; enum _NDIS_MDRV_REFTAG
0x140142b01  xor     edx, edx; unsigned __int8
0x140142b03  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x140142b08  mov     edx, 20000h; unsigned int
0x140142b0d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142b10  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140142b15  test    al, al
0x140142b17  jz      short loc_140142B25
0x140142b19  lea     rcx, dword_14011A018; struct _PKG_REF *
0x140142b20  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140142b25  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140142b28  call    ?ndisRemoveMiniportFromGlobalList@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisRemoveMiniportFromGlobalList(_NDIS_MINIPORT_BLOCK *)
0x140142b2d  test    rdi, rdi
0x140142b30  jz      short loc_140142B77
0x140142b32  inc     byte ptr [rdi+43h]
0x140142b35  mov     rdx, rdi; Irp
0x140142b38  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140142b40  mov     rcx, [rbx+0F00h]; DeviceObject
0x140142b47  call    cs:__imp_IofCallDriver
0x140142b4e  nop     dword ptr [rax+rax+00h]
0x140142b53  mov     rcx, [rbx+0F00h]; TargetDevice
0x140142b5a  mov     esi, eax
0x140142b5c  call    cs:__imp_IoDetachDevice
0x140142b63  nop     dword ptr [rax+rax+00h]
0x140142b68  mov     rcx, rbp; DeviceObject
0x140142b6b  call    cs:__imp_IoDeleteDevice
0x140142b72  nop     dword ptr [rax+rax+00h]
0x140142b77  mov     rcx, rbx; this
0x140142b7a  call    ?ndisMDeleteMiniportBlockOnRemove@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMDeleteMiniportBlockOnRemove(_NDIS_MINIPORT_BLOCK *)
0x140142b7f  mov     rax, [rsp+88h+arg_20]
0x140142b87  mov     byte ptr [rax], 0
0x140142b8a  mov     eax, esi
0x140142b8c  mov     byte ptr [r14], 0
0x140142b90  add     rsp, 60h
0x140142b94  pop     r14
0x140142b96  pop     rdi
0x140142b97  pop     rsi
0x140142b98  pop     rbp
0x140142b99  pop     rbx
0x140142b9a  retn
```
