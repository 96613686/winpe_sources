# ndisMInitializeAdapter(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,_NDIS_WRAPPER_CONFIGURATION_HANDLE *,_UNICODE_STRING *,void *)

- ea: `0x140181e50`
- end: `0x1401846f2`
- name: `?ndisMInitializeAdapter@@YAHPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_WRAPPER_CONFIGURATION_HANDLE@@PEAU_UNICODE_STRING@@PEAX@Z`
- size: `10402`
- prototype: `__int64 __usercall@<rax>(struct _NDIS_M_DRIVER_BLOCK *@<rcx>, struct _NDIS_MINIPORT_BLOCK *@<rdx>, struct _NDIS_WRAPPER_CONFIGURATION_HANDLE *@<r8>, struct _UNICODE_STRING *@<r9>, void *)`
- caller_count: `1`
- callee_count: `92`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006f2b0`

## callees

- `0x140009320`
- `0x14000dbe0`
- `0x1400110b0`
- `0x140011190`
- `0x140011290`
- `0x1400114b0`
- `0x140017480`
- `0x140017510`
- `0x14001ddf0`
- `0x14001ded0`
- `0x14003d6e0`
- `0x1400416b0`
- `0x140044e80`
- `0x14004bfd0`
- `0x14004d400`
- `0x14004d6a0`
- `0x14004dc60`
- `0x14005a760`
- `0x14005b490`
- `0x14005d480`
- `0x14005dc70`
- `0x140060170`
- `0x1400607b0`
- `0x1400615b0`
- `0x140063390`
- `0x140065890`
- `0x1400660e0`
- `0x14006e4f0`
- `0x14006ff30`
- `0x140072760`
- `0x140073330`
- `0x140074810`
- `0x14007a900`
- `0x14007c6f0`
- `0x14007d0d0`
- `0x14007d1e0`
- `0x1400816e0`
- `0x1400834f0`
- `0x140084e10`
- `0x140088a2c`
- `0x140089ed0`
- `0x14008b640`
- `0x14008ba60`
- `0x14008c71c`
- `0x14008d0d0`
- `0x1400903b4`
- `0x140090844`
- `0x140091f9c`
- `0x140092480`
- `0x140092618`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140181fd7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140181fd7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140181ff3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140181ff3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401826a5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401826a5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140182017`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140182017`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1401845de`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1401845de`
- `ntoskrnl!DbgPrintEx` at `0x140184422`
- `ntoskrnl!DbgPrintEx` at `0x140184485`
- `ntoskrnl!DbgPrintEx` at `0x1401844f6`
- `ntoskrnl!DbgPrintEx` at `0x140184422`
- `ntoskrnl!DbgPrintEx` at `0x140184485`
- `ntoskrnl!DbgPrintEx` at `0x1401844f6`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14018393a`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140183a43`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14018393a`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140183a43`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140182668`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140182692`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140182668`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140182692`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140182635`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14018379e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140182635`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14018379e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401825f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184652`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401825f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184652`
- `ntoskrnl!KeInitializeEvent` at `0x1401827c1`
- `ntoskrnl!KeInitializeEvent` at `0x140183288`
- `ntoskrnl!KeInitializeEvent` at `0x1401827c1`
- `ntoskrnl!KeInitializeEvent` at `0x140183288`
- `ntoskrnl!ExAllocatePool2` at `0x1401821d3`
- `ntoskrnl!ExAllocatePool2` at `0x140183b8a`
- `ntoskrnl!ExAllocatePool2` at `0x1401821d3`
- `ntoskrnl!ExAllocatePool2` at `0x140183b8a`
- `ntoskrnl!ZwPowerInformation` at `0x140184208`
- `ntoskrnl!ZwPowerInformation` at `0x140184208`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401827f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140182fb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183418`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018412e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018455d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401827f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140182fb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140183418`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018412e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018455d`
- `ntoskrnl!KeBugCheckEx` at `0x14018444d`
- `ntoskrnl!KeBugCheckEx` at `0x1401844b3`
- `ntoskrnl!KeBugCheckEx` at `0x140184524`
- `ntoskrnl!KeBugCheckEx` at `0x14018444d`
- `ntoskrnl!KeBugCheckEx` at `0x1401844b3`
- `ntoskrnl!KeBugCheckEx` at `0x140184524`

## pseudocode

