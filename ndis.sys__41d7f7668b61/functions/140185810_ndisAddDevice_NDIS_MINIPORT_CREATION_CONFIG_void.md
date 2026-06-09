# ndisAddDevice(NDIS_MINIPORT_CREATION_CONFIG *,void * *)

- ea: `0x140185810`
- end: `0x140186f10`
- name: `?ndisAddDevice@@_Y2PAGENPNP@@AJPEAUNDIS_MINIPORT_CREATION_CONFIG@@PEAPEAX@Z`
- size: `5888`
- prototype: `__int64 __fastcall(struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `60`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140059dc0`
- `0x140168600`

## callees

- `0x1400013f4`
- `0x140009070`
- `0x14000dbe0`
- `0x1400100f0`
- `0x1400110b0`
- `0x140011190`
- `0x14003dec0`
- `0x1400400d0`
- `0x14004bae0`
- `0x14004ce90`
- `0x140053280`
- `0x140054500`
- `0x14005d540`
- `0x14005d590`
- `0x140063390`
- `0x14006c610`
- `0x14006f780`
- `0x1400719b0`
- `0x140074d10`
- `0x140078fa0`
- `0x14007a390`
- `0x14007cad0`
- `0x14007f7c0`
- `0x140080210`
- `0x1400808f0`
- `0x140083450`
- `0x140085a60`
- `0x140088a40`
- `0x14008ac90`
- `0x140092948`
- `0x140092cd0`
- `0x140092d28`
- `0x140092d80`
- `0x14009db0c`
- `0x14009eac0`
- `0x1400b0d0c`
- `0x1400b0de0`
- `0x1400b2b40`
- `0x1400cf9b8`
- `0x1400eb380`
- `0x1400eb460`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x140140050`
- `0x140140b5c`
- `0x1401434f0`
- `0x1401531e4`
- `0x14015dae0`
- `0x14015ed60`
- `0x14016aae0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401859e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14018618e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401859e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14018618e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140185a2d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140185a2d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140186c32`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140186c32`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140185a09`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140185a09`
- `ntoskrnl!MmIsDriverVerifying` at `0x140186084`
- `ntoskrnl!MmIsDriverVerifying` at `0x140186084`
- `ntoskrnl!IoCreateDevice` at `0x140185bc7`
- `ntoskrnl!IoCreateDevice` at `0x140185bc7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140186463`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14018652a`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140186463`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14018652a`
- `ntoskrnl!IoDeleteDevice` at `0x140186d6f`
- `ntoskrnl!IoDeleteDevice` at `0x140186d6f`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140186c57`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140186ce0`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140186c57`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140186ce0`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140185c0f`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140185c0f`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14018624e`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14018624e`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140186319`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140186319`
- `ntoskrnl!IoDetachDevice` at `0x140186d5e`
- `ntoskrnl!IoDetachDevice` at `0x140186d5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140185b52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140185b88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186385`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186704`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140185b52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140185b88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186385`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186704`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186ddb`
- `ntoskrnl!ExAllocatePool2` at `0x140185a6a`
- `ntoskrnl!ExAllocatePool2` at `0x140186149`
- `ntoskrnl!ExAllocatePool2` at `0x140185a6a`
- `ntoskrnl!ExAllocatePool2` at `0x140186149`
- `ntoskrnl!KeReleaseSpinLock` at `0x140185968`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186945`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186b34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186b56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186e19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140185968`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186945`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186b34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186b56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140186e19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140185933`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140186905`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140186dee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140185933`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140186905`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140186dee`

## string_xrefs

- `0x140185d50`: `WorkerThreadPriority`
- `0x140185d74`: `MaxPacketsSendCompleteAtPassive`
- `0x140185cd3`: `MaxPacketsReceiveCompleteAtPassive`
- `0x140185ee3`: `MaxPacketsSendCompleteAtDispatch`
- `0x140185f36`: `MaxPacketsReceiveCompleteAtDispatch`

## pseudocode

```c
__int64 __fastcall ndisAddDevice(struct _GUID *a1, void **a2)
{
  struct _DEVICE_OBJECT *v2; // r12
  struct _NDIS_MINIPORT_BLOCK *DeviceExtension; // rbx
  struct _NDIS_IF_BLOCK *v4; // r15
  struct _DEVICE_OBJECT *v6; // rax
  const ULONG *v7; // rdx
  __int64 v8; // r13
  unsigned int v9; // esi
  NTSTATUS appended; // edi
  KIRQL v11; // al
  struct _NDIS_M_DRIVER_BLOCK *i; // rdi
  int v13; // r12d
  __int16 v14; // ax
  unsigned int v15; // r12d
  struct _NDIS_MINIPORT_BLOCK *Pool2; // rax
  __int64 (__fastcall **v17)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v18; // rcx
  struct _DEVICE_OBJECT *v19; // rax
  __int64 v20; // rcx
  struct _DEVICE_OBJECT *v21; // rax
  NdisWdfIdle *v22; // r12
  PVOID v23; // rcx
  NdisWdfIdle *value; // rdi
  PDEVICE_OBJECT v25; // rdx
  __int64 EventLog; // rax
  _GUID InterfaceGuid; // xmm0
  __int64 m_numElements; // rax
  __int64 v29; // rax
  unsigned __int8 (*v30)(void *, const struct KnobDescriptor *, unsigned __int64 *); // r9
  unsigned int v31; // eax
  LOGICAL IsDriverVerifying; // eax
  int v33; // edx
  _UNICODE_STRING *p_BaseName; // rdi
  __int64 v35; // rax
  __int64 v36; // rax
  const struct _DEVPROPKEY *v37; // rdx
  int DevicePropertyData; // edi
  char No; // al
  struct _UNICODE_STRING *v40; // r8
  int v41; // edx
  int v42; // ecx
  int v43; // edx
  PVOID v44; // rcx
  int v45; // edx
  __int16 v46; // ax
  struct _UNICODE_STRING *p_DriverObject; // rdx
  struct _UNICODE_STRING *p_FdoName; // rsi
  int v49; // edx
  int v50; // ecx
  int v51; // edx
  __int64 v52; // rcx
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // r8
  Rtl::KString *v56; // rax
  Rtl::KString *v57; // rcx
  unsigned int v58; // eax
  int v59; // edx
  unsigned int v60; // eax
  _NDIS_BIND_PATHS *BindPaths; // rax
  char v62; // r13
  struct _NDIS_IF_BLOCK *InterfaceByInterfaceGuid; // rax
  KIRQL v64; // r8
  __int64 v65; // rcx
  _NDIS_MEDIUM MediaType; // eax
  _NDIS_M_DRIVER_BLOCK *DriverHandle; // rax
  _UNICODE_STRING ImageName; // xmm0
  _UNICODE_STRING *pAdapterInstanceName; // rax
  _UNICODE_STRING v70; // xmm1
  __int64 v71; // rax
  unsigned int updated; // eax
  int v73; // edx
  enum Ndis::ReadBindingsOptions::Flags v74; // r8d
  NTSTATUS v75; // eax
  int v76; // edx
  struct _UNICODE_STRING *v77; // rcx
  NTSTATUS v78; // eax
  int v79; // edx
  Rtl::KString *v80; // rax
  Rtl::KString *v81; // rcx
  KIRQL v82; // al
  int v83; // edx
  int v84; // edx
  signed __int32 v86[8]; // [rsp+0h] [rbp-100h] BYREF
  ULONG DeviceCharacteristics[2]; // [rsp+20h] [rbp-E0h]
  BOOLEAN Exclusive[8]; // [rsp+28h] [rbp-D8h]
  char v89; // [rsp+40h] [rbp-C0h]
  PDEVICE_OBJECT v90; // [rsp+48h] [rbp-B8h]
  char v91; // [rsp+50h] [rbp-B0h]
  char v92; // [rsp+51h] [rbp-AFh]
  char v93; // [rsp+52h] [rbp-AEh]
  char v94; // [rsp+53h] [rbp-ADh]
  char v95; // [rsp+54h] [rbp-ACh]
  unsigned __int8 v96; // [rsp+55h] [rbp-ABh]
  char v97; // [rsp+56h] [rbp-AAh]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DriverObject; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  PDEVICE_OBJECT TargetDevice; // [rsp+88h] [rbp-78h]
  struct _NDIS_MINIPORT_BLOCK *v103; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING String; // [rsp+98h] [rbp-68h] BYREF
  struct _CONFIG_KNOB_NAMESPACE v105; // [rsp+A8h] [rbp-58h] BYREF
  void **v106; // [rsp+C0h] [rbp-40h]
  _OWORD Src[10]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v108; // [rsp+170h] [rbp+70h]
  int v109; // [rsp+178h] [rbp+78h]
  __int64 v110; // [rsp+180h] [rbp+80h]
  __int64 v111; // [rsp+188h] [rbp+88h]
  const wchar_t *v112; // [rsp+190h] [rbp+90h]
  unsigned int *p_DpcWatchdogTimerThreshold; // [rsp+198h] [rbp+98h]
  __int64 v114; // [rsp+1A0h] [rbp+A0h]
  int v115; // [rsp+1A8h] [rbp+A8h]
  __int64 v116; // [rsp+1B0h] [rbp+B0h]
  __int64 v117; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v118; // [rsp+1C0h] [rbp+C0h]
  unsigned int *p_WorkerThreadPriority; // [rsp+1C8h] [rbp+C8h]
  __int64 v120; // [rsp+1D0h] [rbp+D0h]
  int v121; // [rsp+1D8h] [rbp+D8h]
  __int64 v122; // [rsp+1E0h] [rbp+E0h]
  __int64 v123; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v124; // [rsp+1F0h] [rbp+F0h]
  _EXECUTION_CONTEXT_WORK_UNIT_KNOBS *p_MaxPacketsSend; // [rsp+1F8h] [rbp+F8h]
  __int64 v126; // [rsp+200h] [rbp+100h]
  int v127; // [rsp+208h] [rbp+108h]
  __int128 v128; // [rsp+210h] [rbp+110h]
  const wchar_t *v129; // [rsp+220h] [rbp+120h]
  _EXECUTION_CONTEXT_WORK_UNIT_KNOBS *p_MaxPacketsSendComplete; // [rsp+228h] [rbp+128h]
  __int64 v131; // [rsp+230h] [rbp+130h]
  int v132; // [rsp+238h] [rbp+138h]
  __int128 v133; // [rsp+240h] [rbp+140h]
  const wchar_t *v134; // [rsp+250h] [rbp+150h]
  _EXECUTION_CONTEXT_WORK_UNIT_KNOBS *p_MaxPacketsReceive; // [rsp+258h] [rbp+158h]
  __int64 v136; // [rsp+260h] [rbp+160h]
  int v137; // [rsp+268h] [rbp+168h]
  __int128 v138; // [rsp+270h] [rbp+170h]
  const wchar_t *v139; // [rsp+280h] [rbp+180h]
  _EXECUTION_CONTEXT_WORK_UNIT_KNOBS *p_MaxPacketsReceiveComplete; // [rsp+288h] [rbp+188h]
  __int64 v141; // [rsp+290h] [rbp+190h]
  int v142; // [rsp+298h] [rbp+198h]
  __int128 v143; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v144; // [rsp+2B0h] [rbp+1B0h]
  unsigned int *p_AtDispatch; // [rsp+2B8h] [rbp+1B8h]
  __int64 v146; // [rsp+2C0h] [rbp+1C0h]
  int v147; // [rsp+2C8h] [rbp+1C8h]
  __int128 v148; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v149; // [rsp+2E0h] [rbp+1E0h]
  unsigned int *v150; // [rsp+2E8h] [rbp+1E8h]
  __int64 v151; // [rsp+2F0h] [rbp+1F0h]
  int v152; // [rsp+2F8h] [rbp+1F8h]
  __int128 v153; // [rsp+300h] [rbp+200h]
  const wchar_t *v154; // [rsp+310h] [rbp+210h]
  unsigned int *v155; // [rsp+318h] [rbp+218h]
  __int64 v156; // [rsp+320h] [rbp+220h]
  int v157; // [rsp+328h] [rbp+228h]
  __int128 v158; // [rsp+330h] [rbp+230h]
  const wchar_t *v159; // [rsp+340h] [rbp+240h]
  unsigned int *v160; // [rsp+348h] [rbp+248h]
  __int64 v161; // [rsp+350h] [rbp+250h]
  int v162; // [rsp+358h] [rbp+258h]
  __int128 v163; // [rsp+360h] [rbp+260h]
  char v164; // [rsp+370h] [rbp+270h] BYREF
  char v165; // [rsp+398h] [rbp+298h] BYREF

  v2 = 0;
  v106 = a2;
  DeviceExtension = 0;
  v90 = 0;
  v4 = 0;
  SourceDevice = 0;
  v89 = 0;
  v91 = 0;
  v95 = 0;
  v93 = 0;
  v92 = 0;
  v94 = 0;
  v97 = 0;
  v96 = 0;
  v6 = *(struct _DEVICE_OBJECT **)&a1[2].Data1;
  TargetDevice = v6;
  v7 = &WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)v7,
      13,
      68,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)v6);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  v8 = *(_QWORD *)&a1[6].Data1;
  if ( a1[5].Data4[1] != *(_BYTE *)(v8 + 26) >> 7 )
    NT_ASSERT("Parameters->IsLightWeight == ((Parameters->MiniBlock->Flags & 0x0080) != 0)");
  if ( !v8 )
  {
    v9 = 1;
    appended = -1073741670;
LABEL_172:
    v62 = 0;
    goto LABEL_173;
  }
  if ( (unsigned int)Feature_NDPQualitySpring26__private_IsEnabledDeviceUsageNoInline() )
    v96 = (*(_BYTE *)(v8 + 26) & 0x40) != 0;
  *(_QWORD *)&DriverObject.Length = *(_QWORD *)(*(_QWORD *)&a1[6].Data1 + 40LL);
  v11 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
  for ( i = ndisMiniDriverList; i; i = i->NextDriver )
  {
    if ( i == (struct _NDIS_M_DRIVER_BLOCK *)v8 )
      break;
  }
  KeReleaseSpinLock(&ndisMiniDriverListLock, v11);
  if ( i != (struct _NDIS_M_DRIVER_BLOCK *)v8 )
  {
    appended = -1073741823;
    v9 = 2;
    goto LABEL_172;
  }
  if ( *(_BYTE *)(v8 + 24) >= 6u && !a1[2].Data4[0] )
  {
    v9 = 3;
    appended = -1073741491;
    goto LABEL_172;
  }
  v13 = **(unsigned __int16 **)a1[3].Data4;
  *(_QWORD *)&String.Length = 2621440;
  *(_QWORD *)&DestinationString.Length = 3932160;
  LODWORD(P) = 8 * ndisMaxNumberOfProcessors;
  String.Buffer = (wchar_t *)&v164;
  DestinationString.Buffer = (wchar_t *)&v165;
  RtlCopyUnicodeString(&DestinationString, &ndisFdoDeviceStr);
  appended = RtlIntegerToUnicodeString(_InterlockedIncrement((volatile signed __int32 *)&ndisFdoIndex), 0xAu, &String);
  v9 = 4;
  if ( appended )
    goto LABEL_171;
  appended = RtlAppendUnicodeStringToString(&DestinationString, &String);
  if ( appended )
    goto LABEL_171;
  v14 = *(_WORD *)(v8 + 26);
  v15 = (_DWORD)P + ((v13 + 6139) & 0xFFFFFFF8);
  if ( (v14 & 0x80u) != 0 )
  {
    Pool2 = (struct _NDIS_MINIPORT_BLOCK *)ExAllocatePool2(66, (int)v15, 2003584078);
    DeviceExtension = Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
      v2 = 0;
      goto LABEL_172;
    }
    ndisMInitializeMiniportBlock((struct _NDIS_M_DRIVER_BLOCK *)v8, Pool2, v15);
    _InterlockedOr((volatile signed __int32 *)&DeviceExtension->Flags, 0x100u);
    goto LABEL_37;
  }
  if ( (v14 & 0x40) == 0 )
  {
    appended = IoCreateDevice(
                 *(PDRIVER_OBJECT *)&DriverObject.Length,
                 v15,
                 &DestinationString,
                 0x17u,
                 0x100u,
                 0,
                 &SourceDevice);
    if ( appended >= 0 )
    {
      v9 = 6;
      v25 = TargetDevice;
      v95 = 1;
      SourceDevice->Flags |= 0x10u;
      v25->Flags &= ~0x80u;
      SourceDevice->Flags |= 0x2000u;
      v90 = IoAttachDeviceToDeviceStack(SourceDevice, v25);
      if ( !v90 )
      {
        appended = -1073741823;
        v2 = 0;
        goto LABEL_172;
      }
      DeviceExtension = (struct _NDIS_MINIPORT_BLOCK *)SourceDevice->DeviceExtension;
      ndisMInitializeMiniportBlock((struct _NDIS_M_DRIVER_BLOCK *)v8, DeviceExtension, v15);
      goto LABEL_37;
    }
    v9 = 5;
LABEL_171:
    v2 = 0;
    goto LABEL_172;
  }
  v17 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v8 + 360);
  v18 = *(_QWORD *)&a1[5].Data1;
  v103 = 0;
  P = v17;
  appended = ((__int64 (__fastcall **)(__int64, _QWORD, struct _NDIS_MINIPORT_BLOCK **))v17)[13](v18, v15, &v103);
  if ( appended )
    goto LABEL_171;
  v19 = (struct _DEVICE_OBJECT *)(*((__int64 (__fastcall **)(_QWORD))P + 8))(*(_QWORD *)&a1[5].Data1);
  v20 = *(_QWORD *)&a1[5].Data1;
  SourceDevice = v19;
  v21 = (struct _DEVICE_OBJECT *)(*((__int64 (__fastcall **)(__int64))P + 9))(v20);
  DeviceExtension = v103;
  v90 = v21;
  ndisMInitializeMiniportBlock((struct _NDIS_M_DRIVER_BLOCK *)v8, v103, v15);
  MakePoolPtrNP<NdisWdfIdle>(&P);
  v22 = (NdisWdfIdle *)P;
  if ( !P )
  {
LABEL_42:
    v2 = v90;
    appended = -1073741670;
    goto LABEL_172;
  }
  appended = NdisWdfIdle::Initialize(P, DeviceExtension);
  if ( appended )
  {
    if ( !v22 )
    {
LABEL_29:
      v2 = v90;
      goto LABEL_172;
    }
    NdisWdfIdle::~NdisWdfIdle(v22);
    v23 = v22;
LABEL_28:
    ExFreePoolWithTag(v23, 0);
    goto LABEL_29;
  }
  value = DeviceExtension->IdleSm.__ptr_.__value_;
  DeviceExtension->IdleSm.__ptr_.__value_ = v22;
  if ( value )
  {
    NdisWdfIdle::~NdisWdfIdle(value);
    ExFreePoolWithTag(value, 0);
  }
  DeviceExtension->MiniportAdapterContext = *(void **)&a1[5].Data1;
