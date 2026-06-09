# DriverEntry

- ea: `0x140039008`
- end: `0x1400396df`
- name: `DriverEntry`
- size: `1751`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400397b0`

## callees

- `0x140007024`
- `0x14000904c`
- `0x14000908c`
- `0x14000c6e0`
- `0x14000d904`
- `0x14000ee40`
- `0x140012b38`
- `0x1400161f0`
- `0x140016700`
- `0x140037008`
- `0x1400374cc`
- `0x1400380e4`
- `0x140039008`
- `0x1400396e8`
- `0x140039818`
- `0x140039970`
- `0x140039b38`
- `0x14003a908`
- `0x14003aa1c`
- `0x14003aad0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14003910b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003914c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140039186`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400391d7`
- `ntoskrnl!KeInitializeSpinLock` at `0x140039245`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003910b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003914c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140039186`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400391d7`
- `ntoskrnl!KeInitializeSpinLock` at `0x140039245`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400391ec`
- `ntoskrnl!KeInitializeTimerEx` at `0x14003925a`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400391ec`
- `ntoskrnl!KeInitializeTimerEx` at `0x14003925a`
- `ntoskrnl!KeInitializeDpc` at `0x140039209`
- `ntoskrnl!KeInitializeDpc` at `0x140039277`
- `ntoskrnl!KeInitializeDpc` at `0x140039209`
- `ntoskrnl!KeInitializeDpc` at `0x140039277`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400392ba`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400392f8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140039336`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140039374`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400393b2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400393f0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400392ba`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400392f8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140039336`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140039374`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400393b2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400393f0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140039576`
- `ntoskrnl!ExInitializeResourceLite` at `0x140039576`
- `ntoskrnl!KeInitializeEvent` at `0x1400390a7`
- `ntoskrnl!KeInitializeEvent` at `0x1400390a7`
- `ntoskrnl!EtwRegister` at `0x140039632`
- `ntoskrnl!EtwRegister` at `0x140039632`
- `NDIS!NdisGetVersion` at `0x140039283`
- `NDIS!NdisGetVersion` at `0x1400392c6`
- `NDIS!NdisGetVersion` at `0x140039304`
- `NDIS!NdisGetVersion` at `0x140039342`
- `NDIS!NdisGetVersion` at `0x140039380`
- `NDIS!NdisGetVersion` at `0x1400393be`
- `NDIS!NdisGetVersion` at `0x140039283`
- `NDIS!NdisGetVersion` at `0x1400392c6`
- `NDIS!NdisGetVersion` at `0x140039304`
- `NDIS!NdisGetVersion` at `0x140039342`
- `NDIS!NdisGetVersion` at `0x140039380`
- `NDIS!NdisGetVersion` at `0x1400393be`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140039477`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400394bd`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140039503`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140039477`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400394bd`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140039503`
- `NDIS!NdisAllocateRWLock` at `0x140039526`
- `NDIS!NdisAllocateRWLock` at `0x140039526`
- `cng!BCryptCloseAlgorithmProvider` at `0x140039673`
- `cng!BCryptCloseAlgorithmProvider` at `0x140039694`
- `cng!BCryptCloseAlgorithmProvider` at `0x140039673`
- `cng!BCryptCloseAlgorithmProvider` at `0x140039694`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400395cd`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400395f8`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400395cd`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400395f8`
- `NETIO!NmrRegisterClient` at `0x1400390d2`
- `NETIO!NmrRegisterClient` at `0x1400390d2`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v4; // ebx
  int v5; // ecx
  NTSTATUS v6; // eax
  struct _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+40h] [rbp-20h] BYREF

  Parameters = 0;
  wil_InitializeFeatureStaging();
  memset(&NdisWanCB, 0, 0x70u);
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  NsiCliTag = 1466851671;
  KeInitializeEvent(&NsiCliDriverUnloadEvent, NotificationEvent, 0);
  xmmword_14001D1F8 = NsiNdiswanGuid;
  v4 = NmrRegisterClient(&NsiCliNotify, 0, &NsiCliHandle);
  if ( v4 )
    goto LABEL_31;
  _InterlockedIncrement(&NsiCliDriverRefCount);
  if ( (unsigned int)NdisWanCreateProtocolInfoTable() )
  {
LABEL_30:
    NsiCliDeregisterClient();
    v4 = -1073741823;
LABEL_31:
    wil_UninitializeFeatureStaging();
    return v4;
  }
  NdisWanReadRegistry();
  KeInitializeSpinLock(&NdisWanCB);
  ::DriverObject = DriverObject;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = &WPP_MAIN_CB.Queue.ListEntry.Blink;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink;
  *(_OWORD *)&WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.DeviceExtension = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  WPP_MAIN_CB.Reserved = 0;
  qword_14001E1C0 = (__int64)&qword_14001E1B8;
  qword_14001E1B8 = (__int64)&qword_14001E1B8;
  *(_OWORD *)(&WPP_MAIN_CB.Reserved + 1) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  memset(&IoRecvList, 0, 0xE0u);
  qword_14001E310 = (__int64)&qword_14001E308;
  qword_14001E308 = (__int64)&qword_14001E308;
  qword_14001E340 = (__int64)&qword_14001E338;
  qword_14001E338 = (__int64)&qword_14001E338;
  KeInitializeSpinLock(&SpinLock);
  KeInitializeTimerEx(&Timer, NotificationTimer);
  KeInitializeDpc(&Dpc, IoRecvIrpWorker, 0);
  memset(&WPP_MAIN_CB.Queue.Wcb.DeviceObject, 0, 0xB0u);
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = &WPP_MAIN_CB.AlignmentRequirement;
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = &WPP_MAIN_CB.AlignmentRequirement;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  KeInitializeTimerEx((PKTIMER)&WPP_MAIN_CB.Dpc.DeferredContext, NotificationTimer);
  KeInitializeDpc((PRKDPC)&WPP_MAIN_CB.DeviceQueue.DeviceListHead, DeferredWorker, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&BundleCBList, 0, 0, 0x200u, 0xC50u, 0x416E6157u, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&LinkProtoCBList, 0, 0, 0x200u, 0x2F0u, 0x426E6157u, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&RecvHeaderLookaside, 0, 0, 0x200u, 0x8Eu, 0x484E6157u, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&WanRequestLegacyList, 0, 0, 0x200u, 0x108u, 0x466E6157u, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&AfSapVcCBList, 0, 0, 0x200u, 0x68u, 0x536E6157u, 0);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&WorkItemList, 0, 0, 0x200u, 0x60u, 0x69776E57u, 0);
  WanInitECP();
  if ( (unsigned int)DoMiniportInit(RegistryPath) )
    goto LABEL_25;
  v5 = glMRRU;
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  if ( glMaxMTU > (unsigned int)glMRRU )
    v5 = glMaxMTU;
  Parameters.fAllocateNetBuffer = 1;
  Parameters.ContextSize = 128;
  Parameters.PoolTag = 1162764631;
  glLargeDataBufferSize = (((unsigned int)(v5 + 7) >> 3) + v5 + 136) & 0xFFFFFFF8;
  Parameters.DataSize = glLargeDataBufferSize;
  glSmallDataBufferSize = ((glLargeDataBufferSize >> 1) + 8) & 0xFFFFFFF8;
  RecvPacketPool = NdisAllocateNetBufferListPool(NdisMiniportDriverHandle, &Parameters);
  if ( !RecvPacketPool )
    goto LABEL_25;
  Parameters.DataSize = glLargeDataBufferSize;
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  Parameters.fAllocateNetBuffer = 1;
  Parameters.ContextSize = 128;
  Parameters.PoolTag = 1179541847;
  SendPacketPool = NdisAllocateNetBufferListPool(NdisMiniportDriverHandle, &Parameters);
  if ( !SendPacketPool )
    goto LABEL_25;
  Parameters.DataSize = glLargeDataBufferSize;
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  Parameters.fAllocateNetBuffer = 1;
  Parameters.ContextSize = 128;
  Parameters.PoolTag = 1196319063;
  IoPacketPool = NdisAllocateNetBufferListPool(NdisMiniportDriverHandle, &Parameters);
  if ( !IoPacketPool )
    goto LABEL_25;
  ConnTableLock = NdisAllocateRWLock(NdisMiniportDriverHandle);
  if ( !ConnTableLock )
    goto LABEL_25;
  if ( (unsigned int)NdisWanCreateConnectionTable((unsigned int)dword_14001E2AC) )
    goto LABEL_25;
  if ( (unsigned int)DoDeviceInit() )
    goto LABEL_25;
  if ( (unsigned int)DoProtocolInit() )
    goto LABEL_25;
  ExInitializeResourceLite(&QoSPolicyResourceLock);
  if ( (unsigned int)BwcInit(NdisMiniportDriverHandle, DriverObject) )
    goto LABEL_25;
  QoSModuleInitialized = 1;
  if ( !gbDisableLegacyProtocol )
  {
    if ( (unsigned int)DoProtocolInitLegacy() )
      goto LABEL_25;
  }
  if ( BCryptOpenAlgorithmProvider(&ghAlgSHA1, L"SHA1", 0, 1u) < 0
    || BCryptOpenAlgorithmProvider(&ghAlgRC4, L"RC4", 0, 1u) < 0 )
  {
LABEL_25:
    if ( ghAlgSHA1 )
    {
      BCryptCloseAlgorithmProvider(ghAlgSHA1, 0);
      ghAlgSHA1 = 0;
    }
    if ( ghAlgRC4 )
    {
      BCryptCloseAlgorithmProvider(ghAlgRC4, 0);
      ghAlgRC4 = 0;
    }
    NdisWanGlobalCleanup();
    goto LABEL_30;
  }
  if ( (int)McGenEventRegister_EtwRegister() >= 0 )
  {
    if ( Microsoft_Windows_Networking_CorrelationHandle
      || (v6 = EtwRegister(
                 &Microsoft_Windows_Networking_CorrelationId,
                 Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                 0,
                 &Microsoft_Windows_Networking_CorrelationHandle)) == 0 )
    {
      Microsoft_Windows_Networking_ProviderId = (__int128)MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER;
    }
    else if ( v6 < 0 )
    {
      McGenEventUnregister_EtwUnregister(&MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER_Context);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140039008  mov     [rsp-18h+arg_10], rbx
0x14003900d  mov     [rsp-18h+arg_18], rsi
0x140039012  push    rbp
0x140039013  push    rdi
0x140039014  push    r14
0x140039016  mov     rbp, rsp
0x140039019  sub     rsp, 60h
0x14003901d  mov     rax, cs:__security_cookie
0x140039024  xor     rax, rsp
0x140039027  mov     [rbp+var_10], rax
0x14003902b  xorps   xmm0, xmm0
0x14003902e  mov     rsi, rdx
0x140039031  movups  xmmword ptr [rbp+Parameters.Header.Type], xmm0
0x140039035  mov     rdi, rcx
0x140039038  call    wil_InitializeFeatureStaging
0x14003903d  xor     edx, edx; Val
0x14003903f  lea     rcx, NdisWanCB; void *
0x140039046  lea     r8d, [rdx+70h]; Size
0x14003904a  call    memset
0x14003904f  xor     r14d, r14d
0x140039052  mov     cs:WPP_MAIN_CB.Timer, 1
0x14003905d  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x140039064  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x14003906b  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140039072  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x140039079  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x140039080  call    WppLoadTracingSupport
0x140039085  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x14003908c  call    WppInitKm
0x140039091  xor     r8d, r8d; State
0x140039094  mov     cs:NsiCliTag, 576E6157h
0x14003909e  xor     edx, edx; Type
0x1400390a0  lea     rcx, NsiCliDriverUnloadEvent; Event
0x1400390a7  call    cs:__imp_KeInitializeEvent
0x1400390ae  nop     dword ptr [rax+rax+00h]
0x1400390b3  movups  xmm0, cs:NsiNdiswanGuid
0x1400390ba  lea     r8, NsiCliHandle; NmrClientHandle
0x1400390c1  xor     edx, edx; ClientContext
0x1400390c3  lea     rcx, NsiCliNotify; ClientCharacteristics
0x1400390ca  movdqu  cs:xmmword_14001D1F8, xmm0
0x1400390d2  call    cs:__imp_NmrRegisterClient
0x1400390d9  nop     dword ptr [rax+rax+00h]
0x1400390de  mov     ebx, eax
0x1400390e0  test    eax, eax
0x1400390e2  jnz     loc_1400396B6
0x1400390e8  lock inc cs:NsiCliDriverRefCount
0x1400390ef  call    NdisWanCreateProtocolInfoTable
0x1400390f4  test    eax, eax
0x1400390f6  jnz     loc_1400396AC
0x1400390fc  mov     rcx, rsi
0x1400390ff  call    NdisWanReadRegistry
0x140039104  lea     rcx, NdisWanCB; SpinLock
0x14003910b  call    cs:__imp_KeInitializeSpinLock
0x140039112  nop     dword ptr [rax+rax+00h]
0x140039117  lea     rax, WPP_MAIN_CB.Queue+8
0x14003911e  mov     cs:DriverObject, rdi
0x140039125  xorps   xmm0, xmm0
0x140039128  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x14003912f  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x140039136  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14003913d  movdqu  xmmword ptr cs:WPP_MAIN_CB.DeviceType, xmm0
0x140039145  mov     cs:WPP_MAIN_CB.DeviceExtension, r14
0x14003914c  call    cs:__imp_KeInitializeSpinLock
0x140039153  nop     dword ptr [rax+rax+00h]
0x140039158  lea     rax, qword_14001E1B8
0x14003915f  mov     cs:WPP_MAIN_CB.Reserved, r14
0x140039166  xorps   xmm0, xmm0
0x140039169  mov     cs:qword_14001E1C0, rax
0x140039170  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140039177  mov     cs:qword_14001E1B8, rax
0x14003917e  movdqu  xmmword ptr cs:WPP_MAIN_CB+148h, xmm0
0x140039186  call    cs:__imp_KeInitializeSpinLock
0x14003918d  nop     dword ptr [rax+rax+00h]
0x140039192  xor     edx, edx; Val
0x140039194  lea     rcx, IoRecvList; void *
0x14003919b  mov     r8d, 0E0h; Size
0x1400391a1  call    memset
0x1400391a6  lea     rax, qword_14001E308
0x1400391ad  mov     cs:qword_14001E310, rax
0x1400391b4  lea     rcx, SpinLock; SpinLock
0x1400391bb  mov     cs:qword_14001E308, rax
0x1400391c2  lea     rax, qword_14001E338
0x1400391c9  mov     cs:qword_14001E340, rax
0x1400391d0  mov     cs:qword_14001E338, rax
0x1400391d7  call    cs:__imp_KeInitializeSpinLock
0x1400391de  nop     dword ptr [rax+rax+00h]
0x1400391e3  xor     edx, edx; Type
0x1400391e5  lea     rcx, Timer; Timer
0x1400391ec  call    cs:__imp_KeInitializeTimerEx
0x1400391f3  nop     dword ptr [rax+rax+00h]
0x1400391f8  xor     r8d, r8d; DeferredContext
0x1400391fb  lea     rdx, IoRecvIrpWorker; DeferredRoutine
0x140039202  lea     rcx, Dpc; Dpc
0x140039209  call    cs:__imp_KeInitializeDpc
0x140039210  nop     dword ptr [rax+rax+00h]
0x140039215  xor     edx, edx; Val
0x140039217  lea     rcx, WPP_MAIN_CB.Queue+30h; void *
0x14003921e  mov     r8d, 0B0h; Size
0x140039224  call    memset
0x140039229  lea     rax, WPP_MAIN_CB.AlignmentRequirement
0x140039230  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140039237  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x14003923e  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rax
0x140039245  call    cs:__imp_KeInitializeSpinLock
0x14003924c  nop     dword ptr [rax+rax+00h]
0x140039251  xor     edx, edx; Type
0x140039253  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; Timer
0x14003925a  call    cs:__imp_KeInitializeTimerEx
0x140039261  nop     dword ptr [rax+rax+00h]
0x140039266  xor     r8d, r8d; DeferredContext
0x140039269  lea     rdx, DeferredWorker; DeferredRoutine
0x140039270  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; Dpc
0x140039277  call    cs:__imp_KeInitializeDpc
0x14003927e  nop     dword ptr [rax+rax+00h]
0x140039283  call    cs:__imp_NdisGetVersion
0x14003928a  nop     dword ptr [rax+rax+00h]
0x14003928f  mov     [rsp+60h+Depth], r14w; Depth
0x140039295  lea     rcx, BundleCBList; Lookaside
0x14003929c  mov     ebx, 200h
0x1400392a1  mov     [rsp+60h+Tag], 416E6157h; Tag
0x1400392a9  mov     r9d, ebx; Flags
0x1400392ac  mov     [rsp+60h+Size], 0C50h; Size
0x1400392b5  xor     r8d, r8d; Free
0x1400392b8  xor     edx, edx; Allocate
0x1400392ba  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400392c1  nop     dword ptr [rax+rax+00h]
0x1400392c6  call    cs:__imp_NdisGetVersion
0x1400392cd  nop     dword ptr [rax+rax+00h]
0x1400392d2  mov     [rsp+60h+Depth], r14w; Depth
0x1400392d8  lea     rcx, LinkProtoCBList; Lookaside
0x1400392df  mov     [rsp+60h+Tag], 426E6157h; Tag
0x1400392e7  mov     r9d, ebx; Flags
0x1400392ea  xor     r8d, r8d; Free
0x1400392ed  mov     [rsp+60h+Size], 2F0h; Size
0x1400392f6  xor     edx, edx; Allocate
0x1400392f8  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400392ff  nop     dword ptr [rax+rax+00h]
0x140039304  call    cs:__imp_NdisGetVersion
0x14003930b  nop     dword ptr [rax+rax+00h]
0x140039310  mov     [rsp+60h+Depth], r14w; Depth
0x140039316  mov     r9d, ebx; Flags
0x140039319  mov     [rsp+60h+Tag], 484E6157h; Tag
0x140039321  xor     r8d, r8d; Free
0x140039324  mov     [rsp+60h+Size], 8Eh; Size
0x14003932d  xor     edx, edx; Allocate
0x14003932f  lea     rcx, RecvHeaderLookaside; Lookaside
0x140039336  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003933d  nop     dword ptr [rax+rax+00h]
0x140039342  call    cs:__imp_NdisGetVersion
0x140039349  nop     dword ptr [rax+rax+00h]
0x14003934e  mov     [rsp+60h+Depth], r14w; Depth
0x140039354  lea     rcx, WanRequestLegacyList; Lookaside
0x14003935b  mov     [rsp+60h+Tag], 466E6157h; Tag
0x140039363  mov     r9d, ebx; Flags
0x140039366  xor     r8d, r8d; Free
0x140039369  mov     [rsp+60h+Size], 108h; Size
0x140039372  xor     edx, edx; Allocate
0x140039374  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003937b  nop     dword ptr [rax+rax+00h]
0x140039380  call    cs:__imp_NdisGetVersion
0x140039387  nop     dword ptr [rax+rax+00h]
0x14003938c  mov     [rsp+60h+Depth], r14w; Depth
0x140039392  lea     rcx, AfSapVcCBList; Lookaside
0x140039399  mov     [rsp+60h+Tag], 536E6157h; Tag
0x1400393a1  mov     r9d, ebx; Flags
0x1400393a4  xor     r8d, r8d; Free
0x1400393a7  mov     [rsp+60h+Size], 68h ; 'h'; Size
0x1400393b0  xor     edx, edx; Allocate
0x1400393b2  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400393b9  nop     dword ptr [rax+rax+00h]
0x1400393be  call    cs:__imp_NdisGetVersion
0x1400393c5  nop     dword ptr [rax+rax+00h]
0x1400393ca  mov     [rsp+60h+Depth], r14w; Depth
0x1400393d0  lea     rcx, WorkItemList; Lookaside
0x1400393d7  mov     [rsp+60h+Tag], 69776E57h; Tag
0x1400393df  mov     r9d, ebx; Flags
0x1400393e2  xor     r8d, r8d; Free
0x1400393e5  mov     [rsp+60h+Size], 60h ; '`'; Size
0x1400393ee  xor     edx, edx; Allocate
0x1400393f0  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400393f7  nop     dword ptr [rax+rax+00h]
0x1400393fc  call    WanInitECP
0x140039401  mov     rcx, rsi; RegistryPath
0x140039404  call    DoMiniportInit
0x140039409  test    eax, eax
0x14003940b  jnz     loc_140039665
0x140039411  mov     ecx, cs:glMRRU
0x140039417  mov     edx, 0FFFFFFF8h
0x14003941c  cmp     cs:glMaxMTU, ecx
0x140039422  mov     ebx, 80h
0x140039427  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x14003942e  cmova   ecx, cs:glMaxMTU
0x140039435  mov     [rbp+Parameters.fAllocateNetBuffer], 1
0x140039439  mov     [rbp+Parameters.ContextSize], bx
0x14003943d  mov     [rbp+Parameters.PoolTag], 454E6157h
0x140039444  lea     eax, [rcx+7]
0x140039447  add     ecx, 88h
0x14003944d  shr     eax, 3
0x140039450  add     ecx, eax
0x140039452  and     ecx, edx
0x140039454  mov     eax, ecx
0x140039456  mov     cs:glLargeDataBufferSize, ecx
0x14003945c  shr     eax, 1
0x14003945e  add     eax, 8
0x140039461  mov     [rbp+Parameters.DataSize], ecx
0x140039464  mov     rcx, cs:NdisMiniportDriverHandle; NdisHandle
0x14003946b  and     eax, edx
0x14003946d  lea     rdx, [rbp+Parameters]; Parameters
0x140039471  mov     cs:glSmallDataBufferSize, eax
0x140039477  call    cs:__imp_NdisAllocateNetBufferListPool
0x14003947e  nop     dword ptr [rax+rax+00h]
0x140039483  mov     cs:RecvPacketPool, rax
0x14003948a  test    rax, rax
0x14003948d  jz      loc_140039665
0x140039493  mov     eax, cs:glLargeDataBufferSize
0x140039499  lea     rdx, [rbp+Parameters]; Parameters
0x14003949d  mov     rcx, cs:NdisMiniportDriverHandle; NdisHandle
0x1400394a4  mov     [rbp+Parameters.DataSize], eax
0x1400394a7  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x1400394ae  mov     [rbp+Parameters.fAllocateNetBuffer], 1
0x1400394b2  mov     [rbp+Parameters.ContextSize], bx
0x1400394b6  mov     [rbp+Parameters.PoolTag], 464E6157h
0x1400394bd  call    cs:__imp_NdisAllocateNetBufferListPool
0x1400394c4  nop     dword ptr [rax+rax+00h]
0x1400394c9  mov     cs:SendPacketPool, rax
0x1400394d0  test    rax, rax
0x1400394d3  jz      loc_140039665
0x1400394d9  mov     eax, cs:glLargeDataBufferSize
0x1400394df  lea     rdx, [rbp+Parameters]; Parameters
0x1400394e3  mov     rcx, cs:NdisMiniportDriverHandle; NdisHandle
0x1400394ea  mov     [rbp+Parameters.DataSize], eax
0x1400394ed  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x1400394f4  mov     [rbp+Parameters.fAllocateNetBuffer], 1
0x1400394f8  mov     [rbp+Parameters.ContextSize], bx
0x1400394fc  mov     [rbp+Parameters.PoolTag], 474E6157h
0x140039503  call    cs:__imp_NdisAllocateNetBufferListPool
0x14003950a  nop     dword ptr [rax+rax+00h]
0x14003950f  mov     cs:IoPacketPool, rax
0x140039516  test    rax, rax
0x140039519  jz      loc_140039665
0x14003951f  mov     rcx, cs:NdisMiniportDriverHandle; NdisHandle
0x140039526  call    cs:__imp_NdisAllocateRWLock
0x14003952d  nop     dword ptr [rax+rax+00h]
0x140039532  mov     cs:ConnTableLock, rax
0x140039539  test    rax, rax
0x14003953c  jz      loc_140039665
0x140039542  mov     ecx, cs:dword_14001E2AC
0x140039548  call    NdisWanCreateConnectionTable
0x14003954d  test    eax, eax
0x14003954f  jnz     loc_140039665
0x140039555  call    DoDeviceInit
0x14003955a  test    eax, eax
0x14003955c  jnz     loc_140039665
0x140039562  call    DoProtocolInit
0x140039567  test    eax, eax
0x140039569  jnz     loc_140039665
0x14003956f  lea     rcx, QoSPolicyResourceLock; Resource
0x140039576  call    cs:__imp_ExInitializeResourceLite
0x14003957d  nop     dword ptr [rax+rax+00h]
0x140039582  mov     rcx, cs:NdisMiniportDriverHandle
0x140039589  mov     rdx, rdi
0x14003958c  call    BwcInit
0x140039591  test    eax, eax
0x140039593  jnz     loc_140039665
0x140039599  cmp     cs:gbDisableLegacyProtocol, r14b
0x1400395a0  mov     cs:QoSModuleInitialized, 1
0x1400395a7  jnz     short loc_1400395B6
0x1400395a9  call    DoProtocolInitLegacy
0x1400395ae  test    eax, eax
0x1400395b0  jnz     loc_140039665
0x1400395b6  mov     r9d, 1; dwFlags
0x1400395bc  lea     rdx, pszAlgId; "SHA1"
0x1400395c3  xor     r8d, r8d; pszImplementation
0x1400395c6  lea     rcx, ghAlgSHA1; phAlgorithm
0x1400395cd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400395d4  nop     dword ptr [rax+rax+00h]
0x1400395d9  test    eax, eax
0x1400395db  js      loc_140039665
0x1400395e1  mov     r9d, 1; dwFlags
0x1400395e7  lea     rdx, aRc4; "RC4"
0x1400395ee  xor     r8d, r8d; pszImplementation
0x1400395f1  lea     rcx, ghAlgRC4; phAlgorithm
0x1400395f8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400395ff  nop     dword ptr [rax+rax+00h]
0x140039604  test    eax, eax
0x140039606  js      short loc_140039665
0x140039608  call    McGenEventRegister_EtwRegister
0x14003960d  test    eax, eax
0x14003960f  js      short loc_140039661
0x140039611  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, r14
0x140039618  jnz     short loc_140039652
0x14003961a  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140039621  xor     r8d, r8d; CallbackContext
0x140039624  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x14003962b  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x140039632  call    cs:__imp_EtwRegister
0x140039639  nop     dword ptr [rax+rax+00h]
0x14003963e  test    eax, eax
0x140039640  jz      short loc_140039652
0x140039642  jns     short loc_140039661
  ... truncated ...
```