```c
__int64 __fastcall ndisMInitializeAdapter(
        struct _NDIS_M_DRIVER_BLOCK *a1,
        struct _NDIS_MINIPORT_BLOCK *a2,
        struct _NDIS_WRAPPER_CONFIGURATION_HANDLE *a3,
        struct _UNICODE_STRING *a4,
        void *a5)
{
  char v7; // bl
  char v8; // r12
  char i; // r15
  char v10; // r14
  bool v11; // r13
  int v12; // edx
  _NDIS_MINIPORT_OFFLOAD *Offload; // rdx
  char v14; // di
  NTSTATUS v15; // eax
  bool v16; // cf
  struct _NDIS_MINIPORT_BLOCK *v17; // r10
  _NDIS_MINIPORT_STATS *Pool2; // rax
  _NDIS_M_DRIVER_BLOCK *DriverHandle; // rdx
  unsigned __int8 v20; // cl
  void (__fastcall *ShutdownHandlerEx)(void *, _NDIS_SHUTDOWN_ACTION); // rax
  _NDIS_M_DRIVER_BLOCK *v22; // rax
  void (__fastcall *ReturnNetBufferListsHandler)(void *, _NET_BUFFER_LIST *, unsigned int); // rcx
  PNDIS_PER_PROCESSOR_SLOT__ *PerProcessorSlot; // rax
  unsigned int v25; // edx
  __int64 v26; // rcx
  struct _NDIS_MINIPORT_BLOCK *v27; // rcx
  void *v28; // rcx
  struct _NDIS_MINIPORT_BLOCK *v29; // r10
  int v30; // eax
  struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *GeneralAttributes; // r8
  char v32; // al
  char v33; // cl
  char v34; // di
  _NDIS_IF_BLOCK *v35; // r8
  int v36; // edx
  int v37; // edx
  int v38; // edx
  __int64 v39; // r8
  KIRQL v40; // dl
  struct _NDIS_MINIPORT_BLOCK *v41; // rax
  int ReenumerateSelfInterface; // eax
  enum Ndis::ReadBindingsOptions::Flags *v43; // rdx
  unsigned int v44; // ecx
  int v45; // eax
  NDIS_STATUS v46; // eax
  int v47; // edx
  int v48; // edx
  unsigned int v49; // eax
  int v50; // edx
  struct _NDIS_MINIPORT_BLOCK *v51; // r10
  __int64 v52; // rcx
  int PciDeviceCustomProperties; // eax
  _NET_LUID_LH *p_NetLuid; // r9
  _DWORD *p_IfIndex; // r11
  _QWORD *v56; // r9
  _DWORD *v57; // r11
  int v58; // edx
  const struct _NDIS_MINIPORT_BLOCK *v59; // rcx
  _CM_RESOURCE_LIST *AllocatedResources; // rax
  _NDIS_PCI_DEVICE_CUSTOM_PROPERTIES *p_PciDeviceCustomProperties; // rax
  struct _NDIS_MINIPORT_BLOCK *v62; // rcx
  unsigned int v63; // eax
  struct _NDIS_MINIPORT_BLOCK **p_BaseMiniport; // rdx
  _NDIS_MINIPORT_INTERRUPT *Interrupt; // rax
  unsigned int MediaType; // eax
  __int64 v67; // rcx
  unsigned __int8 v68; // al
  KIRQL v69; // dl
  int v70; // edx
  __int64 v71; // rcx
  int MiniportInfo; // eax
  int v73; // eax
  const struct _NDIS_MINIPORT_BLOCK *v74; // rcx
  struct _NDIS_MINIPORT_BLOCK *v75; // rcx
  unsigned int v76; // eax
  int v77; // eax
  struct _NDIS_MINIPORT_BLOCK *v78; // rdx
  unsigned int PnPFlags; // r8d
  unsigned __int8 v80; // al
  unsigned int PnPCapabilities; // r9d
  unsigned int v82; // r8d
  bool v83; // zf
  bool v84; // cc
  int v85; // eax
  int v86; // edx
  struct _NDIS_MINIPORT_BLOCK *v87; // rcx
  unsigned int v88; // eax
  struct _NDIS_MINIPORT_BLOCK *v89; // rax
  KIRQL v90; // dl
  struct _NDIS_MINIPORT_BLOCK *v91; // rcx
  _X_FILTER *EthDB; // rcx
  int v93; // edx
  int v94; // edx
  __int64 v95; // rcx
  struct _NDIS_MINIPORT_BLOCK *v96; // r10
  int v97; // edx
  const struct _NDIS_MINIPORT_BLOCK *v98; // rcx
  struct _NDIS_MINIPORT_BLOCK *v99; // r10
  __int64 v100; // rcx
  char v101; // al
  struct _NDIS_IF_BLOCK *v102; // rdx
  __int64 v103; // rcx
  _NDIS_SRIOV_CAPABILITIES *SriovCurrentCapabilities; // rax
  unsigned int v105; // eax
  __int64 v106; // rcx
  __int64 v107; // rcx
  int v108; // edx
  __int64 v109; // rcx
  _NDIS_MINIPORT_OFFLOAD *v110; // rax
  _NDIS_MINIPORT_OFFLOAD *v111; // rax
  _NDIS_MINIPORT_OFFLOAD *v112; // rax
  _NDIS_MINIPORT_OFFLOAD *v113; // rcx
  enum Ndis::ReadBindingsOptions::Flags v114; // r8d
  int v115; // edx
  int v116; // edx
  int v117; // edx
  int v118; // edx
  enum _NDIS_DEVICE_PNP_EVENT v119; // edx
  unsigned int v120; // r9d
  const struct _NDIS_MINIPORT_BLOCK *v121; // rcx
  unsigned __int8 (__fastcall *v122)(_NDIS_MINIPORT_BLOCK *); // rax
  KIRQL v123; // dl
  unsigned int v124; // eax
  _NDIS_IF_BLOCK *IfBlock; // rax
  KIRQL v126; // dl
  _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *v127; // rcx
  ULONG OutputBufferLength[2]; // [rsp+20h] [rbp-E0h]
  bool v130; // [rsp+40h] [rbp-C0h]
  char v131; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v133; // [rsp+50h] [rbp-B0h] BYREF
  char v134; // [rsp+51h] [rbp-AFh]
  unsigned __int8 v135; // [rsp+52h] [rbp-AEh]
  unsigned __int8 v136; // [rsp+53h] [rbp-ADh] BYREF
  unsigned __int8 MajorNdisVersion; // [rsp+54h] [rbp-ACh]
  char v138; // [rsp+55h] [rbp-ABh]
  char v139[4]; // [rsp+58h] [rbp-A8h] BYREF
  char v140; // [rsp+5Ch] [rbp-A4h]
  char v141; // [rsp+5Dh] [rbp-A3h]
  char v142[4]; // [rsp+60h] [rbp-A0h]
  PVOID ConfigurationHandle; // [rsp+68h] [rbp-98h] BYREF
  int Status; // [rsp+70h] [rbp-90h] BYREF
  unsigned int OidList; // [rsp+74h] [rbp-8Ch]
  UNICODE_STRING Keyword; // [rsp+78h] [rbp-88h] BYREF
  int v147; // [rsp+88h] [rbp-78h] BYREF
  BOOL v148; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v149; // [rsp+90h] [rbp-70h] BYREF
  struct _KEVENT Event; // [rsp+98h] [rbp-68h] BYREF
  int v151; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _X_FILTER *v153[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v154; // [rsp+D8h] [rbp-28h]
  struct _NDIS_MINIPORT_INIT_PARAMETERS v155; // [rsp+F0h] [rbp-10h] BYREF
  struct _NDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+130h] [rbp+30h] BYREF
  char v157[160]; // [rsp+150h] [rbp+50h] BYREF
  struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES v158; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 InputBuffer; // [rsp+2D0h] [rbp+1D0h] BYREF
  _NDIS_PORT_AUTHORIZATION_STATE DefaultPortRcvAuthorizationState; // [rsp+2E0h] [rbp+1E0h]
  __int128 v161; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v162; // [rsp+2F8h] [rbp+1F8h]
  _OWORD v163[2]; // [rsp+308h] [rbp+208h] BYREF
  GUID InterfaceClassGuid; // [rsp+328h] [rbp+228h] BYREF
  GUID v165; // [rsp+338h] [rbp+238h] BYREF
  char v166; // [rsp+350h] [rbp+250h] BYREF

  *(_QWORD *)&InputBuffer = a3;
  memset(&v155, 0, sizeof(v155));
  *(_DWORD *)v139 = 1;
  v147 = 1;
  *(_OWORD *)v153 = 0;
  v7 = 0;
  v8 = 0;
  v154 = 0;
  i = 0;
  v10 = 0;
  DestinationString = 0;
  v11 = 0;
  v151 = 0;
  v148 = 0;
  InterfaceClassGuid = GUID_NDIS_LAN_CLASS;
  v149 = 0;
  v136 = 0;
  memset(v163, 0, 28);
  v141 = 0;
  v140 = 0;
  v133 = 0;
  v131 = 0;
  v138 = 0;
  v135 = 0;
  v130 = 0;
  v161 = 0;
  v162 = 0;
  memset(&v158, 0, sizeof(v158));
  v134 = 0;
  v165 = GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v12,
      13,
      13,
      (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
      (char)a2,
      (__int64)a2->pAdapterInstanceName);
  ndisIfEnsureNsiInitialized();
  MajorNdisVersion = a1->MajorNdisVersion;
  if ( !ndisReferenceDriver(a1, MDRVREF_MINIPORT) )
  {
    v17 = a2;
    goto LABEL_46;
  }
  *(_DWORD *)&DestinationString.Length = 0x1000000;
  v14 = 1;
  DestinationString.Buffer = (wchar_t *)&v166;
  v141 = 1;
  RtlCopyUnicodeString(&DestinationString, &ndisDosDevicesStr);
  if ( RtlAppendUnicodeStringToString(&DestinationString, &a2->BaseName) < 0 )
    goto LABEL_45;
  v15 = IoCreateSymbolicLink(&DestinationString, &a2->FdoName);
  *(_DWORD *)v142 = v15;
  v11 = v15 >= 0 || v15 == -1073741771;
  v16 = MajorNdisVersion < 6u;
  v17 = a2;
  a2->DeviceContext = a5;
  a2->PacketIndicateHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMDummyIndicatePacket;
  a2->SavedPacketIndicateHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMDummyIndicatePacket;
  a2->TopIndicateNetBufferListsHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))ndisMDispatchReceiveNetBufferLists;
  a2->TopIndicateLoopbackNetBufferListsHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))ndisMDispatchReceiveNetBufferLists;
  a2->EthRxIndicateHandler = (void (__fastcall *)(_X_FILTER *, void *, char *, void *, unsigned int, void *, unsigned int, unsigned int))&EthFilterDprIndicateReceive;
  a2->EthRxCompleteHandler = (void (__fastcall *)(_X_FILTER *))EthFilterDprIndicateReceiveComplete;
  a2->SendCompleteHandler = (void (__fastcall *)(void *, _NDIS_PACKET *, int))NdisMSendComplete;
  a2->SendNetBufferListsCompleteHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int))NdisMSendNetBufferListsComplete;
  a2->TDCompleteHandler = (void (__fastcall *)(void *, _NDIS_PACKET *, int, unsigned int))NdisMTransferDataComplete;
  a2->ResetCompleteHandler = (void (__fastcall *)(void *, int, unsigned __int8))NdisMResetComplete;
  a2->StatusHandler = (void (__fastcall *)(void *, int, void *, unsigned int))NdisMIndicateStatus;
  a2->StatusCompleteHandler = (void (__fastcall *)(void *))NdisQueryOffloadState;
  a2->SendResourcesHandler = (void (__fastcall *)(void *))NdisMSendResourcesAvailable;
  a2->QueryCompleteHandler = (void (__fastcall *)(void *, int))NdisMQueryInformationComplete;
  a2->SetCompleteHandler = (void (__fastcall *)(void *, int))NdisMSetInformationComplete;
  a2->WanSendCompleteHandler = (void (__fastcall *)(void *, void *, int))ndisMWanSendCompleteInternal;
  a2->WanRcvHandler = (void (__fastcall *)(int *, void *, void *, unsigned __int8 *, unsigned int))&NdisMWanIndicateReceive;
  a2->WanRcvCompleteHandler = (void (__fastcall *)(void *, void *))NdisMWanIndicateReceiveComplete;
  a2->NoFilter.SendNetBufferListsCompleteHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int))ndisMSendCompleteNetBufferListsInternal;
  a2->Next.SendNetBufferListsCompleteHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int))ndisMSendCompleteNetBufferListsInternal;
  a2->NormalTopReceive = 1;
  a2->NoFilter.SendNetBufferListsCompleteContext = a2;
  a2->NoFilter.SendNetBufferListsCompleteTracker = (NDIS_NBL_TRACKER_HANDLE__ *)48;
  a2->NoFilter.SendNetBufferListsCompleteObject = &a2->Header;
  a2->Next.SendNetBufferListsCompleteContext = a2;
  a2->Next.SendNetBufferListsCompleteTracker = (NDIS_NBL_TRACKER_HANDLE__ *)48;
  a2->Next.SendNetBufferListsCompleteObject = &a2->Header;
  a2->NoFilter.RequestHandle = a2;
  a2->NoFilter.DirectRequestHandle = a2;
  a2->Next.RequestHandle = a2;
  a2->Next.DirectRequestHandle = a2;
  a2->TimeOfInitialization.QuadPart = MEMORY[0xFFFFF78000000014];
  if ( v16 )
  {
    Pool2 = (_NDIS_MINIPORT_STATS *)ExAllocatePool2(64, 112 * ndisMaxNumberOfProcessors, 538985550);
    v17 = a2;
    a2->BottomIfStats = Pool2;
    if ( !Pool2 )
    {
LABEL_46:
      v32 = 0;
LABEL_47:
      v33 = 0;
      LOBYTE(Offload) = 0;
LABEL_48:
      GeneralAttributes = (struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *)&WPP_RECORDER_INITIALIZED;
      goto LABEL_49;
    }
    DriverHandle = a2->DriverHandle;
    v20 = MajorNdisVersion;
    a2->DeferredSendHandler = ndisMDeferredSend;
    a2->DisableInterruptHandler = DriverHandle->MiniportCharacteristics.Ndis50Chars.DisableInterruptHandler;
    a2->EnableInterruptHandler = DriverHandle->MiniportCharacteristics.Ndis50Chars.EnableInterruptHandler;
    a2->NoFilter.ReturnNetBufferListsHandler = (void (__fastcall *)(void *, _NET_BUFFER_LIST *, unsigned int))ndisReturnNetBufferListsToPackets;
    a2->NoFilter.ReturnNetBufferListsContext = a2;
    a2->NoFilter.ReturnNetBufferListsTracker = (NDIS_NBL_TRACKER_HANDLE__ *)64;
    a2->NoFilter.ReturnNetBufferListsObject = &a2->Header;
    a2->SendHandler = DriverHandle->MiniportCharacteristics.Ndis50Chars.SendHandler;
    if ( v20 >= 4u )
    {
      if ( a1->MiniportDriverCharacteristics.DevicePnPEventNotifyHandler )
        a2->InfoFlags |= 0x10u;
      a2->SynchronousReturnPacketHandler = DriverHandle->MiniportCharacteristics.Ndis50Chars.ReturnPacketHandler;
      a2->MiniportReturnPacketHandler = DriverHandle->MiniportCharacteristics.Ndis50Chars.ReturnPacketHandler;
      a2->SynchronousReturnPacketContext = a2->MiniportAdapterContext;
      if ( a1->MiniportDriverCharacteristics.ShutdownHandlerEx )
      {
        a2->SendFlags |= 1u;
        a2->DeferredSendHandler = ndisMDeferredSendPackets;
        ShutdownHandlerEx = a1->MiniportDriverCharacteristics.ShutdownHandlerEx;
        a2->InfoFlags |= 0x8000000u;
        a2->WSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ShutdownHandlerEx;
      }
      if ( v20 >= 5u )
      {
        a2->InfoFlags |= 0x200u;
        if ( a1->MiniportCharacteristics.Ndis50Chars.CoSendPacketsHandler )
        {
          MINIPORT_SET_FLAG(a2, 0x20000u);
          a1->CoOidRequestHandler = (int (__fastcall *)(void *, void *, _NDIS_OID_REQUEST *))ndisMCoOidRequestToRequest;
          v17->NextCoOidRequestHandle = v17;
        }
      }
    }
    ConfigurationHandle = &v17->NblTracker;
  }
  else
  {
    v22 = a2->DriverHandle;
    a2->Miniport5HasNdis6Component = 1;
    ReturnNetBufferListsHandler = v22->MiniportDriverCharacteristics.ReturnNetBufferListsHandler;
    a2->NoFilter.ReturnNetBufferListsContext = a2->MiniportAdapterContext;
    a2->NoFilter.ReturnNetBufferListsHandler = ReturnNetBufferListsHandler;
    a2->NoFilter.ReturnNetBufferListsTracker = a2->NblTracker;
    a2->SynchronousReturnPacketHandler = (void (__fastcall *)(void *, _NDIS_PACKET *))ndisSynchReturnPacketsForTranslation;
    a2->NoFilter.ReturnNetBufferListsObject = &a2->Header;
    a2->SynchronousReturnPacketContext = a2;
    v83 = a1->CoSendNetBufferListsHandler == 0;
    ConfigurationHandle = &a2->NblTracker;
    if ( v83 )
      ConfigurationHandle = &a2->NblTracker;
    else
      MINIPORT_SET_FLAG(a2, 0x20000u);
  }
  ndisReferenceMiniportNoCheck(v17, MPREF_PNP_INITIALIZED);
  v7 = 1;
  v140 = 1;
  if ( a2->CurrentDevicePowerState == PowerDeviceUnspecified )
  {
    a2->CurrentDevicePowerState = PowerDeviceD0;
    a2->DriverPowerState = PowerDeviceD0;
  }
  ndisQueryPowerCapabilities(a2);
  ndisMInitializeInitMode(a2);
  *(_QWORD *)ConfigurationHandle = NdisNblTrackerRegisterComponent(0, a2, a2->pAdapterInstanceName);
  PerProcessorSlot = ndisAllocatePerProcessorSlot(0x527374u);
  v17 = a2;
  a2->PeriodicReceivesNblCountIndex = PerProcessorSlot;
  if ( !PerProcessorSlot )
    goto LABEL_46;
  v25 = 0;
  for ( i = 1; v25 < ndisMaxNumberOfProcessors; *(_DWORD *)((char *)a2->PeriodicReceivesNblCountIndex + v26) = 6 )
    v26 = v25++ << 12;
  MINIPORT_SET_FLAG(a2, 0x20000002u);
  MINIPORT_CLEAR_FLAG(v27, 1u);
  if ( (a1->Flags & 2) != 0 )
  {
    v29->PnPFlags |= 0x100000u;
    if ( !ndisDriverTrackAlloc || (v83 = ndisMiniportTrackAlloc == 0, ndisMiniportTrackAlloc = v29, !v83) )
      ndisMiniportTrackAlloc = 0;
  }
  if ( ndisDatapathVerifierMode == 1 )
  {
    if ( (v29->PnPFlags & 0x100000) == 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  if ( ndisDatapathVerifierMode == 2 )
LABEL_35:
    v29->DriverVerifyFlags |= 0x800u;
LABEL_36:
  if ( v29->MajorNdisVersion < 6u )
    goto LABEL_42;
  if ( ndisNblContextVerifierMode == 1 )
  {
    if ( (v29->PnPFlags & 0x100000) == 0 )
      goto LABEL_42;
    goto LABEL_41;
  }
  if ( ndisNblContextVerifierMode == 2 )
LABEL_41:
    v29->DriverVerifyFlags |= 0x1000u;
LABEL_42:
  v30 = ndisRssV2Initialize(v28);
  if ( v30 )
  {
    GeneralAttributes = (struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *)&WPP_RECORDER_INITIALIZED;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
      v17 = a2;
      v32 = 0;
      v33 = 0;
      LOBYTE(Offload) = 0;
LABEL_49:
      v34 = 0;
      if ( !*(_DWORD *)v139 )
        goto LABEL_51;
      goto LABEL_50;
    }
    LOBYTE(Offload) = 2;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)Offload,
      1,
      14,
      (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
      (char)a2,
      v30);
LABEL_45:
    v17 = a2;
    goto LABEL_46;
  }
  v41 = a2;
  if ( a1->ReenumerateFailedAdapterHandler )
  {
    v83 = a2->ReenumerateSelfInterface == 0;
    *(_QWORD *)&Keyword.Length = &a2->ReenumerateSelfInterface;
    if ( v83 )
    {
      ReenumerateSelfInterface = ndisQueryReenumerateSelfInterface(a2->NextDeviceObject, &a2->ReenumerateSelfInterface);
      *(_DWORD *)v142 = ReenumerateSelfInterface;
      if ( ReenumerateSelfInterface >= 0 )
      {
        ConfigurationHandle = 0;
        memset(&Event, 0, sizeof(Event));
        v44 = *(_DWORD *)(**(_QWORD **)&Keyword.Length + 40LL);
        v45 = (v44 >> 1) & 1;
        OidList = v45;
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)&WPP_RECORDER_INITIALIZED,
            1,
            16,
            (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
            v45,
            v44 & 1);
        Event.Header.WaitListHead.Flink = (_LIST_ENTRY *)a2;
        Event.Header.LockNV = 1573289;
        LODWORD(Event.Header.WaitListHead.Blink) = 0;
        v46 = NdisOpenConfigurationEx((PNDIS_CONFIGURATION_OBJECT)&Event, &ConfigurationHandle);
        Status = v46;
        if ( v46 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v47) = 3;
            WPP_RECORDER_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v47,
              1,
              17,
              (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
              v46);
          }
        }
        else
        {
          *(_QWORD *)&Keyword.Length = 1966108;
          Keyword.Buffer = L"PldrCapability";
          memset(&ParameterValue, 0, sizeof(ParameterValue));
          ParameterValue.ParameterData.IntegerData = OidList;
          NdisWriteConfiguration(&Status, ConfigurationHandle, &Keyword, &ParameterValue);
          if ( Status
            && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v48) = 3;
            WPP_RECORDER_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v48,
              1,
              18,
              (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
              Status);
          }
          NdisCloseConfiguration(ConfigurationHandle);
        }
      }
      else
      {
        v43 = &WPP_RECORDER_INITIALIZED;
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v43) = 3;
          WPP_RECORDER_SF_qL(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)v43,
            1,
            15,
            (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
            (char)a2,
            ReenumerateSelfInterface);
        }
        *(_DWORD *)v142 = 0;
      }
      v41 = a2;
    }
  }
  v41->State = NdisMiniportInitializing;
  memset(&v155, 0, sizeof(v155));
  memset(&v158, 0, sizeof(v158));
  v158.Header.Revision = 2;
  if ( MajorNdisVersion < 6u )
  {
    v49 = ((__int64 (__fastcall *)(int *, unsigned int *, PVOID, __int64, struct _NDIS_MINIPORT_BLOCK *, _QWORD))a1->MiniportDriverCharacteristics.PauseHandler)(
            &v151,
            &v149,
            ndisMediumArray,
            15,
            a2,
            InputBuffer);
    v51 = a2;
    v52 = v49;
    Status = v49;
    if ( a2->BusType == PCIBus )
    {
      PciDeviceCustomProperties = ndisGetPciDeviceCustomProperties(a2, &a2->PciDeviceCustomProperties);
      v51 = a2;
      v52 = (unsigned int)Status;
      *(_DWORD *)v142 = PciDeviceCustomProperties;
    }
LABEL_94:
    p_NetLuid = &v51->NetLuid;
    p_IfIndex = &v51->IfIndex;
    *(_QWORD *)&Keyword.Length = &v51->NetLuid;
    ConfigurationHandle = &v51->IfIndex;
    goto LABEL_95;
  }
  InputBuffer = 0;
  DefaultPortRcvAuthorizationState = NdisPortAuthorizationUnknown;
  ndisReadMiniportDefaultPortAuthStates(a2);
  v59 = a2;
  LODWORD(InputBuffer) = 1311104;
  v155.Header = (_NDIS_OBJECT_HEADER)4194689;
  *(_QWORD *)((char *)&InputBuffer + 4) = *(_QWORD *)&a2->DefaultPortSendControlState;
  HIDWORD(InputBuffer) = a2->DefaultPortSendAuthorizationState;
  DefaultPortRcvAuthorizationState = a2->DefaultPortRcvAuthorizationState;
  AllocatedResources = a2->AllocatedResources;
  if ( AllocatedResources )
    v155.AllocatedResources = &AllocatedResources->List[0].PartialResourceList;
  v83 = a2->BusType == PCIBus;
  v155.IMDeviceInstanceContext = a2->DeviceContext;
  v155.MiniportAddDeviceContext = a2->AddDeviceContext;
  v155.DefaultPortAuthStates = (_NDIS_PORT_AUTHENTICATION_PARAMETERS *)&InputBuffer;
  *(_QWORD *)&Keyword.Length = &a2->NetLuid;
  v155.NetLuid.Value = a2->NetLuid.Value;
  ConfigurationHandle = &a2->IfIndex;
  v155.IfIndex = a2->IfIndex;
  if ( v83 )
  {
    *(_DWORD *)v142 = ndisGetPciDeviceCustomProperties(a2, &a2->PciDeviceCustomProperties);
    p_PciDeviceCustomProperties = v155.PciDeviceCustomProperties;
    v59 = a2;
    if ( *(int *)v142 >= 0 )
      p_PciDeviceCustomProperties = &a2->PciDeviceCustomProperties;
    v7 = 1;
    v155.PciDeviceCustomProperties = p_PciDeviceCustomProperties;
  }
  if ( MINIPORT_TEST_FLAG(v59, 0x100u) )
    v63 = ndisLWMInitializeHandler(v62);
  else
    v63 = ndisMInvokeInitialize(v62, &v155);
  v51 = a2;
  v52 = v63;
  Status = v63;
  if ( a2->BusType != PCIBus )
    goto LABEL_94;
  ndisMReadPciPropertiesFromConfigSpace(a2);
  v51 = a2;
  v52 = (unsigned int)Status;
  p_NetLuid = *(_NET_LUID_LH **)&Keyword.Length;
  p_IfIndex = ConfigurationHandle;
LABEL_95:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v50) = 4;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v50,
      13,
      19,
      (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
      (char)v51,
      v52);
    v51 = a2;
    v52 = (unsigned int)Status;
    p_NetLuid = *(_NET_LUID_LH **)&Keyword.Length;
    p_IfIndex = ConfigurationHandle;
  }
  if ( (byte_140121002 & 8) != 0 )
  {
    McTemplateK0jqxqq_EtwWriteTransfer(
      v52,
      InitializeAdapterInfo,
      &v51->InterfaceGuid,
      &v51->InterfaceGuid,
      *p_IfIndex,
      p_NetLuid->Value,
      1,
      v52);
    v51 = a2;
  }
  MINIPORT_CLEAR_FLAG(v51, 2u);
  if ( Status )
  {
    v17->State = NdisMiniportHalted;
    *(_QWORD *)&v17->OperStatus = 2;
    IfBlock = v17->IfBlock;
    if ( IfBlock && IfBlock->ifOperStatus != NET_IF_OPER_STATUS_DOWN )
    {
      IfBlock->ifOperStatus = NET_IF_OPER_STATUS_DOWN;
      v17->IfBlock->ifOperStatusFlags = v17->OperStatusFlags;
      ndisNsiSyncMiniportOperStatusNotification(v17);
      v17 = a2;
    }
    if ( v17->InvalidateBlockIoctlVf )
    {
      ndisIovTeardownVf(v17);
      v17 = a2;
    }
    ndisMDeregisterBugCheckHandler(v17);
    v17 = a2;
    *(_DWORD *)v139 = Status;
    if ( !a2->TimerQueue )
    {
      if ( a2->Interrupt )
        goto LABEL_342;
      if ( !a2->InterruptEx )
        goto LABEL_324;
    }
    if ( !a2->Interrupt )
    {
      if ( a2->InterruptEx )
      {
        DbgPrintEx(
          0x78u,
          0,
          " ***NDIS*** : Miniport %Z - %s\n",
          a2->pAdapterInstanceName,
          "Init failed without deregistering interrupt");
        KeBugCheckEx(0x7Cu, 0xBu, (ULONG_PTR)a2, (ULONG_PTR)a2->InterruptEx, 0);
      }
      if ( !MINIPORT_TEST_FLAG(a2, 0x80u) )
      {
        DbgPrintEx(
          0x78u,
          0,
          " ***NDIS*** : Miniport %Z - %s\n",
          v17->pAdapterInstanceName,
          "Init failed without canceling timer");
        KeBugCheckEx(0x7Cu, 0xCu, (ULONG_PTR)a2, (ULONG_PTR)a2->TimerQueue, 0);
      }
      goto LABEL_324;
    }
LABEL_342:
    DbgPrintEx(
      0x78u,
      0,
      " ***NDIS*** : Miniport %Z - %s\n",
      a2->pAdapterInstanceName,
      "Init failed without deregistering interrupt");
    KeBugCheckEx(0x7Cu, 0xBu, (ULONG_PTR)a2, (ULONG_PTR)a2->Interrupt, 0);
  }
  v34 = 0;
  v131 = 1;
  if ( v17->MajorNdisVersion >= 6u && !v17->GeneralAttributes )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v17 = a2;
    GeneralAttributes = (struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *)&WPP_RECORDER_INITIALIZED;
    v56 = *(_QWORD **)&Keyword.Length;
    v57 = ConfigurationHandle;
    if ( !a2->GeneralAttributes )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v58) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v58,
          1,
          20,
          (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
          (char)a2);
        v17 = a2;
      }
      goto LABEL_105;
    }
  }
  v83 = (v17->PnPFlags & 0x8000000) == 0;
  p_BaseMiniport = &v17->BaseMiniport;
  *(_QWORD *)&InputBuffer = &v17->BaseMiniport;
  if ( v83 )
  {
    *p_BaseMiniport = v17;
  }
  else
  {
    ndisReferenceMiniportByName(v17->BindPaths->Paths, p_BaseMiniport, 1u, MPREF_PNP_BASEINIT);
    if ( *(_QWORD *)InputBuffer )
      ndisDereferenceMiniportRef(*(struct _NDIS_MINIPORT_BLOCK **)InputBuffer, MPREF_PNP_BASEINIT);
    v57 = ConfigurationHandle;
    GeneralAttributes = (struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES *)&WPP_RECORDER_INITIALIZED;
    v56 = *(_QWORD **)&Keyword.Length;
    v17 = a2;
  }
  if ( MajorNdisVersion < 6u )
  {
    Interrupt = v17->Interrupt;
    if ( !Interrupt || Interrupt->IsrRequested || Interrupt->SharedInterrupt )
      v17->Flags &= ~1u;
    else
      v17->Flags |= 1u;
    if ( !v17->ShutdownHandler )
    {
      v17->ShutdownHandler = a1->MiniportCharacteristics.AdapterShutdownHandler;
      v17->ShutdownContext = v17->MiniportAdapterContext;
    }
    LODWORD(p_BaseMiniport) = *((_DWORD *)ndisMediumArray + v149);
    v158.MediaType = (int)p_BaseMiniport;
    v17->MediaType = (int)p_BaseMiniport;
    v17->MiniportMediaType = (int)p_BaseMiniport;
  }
  MediaType = v17->MediaType;
  v17->State = NdisMiniportPaused;
  if ( MediaType > 0xD || (v67 = 8390, !_bittest((const int *)&v67, MediaType)) )
  {
    ndisMRegisterBugCheckHandler(v17);
    v17 = a2;
    if ( a2->MediaType == NdisMediumWan )
    {
      if ( MajorNdisVersion > 4u && !MINIPORT_TEST_FLAG(a2, 0x20000u) )
      {
        *(_DWORD *)v139 = 32;
        v133 = 1;
        goto LABEL_50;
      }
      if ( !MINIPORT_TEST_FLAG(v17, 0x20000u) )
        v17->DeferredSendHandler = ndisMStartWanSends;
    }
    NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(v17, &v136);
    v68 = ndisSetWakeUpTimer(a2);
    v69 = v136;
    v130 = v68 != 0;
    a2->MiniportThread = 0;
    KeReleaseSpinLock(&a2->Lock, v69);
    ndisMStartInitMode(a2);
    if ( (unsigned int)ndisCreateNdisSupportedOidList(a2) )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v70) = 2;
        WPP_RECORDER_SF_qL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v70,
          1,
          22,
          (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
          (char)a2,
          v142[0]);
      }
      if ( (byte_140121002 & 0x10) != 0 )
        McTemplateK0jqxqq_EtwWriteTransfer(
          v71,
          InitializeAdapterFailed,
          &a2->InterfaceGuid,
          &a2->InterfaceGuid,
          *(_DWORD *)ConfigurationHandle,
          **(_QWORD **)&Keyword.Length,
          2,
          *(_DWORD *)v142);
      v17 = a2;
      *(_DWORD *)v139 = 36;
      goto LABEL_50;
    }
    if ( MajorNdisVersion >= 6u )
    {
      v17 = a2;
      if ( a2->MP6SupportPM )
        v147 = 0;
      goto LABEL_160;
    }
    v158.PowerManagementCapabilitiesEx = (_NDIS_PM_CAPABILITIES *)&v161;
    v163[0] = 0;
    a2->GeneralAttributes = &v158;
    v161 = 0;
    v162 = 0;
    *(_OWORD *)((char *)v163 + 12) = 0;
    MiniportInfo = ndisGetMiniportInfo(a2, &v158, (int *)v139, &v133, &v147);
    if ( !MiniportInfo )
    {
      v73 = ndisMSetGeneralAttributes(a2, a2->GeneralAttributes);
      v17 = a2;
      if ( v73 )
      {
LABEL_156:
        v32 = 1;
        goto LABEL_47;
      }
      Offload = a2->Offload;
      if ( !Offload )
      {
        MiniportInfo = 0;
LABEL_155:
        if ( MiniportInfo )
          goto LABEL_156;
LABEL_160:
        if ( !MINIPORT_TEST_FLAG(v17, 0x80u) && !MINIPORT_TEST_FLAG(v74, 0x100u) )
        {
          v76 = ndisCheckNetworkInterfaceDataMismatch(v75, v17->GeneralAttributes);
          v77 = NdisConvertNtStatusToNdisStatus(v76);
          v17 = a2;
          if ( v77 )
          {
            v32 = 1;
            goto LABEL_47;
          }
        }
        *(_DWORD *)v142 = ndisIovCreateDefaultNicSwitch(v17);
        if ( *(_DWORD *)v142 )
        {
          v17 = a2;
          v32 = 1;
          goto LABEL_47;
        }
        ndisMNotifyMachineName(a2);
        v78 = a2;
        PnPFlags = a2->PnPFlags;
        if ( ((PnPFlags & 0x8001) != 0 || (a2->DriverHandle->Flags & 1) != 0)
          && a2->MediaType < (unsigned int)NdisMediumMax )
        {
          if ( v147 )
            PnPFlags &= ~1u;
          else
            PnPFlags |= 1u;
          a2->PnPFlags = PnPFlags;
        }
        if ( ((PnPFlags & 0x200000) != 0 && ndisAoAcCapable || (a2->FilterPnPFlags & 0x200) != 0)
          && (unsigned int)(a2->PMHardwareCapabilities.MinMagicPacketWakeUp - 2) <= 2
          && (a2->PMAdminConfig.Value & 0xC) == 0 )
        {
          DisableMagicPacketKeyword(a2);
          v78 = a2;
        }
        NdisInitializeTimer(&v78->MediaDisconnectTimer, ndisMediaDisconnectTimeout, v78);
        KeInitializeEvent(&a2->WaitWakeIrpCompleted, NotificationEvent, 1u);
        ndisUpdatePMCurrentCapabilities(a2);
        if ( (a2->PnPFlags & 1) != 0 )
        {
          v80 = ndisCheckMiniportWakeUpCapable(a2);
          PnPCapabilities = a2->PnPCapabilities;
          if ( (PnPCapabilities & 8) == 0 )
          {
            a2->PnPFlags |= 0x20u;
            v82 = a2->PnPFlags;
            if ( (unsigned int)(a2->PMAdvertisedCapabilities.MinLinkChangeWakeUp - 2) <= 2 )
              a2->PMCurrentParameters.WakeUpFlags |= 1u;
            if ( (PnPCapabilities & 0x10) == 0 && v80 )
            {
              if ( (unsigned int)(a2->PMAdvertisedCapabilities.MinPatternWakeUp - 2) <= 2 )
              {
                v82 |= 0x40u;
                a2->PnPFlags = v82;
              }
              if ( (unsigned int)(a2->PMAdvertisedCapabilities.MinMagicPacketWakeUp - 2) <= 2 )
              {
                a2->PMCurrentParameters.EnabledWoLPacketPatterns |= 2u;
                v83 = a2->MajorNdisVersion == 6;
                v84 = a2->MajorNdisVersion <= 6u;
                a2->PnPFlags = v82 | 0x40;
                if ( !v84 || v83 && a2->MinorNdisVersion >= 0x14u )
                {
                  v85 = ndisAddWoLMagicPacket(a2);
                  *(_DWORD *)v142 = v85;
                  if ( v85 )
                  {
                    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v86) = 2;
                      WPP_RECORDER_SF_qL(
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        v86,
                        1,
                        23,
                        (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                        (char)a2,
                        v85);
                    }
                  }
                }
              }
            }
            if ( !MINIPORT_TEST_FLAG(a2, 0x80u) )
            {
              v88 = v87->PnPFlags;
              if ( (v88 & 0x40) != 0 )
              {
                if ( !v87->WaitWakeIrp )
                {
                  v87->PnPFlags = v88 & 0xFFFFFBFF;
                  *(_DWORD *)v142 = ndisRequestWaitWake(v87, ndisGenericWaitWakeCallback);
                }
              }
              else
              {
                ndisCancelWaitWake(v87);
              }
            }
          }
        }
        NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(a2, &v136);
        v89 = a2;
        if ( a2->MediaConnectState == MediaConnectStateDisconnected )
        {
          ndisSetMediaDisconnectTimer(a2);
          v89 = a2;
        }
        v90 = v136;
        v89->MiniportThread = 0;
        KeReleaseSpinLock(&v89->Lock, v90);
        v91 = a2;
        a2->D0CompleteSignalWorkItem.WorkItem.Context = a2;
        a2->D0CompleteSignalWorkItem.WorkItem.Routine = (void (__fastcall *)(_NDIS_WORK_ITEM *, void *))ndisSignalD0CompleteWorkItem;
        a2->DevicePowerOnWorkItem.Workitem.WorkerRoutine = ndisDevicePowerOn;
        a2->DevicePowerOnWorkItem.Workitem.Parameter = &a2->DevicePowerOnWorkItem;
        a2->DevicePowerOnWorkItem.Workitem.List.Flink = 0;
        a2->DevicePowerDownWorkItem.Workitem.WorkerRoutine = ndisDevicePowerDown;
        a2->DevicePowerDownWorkItem.Workitem.Parameter = &a2->DevicePowerDownWorkItem;
        a2->DevicePowerDownWorkItem.Workitem.List.Flink = 0;
        if ( (a2->PMAdvertisedCapabilities.Flags & 6) != 0 )
        {
          ndisSelectiveSuspendInitialize(a2);
          v91 = a2;
        }
        if ( (v91->PnPFlags & 0x200000) != 0 && ndisAoAcCapable || (v91->FilterPnPFlags & 0x200) != 0 )
        {
          ndisAoAcInitialize(v91);
          ndisReadModernStandyWoLMagicPacketKeywords(a2);
          ndisMRegisterPDCTaskClient(a2);
          ndisMInitializePDCTaskClient(a2);
          v91 = a2;
        }
        if ( v91->MediaType )
        {
          EthDB = v91->EthDB;
          if ( EthDB )
          {
            nullDeleteFilter(EthDB);
            a2->EthDB = 0;
          }
          if ( !nullCreateFilter(v153) )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v93) = 3;
              WPP_RECORDER_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v93,
                1,
                25,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                (char)a2);
            }
            *(_DWORD *)v139 = 30;
            v133 = 1;
            if ( (byte_140121002 & 0x10) != 0 )
              McTemplateK0jqxqq_EtwWriteTransfer(
                30,
                InitializeAdapterFailed,
                &a2->InterfaceGuid,
                &a2->InterfaceGuid,
                *(_DWORD *)ConfigurationHandle,
                **(_QWORD **)&Keyword.Length,
                6,
                30);
LABEL_219:
            v96 = a2;
            goto LABEL_221;
          }
        }
        else if ( !EthCreateFilter(
                     v91->GeneralAttributes->MaxMulticastListSize,
                     v91->GeneralAttributes->CurrentMacAddress,
                     v153) )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v94) = 3;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v94,
              1,
              24,
              (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
              (char)a2);
          }
          *(_DWORD *)v139 = 9;
          v133 = 1;
          if ( (byte_140121002 & 0x10) != 0 )
            McTemplateK0jqxqq_EtwWriteTransfer(
              v95,
              InitializeAdapterFailed,
              &a2->InterfaceGuid,
              &a2->InterfaceGuid,
              *(_DWORD *)ConfigurationHandle,
              **(_QWORD **)&Keyword.Length,
              4,
              9);
          goto LABEL_219;
        }
        v96 = a2;
        v153[0]->Miniport = a2;
LABEL_221:
        if ( v96->MiniportMediaType == NdisMediumNative802_11 && MajorNdisVersion >= 6u )
        {
          *(_QWORD *)&InputBuffer = &v96->600;
          if ( !nullCreateFilter((struct _X_FILTER **)&v96->600) )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(Offload) = 3;
              WPP_RECORDER_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                (int)Offload,
                1,
                26,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                (char)a2);
            }
            a2->Reserved1 = 0;
            *(_DWORD *)v139 = 30;
            v133 = 1;
            if ( (byte_140121002 & 0x10) != 0 )
              McTemplateK0jqxqq_EtwWriteTransfer(
                30,
                InitializeAdapterFailed,
                &a2->InterfaceGuid,
                &a2->InterfaceGuid,
                *(_DWORD *)ConfigurationHandle,
                **(_QWORD **)&Keyword.Length,
                7,
                30);
            v32 = 1;
            v17 = a2;
            goto LABEL_47;
          }
          v96 = a2;
          *(_QWORD *)(*(_QWORD *)InputBuffer + 296LL) = a2;
        }
        if ( v96->MediaType == NdisMedium802_3 )
          v96->CheckPacketFilters = 1;
        if ( !MINIPORT_TEST_FLAG(v96, 0x80u) && !MINIPORT_TEST_FLAG(v98, 0x100u) )
        {
          OidList = IoWMIRegistrationControl(v99->DeviceObject, 1u);
          v100 = OidList;
          if ( (OidList & 0x80000000) != 0 )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v97) = 3;
              WPP_RECORDER_SF_qL(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v97,
                1,
                27,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                (char)a2,
                OidList);
              v100 = OidList;
            }
            if ( (byte_140121002 & 0x10) != 0 )
              McTemplateK0jqxqq_EtwWriteTransfer(
                v100,
                InitializeAdapterFailed,
                &a2->InterfaceGuid,
                &a2->InterfaceGuid,
                *(_DWORD *)ConfigurationHandle,
                **(_QWORD **)&Keyword.Length,
                8,
                v100);
            v99 = a2;
            v101 = 1;
            v133 = 1;
            *(_DWORD *)v139 = 31;
            goto LABEL_242;
          }
          v99 = a2;
          v135 = 1;
        }
        v101 = v133;
        if ( v133 )
        {
LABEL_242:
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v97) = 3;
            WPP_RECORDER_SF_qL(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v97,
              1,
              28,
              (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
              (char)v99,
              v101);
            v99 = a2;
          }
          OutputBufferLength[0] = *(_DWORD *)v139;
          NdisWriteErrorLogEntry(v99, 0xC000138D, 2u, 4278255360LL, *(_QWORD *)OutputBufferLength);
          v32 = 1;
          v17 = a2;
          v33 = 0;
          LODWORD(Offload) = v135;
          goto LABEL_48;
        }
        *(_DWORD *)v139 = 1;
        if ( !MINIPORT_TEST_FLAG(v99, 0x100u) )
        {
          OidList = IoRegisterDeviceInterface(
                      v17->PhysicalDeviceObject,
                      &InterfaceClassGuid,
                      &v17->BaseName,
                      &v17->SymbolicLinkName);
          v103 = OidList;
          if ( (OidList & 0x80000000) != 0 )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v102) = 2;
              WPP_RECORDER_SF_qL(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                (int)v102,
                1,
                29,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                (char)a2,
                OidList);
              v103 = OidList;
            }
            if ( (byte_140121002 & 0x10) != 0 )
              McTemplateK0jqxqq_EtwWriteTransfer(
                v103,
                InitializeAdapterFailed,
                &a2->InterfaceGuid,
                &a2->InterfaceGuid,
                *(_DWORD *)ConfigurationHandle,
                **(_QWORD **)&Keyword.Length,
                10,
                v103);
            v17 = a2;
            *(_DWORD *)v139 = 35;
            goto LABEL_50;
          }
          v17 = a2;
          v138 = 1;
          SriovCurrentCapabilities = a2->SriovCurrentCapabilities;
          if ( SriovCurrentCapabilities && (SriovCurrentCapabilities->SriovCapabilities & 3) == 3 )
          {
            v105 = IoRegisterDeviceInterface(a2->PhysicalDeviceObject, &v165, 0, &a2->DevinterfaceVirtSymbolicLinkName);
            v106 = v105;
            OidList = v105;
            if ( *(int *)v142 < 0 )
            {
              if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v102) = 2;
                WPP_RECORDER_SF_qL(
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  (int)v102,
                  1,
                  30,
                  (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                  (char)a2,
                  v105);
                v106 = OidList;
              }
              if ( (byte_140121002 & 0x10) != 0 )
                McTemplateK0jqxqq_EtwWriteTransfer(
                  v106,
                  InitializeAdapterFailed,
                  &a2->InterfaceGuid,
                  &a2->InterfaceGuid,
                  *(_DWORD *)ConfigurationHandle,
                  **(_QWORD **)&Keyword.Length,
                  0,
                  v106);
              v17 = a2;
              *(_DWORD *)v139 = 34;
              v133 = 1;
              goto LABEL_50;
            }
            v17 = a2;
            v134 = 1;
          }
          v17->DeviceObject->Flags &= ~0x80u;
        }
        GeneralAttributes = v17->GeneralAttributes;
        if ( !GeneralAttributes || (v102 = v17->IfBlock) == 0 )
        {
          v107 = 3221225473LL;
          *(_DWORD *)v142 = -1073741823;
LABEL_327:
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v102) = 2;
            WPP_RECORDER_SF_qL(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              (int)v102,
              1,
              31,
              (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
              (char)v17,
              v107);
            v17 = a2;
            v107 = *(unsigned int *)v142;
          }
          if ( (byte_140121002 & 0x10) != 0 )
          {
            McTemplateK0jqxqq_EtwWriteTransfer(
              v107,
              InitializeAdapterFailed,
              &v17->InterfaceGuid,
              &v17->InterfaceGuid,
              *(_DWORD *)ConfigurationHandle,
              **(_QWORD **)&Keyword.Length,
              11,
              v107);
            v17 = a2;
          }
          *(_DWORD *)v139 = 32;
          v133 = 1;
          goto LABEL_50;
        }
        *(_DWORD *)v142 = ndisIfUpdateInterfaceOnInitialize(v17, v102, GeneralAttributes);
        v107 = *(unsigned int *)v142;
        if ( *(_DWORD *)v142 )
        {
          v17 = a2;
          goto LABEL_327;
        }
        v10 = 1;
        if ( (a2->PnPFlags & 0x200000) != 0 )
          a2->PhysicalPerformanceCounters = (_NDIS_PHYSICAL_PERFORMANCE_COUNTERS *)ExAllocatePool2(64, 32, 2002994254);
        if ( !a2->OidList )
        {
          memset(v157, 0, 0x60u);
          *(_QWORD *)&v157[8] = a2;
          OidList = ndisQueryOidList((struct _NDIS_USER_OPEN_CONTEXT *)v157);
          v109 = OidList;
          if ( OidList )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v108) = 2;
              WPP_RECORDER_SF_qL(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v108,
                1,
                32,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                (char)a2,
                OidList);
              v109 = OidList;
            }
            if ( (byte_140121002 & 0x10) != 0 )
              McTemplateK0jqxqq_EtwWriteTransfer(
                v109,
                InitializeAdapterFailed,
                &a2->InterfaceGuid,
                &a2->InterfaceGuid,
                *(_DWORD *)ConfigurationHandle,
                **(_QWORD **)&Keyword.Length,
                12,
                v109);
          }
        }
        v110 = a2->Offload;
        if ( v110 )
        {
          if ( v110->SupportsOffload == 1 )
          {
            v110->SupportsTopOffload = 1;
            v111 = a2->Offload;
            *(_OWORD *)&v111->TopCapabilities.Header.Type = *(_OWORD *)&v111->MiniportCurrentConfig.Header.Type;
            *(_OWORD *)((char *)&v111->TopCapabilities.Checksum.IPv4Receive + 4) = *(_OWORD *)((char *)&v111->MiniportCurrentConfig.Checksum.IPv4Receive
                                                                                             + 4);
            *(_OWORD *)((char *)&v111->TopCapabilities.Checksum.IPv6Receive + 4) = *(_OWORD *)((char *)&v111->MiniportCurrentConfig.Checksum.IPv6Receive
                                                                                             + 4);
            *(_NDIS_TCP_LARGE_SEND_OFFLOAD_V1::<unnamed_type_IPv4> *)((char *)&v111->TopCapabilities.LsoV1.IPv4 + 12) = *(_NDIS_TCP_LARGE_SEND_OFFLOAD_V1::<unnamed_type_IPv4> *)((char *)&v111->MiniportCurrentConfig.LsoV1.IPv4 + 12);
            *(_OWORD *)&v111->TopCapabilities.IPsecV1.Supported.IPv4Options = *(_OWORD *)&v111->MiniportCurrentConfig.IPsecV1.Supported.IPv4Options;
            *(_OWORD *)&v111->TopCapabilities.LsoV2.IPv4.Encapsulation = *(_OWORD *)&v111->MiniportCurrentConfig.LsoV2.IPv4.Encapsulation;
            *(_OWORD *)&v111->TopCapabilities.LsoV2.IPv6.MaxOffLoadSize = *(_OWORD *)&v111->MiniportCurrentConfig.LsoV2.IPv6.MaxOffLoadSize;
            *(_OWORD *)&v111->TopCapabilities.IPsecV2.Encapsulation = *(_OWORD *)&v111->MiniportCurrentConfig.IPsecV2.Encapsulation;
            *(_OWORD *)&v111->TopCapabilities.IPsecV2.UdpEsp = *(_OWORD *)&v111->MiniportCurrentConfig.IPsecV2.UdpEsp;
            *(_OWORD *)&v111->TopCapabilities.Rsc.IPv4.Enabled = *(_OWORD *)&v111->MiniportCurrentConfig.Rsc.IPv4.Enabled;
            *(_OWORD *)&v111->TopCapabilities.EncapsulatedPacketTaskOffloadVxlan.MaxHeaderSizeSupported = *(_OWORD *)&v111->MiniportCurrentConfig.EncapsulatedPacketTaskOffloadVxlan.MaxHeaderSizeSupported;
            *(_OWORD *)&v111->TopCapabilities.EncapsulationTypes = *(_OWORD *)&v111->MiniportCurrentConfig.EncapsulationTypes;
            *(_OWORD *)&v111->TopCapabilities.UdpSegmentation.IPv4.MaxOffLoadSize = *(_OWORD *)&v111->MiniportCurrentConfig.UdpSegmentation.IPv4.MaxOffLoadSize;
            *(_OWORD *)&v111->TopCapabilities.UdpSegmentation.IPv6.MaxOffLoadSize = *(_OWORD *)&v111->MiniportCurrentConfig.UdpSegmentation.IPv6.MaxOffLoadSize;
            ndisMergeOffloadCapsAndRegistry(a2, &a2->Offload->TopCapabilities);
          }
          v112 = a2->Offload;
          if ( v112->SupportsTcpConnectionOffload == 1 )
          {
            v112->SupportsTopTcpConnectionOffload = 1;
            v113 = a2->Offload;
            *(_OWORD *)&v113->TopTcpConnectionOffloadCapabilities.Header.Type = *(_OWORD *)&v113->MiniportTcpConnectionOffloadCurrentConfig.Header.Type;
            v113->TopTcpConnectionOffloadCapabilities.Flags = v113->MiniportTcpConnectionOffloadCurrentConfig.Flags;
          }
        }
        if ( !ndisQueueMiniportOnDriver(a2, a1) )
        {
          v17 = a2;
          v33 = v134;
          v32 = 1;
          LODWORD(Offload) = v135;
          goto LABEL_48;
        }
        ndisSetDeviceInterfaceState(a2, 1u);
        if ( (int)Ndis::BindRegistry::Reload((Ndis::BindRegistry *)a2, 0, v114) < 0 )
        {
          v34 = 1;
          v17 = a2;
          *(_DWORD *)v139 = 39;
          v133 = 1;
          goto LABEL_50;
        }
        ndisPcwNotifyMiniportCreation(a2);
        Ndis::BindEngine::BeginPolicyUpdates(&a2->BindEngine);
        if ( Ndis::BindState::SetBinding(&a2->Bindings.Miniport, BindingDisabled, Reason_MiniportDeviceNotStarted) )
        {
          memset(v157, 0, sizeof(v157));
          if ( (unsigned __int8)byte_140122AD3 >= 4u )
          {
            ndisGetBindLinkNameForTracing(a2, (struct NDIS_PNPTRACE_LOCALS *)v157);
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_Zq(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v115,
                28,
                33,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                *(__int64 *)&v157[8],
                v157[0]);
          }
        }
        if ( Ndis::BindState::SetPause(&a2->Bindings.Miniport, DatapathRunning, PauseReason_InitialPause) )
        {
          memset(v157, 0, sizeof(v157));
          if ( (unsigned __int8)byte_140122AD3 >= 4u )
          {
            ndisGetBindLinkNameForTracing(a2, (struct NDIS_PNPTRACE_LOCALS *)v157);
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_Zq(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v116,
                28,
                34,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                *(__int64 *)&v157[8],
                v157[0]);
          }
        }
        if ( Ndis::BindState::SetPause(&a2->Bindings.Miniport, DatapathRunning, PauseReason_RemovingMiniport) )
        {
          memset(v157, 0, sizeof(v157));
          if ( (unsigned __int8)byte_140122AD3 >= 4u )
          {
            ndisGetBindLinkNameForTracing(a2, (struct NDIS_PNPTRACE_LOCALS *)v157);
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_Zq(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v117,
                28,
                35,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                *(__int64 *)&v157[8],
                v157[0]);
          }
        }
        if ( !MINIPORT_TEST_FLAG(a2, 0x10000u)
          && Ndis::BindState::SetBinding(&a2->Bindings.Miniport, BindingDisabled, Reason_DefaultPortNotActive) )
        {
          memset(v157, 0, sizeof(v157));
          if ( (unsigned __int8)byte_140122AD3 >= 4u )
          {
            ndisGetBindLinkNameForTracing(a2, (struct NDIS_PNPTRACE_LOCALS *)v157);
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_Zq(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v118,
                28,
                36,
                (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
                *(__int64 *)&v157[8],
                v157[0]);
          }
        }
        Ndis::BindEngine::EndPolicyUpdates(&a2->BindEngine);
        Ndis::BindEngine::ApplyBindChanges(&a2->BindEngine, RunSynchronous, 0);
        if ( !MINIPORT_TEST_FLAG(a2, 0x100u) )
        {
          v148 = (_BYTE)ndisAcOnLine == 1;
          ndisNotifyMiniports(a2, v119, &v148, v120);
        }
        v16 = MajorNdisVersion < 6u;
        a2->EthDB = v153[0];
        if ( v16 )
        {
          a2->SendPacketsHandler = ndisMSendPackets;
          if ( MINIPORT_TEST_FLAG(a2, 0x40000u) )
          {
            a2->FinalSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsXToMiniport;
            a2->NextSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsXToMiniport;
          }
          else if ( MINIPORT_TEST_FLAG(v121, 0x40u) )
          {
            a2->FinalSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsSGToMiniport;
            a2->NextSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsSGToMiniport;
            v122 = ndisMDeferredSendPacketsSG;
            if ( !a1->MiniportDriverCharacteristics.ShutdownHandlerEx )
              v122 = ndisMDeferredSendSG;
            a2->DeferredSendHandler = v122;
          }
          else
          {
            a2->FinalSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsToMiniport;
            a2->NextSendPacketsHandler = (void (__fastcall *)(void *, _NDIS_PACKET **, unsigned int))ndisMSendPacketsToMiniport;
          }
        }
        else
        {
          a2->NextSendPacketsHandler = ndisMSendPacketsToNetBufferLists;
          a2->FinalSendPacketsHandler = ndisMSendPacketsToNetBufferLists;
        }
        NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(a2, &v136);
        ndisMSetIndicatePacketHandler(a2);
        v123 = v136;
        a2->MiniportThread = 0;
        KeReleaseSpinLock(&a2->Lock, v123);
        if ( ((a2->PnPFlags & 0x200000) != 0 && ndisAoAcCapable || (a2->FilterPnPFlags & 0x200) != 0)
          && a2->PhysicalMediumType == NdisPhysicalMedium802_3 )
        {
          DWORD2(InputBuffer) = 4;
          v83 = a2->PMHardwareCapabilities.Header.Revision == 2;
          HIWORD(InputBuffer) = 0;
          *(_QWORD *)&InputBuffer = a2->PhysicalDeviceObject;
          BYTE12(InputBuffer) = 1;
          if ( !v83
            || (a2->PMHardwareCapabilities.SupportedWoLPacketPatterns & 1) == 0
            || a2->PMHardwareCapabilities.NumTotalWoLPatterns < 0x10
            || a2->PMHardwareCapabilities.MaxWoLPatternSize < 0x4A
            || (unsigned int)(a2->PMHardwareCapabilities.MinPatternWakeUp - 3) > 1
            || (a2->PMHardwareCapabilities.SupportedWakeUpEvents & 1) == 0
            || (v124 = a2->PMHardwareCapabilities.SupportedProtocolOffloads & 3,
                BYTE13(InputBuffer) = 1,
                (_BYTE)v124 != 3) )
          {
            BYTE13(InputBuffer) = 0;
          }
          ZwPowerInformation(SystemReserveHiberFile|0x40, &InputBuffer, 0x10u, 0, 0);
        }
        ndisPktMonMiniportRegister(a2);
        v14 = 0;
        v17 = a2;
        v11 = 0;
        *(_DWORD *)v139 = 0;
        v141 = 0;
LABEL_324:
        v32 = 0;
        LOBYTE(Offload) = 0;
        v10 = 0;
        v131 = 0;
        v33 = 0;
        v138 = 0;
        v7 = v14;
        v134 = 0;
        v135 = 0;
        v8 = v14;
        v140 = v14;
        i = v14;
        goto LABEL_48;
      }
      MiniportInfo = ndisMSetOffloadAttributes(
                       a2,
                       &Offload->MiniportInitialConfig,
                       &Offload->MiniportInitialConfig,
                       0,
                       0);
    }
    v17 = a2;
    goto LABEL_155;
  }
  if ( *(struct _NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES **)&WPP_RECORDER_INITIALIZED != GeneralAttributes )
  {
    LOBYTE(p_BaseMiniport) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)p_BaseMiniport,
      13,
      21,
      (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
      (char)v17);
    v17 = a2;
    v56 = *(_QWORD **)&Keyword.Length;
    v57 = ConfigurationHandle;
  }
  if ( (byte_140121003 & 0x10) != 0 )
  {
    McTemplateK0jqxd_EtwWriteTransfer(
      v67,
      UnsupportedMiniportMediaType,
      &v17->InterfaceGuid,
      &v17->InterfaceGuid,
      *v57,
      *v56,
      v17->MediaType);
    v17 = a2;
    *(_DWORD *)v139 = 32;
    v133 = 1;
    goto LABEL_50;
  }
LABEL_105:
  *(_DWORD *)v139 = 32;
  v133 = 1;
LABEL_50:
  Ndis::BindRegistry::Reload((Ndis::BindRegistry *)v17, 0, (enum Ndis::ReadBindingsOptions::Flags)GeneralAttributes);
  ndisNotifyBindFailureOnUnboundProtocols(a2);
  v32 = v131;
  v33 = v134;
  LODWORD(Offload) = v135;
LABEL_51:
  if ( v10 )
  {
    *(_QWORD *)&a2->OperStatus = 2;
    v35 = a2->IfBlock;
    if ( v35->ifOperStatus != NET_IF_OPER_STATUS_DOWN )
    {
      v35->ifOperStatus = NET_IF_OPER_STATUS_DOWN;
      a2->IfBlock->ifOperStatusFlags = a2->OperStatusFlags;
      ndisNsiSyncMiniportOperStatusNotification(a2);
      v32 = v131;
      v33 = v134;
      LODWORD(Offload) = v135;
    }
    if ( a2->PhysicalPerformanceCounters )
    {
      ExFreePoolWithTag(a2->PhysicalPerformanceCounters, 0);
      v32 = v131;
      v33 = v134;
      LODWORD(Offload) = v135;
      a2->PhysicalPerformanceCounters = 0;
    }
  }
  if ( (_BYTE)Offload )
  {
    IoWMIRegistrationControl(a2->DeviceObject, 2u);
    v33 = v134;
    v135 = 0;
    v32 = v131;
  }
  if ( v138 )
  {
    IoSetDeviceInterfaceState(&a2->DevinterfaceNetSymbolicLinkName, 0);
    v32 = v131;
    v33 = v134;
  }
  if ( v33 )
  {
    IoSetDeviceInterfaceState(&a2->DevinterfaceVirtSymbolicLinkName, 0);
    RtlFreeUnicodeString(&a2->DevinterfaceVirtSymbolicLinkName);
    v32 = v131;
    v7 = v140;
    a2->DevinterfaceVirtSymbolicLinkName.Buffer = 0;
    v134 = 0;
  }
  if ( v32 )
  {
    ndisIovDeleteDefaultNicSwitch(a2);
    v36 = 384;
    if ( !v134 )
      v36 = 128;
    v16 = v135 != 0;
    v135 = -v135;
    v37 = (v16 ? 2 : 0) | (v130 ? 8 : 0) | v36;
    v16 = v138 != 0;
    v138 = -v138;
    ndisMCommonHaltMiniport(a2, (v16 ? 4 : 0) | v37);
    ndisMDeregisterBugCheckHandler(a2);
  }
  if ( v8 )
  {
    if ( MINIPORT_TEST_FLAG(a2, 0x40u) && a2->MiniportSGDmaBlock )
    {
      if ( *(_QWORD *)&WPP_RECORDER_INITIALIZED != v39 )
      {
        LOBYTE(v38) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v38,
          1,
          37,
          (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
          (char)a2);
      }
      ndisDereferenceDmaAdapter(a2->MiniportSGDmaBlock);
    }
    NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(a2, &v136);
    if ( a2->MiniportSGDmaBlock )
    {
      memset(&Event, 0, sizeof(Event));
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v40 = v136;
      a2->MiniportSGDmaBlock->DmaResourcesReleasedEvent = &Event;
      a2->MiniportThread = 0;
      KeReleaseSpinLock(&a2->Lock, v40);
      if ( !ndisWaitForKernelObject(&Event, 30000) )
        goto LABEL_351;
    }
    else
    {
      v126 = v136;
      a2->MiniportThread = 0;
      KeReleaseSpinLock(&a2->Lock, v126);
    }
    MINIPORT_CLEAR_FLAG(a2, 0x40u);
  }
LABEL_351:
  if ( v34 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Offload) = 3;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)Offload,
        1,
        38,
        (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
        (char)a2);
    }
    ndisDeQueueMiniportOnDriver(a2, a1);
  }
  if ( v11 )
    IoDeleteSymbolicLink(&DestinationString);
  if ( v7 )
    ndisDereferenceMiniportRef(a2, MPREF_PNP_INITIALIZED);
  if ( v141 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Offload) = 3;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)Offload,
        1,
        39,
        (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
        (char)a2);
    }
    ndisDereferenceDriver(a1, 0, MDRVREF_MINIPORT);
  }
  v127 = a2->GeneralAttributes;
  if ( v127 )
  {
    if ( MajorNdisVersion >= 6u )
      ExFreePoolWithTag(v127, 0);
    a2->GeneralAttributes = 0;
  }
  if ( i )
  {
    ndisFreePerProcessorSlot((ULONG_PTR)a2->PeriodicReceivesNblCountIndex, 0x527374u);
    a2->PeriodicReceivesNblCountIndex = 0;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Offload) = 4;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)Offload,
      13,
      40,
      (struct _GUID *)&WPP_c79da8ce923232a16935bdab002d8339_Traceguids,
      (char)a2,
      v139[0]);
  }
  return *(unsigned int *)v139;
}

```