LABEL_37:
  if ( (*(_BYTE *)(v8 + 26) & 0x40) != 0 )
    _InterlockedOr((volatile signed __int32 *)&DeviceExtension->Flags, 0x80u);
  DeviceExtension->InterfaceGuid = *a1;
  EventLog = ndisAllocateEventLog(2, 1);
  InterfaceGuid = DeviceExtension->InterfaceGuid;
  DeviceExtension->PnpEventLog = (NDIS_EVENT_LOG_HANDLE__ *)EventLog;
  v105.NamespaceType = ConfigKnobNamespaceNetworkInterfaceProfile;
  v105.ObjectId = InterfaceGuid;
  if ( DeviceExtension != (struct _NDIS_MINIPORT_BLOCK *)-5920LL )
    KnobNamespace::KnobNamespace(
      &DeviceExtension->PollModeConfigKnobsNamespace,
      (struct _DRIVER_OBJECT *)ndisDriverObject,
      &v105);
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.MaxTimeAtDispatch = 0;
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.DispatchTimeWarningInterval = 0;
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.WorkerThreadPriority = 0;
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.MaxPacketsSend.AtDispatch = 0;
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.MaxPacketsSendComplete.AtDispatch = 0;
  *(_QWORD *)&DeviceExtension->PollModeConfigKnobs.MaxPacketsReceive.AtDispatch = 0;
  DeviceExtension->PollModeConfigKnobs.MaxPacketsReceiveComplete.AtDispatch = 0;
  DeviceExtension->PollModeConfigKnobs.Flags = ExecutionContextFlagNone;
  *((_QWORD *)&Src[0] + 1) = &DeviceExtension->PollModeConfigKnobs.Flags;
  *(_QWORD *)&Src[3] = L"MaxTimeAtDispatch";
  *((_QWORD *)&Src[3] + 1) = &DeviceExtension->PollModeConfigKnobs.MaxTimeAtDispatch;
  *(_QWORD *)&Src[6] = L"DispatchTimeWarning";
  *((_QWORD *)&Src[6] + 1) = &DeviceExtension->PollModeConfigKnobs.DispatchTimeWarning;
  *(_QWORD *)&Src[9] = L"DispatchTimeWarningInterval";
  *((_QWORD *)&Src[9] + 1) = &DeviceExtension->PollModeConfigKnobs.DispatchTimeWarningInterval;
  v112 = L"DpcWatchdogTimerThreshold";
  p_DpcWatchdogTimerThreshold = &DeviceExtension->PollModeConfigKnobs.DpcWatchdogTimerThreshold;
  v118 = L"WorkerThreadPriority";
  p_WorkerThreadPriority = &DeviceExtension->PollModeConfigKnobs.WorkerThreadPriority;
  *(_QWORD *)&Src[0] = L"Flags";
  *(_QWORD *)&Src[4] = 0;
  *(_QWORD *)&Src[7] = 0;
  v124 = L"MaxPacketsSendAtPassive";
  v129 = L"MaxPacketsSendCompleteAtPassive";
  v134 = L"MaxPacketsReceiveAtPassive";
  DeviceExtension->PollModeConfigKnobs.Size = 60;
  p_MaxPacketsSend = &DeviceExtension->PollModeConfigKnobs.MaxPacketsSend;
  *(_QWORD *)&Src[1] = 1;
  DWORD2(Src[1]) = 32;
  Src[2] = 0;
  DWORD2(Src[4]) = 32;
  Src[5] = 0;
  DWORD2(Src[7]) = 32;
  Src[8] = 0;
  v108 = 900000;
  v109 = 32;
  v110 = 60000;
  v111 = 1440000;
  v114 = 80;
  v115 = 32;
  v116 = 1;
  v117 = 80;
  v120 = 10;
  v121 = 32;
  v122 = 1;
  v123 = 15;
  v126 = 64;
  v127 = 32;
  v128 = 0;
  p_MaxPacketsSendComplete = &DeviceExtension->PollModeConfigKnobs.MaxPacketsSendComplete;
  v131 = 64;
  v132 = 32;
  v133 = 0;
  p_MaxPacketsReceive = &DeviceExtension->PollModeConfigKnobs.MaxPacketsReceive;
  v136 = 64;
  v137 = 32;
  v138 = 0;
  v139 = L"MaxPacketsReceiveCompleteAtPassive";
  p_MaxPacketsReceiveComplete = &DeviceExtension->PollModeConfigKnobs.MaxPacketsReceiveComplete;
  p_AtDispatch = &DeviceExtension->PollModeConfigKnobs.MaxPacketsSend.AtDispatch;
  v141 = 64;
  v149 = L"MaxPacketsSendCompleteAtDispatch";
  v150 = &DeviceExtension->PollModeConfigKnobs.MaxPacketsSendComplete.AtDispatch;
  v142 = 32;
  v154 = L"MaxPacketsReceiveAtDispatch";
  v155 = &DeviceExtension->PollModeConfigKnobs.MaxPacketsReceive.AtDispatch;
  v144 = L"MaxPacketsSendAtDispatch";
  v159 = L"MaxPacketsReceiveCompleteAtDispatch";
  v160 = &DeviceExtension->PollModeConfigKnobs.MaxPacketsReceiveComplete.AtDispatch;
  v143 = 0;
  v146 = 64;
  v147 = 32;
  v148 = 0;
  v151 = 64;
  v152 = 32;
  v153 = 0;
  v156 = 64;
  v157 = 32;
  v158 = 0;
  v161 = 64;
  v162 = 32;
  v163 = 0;
  if ( !(unsigned __int8)Rtl::KArray<KnobDescriptor,1>::reserve(&DeviceExtension->PollModeConfigKnobDescriptors, 14) )
    goto LABEL_42;
  m_numElements = DeviceExtension->PollModeConfigKnobDescriptors.m_numElements;
  if ( (unsigned int)m_numElements < 0xE )
    memset(&DeviceExtension->PollModeConfigKnobDescriptors._p[m_numElements], 0, 672 - 48 * m_numElements);
  DeviceExtension->PollModeConfigKnobDescriptors.m_numElements = 14;
  v29 = DeviceExtension->PollModeConfigKnobDescriptors.m_numElements;
  if ( !(_DWORD)v29
    || (memmove(DeviceExtension->PollModeConfigKnobDescriptors._p, Src, 48 * v29),
        (v31 = DeviceExtension->PollModeConfigKnobDescriptors.m_numElements) == 0) )
  {
    __fastfail(5u);
  }
  KnobNamespace::AddKnobCollection(
    &DeviceExtension->PollModeConfigKnobsNamespace,
    DeviceExtension->PollModeConfigKnobDescriptors._p,
    v31,
    v30,
    0,
    *(void **)Exclusive);
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) != 0 )
    IsDriverVerifying = (*(unsigned __int16 *)(v8 + 26) >> 1) & 1;
  else
    IsDriverVerifying = MmIsDriverVerifying(*(struct _DRIVER_OBJECT **)&DriverObject.Length);
  if ( ndisVerifierNdisDispatch )
  {
    if ( IsDriverVerifying )
    {
      v9 = 1;
      appended = (*((__int64 (__fastcall **)(PDEVICE_OBJECT, struct _NDIS_MINIPORT_BLOCK *, void **, void **))ndisVerifierNdisDispatch
                  + 1))(
                   SourceDevice,
                   DeviceExtension,
                   &DeviceExtension->MiniportAdapterContext,
                   &DeviceExtension->VerifierContext);
      if ( appended < 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v33) = 2;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v33,
            13,
            69,
            (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
            (char)DeviceExtension);
          v2 = v90;
          goto LABEL_172;
        }
        goto LABEL_29;
      }
    }
  }
  p_BaseName = &DeviceExtension->BaseName;
  ndisSetDeviceNames(
    *(PCUNICODE_STRING *)a1[3].Data4,
    &DeviceExtension->MiniportName,
    &DeviceExtension->BaseName,
    &DeviceExtension[1].Header.Type);
  v35 = ExAllocatePool2(66, DestinationString.Length + 2LL, 1851868238);
  DeviceExtension->FdoName.Buffer = (wchar_t *)v35;
  if ( !v35 )
  {
    v2 = v90;
    v9 = 1;
    appended = -1073741670;
    goto LABEL_172;
  }
  DeviceExtension->FdoName.MaximumLength = DestinationString.Length + 2;
  RtlCopyUnicodeString(&DeviceExtension->FdoName, &DestinationString);
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    DeviceExtension->PhysicalDeviceObject = TargetDevice;
    DeviceExtension->DeviceObject = SourceDevice;
    DeviceExtension->NextDeviceObject = v90;
    P = 0;
    v36 = wil::out_param<wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>>(&v105, &P);
    DevicePropertyData = ndisMiniportQueryDevicePropertyData(DeviceExtension, v37, (wchar_t **)(v36 + 8));
    if ( v105.ObjectId.Data4[4] )
      wil::attach_to_smart_pointer<wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>,void>(
        *(_QWORD *)&v105.NamespaceType,
        *(_QWORD *)&v105.ObjectId.Data2);
    if ( !DevicePropertyData )
    {
      DeviceExtension->PnPInstanceId = (wchar_t *)P;
      P = 0;
    }
    No = mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags);
    v40 = 0;
    if ( No < 0 )
      v40 = &DeviceExtension->BaseName;
    v9 = 8;
    appended = IoRegisterDeviceInterface(
                 DeviceExtension->PhysicalDeviceObject,
                 &GUID_DEVINTERFACE_NET,
                 v40,
                 &DeviceExtension->DevinterfaceNetSymbolicLinkName);
    if ( appended < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v41) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v41,
          13,
          70,
          (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
          (char)DeviceExtension);
      }
      if ( (Microsoft_Windows_NDISEnableBits & 0x40) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          v42,
          (unsigned int)AddDeviceFailed,
          (unsigned int)&NDIS_PROVIDER_ID,
          appended,
          1,
          (char)DeviceExtension);
      goto LABEL_69;
    }
    appended = IoSetDeviceInterfacePropertyData(
                 &DeviceExtension->DevinterfaceNetSymbolicLinkName,
                 DEVPKEY_NetworkInterface_Guid,
                 0,
                 1,
                 13,
                 16,
                 &DeviceExtension->InterfaceGuid);
    if ( appended )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v43) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v43,
          13,
          71,
          (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
          (char)DeviceExtension);
      }
LABEL_69:
      v23 = P;
      P = 0;
      if ( !v23 )
        goto LABEL_29;
      goto LABEL_28;
    }
    v44 = P;
    v91 = 1;
    P = 0;
    if ( v44 )
      ExFreePoolWithTag(v44, 0);
    p_BaseName = &DeviceExtension->BaseName;
  }
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80u) != 0LL
    || (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) != 0 )
  {
    *(_QWORD *)&DriverObject.Length = 8912896;
    DriverObject.Buffer = (wchar_t *)Src;
    appended = RtlUnicodeStringPrintf(&DriverObject, L"\\Device\\lwm\\NetworkInterface\\%wZ", p_BaseName);
    if ( appended )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v45) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v45,
          13,
          72,
          (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
          (char)DeviceExtension);
        v2 = v90;
        goto LABEL_172;
      }
      goto LABEL_29;
    }
    if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80u) == 0LL
      || (v46 = mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags),
          p_DriverObject = &DeviceExtension->DevinterfaceNetSymbolicLinkName,
          (v46 & 0x100) != 0) )
    {
      p_DriverObject = &DriverObject;
    }
    p_FdoName = &DeviceExtension->FdoName;
    appended = IoCreateSymbolicLink(&DeviceExtension->FdoName, p_DriverObject);
    if ( appended )
    {
      v9 = 7;
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v49) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v49,
          13,
          73,
          (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
          (char)DeviceExtension);
      }
      if ( (Microsoft_Windows_NDISEnableBits & 0x40) == 0 )
        goto LABEL_29;
      *(_DWORD *)Exclusive = (_DWORD)DeviceExtension;
      DeviceCharacteristics[0] = 65538;