## disassembly

```asm
0x140181e50  mov     [rsp-8+arg_18], rbx
0x140181e55  push    rbp
0x140181e56  push    rsi
0x140181e57  push    rdi
0x140181e58  push    r12
0x140181e5a  push    r13
0x140181e5c  push    r14
0x140181e5e  push    r15
0x140181e60  lea     rbp, [rsp-360h]
0x140181e68  sub     rsp, 460h
0x140181e6f  mov     rax, cs:__security_cookie
0x140181e76  xor     rax, rsp
0x140181e79  mov     [rbp+390h+var_40], rax
0x140181e80  mov     qword ptr [rbp+390h+InputBuffer], r8
0x140181e87  mov     rdi, rdx
0x140181e8a  mov     [rsp+490h+FunctionContext], rdx
0x140181e8f  mov     rsi, rcx
0x140181e92  xor     edx, edx; Val
0x140181e94  lea     rcx, [rbp+390h+var_3A0]; void *
0x140181e98  mov     r8d, 40h ; '@'; Size
0x140181e9e  call    memset
0x140181ea3  xor     eax, eax
0x140181ea5  mov     dword ptr [rsp+490h+var_438], 1
0x140181ead  xorps   xmm0, xmm0
0x140181eb0  mov     [rbp+390h+var_408], 1
0x140181eb7  movups  xmmword ptr [rbp+390h+var_3C8], xmm0
0x140181ebb  xor     bl, bl
0x140181ebd  xor     r12b, r12b
0x140181ec0  movups  [rbp+390h+var_3B8], xmm0
0x140181ec4  xor     r15b, r15b
0x140181ec7  xor     r14b, r14b
0x140181eca  movups  xmmword ptr [rbp+390h+DestinationString.Length], xmm0
0x140181ece  xor     r13b, r13b
0x140181ed1  xor     edx, edx; Val
0x140181ed3  movups  xmm0, xmmword ptr cs:GUID_NDIS_LAN_CLASS.Data1
0x140181eda  mov     r8d, 0E0h; Size
0x140181ee0  mov     [rbp+390h+var_3E0], eax
0x140181ee3  lea     rcx, [rbp+390h+var_2A0]; void *
0x140181eea  mov     [rbp+390h+var_404], eax
0x140181eed  movups  xmmword ptr [rbp+390h+InterfaceClassGuid.Data1], xmm0
0x140181ef4  mov     [rbp+390h+var_400], eax
0x140181ef7  xorps   xmm0, xmm0
0x140181efa  mov     [rsp+490h+var_43D], al
0x140181efe  movups  xmmword ptr [rbp+390h+var_188], xmm0
0x140181f05  mov     [rsp+490h+var_433], al
0x140181f09  movups  xmmword ptr [rbp+390h+var_188+0Ch], xmm0
0x140181f10  mov     [rsp+490h+var_434], bl
0x140181f14  mov     [rsp+490h+var_440], al
0x140181f18  mov     [rsp+490h+var_44F], al
0x140181f1c  mov     [rsp+490h+var_43B], al
0x140181f20  mov     [rsp+490h+var_43E], al
0x140181f24  mov     [rsp+490h+var_450], al
0x140181f28  movups  [rbp+390h+var_1A8], xmm0
0x140181f2f  movups  [rbp+390h+var_198], xmm0
0x140181f36  call    memset
0x140181f3b  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.Data1
0x140181f42  mov     [rsp+490h+var_43F], bl
0x140181f46  movups  xmmword ptr [rbp+390h+var_158.Data1], xmm0
0x140181f4d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140181f54  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140181f5b  lea     rcx, WPP_c79da8ce923232a16935bdab002d8339_Traceguids
0x140181f62  jz      short loc_140181F93
0x140181f64  mov     rax, [rdi+0F10h]
0x140181f6b  mov     r9d, 0Dh; int
0x140181f71  mov     qword ptr [rsp+490h+var_460], rax; __int64
0x140181f76  mov     r8d, r9d; int
0x140181f79  mov     qword ptr [rsp+490h+var_468], rdi; char
0x140181f7e  mov     qword ptr [rsp+490h+OutputBufferLength], rcx; struct _GUID *
0x140181f83  mov     rcx, cs:WPP_GLOBAL_Control
0x140181f8a  mov     rcx, [rcx+40h]; int
0x140181f8e  call    WPP_RECORDER_SF_qZ
0x140181f93  call    ?ndisIfEnsureNsiInitialized@@YAJXZ; ndisIfEnsureNsiInitialized(void)
0x140181f98  movzx   eax, byte ptr [rsi+18h]
0x140181f9c  mov     dl, 2; enum _NDIS_MDRV_REFTAG
0x140181f9e  mov     rcx, rsi; struct _NDIS_M_DRIVER_BLOCK *
0x140181fa1  mov     [rsp+490h+var_43C], al
0x140181fa5  call    ?ndisReferenceDriver@@YAEPEAU_NDIS_M_DRIVER_BLOCK@@W4_NDIS_MDRV_REFTAG@@@Z; ndisReferenceDriver(_NDIS_M_DRIVER_BLOCK *,_NDIS_MDRV_REFTAG)
0x140181faa  test    al, al
0x140181fac  jz      loc_140184531
0x140181fb2  lea     rax, [rbp+390h+var_140]
0x140181fb9  mov     dword ptr [rbp+390h+DestinationString.Length], 1000000h
0x140181fc0  mov     dil, 1
0x140181fc3  mov     [rbp+390h+DestinationString.Buffer], rax
0x140181fc7  lea     rdx, ?ndisDosDevicesStr@@3U_UNICODE_STRING@@A; SourceString
0x140181fce  mov     [rsp+490h+var_433], dil
0x140181fd3  lea     rcx, [rbp+390h+DestinationString]; DestinationString
0x140181fd7  call    cs:__imp_RtlCopyUnicodeString
0x140181fde  nop     dword ptr [rax+rax+00h]
0x140181fe3  mov     rdx, [rsp+490h+FunctionContext]
0x140181fe8  lea     rcx, [rbp+390h+DestinationString]; Destination
0x140181fec  add     rdx, 0ED0h; Source
0x140181ff3  call    cs:__imp_RtlAppendUnicodeStringToString
0x140181ffa  nop     dword ptr [rax+rax+00h]
0x140181fff  test    eax, eax
0x140182001  js      loc_140182541
0x140182007  mov     rdx, [rsp+490h+FunctionContext]
0x14018200c  lea     rcx, [rbp+390h+DestinationString]; SymbolicLinkName
0x140182010  add     rdx, 1068h; DeviceName
0x140182017  call    cs:__imp_IoCreateSymbolicLink
0x14018201e  nop     dword ptr [rax+rax+00h]
0x140182023  mov     dword ptr [rsp+490h+var_430], eax
0x140182027  test    eax, eax
0x140182029  jns     short loc_140182036
0x14018202b  cmp     eax, 0C0000035h
0x140182030  setz    r13b
0x140182034  jmp     short loc_14018203A
0x140182036  movzx   r13d, dil
0x14018203a  cmp     [rsp+490h+var_43C], 6
0x14018203f  mov     r10, [rsp+490h+FunctionContext]
0x140182044  mov     rax, [rbp+390h+arg_20]
0x14018204b  mov     [r10+7B8h], rax
0x140182052  lea     rax, ?ndisMDummyIndicatePacket@@YAXPEAXPEAPEAU_NDIS_PACKET@@I@Z; ndisMDummyIndicatePacket(void *,_NDIS_PACKET * *,uint)
0x140182059  mov     [r10+1B0h], rax
0x140182060  mov     [r10+768h], rax
0x140182067  lea     rax, ?ndisMDispatchReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z; ndisMDispatchReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)
0x14018206e  mov     [r10+858h], rax
0x140182075  mov     [r10+860h], rax
0x14018207c  lea     rax, EthFilterDprIndicateReceive
0x140182083  mov     [r10+280h], rax
0x14018208a  lea     rax, EthFilterDprIndicateReceiveComplete
0x140182091  mov     [r10+298h], rax
0x140182098  lea     rax, NdisMSendComplete
0x14018209f  mov     [r10+1B8h], rax
0x1401820a6  lea     rax, NdisMSendNetBufferListsComplete
0x1401820ad  mov     [r10+2F0h], rax
0x1401820b4  lea     rax, NdisMTransferDataComplete
0x1401820bb  mov     [r10+2C0h], rax
0x1401820c2  lea     rax, NdisMResetComplete
0x1401820c9  mov     [r10+1C8h], rax
0x1401820d0  lea     rax, NdisMIndicateStatus
0x1401820d7  mov     [r10+2B0h], rax
0x1401820de  lea     rax, NdisQueryOffloadState
0x1401820e5  mov     [r10+2B8h], rax
0x1401820ec  lea     rax, NdisMSendResourcesAvailable
0x1401820f3  mov     [r10+1C0h], rax
0x1401820fa  lea     rax, NdisMQueryInformationComplete
0x140182101  mov     [r10+2C8h], rax
0x140182108  lea     rax, NdisMSetInformationComplete
0x14018210f  mov     [r10+2D0h], rax
0x140182116  lea     rax, ?ndisMWanSendCompleteInternal@@YAXPEAX0H@Z; ndisMWanSendCompleteInternal(void *,void *,int)
0x14018211d  mov     [r10+2D8h], rax
0x140182124  lea     rax, NdisMWanIndicateReceive
0x14018212b  mov     [r10+2E0h], rax
0x140182132  lea     rax, NdisMWanIndicateReceiveComplete
0x140182139  mov     [r10+2E8h], rax
0x140182140  lea     rax, ?ndisMSendCompleteNetBufferListsInternal@@YAXPEAXPEAU_NET_BUFFER_LIST@@K@Z; ndisMSendCompleteNetBufferListsInternal(void *,_NET_BUFFER_LIST *,ulong)
0x140182147  mov     [r10+980h], rax
0x14018214e  mov     [r10+0A38h], rax
0x140182155  mov     [r10+0A69h], dil
0x14018215c  mov     [r10+958h], r10
0x140182163  mov     qword ptr [r10+960h], 30h ; '0'
0x14018216e  mov     [r10+968h], r10
0x140182175  mov     [r10+0A10h], r10
0x14018217c  mov     qword ptr [r10+0A18h], 30h ; '0'
0x140182187  mov     [r10+0A20h], r10
0x14018218e  mov     [r10+970h], r10
0x140182195  mov     [r10+9A8h], r10
0x14018219c  mov     [r10+0A28h], r10
0x1401821a3  mov     [r10+0A60h], r10
0x1401821aa  mov     rax, ds:0FFFFF78000000014h
0x1401821b4  mov     [r10+11E0h], rax
0x1401821bb  jnb     loc_140182323
0x1401821c1  imul    edx, cs:?ndisMaxNumberOfProcessors@@3KA, 70h ; 'p'; ulong ndisMaxNumberOfProcessors
0x1401821c8  mov     ecx, 40h ; '@'
0x1401821cd  mov     r8d, 2020444Eh
0x1401821d3  call    cs:__imp_ExAllocatePool2
0x1401821da  nop     dword ptr [rax+rax+00h]
0x1401821df  mov     r10, [rsp+490h+FunctionContext]
0x1401821e4  mov     [r10+0C50h], rax
0x1401821eb  test    rax, rax
0x1401821ee  jz      loc_140182546
0x1401821f4  mov     rdx, [r10+0EB0h]
0x1401821fb  lea     rax, ?ndisMDeferredSend@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMDeferredSend(_NDIS_MINIPORT_BLOCK *)
0x140182202  movzx   ecx, [rsp+490h+var_43C]
0x140182207  mov     [r10+278h], rax
0x14018220e  mov     rax, [rdx+80h]
0x140182215  mov     [r10+260h], rax
0x14018221c  mov     rax, [rdx+88h]
0x140182223  mov     [r10+268h], rax
0x14018222a  lea     rax, ?ndisReturnNetBufferListsToPackets@@YAXPEAXPEAU_NET_BUFFER_LIST@@K@Z; ndisReturnNetBufferListsToPackets(void *,_NET_BUFFER_LIST *,ulong)
0x140182231  mov     [r10+998h], rax
0x140182238  mov     [r10+928h], r10
0x14018223f  mov     qword ptr [r10+930h], 40h ; '@'
0x14018224a  mov     [r10+938h], r10
0x140182251  mov     rax, [rdx+0C8h]
0x140182258  mov     [r10+0FE8h], rax
0x14018225f  cmp     cl, 4
0x140182262  jb      loc_140182315
0x140182268  cmp     qword ptr [rsi+0E0h], 0
0x140182270  jz      short loc_14018227A
0x140182272  or      dword ptr [r10+750h], 10h
0x14018227a  mov     rax, [rdx+0E0h]
0x140182281  mov     [r10+880h], rax
0x140182288  mov     rax, [rdx+0E0h]
0x14018228f  mov     [r10+870h], rax
0x140182296  mov     rax, [r10+18h]
0x14018229a  mov     [r10+888h], rax
0x1401822a1  cmp     qword ptr [rsi+0E8h], 0
0x1401822a9  jz      short loc_1401822D9
0x1401822ab  or      [r10+3A0h], dil
0x1401822b2  lea     rax, ?ndisMDeferredSendPackets@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMDeferredSendPackets(_NDIS_MINIPORT_BLOCK *)
0x1401822b9  mov     [r10+278h], rax
0x1401822c0  mov     rax, [rsi+0E8h]
0x1401822c7  or      dword ptr [r10+750h], 8000000h
0x1401822d2  mov     [r10+710h], rax
0x1401822d9  cmp     cl, 5
0x1401822dc  jb      short loc_140182315
0x1401822de  or      dword ptr [r10+750h], 200h
0x1401822e9  cmp     qword ptr [rsi+118h], 0
0x1401822f1  jz      short loc_140182315
0x1401822f3  mov     edx, 20000h; unsigned int
0x1401822f8  mov     rcx, r10; struct _NDIS_MINIPORT_BLOCK *
0x1401822fb  call    ?MINIPORT_SET_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_SET_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x140182300  lea     rax, ?ndisMCoOidRequestToRequest@@YAHPEAX0PEAU_NDIS_OID_REQUEST@@@Z; ndisMCoOidRequestToRequest(void *,void *,_NDIS_OID_REQUEST *)
0x140182307  mov     [rsi+228h], rax
0x14018230e  mov     [r10+8B8h], r10
0x140182315  lea     rax, [r10+0FF0h]
0x14018231c  mov     [rsp+490h+ConfigurationHandle], rax
0x140182321  jmp     short loc_14018239A
0x140182323  mov     rax, [r10+0EB0h]
0x14018232a  mov     [r10+7CAh], dil
0x140182331  mov     rcx, [rax+0C0h]
0x140182338  mov     rax, [r10+18h]
0x14018233c  mov     [r10+928h], rax
0x140182343  mov     [r10+998h], rcx
0x14018234a  lea     rcx, [r10+0FF0h]
0x140182351  mov     rax, [rcx]
0x140182354  mov     [r10+930h], rax
0x14018235b  lea     rax, ?ndisSynchReturnPacketsForTranslation@@YAXPEAXPEAU_NDIS_PACKET@@@Z; ndisSynchReturnPacketsForTranslation(void *,_NDIS_PACKET *)
0x140182362  mov     [r10+880h], rax
0x140182369  mov     [r10+938h], r10
0x140182370  mov     [r10+888h], r10
0x140182377  cmp     qword ptr [rsi+218h], 0
0x14018237f  mov     [rsp+490h+ConfigurationHandle], rcx
0x140182384  jz      short loc_140182395
0x140182386  mov     edx, 20000h; unsigned int
0x14018238b  mov     rcx, r10; struct _NDIS_MINIPORT_BLOCK *
0x14018238e  call    ?MINIPORT_SET_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_SET_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x140182393  jmp     short loc_14018239A
0x140182395  mov     [rsp+490h+ConfigurationHandle], rcx
0x14018239a  mov     dl, 18h; enum _NDIS_MP_REFTAG
0x14018239c  mov     rcx, r10; struct _NDIS_MINIPORT_BLOCK *
0x14018239f  call    ?ndisReferenceMiniportNoCheck@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniportNoCheck(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x1401823a4  mov     rax, [rsp+490h+FunctionContext]
0x1401823a9  movzx   ebx, dil
0x1401823ad  mov     [rsp+490h+var_434], bl
0x1401823b1  cmp     dword ptr [rax+0F1Ch], 0
0x1401823b8  jnz     short loc_1401823CE
0x1401823ba  mov     dword ptr [rax+0F1Ch], 1
0x1401823c4  mov     dword ptr [rax+0F28h], 1
0x1401823ce  mov     rcx, rax; struct _NDIS_MINIPORT_BLOCK *
0x1401823d1  call    ?ndisQueryPowerCapabilities@@YAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisQueryPowerCapabilities(_NDIS_MINIPORT_BLOCK *)
0x1401823d6  mov     rcx, [rsp+490h+FunctionContext]; FunctionContext
0x1401823db  call    ?ndisMInitializeInitMode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMInitializeInitMode(_NDIS_MINIPORT_BLOCK *)
0x1401823e0  mov     rax, [rsp+490h+FunctionContext]
0x1401823e5  xor     ecx, ecx
0x1401823e7  mov     rdx, rax
0x1401823ea  mov     r8, [rax+0F10h]
0x1401823f1  call    NdisNblTrackerRegisterComponent
0x1401823f6  mov     rcx, [rsp+490h+ConfigurationHandle]
0x1401823fb  mov     [rcx], rax
0x1401823fe  mov     ecx, 527374h; unsigned int
0x140182403  call    ?ndisAllocatePerProcessorSlot@@YAPEAUPNDIS_PER_PROCESSOR_SLOT__@@K@Z; ndisAllocatePerProcessorSlot(ulong)
0x140182408  mov     r10, [rsp+490h+FunctionContext]
0x14018240d  mov     [r10+0CE0h], rax
0x140182414  test    rax, rax
0x140182417  jz      loc_140182546
0x14018241d  xor     edx, edx
0x14018241f  movzx   r15d, bl
0x140182423  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, edx; ulong ndisMaxNumberOfProcessors
0x140182429  jbe     short loc_140182448
0x14018242b  mov     rax, [r10+0CE0h]
0x140182432  mov     ecx, edx
0x140182434  shl     ecx, 0Ch
0x140182437  inc     edx
0x140182439  mov     dword ptr [rcx+rax], 6
0x140182440  cmp     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140182446  jb      short loc_14018242B
0x140182448  mov     edx, 20000002h; unsigned int
0x14018244d  mov     rcx, r10; struct _NDIS_MINIPORT_BLOCK *
0x140182450  call    ?MINIPORT_SET_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_SET_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x140182455  mov     edx, 1; unsigned int
0x14018245a  call    ?MINIPORT_CLEAR_FLAG@@YAXPEAU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_CLEAR_FLAG(_NDIS_MINIPORT_BLOCK *,ulong)
0x14018245f  test    byte ptr [rsi+1Ah], 2
0x140182463  jz      short loc_140182493
0x140182465  or      dword ptr [r10+7Ch], 100000h
0x14018246d  cmp     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, 0; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x140182475  jz      short loc_140182488
0x140182477  cmp     cs:?ndisMiniportTrackAlloc@@3PEAU_NDIS_MINIPORT_BLOCK@@EA, 0; _NDIS_MINIPORT_BLOCK * ndisMiniportTrackAlloc
0x14018247f  mov     cs:?ndisMiniportTrackAlloc@@3PEAU_NDIS_MINIPORT_BLOCK@@EA, r10; _NDIS_MINIPORT_BLOCK * ndisMiniportTrackAlloc
0x140182486  jz      short loc_140182493
0x140182488  mov     cs:?ndisMiniportTrackAlloc@@3PEAU_NDIS_MINIPORT_BLOCK@@EA, 0; _NDIS_MINIPORT_BLOCK * ndisMiniportTrackAlloc
0x140182493  mov     eax, cs:?ndisDatapathVerifierMode@@3W4NDIS_DATAPATH_VERIFIER_MODE@@A; NDIS_DATAPATH_VERIFIER_MODE ndisDatapathVerifierMode
0x140182499  sub     eax, 1
0x14018249c  jz      short loc_1401824A5
0x14018249e  cmp     eax, 1
0x1401824a1  jz      short loc_1401824AF
0x1401824a3  jmp     short loc_1401824BA
0x1401824a5  test    dword ptr [r10+7Ch], 100000h
0x1401824ad  jz      short loc_1401824BA
  ... truncated ...
```