LABEL_90:
      McTemplateK0qqq_EtwWriteTransfer(
        v50,
        (unsigned int)AddDeviceFailed,
        (unsigned int)&NDIS_PROVIDER_ID,
        appended,
        DeviceCharacteristics[0],
        Exclusive[0]);
      v2 = v90;
      goto LABEL_172;
    }
    v92 = 1;
  }
  else
  {
    p_FdoName = &DeviceExtension->FdoName;
  }
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80u) != 0LL
    && (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    p_FdoName = &DeviceExtension->DevinterfaceNetSymbolicLinkName;
  }
  appended = IoCreateSymbolicLink(*(PUNICODE_STRING *)a1[3].Data4, p_FdoName);
  if ( appended )
  {
    v9 = 7;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v51) = 2;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v51,
        13,
        74,
        (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
        (char)DeviceExtension);
    }
    if ( (Microsoft_Windows_NDISEnableBits & 0x40) == 0 )
      goto LABEL_29;
    *(_DWORD *)Exclusive = (_DWORD)DeviceExtension;
    DeviceCharacteristics[0] = 65539;
    goto LABEL_90;
  }
  v93 = 1;
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    DeviceExtension->DeviceFlags = 0;
    v52 = *(_QWORD *)&a1[3].Data1;
    if ( v52 && *(_WORD *)v52 )
      ndisQueryDeviceFlags(*(const wchar_t **)(v52 + 8), &DeviceExtension->DeviceFlags);
    if ( a1[4].Data4[0] )
      DeviceExtension->PnPFlags |= 0x2000u;
    if ( a1[4].Data4[1] )
      DeviceExtension->PnPFlags |= 2u;
    if ( a1[4].Data4[2] )
      DeviceExtension->PnPFlags |= 0x200000u;
    if ( a1[4].Data4[0] )
    {
      *(_QWORD *)&DriverObject.Length = 0;
      appended = ndisQueryReferenceBusInterface(TargetDevice, (struct BUS_INTERFACE_REFERENCE **)&DriverObject);
      if ( appended < 0 )
      {
LABEL_115:
        v2 = v90;
        v9 = 4;
        goto LABEL_172;
      }
      DeviceExtension->BusInterface = *(void **)&DriverObject.Length;
    }
    appended = ndisCreateSecurityDescriptor(DeviceExtension->DeviceObject, &DeviceExtension->SecurityDescriptor, 5u);
    if ( appended < 0 )
      goto LABEL_115;
  }
  appended = ndisCreateAdapterInstanceName(
               DeviceExtension,
               &DeviceExtension->pAdapterInstanceName,
               &DeviceExtension->pModifiedInstanceName);
  if ( appended < 0 )
    goto LABEL_115;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v53,
      13,
      75,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)DeviceExtension,
      (__int64)DeviceExtension->pAdapterInstanceName);
  if ( (Microsoft_Windows_NDISEnableBits & 0x20) != 0 )
    McTemplateK0z_EtwWriteTransfer(v54, AddDevice, v55, DeviceExtension->pAdapterInstanceName->Buffer);
  DeviceExtension->AdminStatus = NET_IF_ADMIN_STATUS_UP;
  v56 = *(Rtl::KString **)a1[3].Data4;
  *(_QWORD *)a1[3].Data4 = 0;
  v57 = DeviceExtension->ExportName.__ptr_.__value_;
  DeviceExtension->ExportName.__ptr_.__value_ = v56;
  if ( v57 )
    ExFreePoolWithTag(v57, 0x7274534Bu);
  v9 = 4;
  v58 = ndisInitializeConfiguration(DeviceExtension, *(void **)a1[1].Data4);
  if ( v58 )
  {
    v2 = v90;
    appended = NdisConvertNdisStatusToNtStatus(v58);
    goto LABEL_172;
  }
  Ndis::BindEngine::Initialize(&DeviceExtension->BindEngine, DeviceExtension);
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80u) != 0LL
    && (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    Ndis::BindEngine::BeginPolicyUpdates(&DeviceExtension->BindEngine);
    if ( Ndis::BindState::SetPause(&DeviceExtension->Bindings.Miniport, DatapathPaused, PauseReason_Wdf) )
    {
      memset(Src, 0, sizeof(Src));
      if ( (unsigned __int8)byte_140122AD3 >= 4u )
      {
        ndisGetBindLinkNameForTracing(DeviceExtension, (struct NDIS_PNPTRACE_LOCALS *)Src);
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Zq(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v59,
            28,
            76,
            (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
            *((__int64 *)&Src[0] + 1),
            Src[0]);
      }
    }
    Ndis::BindEngine::EndPolicyUpdates(&DeviceExtension->BindEngine);
  }
  v97 = 1;
  appended = ndisPDReadKeywords(DeviceExtension);
  if ( appended < 0 )
    goto LABEL_29;
  ndisMFindNumaDistances(DeviceExtension);
  ndisReadRssKeywords(DeviceExtension);
  if ( *(_QWORD *)(v8 + 776) )
  {
    v60 = ndisMInvokeAddDevice(DeviceExtension);
    if ( v60 )
    {
      v9 = 10;
      v2 = v90;
      appended = NdisConvertNdisStatusToNtStatus(v60);
      goto LABEL_172;
    }
    v89 = 1;
  }
  else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      1,
      77,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      v8,
      (char)DeviceExtension);
  }
  if ( (*(_BYTE *)(v8 + 26) & 1) != 0 && DeviceExtension->MajorNdisVersion >= 6u )
  {
    BindPaths = DeviceExtension->BindPaths;
    if ( !BindPaths )
    {
      v9 = 3;
      appended = -1073741823;
LABEL_143:
      v2 = v90;
      v62 = v89;
      goto LABEL_173;
    }
    if ( BindPaths->Number > 1 )
    {
      v2 = v90;
      v9 = 3;
      v62 = v89;
      appended = -1073741637;
      goto LABEL_173;
    }
  }
  KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  InterfaceByInterfaceGuid = ndisIfFindInterfaceByInterfaceGuid(a1);
  v4 = InterfaceByInterfaceGuid;
  if ( !InterfaceByInterfaceGuid )
  {
    appended = -1073741072;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v64);
    v2 = v90;
    v62 = v89;
    goto LABEL_173;
  }
  if ( InterfaceByInterfaceGuid->NetLuid.Value != *(_QWORD *)&a1[1].Data1 )
  {
    v4 = 0;
    appended = -1073741072;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v64);
    v2 = v90;
    v62 = v89;
    goto LABEL_173;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v64);
  if ( appended )
    goto LABEL_143;
  ndisMUpdateHiddenFlag(DeviceExtension, a1[4].Data4[3]);
  ndisIfUpdateInterfaceHiddenFlag(v4, a1[4].Data4[3]);
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80u) != 0LL
    && (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    if ( !a1[5].Data4[0] )
      DeviceExtension->MacOptions |= 8u;
    if ( !v4->IsWDFMiniportInterface )
    {
      v2 = v90;
      appended = -1073741811;
      v62 = v89;
      goto LABEL_173;
    }
    v65 = *(_QWORD *)&a1[5].Data1;
    MediaType = v4->MediaType;
    Src[1] = 0;
    DWORD2(Src[1]) = MediaType;
    *(_QWORD *)&Src[1] = v4->NetLuid.Value;
    DriverHandle = DeviceExtension->DriverHandle;
    memset(&Src[3], 0, 40);
    Src[0] = DeviceExtension->InterfaceGuid;
    Src[2] = DeviceExtension->BaseName;
    ImageName = DriverHandle->ImageName;
    pAdapterInstanceName = DeviceExtension->pAdapterInstanceName;
    Src[4] = ImageName;
    v70 = *pAdapterInstanceName;
    *(_QWORD *)&Src[5] = &DeviceExtension->PollModeConfigKnobs;
    v71 = *(_QWORD *)(v8 + 360);
    Src[3] = v70;
    (*(void (__fastcall **)(__int64, _OWORD *))(v71 + 112))(v65, Src);
  }
  updated = ndisIfUpdateInterfaceOnAddDevice(v4, DeviceExtension);
  if ( updated || (v94 = 1, (updated = ndisAllocateDefaultQueue(DeviceExtension)) != 0) )
  {
    appended = NdisConvertNdisStatusToNtStatus(updated);
LABEL_158:
    v2 = v90;
    v62 = v89;
    goto LABEL_173;
  }
  if ( (unsigned int)Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline() )
  {
    appended = ndisRegisterMiniportTriageData(DeviceExtension);
    if ( appended )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v73) = 2;
        WPP_RECORDER_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v73,
          13,
          78,
          (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
          (char)DeviceExtension,
          appended);
        v2 = v90;
        v62 = v89;
        goto LABEL_173;
      }
      goto LABEL_158;
    }
  }
  v62 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v95 = 0;
  v94 = 0;
  if ( (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x100) == 0 )
  {
    _InterlockedOr(v86, 0);
    SourceDevice->Flags &= ~0x80u;
  }
  v2 = v90;
LABEL_173:
  if ( !(unsigned int)Feature_NDPQualitySpring26__private_IsEnabledDeviceUsageNoInline() && dword_1401206F8 )
  {
    Exclusive[0] = (mem::ReadNoFence<unsigned long,void>(&DeviceExtension->Flags) & 0x80) != 0;
    NdisTraceLoggingDeviceAdded(
      v4,
      v9,
      a1,
      (unsigned int)appended,
      DeviceExtension->PnPInstanceId,
      *(_DWORD *)Exclusive);
  }
  if ( appended >= 0 )
  {
    if ( (unsigned int)Feature_NDPQualitySpring26__private_IsEnabledDeviceUsageNoInline() && dword_1401206F8 )
      NdisTraceLoggingDeviceAddSuccess(DeviceExtension, v4, v96);
    DeviceExtension->PhysicalMediumInInf = *(_DWORD *)&a1[2].Data4[4];
    v80 = *(Rtl::KString **)&a1[4].Data1;
    *(_QWORD *)&a1[4].Data1 = 0;
    v81 = DeviceExtension->FilterClass.__ptr_.__value_;
    DeviceExtension->FilterClass.__ptr_.__value_ = v80;
    if ( v81 )
      ExFreePoolWithTag(v81, 0x7274534Bu);
    v82 = KeAcquireSpinLockRaiseToDpc(&ndisMiniportListLock);
    DeviceExtension->NextGlobalMiniport = ndisMiniportList;
    ndisMiniportList = DeviceExtension;
    KeReleaseSpinLock(&ndisMiniportListLock, v82);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qZ(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v83,
        9,
        81,
        (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
        (char)DeviceExtension,
        (__int64)DeviceExtension->pAdapterInstanceName);
    ndisLogMiniportEvent(DeviceExtension, NdisMEvent_DeviceAdded);
    if ( v106 )
      *v106 = DeviceExtension;
  }
  else
  {
    if ( (unsigned int)Feature_NDPQualitySpring26__private_IsEnabledDeviceUsageNoInline() && dword_1401206F8 )
      NdisTraceLoggingDeviceAddFailure(v9, a1, (unsigned int)appended, v96, DeviceExtension);
    if ( DeviceExtension )
    {
      if ( v97 )
      {
        Ndis::BindRegistry::Reload((Ndis::BindRegistry *)DeviceExtension, 0, v74);
        ndisNotifyBindFailureOnUnboundProtocols(DeviceExtension);
      }
      if ( v62 )
        ndisMInvokeRemoveDevice(DeviceExtension);
      if ( v91 )
      {
        RtlFreeUnicodeString(&DeviceExtension->DevinterfaceNetSymbolicLinkName);
        DeviceExtension->DevinterfaceNetSymbolicLinkName.Buffer = 0;
      }
      if ( v92 )
      {
        v75 = IoDeleteSymbolicLink(&DeviceExtension->FdoName);
        if ( v75 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v76) = 4;
            WPP_RECORDER_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v76,
              13,
              79,
              (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
              (char)DeviceExtension,
              v75);
          }
        }
      }
      if ( v93 )
      {
        v77 = *(struct _UNICODE_STRING **)a1[3].Data4;
        if ( !v77 )
          v77 = &DeviceExtension->ExportName.__ptr_.__value_->_UNICODE_STRING;
        v78 = IoDeleteSymbolicLink(v77);
        if ( v78 && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v79) = 4;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v79,
            13,
            80,
            (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
            (char)DeviceExtension,
            v78);
        }
      }
      if ( v94 )
        ndisIfRemoveIfBlockMiniportAssociation(DeviceExtension->IfBlock, DeviceExtension, NET_IF_ADMIN_STATUS_DOWN);
      ndisMDeleteMiniportBlockOnRemove(DeviceExtension);
      LOBYTE(DeviceExtension) = 0;
    }
    if ( v95 )
    {
      if ( v2 )
        IoDetachDevice(v2);
      IoDeleteDevice(SourceDevice);
      SourceDevice = 0;
    }
  }
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v84) = 4;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v84,
      13,
      82,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)DeviceExtension,
      appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140185810  push    rbp
0x140185812  push    rbx
0x140185813  push    r12
0x140185815  push    r13
0x140185817  push    r14
0x140185819  push    r15
0x14018581b  lea     rbp, [rsp-2E8h]
0x140185823  sub     rsp, 3E8h
0x14018582a  mov     rax, cs:__security_cookie
0x140185831  xor     rax, rsp
0x140185834  mov     [rbp+310h+var_38], rax
0x14018583b  xor     r12d, r12d
0x14018583e  mov     [rbp+310h+var_350], rdx
0x140185842  xor     ebx, ebx
0x140185844  mov     [rsp+410h+var_3C8], r12
0x140185849  xor     r15d, r15d
0x14018584c  mov     [rsp+410h+SourceDevice], r12
0x140185851  xor     al, al
0x140185853  mov     r14, rcx
0x140185856  mov     [rsp+410h+var_3D0], al
0x14018585a  mov     [rsp+410h+var_3C0], al
0x14018585e  mov     [rsp+410h+var_3BC], al
0x140185862  mov     [rsp+410h+var_3BE], al
0x140185866  mov     [rsp+410h+var_3BF], al
0x14018586a  mov     [rsp+410h+var_3BD], al
0x14018586e  mov     [rsp+410h+var_3BA], al
0x140185872  mov     [rsp+410h+var_3BB], al
0x140185876  mov     rax, [rcx+20h]
0x14018587a  mov     [rbp+310h+TargetDevice], rax
0x14018587e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140185885  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14018588c  lea     rdx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140185893  jz      short loc_1401858BD
0x140185895  mov     rcx, cs:WPP_GLOBAL_Control
0x14018589c  mov     r9d, 44h ; 'D'; int
0x1401858a2  mov     qword ptr [rsp+410h+Exclusive], rax; char
0x1401858a7  mov     r8d, 0Dh; int
0x1401858ad  mov     qword ptr [rsp+410h+DeviceCharacteristics], rdx; struct _GUID *
0x1401858b2  mov     dl, 4; int
0x1401858b4  mov     rcx, [rcx+40h]; int
0x1401858b8  call    WPP_RECORDER_SF_q
0x1401858bd  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1401858c4  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1401858c9  mov     r13, [r14+60h]
0x1401858cd  movzx   ecx, byte ptr [r13+1Ah]
0x1401858d2  shr     cl, 7
0x1401858d5  and     cl, 1
0x1401858d8  cmp     [r14+59h], cl
0x1401858dc  jz      short loc_1401858E0
0x1401858de  int     2Ch; NT_ASSERT("Parameters->IsLightWeight == ((Parameters->MiniBlock->Flags & 0x0080) != 0)")
0x1401858e0  mov     [rsp+410h+arg_10], rsi
0x1401858e8  mov     [rsp+410h+var_30], rdi
0x1401858f0  test    r13, r13
0x1401858f3  jnz     short loc_140185904
0x1401858f5  mov     esi, 1
0x1401858fa  mov     edi, 0C000009Ah
0x1401858ff  jmp     loc_140186B7E
0x140185904  call    Feature_NDPQualitySpring26__private_IsEnabledDeviceUsageNoInline
0x140185909  test    eax, eax
0x14018590b  jz      short loc_14018591F
0x14018590d  movzx   esi, byte ptr [r13+1Ah]
0x140185912  shr     sil, 6
0x140185916  and     sil, 1
0x14018591a  mov     [rsp+410h+var_3BB], sil
0x14018591f  mov     rax, [r14+60h]
0x140185923  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14018592a  mov     rax, [rax+28h]
0x14018592e  mov     [rsp+410h+DriverObject], rax
0x140185933  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14018593a  nop     dword ptr [rax+rax+00h]
0x14018593f  mov     rdi, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x140185946  test    rdi, rdi
0x140185949  jz      short loc_14018595E
0x14018594b  nop     dword ptr [rax+rax+00h]
0x140185950  cmp     rdi, r13
0x140185953  jz      short loc_14018595E
0x140185955  mov     rdi, [rdi+8]
0x140185959  test    rdi, rdi
0x14018595c  jnz     short loc_140185950
0x14018595e  movzx   edx, al; NewIrql
0x140185961  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140185968  call    cs:__imp_KeReleaseSpinLock
0x14018596f  nop     dword ptr [rax+rax+00h]
0x140185974  cmp     rdi, r13
0x140185977  jnz     loc_140186CAC
0x14018597d  cmp     byte ptr [r13+18h], 6
0x140185982  jb      short loc_140185999
0x140185984  cmp     [r14+28h], bl
0x140185988  jnz     short loc_140185999
0x14018598a  mov     esi, 3
0x14018598f  mov     edi, 0C000014Dh
0x140185994  jmp     loc_140186B7E
0x140185999  mov     rax, [r14+38h]
0x14018599d  lea     rdx, ?ndisFdoDeviceStr@@3U_UNICODE_STRING@@A; SourceString
0x1401859a4  lea     rcx, [rsp+410h+DestinationString]; DestinationString
0x1401859a9  movzx   r12d, word ptr [rax]
0x1401859ad  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x1401859b3  mov     qword ptr [rbp+310h+String.Length], 280000h
0x1401859bb  mov     qword ptr [rsp+410h+DestinationString.Length], 3C0000h
0x1401859c4  lea     eax, ds:0[rax*8]
0x1401859cb  mov     dword ptr [rsp+410h+P], eax
0x1401859cf  lea     rax, [rbp+310h+var_A0]
0x1401859d6  mov     [rbp+310h+String.Buffer], rax
0x1401859da  lea     rax, [rbp+310h+var_78]
0x1401859e1  mov     [rbp+310h+DestinationString.Buffer], rax
0x1401859e5  call    cs:__imp_RtlCopyUnicodeString
0x1401859ec  nop     dword ptr [rax+rax+00h]
0x1401859f1  mov     ecx, 1
0x1401859f6  lock xadd cs:?ndisFdoIndex@@3KA, ecx; ulong ndisFdoIndex
0x1401859fe  inc     ecx; Value
0x140185a00  lea     r8, [rbp+310h+String]; String
0x140185a04  mov     edx, 0Ah; Base
0x140185a09  call    cs:__imp_RtlIntegerToUnicodeString
0x140185a10  nop     dword ptr [rax+rax+00h]
0x140185a15  mov     edi, eax
0x140185a17  mov     esi, 4
0x140185a1c  test    eax, eax
0x140185a1e  jnz     loc_140186B7B
0x140185a24  lea     rdx, [rbp+310h+String]; Source
0x140185a28  lea     rcx, [rsp+410h+DestinationString]; Destination
0x140185a2d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140185a34  nop     dword ptr [rax+rax+00h]
0x140185a39  mov     edi, eax
0x140185a3b  test    eax, eax
0x140185a3d  jnz     loc_140186B7B
0x140185a43  movzx   eax, word ptr [r13+1Ah]
0x140185a48  add     r12d, 17FBh
0x140185a4f  and     r12d, 0FFFFFFF8h
0x140185a53  add     r12d, dword ptr [rsp+410h+P]
0x140185a58  test    al, al
0x140185a5a  jns     short loc_140185AA6
0x140185a5c  movsxd  rdx, r12d
0x140185a5f  mov     ecx, 42h ; 'B'
0x140185a64  mov     r8d, 776C444Eh
0x140185a6a  call    cs:__imp_ExAllocatePool2
0x140185a71  nop     dword ptr [rax+rax+00h]
0x140185a76  mov     rbx, rax
0x140185a79  test    rax, rax
0x140185a7c  jnz     short loc_140185A8B
0x140185a7e  mov     edi, 0C000009Ah
0x140185a83  mov     r12, r15
0x140185a86  jmp     loc_140186B7E
0x140185a8b  mov     r8d, r12d; int
0x140185a8e  mov     rdx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140185a91  mov     rcx, r13; struct _NDIS_M_DRIVER_BLOCK *
0x140185a94  call    ?ndisMInitializeMiniportBlock@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisMInitializeMiniportBlock(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,long)
0x140185a99  lock or dword ptr [rbx+78h], 100h
0x140185aa1  jmp     loc_140185C49
0x140185aa6  mov     edx, r12d; DeviceExtensionSize
0x140185aa9  test    al, 40h
0x140185aab  jz      loc_140185BA1
0x140185ab1  mov     rax, [r13+168h]
0x140185ab8  lea     r8, [rbp+310h+var_380]
0x140185abc  mov     rcx, [r14+50h]
0x140185ac0  mov     [rbp+310h+var_380], rbx
0x140185ac4  mov     [rsp+410h+P], rax
0x140185ac9  mov     rax, [rax+68h]
0x140185acd  call    _guard_dispatch_icall
0x140185ad2  mov     edi, eax
0x140185ad4  test    eax, eax
0x140185ad6  jnz     loc_140186B7B
0x140185adc  mov     rbx, [rsp+410h+P]
0x140185ae1  mov     rcx, [r14+50h]
0x140185ae5  mov     rax, [rbx+40h]
0x140185ae9  call    _guard_dispatch_icall
0x140185aee  mov     rcx, [r14+50h]
0x140185af2  mov     [rsp+410h+SourceDevice], rax
0x140185af7  mov     rax, [rbx+48h]
0x140185afb  call    _guard_dispatch_icall
0x140185b00  mov     rbx, [rbp+310h+var_380]
0x140185b04  mov     r8d, r12d; int
0x140185b07  mov     rdx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140185b0a  mov     [rsp+410h+var_3C8], rax
0x140185b0f  mov     rcx, r13; struct _NDIS_M_DRIVER_BLOCK *
0x140185b12  call    ?ndisMInitializeMiniportBlock@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisMInitializeMiniportBlock(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,long)
0x140185b17  lea     rcx, [rsp+410h+P]
0x140185b1c  call    ??$MakePoolPtrNP@VNdisWdfIdle@@@@YA?AV?$unique_ptr@VNdisWdfIdle@@U?$KFreePoolNP@VNdisWdfIdle@@@@@wistd@@K@Z; MakePoolPtrNP<NdisWdfIdle>(ulong)
0x140185b21  mov     r12, [rsp+410h+P]
0x140185b26  test    r12, r12
0x140185b29  jz      loc_140185FD6
0x140185b2f  mov     rdx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140185b32  mov     rcx, r12; DeferredContext
0x140185b35  call    ?Initialize@NdisWdfIdle@@QEAAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; NdisWdfIdle::Initialize(_NDIS_MINIPORT_BLOCK *)
0x140185b3a  mov     edi, eax
0x140185b3c  test    eax, eax
0x140185b3e  jz      short loc_140185B68
0x140185b40  test    r12, r12
0x140185b43  jz      short loc_140185B5E
0x140185b45  mov     rcx, r12; this
0x140185b48  call    ??1NdisWdfIdle@@QEAA@XZ; NdisWdfIdle::~NdisWdfIdle(void)
0x140185b4d  mov     rcx, r12; P
0x140185b50  xor     edx, edx; Tag
0x140185b52  call    cs:__imp_ExFreePoolWithTag
0x140185b59  nop     dword ptr [rax+rax+00h]
0x140185b5e  mov     r12, [rsp+410h+var_3C8]
0x140185b63  jmp     loc_140186B7E
0x140185b68  mov     rdi, [rbx+17C8h]
0x140185b6f  mov     [rbx+17C8h], r12
0x140185b76  test    rdi, rdi
0x140185b79  jz      short loc_140185B94
0x140185b7b  mov     rcx, rdi; this
0x140185b7e  call    ??1NdisWdfIdle@@QEAA@XZ; NdisWdfIdle::~NdisWdfIdle(void)
0x140185b83  xor     edx, edx; Tag
0x140185b85  mov     rcx, rdi; P
0x140185b88  call    cs:__imp_ExFreePoolWithTag
0x140185b8f  nop     dword ptr [rax+rax+00h]
0x140185b94  mov     rax, [r14+50h]
0x140185b98  mov     [rbx+18h], rax
0x140185b9c  jmp     loc_140185C49
0x140185ba1  mov     rcx, [rsp+410h+DriverObject]; DriverObject
0x140185ba6  lea     rax, [rsp+410h+SourceDevice]
0x140185bab  mov     [rsp+410h+DeviceObject], rax; DeviceObject
0x140185bb0  lea     r8, [rsp+410h+DestinationString]; DeviceName
0x140185bb5  mov     [rsp+410h+Exclusive], bl; void *
0x140185bb9  mov     r9d, 17h; DeviceType
0x140185bbf  mov     [rsp+410h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140185bc7  call    cs:__imp_IoCreateDevice
0x140185bce  nop     dword ptr [rax+rax+00h]
0x140185bd3  mov     edi, eax
0x140185bd5  test    eax, eax
0x140185bd7  js      loc_140186B76
0x140185bdd  mov     rax, [rsp+410h+SourceDevice]
0x140185be2  mov     esi, 6
0x140185be7  mov     rcx, [rbp+310h+TargetDevice]
0x140185beb  mov     rdx, rcx; TargetDevice
0x140185bee  mov     [rsp+410h+var_3BC], 1
0x140185bf3  or      dword ptr [rax+30h], 10h
0x140185bf7  and     dword ptr [rcx+30h], 0FFFFFF7Fh
0x140185bfe  mov     rax, [rsp+410h+SourceDevice]
0x140185c03  or      dword ptr [rax+30h], 2000h
0x140185c0a  mov     rcx, [rsp+410h+SourceDevice]; SourceDevice
0x140185c0f  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140185c16  nop     dword ptr [rax+rax+00h]
0x140185c1b  mov     [rsp+410h+var_3C8], rax
0x140185c20  test    rax, rax
0x140185c23  jnz     short loc_140185C32
0x140185c25  mov     edi, 0C0000001h
0x140185c2a  mov     r12, rax
0x140185c2d  jmp     loc_140186B7E
0x140185c32  mov     rbx, [rsp+410h+SourceDevice]
0x140185c37  mov     r8d, r12d; int
0x140185c3a  mov     rcx, r13; struct _NDIS_M_DRIVER_BLOCK *
0x140185c3d  mov     rbx, [rbx+40h]
0x140185c41  mov     rdx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140185c44  call    ?ndisMInitializeMiniportBlock@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisMInitializeMiniportBlock(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,long)
0x140185c49  test    byte ptr [r13+1Ah], 40h
0x140185c4e  jz      short loc_140185C58
0x140185c50  lock or dword ptr [rbx+78h], 80h
0x140185c58  movups  xmm0, xmmword ptr [r14]
0x140185c5c  mov     edx, 1
0x140185c61  mov     ecx, 2
0x140185c66  movups  xmmword ptr [rbx+0FA8h], xmm0
0x140185c6d  call    ?ndisAllocateEventLog@@YAPEAUNDIS_EVENT_LOG_HANDLE__@@W4_NDIS_EVENT_LOG_SIZE@@G@Z; ndisAllocateEventLog(_NDIS_EVENT_LOG_SIZE,ushort)
0x140185c72  movups  xmm0, xmmword ptr [rbx+0FA8h]
0x140185c79  lea     r12, [rbx+1720h]
0x140185c80  mov     [rbx+1178h], rax
0x140185c87  mov     [rbp+310h+var_368.NamespaceType], 2
0x140185c8e  movups  xmmword ptr [rbp+310h+var_368.ObjectId.Data1], xmm0
0x140185c92  test    r12, r12
0x140185c95  jz      short loc_140185CAA
0x140185c97  mov     rdx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; struct _DRIVER_OBJECT *
0x140185c9e  lea     r8, [rbp+310h+var_368]; struct _CONFIG_KNOB_NAMESPACE *
0x140185ca2  mov     rcx, r12; this
0x140185ca5  call    ??0KnobNamespace@@QEAA@PEAU_DRIVER_OBJECT@@PEAU_CONFIG_KNOB_NAMESPACE@@@Z; KnobNamespace::KnobNamespace(_DRIVER_OBJECT *,_CONFIG_KNOB_NAMESPACE *)
0x140185caa  xor     edx, edx
0x140185cac  lea     r8, [rbx+1778h]
0x140185cb3  mov     [rbx+1780h], rdx
0x140185cba  lea     rax, [r8+4]
0x140185cbe  mov     [rbx+1788h], rdx
0x140185cc5  lea     rcx, aFlags; "Flags"
0x140185ccc  mov     [rbx+1790h], rdx
0x140185cd3  lea     r9, aMaxpacketsrece_0; "MaxPacketsReceiveCompleteAtPassive"
0x140185cda  mov     [rbx+1798h], rdx
0x140185ce1  xorps   xmm0, xmm0
0x140185ce4  mov     [rbx+17A0h], rdx
0x140185ceb  mov     [rbx+17A8h], rdx
0x140185cf2  mov     [rbx+17B0h], edx
0x140185cf8  mov     [rax], edx
0x140185cfa  mov     qword ptr [rbp+310h+Src+8], rax
0x140185cfe  lea     rax, aMaxtimeatdispa; "MaxTimeAtDispatch"
0x140185d05  mov     qword ptr [rbp+310h+var_310], rax
0x140185d09  lea     rax, [r8+8]
0x140185d0d  mov     qword ptr [rbp+310h+var_310+8], rax
0x140185d11  lea     rax, aDispatchtimewa_0; "DispatchTimeWarning"
0x140185d18  mov     [rbp+310h+var_2E0], rax
0x140185d1c  lea     rax, [r8+0Ch]
0x140185d20  mov     [rbp+310h+var_2D8], rax
0x140185d24  lea     rax, aDispatchtimewa; "DispatchTimeWarningInterval"
0x140185d2b  mov     [rbp+310h+var_2B0], rax
0x140185d2f  lea     rax, [r8+10h]
0x140185d33  mov     [rbp+310h+var_2A8], rax
0x140185d37  lea     rax, aDpcwatchdogtim; "DpcWatchdogTimerThreshold"
0x140185d3e  mov     [rbp+310h+var_280], rax
0x140185d45  lea     rax, [r8+14h]
0x140185d49  mov     [rbp+310h+var_278], rax
0x140185d50  lea     rax, aWorkerthreadpr; "WorkerThreadPriority"
0x140185d57  mov     [rbp+310h+var_250], rax
0x140185d5e  lea     rax, [r8+18h]
0x140185d62  mov     [rbp+310h+var_248], rax
0x140185d69  lea     rax, aMaxpacketssend_2; "MaxPacketsSendAtPassive"
  ... truncated ...
```
