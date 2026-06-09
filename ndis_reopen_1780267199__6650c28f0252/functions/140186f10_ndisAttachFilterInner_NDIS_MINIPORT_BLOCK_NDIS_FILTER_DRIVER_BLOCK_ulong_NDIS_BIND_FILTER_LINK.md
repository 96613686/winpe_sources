# ndisAttachFilterInner(_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_DRIVER_BLOCK *,ulong,NDIS_BIND_FILTER_LINK *)

- ea: `0x140186f10`
- end: `0x14018896a`
- name: `?ndisAttachFilterInner@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_DRIVER_BLOCK@@KPEAUNDIS_BIND_FILTER_LINK@@@Z`
- size: `6746`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_FILTER_DRIVER_BLOCK *, unsigned int, struct NDIS_BIND_FILTER_LINK *)`
- caller_count: `1`
- callee_count: `65`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140162680`

## callees

- `0x140007660`
- `0x140008390`
- `0x140010d20`
- `0x1400110b0`
- `0x140011190`
- `0x140012610`
- `0x14001c3f0`
- `0x14001c6b0`
- `0x14002ab60`
- `0x14003d970`
- `0x1400400d0`
- `0x140049130`
- `0x1400497f0`
- `0x140053280`
- `0x140057b80`
- `0x140057f10`
- `0x140058390`
- `0x14005b320`
- `0x14005c080`
- `0x140063390`
- `0x140067310`
- `0x140069920`
- `0x14006a540`
- `0x14006b9d0`
- `0x140072ed0`
- `0x140074ea0`
- `0x140075670`
- `0x140077b30`
- `0x14007ba00`
- `0x14007bd80`
- `0x14007dfd0`
- `0x14007ff50`
- `0x140082c90`
- `0x140084e10`
- `0x140087b14`
- `0x140089250`
- `0x140089fe0`
- `0x14008a850`
- `0x14008cdf0`
- `0x140092d28`
- `0x140092d80`
- `0x140098928`
- `0x1400cee00`
- `0x1400eb380`
- `0x1400eb460`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14014d14c`
- `0x140153100`
- `0x14015bc60`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14018752b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140187560`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14018752b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140187560`
- `ntoskrnl!MmIsDriverVerifying` at `0x1401871dc`
- `ntoskrnl!MmIsDriverVerifying` at `0x1401871dc`
- `ntoskrnl!IoWMIWriteEvent` at `0x1401886bf`
- `ntoskrnl!IoWMIWriteEvent` at `0x1401886bf`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x1401876d6`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14018771f`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x1401876d6`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14018771f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018749c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018873f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401888a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018749c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018873f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401888a3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018760c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018760c`
- `ntoskrnl!ExAllocatePool2` at `0x140187313`
- `ntoskrnl!ExAllocatePool2` at `0x1401874e3`
- `ntoskrnl!ExAllocatePool2` at `0x140187313`
- `ntoskrnl!ExAllocatePool2` at `0x1401874e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018767d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140187855`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401878a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140188109`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401882f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018842f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018852a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018859f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018767d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140187855`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401878a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140188109`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401882f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018842f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018852a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14018859f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018761f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018780f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018787a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401880ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401882d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188312`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401883a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018849a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018761f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018780f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018787a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401880ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401882d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140188312`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401883a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14018849a`
- `ntoskrnl!EtwWriteTransfer` at `0x140187ff5`
- `ntoskrnl!EtwWriteTransfer` at `0x140187ff5`

## pseudocode

```c
__int64 __fastcall ndisAttachFilterInner(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NDIS_FILTER_DRIVER_BLOCK *a2,
        int a3,
        struct NDIS_BIND_FILTER_LINK *a4)
{
  int v7; // edx
  KRef<NDIS_BIND_FILTER_DRIVER>::KRefHolder *p; // rsi
  int v10; // r14d
  int v11; // r15d
  struct _NDIS_MINIPORT_BLOCK *v12; // rdi
  struct NDIS_BIND_FILTER_LINK *v13; // r13
  struct _NDIS_FILTER_DRIVER_BLOCK *v14; // r15
  unsigned int FilterAdapterRegistry; // r14d
  __int64 v16; // rsi
  int v17; // edx
  unsigned __int8 v18; // bl
  __int64 Pool2; // rax
  unsigned __int8 v20; // dl
  struct Rtl::KString *v21; // rax
  void *v22; // rcx
  __int64 v23; // r14
  _WORD *v24; // rax
  struct NDISWATCHDOG__ *Watchdog; // rax
  struct NDISWATCHDOG__ *v26; // rcx
  struct NDISWATCHDOG__ *v27; // rbx
  const struct _NDIS_FILTER_BLOCK *v28; // rcx
  unsigned int v29; // edx
  struct _NDIS_FILTER_BLOCK *v30; // rcx
  KIRQL v31; // r8
  unsigned __int8 v32; // dl
  struct _NDIS_FILTER_BLOCK *v33; // r13
  struct _NDIS_FILTER_BLOCK *v34; // rbx
  KIRQL v35; // al
  struct _NDIS_MINIPORT_BLOCK *BaseMiniport; // rbx
  KIRQL v37; // al
  __int64 v38; // rax
  unsigned __int8 v39; // al
  UCHAR v40; // r10
  __int64 v41; // r8
  __int64 v42; // rcx
  _NDIS_PHYSICAL_MEDIUM MiniportPhysicalMediumType; // eax
  _NDIS_MINIPORT_OFFLOAD *Offload; // rax
  _NDIS_HD_SPLIT_CURRENT_CONFIG *HDSplitCurrentConfig; // rax
  _NDIS_SRIOV_CAPABILITIES *SriovHwCapabilities; // rbx
  _NDIS_SRIOV_CAPABILITIES *SriovCurrentCapabilities; // r11
  _NDIS_NIC_SWITCH_CAPABILITIES *NicSwitchHwCapabilities; // rcx
  _NDIS_NIC_SWITCH_CAPABILITIES *NicSwitchCurrentCapabilities; // rdx
  _NDIS_RECEIVE_FILTER_CAPABILITIES *ReceiveFilterHwCapabilities; // r9
  _NDIS_RECEIVE_FILTER_CAPABILITIES *ReceiveFilterCurrentCapabilities; // r8
  _NDIS_NIC_SWITCH_CAPABILITIES *NicSwitchCapabilities; // rax
  _NDIS_IF_BLOCK *IfBlock; // rdx
  _NET_IF_MEDIA_CONNECT_STATE MediaConnectState; // ecx
  void (__stdcall *v55)(PVOID); // rax
  void (__usercall *v56)(struct _NDIS_OBJECT_HEADER *@<rcx>, struct _NET_BUFFER_LIST *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int); // rcx
  void (*v57)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int); // rdx
  _NDIS_MEDIUM MediaType; // eax
  int v59; // edx
  const GUID *v60; // r8
  const GUID *p_InterfaceGuid; // r9
  unsigned int v62; // eax
  int v63; // r9d
  enum Ndis::ReadBindingsOptions::Flags *v64; // rdx
  unsigned __int8 v65; // r12
  const struct _NDIS_FILTER_BLOCK *v66; // rcx
  unsigned int v67; // edx
  struct _NDIS_FILTER_BLOCK *v68; // rcx
  KIRQL v69; // r8
  bool v70; // zf
  int v71; // ecx
  char MiniportMediaType; // r8
  __int64 v73; // rcx
  __int64 v74; // rax
  NET_IFINDEX IfIndex; // edx
  __int64 v76; // rax
  NET_IFINDEX v77; // edx
  __int64 v78; // rcx
  KIRQL v79; // bl
  __int64 v80; // r13
  KIRQL v81; // al
  KIRQL v82; // bl
  KSPIN_LOCK *p_Lock; // rcx
  KIRQL v84; // al
  struct _KTHREAD *CurrentThread; // rcx
  _NDIS_SUPPORTED_PAUSE_FUNCTIONS MiniportPauseFunctions; // edx
  unsigned int MiniportAutoNegotiationFlags; // edx
  struct _NDIS_FILTER_BLOCK *v88; // rcx
  struct _NDIS_FILTER_BLOCK *v89; // rcx
  KIRQL v90; // r8
  _NDIS_PHYSICAL_MEDIUM MiniportPhysicalMediaType; // eax
  _NDIS_MEDIUM v92; // ecx
  __int64 v93; // rax
  KIRQL v94; // r8
  _NDIS_MEDIUM v95; // ecx
  _NDIS_PHYSICAL_MEDIUM v96; // eax
  PVOID v97; // r12
  char *v98; // rbx
  int v99; // edx
  int v100; // ecx
  NTSTATUS v101; // ebx
  int v102; // edx
  struct _NDIS_MINIPORT_BLOCK *v103; // rdx
  int v104; // edx
  int UserDataCount; // [rsp+20h] [rbp-130h]
  char v106; // [rsp+D0h] [rbp-80h]
  char v107; // [rsp+D0h] [rbp-80h]
  int Data2; // [rsp+E0h] [rbp-70h] BYREF
  struct _NDIS_MINIPORT_BLOCK *v110; // [rsp+E8h] [rbp-68h]
  int v111; // [rsp+F0h] [rbp-60h]
  int v112; // [rsp+F4h] [rbp-5Ch]
  int v113; // [rsp+F8h] [rbp-58h]
  int v114; // [rsp+FCh] [rbp-54h]
  int v115; // [rsp+100h] [rbp-50h]
  int v116; // [rsp+104h] [rbp-4Ch]
  int v117; // [rsp+108h] [rbp-48h]
  int Data3; // [rsp+10Ch] [rbp-44h]
  int v119; // [rsp+110h] [rbp-40h] BYREF
  char v120[8]; // [rsp+118h] [rbp-38h]
  struct _NDIS_FILTER_DRIVER_BLOCK *v121; // [rsp+120h] [rbp-30h]
  struct _NDIS_FILTER_BLOCK *v122; // [rsp+128h] [rbp-28h] BYREF
  struct _NDIS_FILTER_BLOCK *v123; // [rsp+130h] [rbp-20h] BYREF
  PVOID WnodeEventItem[3]; // [rsp+138h] [rbp-18h] BYREF
  struct _NDIS_FILTER_ATTACH_PARAMETERS v125; // [rsp+150h] [rbp+0h] BYREF
  char v126[160]; // [rsp+230h] [rbp+E0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+2D0h] [rbp+180h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+2E0h] [rbp+190h] BYREF
  int *p_Data2; // [rsp+2F0h] [rbp+1A0h]
  __int64 v130; // [rsp+2F8h] [rbp+1A8h]
  wchar_t v131[88]; // [rsp+300h] [rbp+1B0h] BYREF

  v111 = a3;
  v121 = a2;
  v110 = a1;
  v122 = 0;
  v123 = 0;
  memset(&v125, 0, sizeof(v125));
  v119 = 0;
  WnodeEventItem[0] = 0;
  if ( !ndisReferenceFilterDriver(a2, LWFDRV_ATTACHING) )
    return 3221291010LL;
  if ( !ndisReferenceMiniport(a1, MPREF_LWF_ATTACHING) )
  {
    ndisDereferenceFilterDriver(a2, 0, LWFDRV_ATTACHING);
    return 3221291010LL;
  }
  *(_QWORD *)v120 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_qqZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v7,
      1,
      24,
      (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
      (char)a2,
      (char)a1,
      (__int64)&a2->DefaultFilterCharacteristics.FriendlyName);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  p = a4->BindDriver._p;
  v10 = a1->InterfaceGuid.Data4[7];
  v11 = a1->InterfaceGuid.Data4[6];
  *(_QWORD *)&EventDescriptor.Id = &a1->InterfaceGuid;
  v112 = v10;
  v113 = v11;
  WnodeEventItem[1] = p;
  v114 = v110->InterfaceGuid.Data4[3];
  v115 = v110->InterfaceGuid.Data4[2];
  v116 = v110->InterfaceGuid.Data4[1];
  v117 = v110->InterfaceGuid.Data4[0];
  Data3 = v110->InterfaceGuid.Data3;
  Data2 = v110->InterfaceGuid.Data2;
  UserDataCount = Data2;
  v12 = v110;
  v13 = a4;
  if ( (int)RtlStringCbPrintfW(
              v131,
              0xA8u,
              L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}-{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}-%04u",
              **(unsigned int **)&EventDescriptor.Id) >= 0 )
  {
    v18 = 1;
    ndisFindAdjacentFilters(v110, a4, &v123, &v122);
    v14 = v121;
    if ( v121->DefaultFilterCharacteristics.MajorNdisVersion <= 6u
      && (v121->DefaultFilterCharacteristics.MajorNdisVersion != 6
       || v121->DefaultFilterCharacteristics.MinorNdisVersion < 0x28u) )
    {
      v18 = 0;
    }
    FilterAdapterRegistry = ndisCreateFilterAdapterRegistry(&v121->DefaultFilterCharacteristics.ServiceName, v110, v18);
    if ( FilterAdapterRegistry )
      goto LABEL_9;
    if ( v110->MajorNdisVersion < 6u && (v110->LinkStateIndicationFlags & 1) == 0 )
      ndisMDoMiniportOp(v110, 1u, 0x10114u, &v119, 4, 1, 1u);
    if ( !ndisReferenceFilterDriver(v14, LWFDRV_FILTERMODULE) )
    {
      FilterAdapterRegistry = -1073676282;
      goto LABEL_9;
    }
    Pool2 = ExAllocatePool2(64, 1424, 1650869326);
    v16 = Pool2;
    if ( !Pool2 )
    {
      FilterAdapterRegistry = -1073741670;
      ndisDereferenceFilterDriver(v14, 0, LWFDRV_FILTERMODULE);
      goto LABEL_10;
    }
    *(_QWORD *)(Pool2 + 184) = -1;
    v106 = 0;
    *(_QWORD *)(Pool2 + 40) = 0;
    *(_QWORD *)(Pool2 + 960) = 0;
    *(_DWORD *)(Pool2 + 968) = 0;
    *(_QWORD *)(Pool2 + 972) = 0;
    *(_DWORD *)(Pool2 + 980) = 0;
    *(_OWORD *)(Pool2 + 984) = 0;
    *(_OWORD *)(Pool2 + 1000) = 0;
    *(_OWORD *)(Pool2 + 1016) = 0;
    *(_OWORD *)(Pool2 + 1032) = 0;
    *(_OWORD *)(Pool2 + 1048) = 0;
    *(_OWORD *)(Pool2 + 1064) = 0;
    *(_OWORD *)(Pool2 + 1080) = 0;
    *(_OWORD *)(Pool2 + 1096) = 0;
    *(_DWORD *)(Pool2 + 1112) = 0;
    *(_OWORD *)(Pool2 + 1116) = 0;
    *(_OWORD *)(Pool2 + 1132) = 0;
    *(_OWORD *)(Pool2 + 1148) = 0;
    *(_OWORD *)(Pool2 + 1164) = 0;
    *(_OWORD *)(Pool2 + 1180) = 0;
    *(_OWORD *)(Pool2 + 1196) = 0;
    *(_OWORD *)(Pool2 + 1212) = 0;
    *(_OWORD *)(Pool2 + 1228) = 0;
    *(_DWORD *)(Pool2 + 1244) = 0;
    *(_OWORD *)(Pool2 + 1248) = 0;
    *(_OWORD *)(Pool2 + 1264) = 0;
    *(_OWORD *)(Pool2 + 1280) = 0;
    *(_OWORD *)(Pool2 + 1296) = 0;
    *(_OWORD *)(Pool2 + 1312) = 0;
    *(_DWORD *)(Pool2 + 1328) = 0;
    *(_OWORD *)(Pool2 + 1332) = 0;
    *(_OWORD *)(Pool2 + 1348) = 0;
    *(_OWORD *)(Pool2 + 1364) = 0;
    *(_OWORD *)(Pool2 + 1380) = 0;
    *(_OWORD *)(Pool2 + 1396) = 0;
    *(_DWORD *)(Pool2 + 1412) = 0;
    *(_QWORD *)(Pool2 + 1416) = 0;
    *(_DWORD *)Pool2 = 93323525;
    *(_QWORD *)(Pool2 + 16) = v14;
    if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
    {
      ndisInitializeRef((struct _REFERENCE_EX *)(v16 + 72), 3u);
      ndisInitializeZeroBasedRef((struct _REFERENCE_EX *)(v16 + 312), v20);
      ndisCloseRef((PKSPIN_LOCK)(v16 + 312));
    }
    v21 = Rtl::KString::Initialize(v131);
    v22 = *(void **)(v16 + 40);
    *(_QWORD *)(v16 + 40) = v21;
    if ( v22 )
      ExFreePoolWithTag(v22, 0x7274534Bu);
    if ( !*(_QWORD *)(v16 + 40) )
    {
      FilterAdapterRegistry = -1073741670;
LABEL_200:
      v65 = 0;
      goto LABEL_201;
    }
    v23 = (unsigned __int16)(v14->DefaultFilterCharacteristics.FriendlyName.Length
                           + 14
                           + v12->pAdapterInstanceName->Length);
    v24 = (_WORD *)ExAllocatePool2(66, v23 + 16, 1953711182);
    *(_QWORD *)(v16 + 48) = v24;
    if ( !v24 )
    {
      FilterAdapterRegistry = -1073741670;
      goto LABEL_200;
    }
    *v24 = 0;
    *(_WORD *)(*(_QWORD *)(v16 + 48) + 2LL) = v23;
    *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL) = *(_QWORD *)(v16 + 48) + 16LL;
    RtlAppendUnicodeStringToString(*(PUNICODE_STRING *)(v16 + 48), v12->pAdapterInstanceName);
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL) + 2 * ((unsigned __int64)**(unsigned __int16 **)(v16 + 48) >> 1)) = 45;
    **(_WORD **)(v16 + 48) += 2;
    RtlAppendUnicodeStringToString(*(PUNICODE_STRING *)(v16 + 48), &v14->DefaultFilterCharacteristics.FriendlyName);
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL) + 2 * ((unsigned __int64)**(unsigned __int16 **)(v16 + 48) >> 1)) = 45;
    **(_WORD **)(v16 + 48) += 2;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL) + 2
                                                         * ((unsigned __int64)**(unsigned __int16 **)(v16 + 48) >> 1)) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 40) + 8LL) + 2 * (((unsigned __int64)**(unsigned __int16 **)(v16 + 40) - 8) >> 1));
    **(_WORD **)(v16 + 48) += 8;
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL) + 2 * ((unsigned __int64)**(unsigned __int16 **)(v16 + 48) >> 1)) = 0;
    *(_QWORD *)(v16 + 648) = NdisNblTrackerRegisterComponent(1, v16, *(_QWORD *)(v16 + 48));
    Watchdog = ndisAllocateWatchdog();
    v26 = *(struct NDISWATCHDOG__ **)(v16 + 184);
    v27 = Watchdog;
    if ( v26 != (struct NDISWATCHDOG__ *)-1LL )
      ndisFreeWatchdog(v26);
    *(_QWORD *)(v16 + 184) = v27;
    KeInitializeSpinLock((PKSPIN_LOCK)(v16 + 144));
    KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 144));
    *(_QWORD *)(v16 + 152) = KeGetCurrentThread();
    FILTER_CLEAR_ALL_STATE_FLAGS((struct _NDIS_FILTER_BLOCK *)v16);
    if ( FILTER_TEST_FLAG(v28, 0x100u) )
      FILTER_CLEAR_FLAG(v30, v29);
    FILTER_SET_FLAG((struct _NDIS_FILTER_BLOCK *)v16, 8u);
    *(_QWORD *)(v16 + 152) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 144), v31);
    *(_BYTE *)(v16 + 64) = 0;
    if ( !(unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
    {
      ndisInitializeRef((struct _REFERENCE_EX *)(v16 + 72), 3u);
      ndisInitializeZeroBasedRef((struct _REFERENCE_EX *)(v16 + 312), v32);
      ndisCloseRef((PKSPIN_LOCK)(v16 + 312));
    }
    if ( ndisDatapathVerifierMode == 1 )
    {
      if ( !MmIsDriverVerifyingByAddress(*(PVOID *)(*(_QWORD *)(v16 + 16) + 176LL))
        || !ndisDriverVerifierNdisFlagEnabled() )
      {
LABEL_49:
        if ( v12->MajorNdisVersion >= 6u )
        {
          if ( ndisNblContextVerifierMode == 1 )
          {
            if ( !MmIsDriverVerifyingByAddress(*(PVOID *)(*(_QWORD *)(v16 + 16) + 176LL))
              || !ndisDriverVerifierNdisFlagEnabled() )
            {
              goto LABEL_56;
            }
          }
          else if ( ndisNblContextVerifierMode != 2 )
          {
            goto LABEL_56;
          }
          *(_OWORD *)(v16 + 928) = 0;
          *(_OWORD *)(v16 + 944) = 0;
          FILTER_SET_FLAG((struct _NDIS_FILTER_BLOCK *)v16, 0x400u);
        }
LABEL_56:
        *(_QWORD *)(v16 + 584) = v14->DefaultFilterCharacteristics.SendNetBufferListsHandler;
        *(_QWORD *)(v16 + 592) = v14->DefaultFilterCharacteristics.SendNetBufferListsCompleteHandler;
        *(_QWORD *)(v16 + 608) = v14->DefaultFilterCharacteristics.ReceiveNetBufferListsHandler;
        *(_QWORD *)(v16 + 616) = v14->DefaultFilterCharacteristics.ReturnNetBufferListsHandler;
        *(_QWORD *)(v16 + 600) = v14->DefaultFilterCharacteristics.CancelSendNetBufferListsHandler;
        *(_QWORD *)(v16 + 168) = v16 + 160;
        *(_QWORD *)(v16 + 160) = v16 + 160;
        FilterAdapterRegistry = ndisAllocOrFreeIterativeDataPathTrackerIfNeeded(
                                  (struct _NDIS_FILTER_BLOCK *)v16,
                                  (struct _NDIS_FILTER_PARTIAL_CHARACTERISTICS *)(v16 + 576),
                                  0);
        if ( FilterAdapterRegistry )
          goto LABEL_200;
        v33 = v122;
        v34 = v123;
        *(_QWORD *)(v16 + 208) = ndisStackExpansionFallbackWorker;
        *(_QWORD *)(v16 + 216) = v16;
        *(_QWORD *)(v16 + 192) = 0;
        *(_QWORD *)(v16 + 112) = v33;
        *(_QWORD *)(v16 + 120) = v34;
        if ( !v33 && !v34 && v12->HighestFilter )
          goto LABEL_198;
        v35 = KeAcquireSpinLockRaiseToDpc(&v12->Lock);
        if ( v34 )
          v34->LowerFilter = (_NDIS_FILTER_BLOCK *)v16;
        else
          v12->HighestFilter = (_NDIS_FILTER_BLOCK *)v16;
        if ( v33 )
          v33->HigherFilter = (_NDIS_FILTER_BLOCK *)v16;
        else
          v12->LowestFilter = (_NDIS_FILTER_BLOCK *)v16;
        *(_QWORD *)(v16 + 32) = v12;
        v12->MiniportThread = 0;
        KeReleaseSpinLock(&v12->Lock, v35);
        v106 = 1;
        BaseMiniport = v12;
        if ( v12->BaseMiniport )
          BaseMiniport = v12->BaseMiniport;
        v37 = KeAcquireSpinLockRaiseToDpc(&ndisGlobalFilterListLock);
        *(_QWORD *)(v16 + 104) = ndisGlobalFilterList;
        ndisGlobalFilterList = (_NDIS_FILTER_BLOCK *)v16;
        KeReleaseSpinLock(&ndisGlobalFilterListLock, v37);
        if ( !ndisQueueFilterOnDriver((struct _NDIS_FILTER_BLOCK *)v16, v14) )
        {
          FilterAdapterRegistry = -1073676286;
LABEL_199:
          v13 = a4;
          goto LABEL_200;
        }
        if ( (v14->Bind._p->_t.FilterBindFlags & 2) != 0 )
        {
          FilterAdapterRegistry = ndisCreateFilterInstanceRegistry(
                                    &v14->DefaultFilterCharacteristics.ServiceName,
                                    (struct _NDIS_FILTER_BLOCK *)v16,
                                    v12);
          if ( FilterAdapterRegistry )
            goto LABEL_199;
        }
        *(_QWORD *)(v16 + 752) = a4;
        *(_BYTE *)(v16 + 64) = 1;
        Ndis::BindEngine::BeginPolicyUpdates(&v12->BindEngine);
        Ndis::BindState::AddBindContext(&a4->BindState, (void *)v16);
        Ndis::BindEngine::EndPolicyUpdates(&v12->BindEngine);
        memset(&v125, 0, sizeof(v125));
        v38 = *(_QWORD *)(v16 + 16);
        if ( *(_BYTE *)(v38 + 100) > 6u )
          goto LABEL_79;
        v39 = *(_BYTE *)(v38 + 101);
        if ( !v39 )
        {
          v40 = 1;
          v125.Header.Size = 164;
          goto LABEL_80;
        }
        if ( v39 < 0x14u )
        {
          v40 = 2;
          v125.Header.Size = 176;
          goto LABEL_80;
        }
        if ( v39 >= 0x1Eu )
        {
LABEL_79:
          v125.Header.Size = 224;
          v40 = 4;
        }
        else
        {
          v40 = 3;
          v125.Header.Size = 200;
        }
LABEL_80:
        v41 = *(_QWORD *)(v16 + 112);
        v125.Header.Revision = v40;
        v125.Header.Type = -103;
        v125.BaseMiniportIfIndex = BaseMiniport->IfIndex;
        v125.BaseMiniportNetLuid.Value = BaseMiniport->NetLuid.Value;
        v125.BaseMiniportName = &BaseMiniport->MiniportName;
        v125.BaseMiniportInstanceName = BaseMiniport->pAdapterInstanceName;
        if ( v41 )
        {
          v125.LowerIfIndex = *(_DWORD *)(v41 + 680);
          v125.LowerIfNetLuid.Value = *(_QWORD *)(*(_QWORD *)(v41 + 688) + 1312LL);
        }
        else
        {
          v42 = *(_QWORD *)(v16 + 32);
          v125.LowerIfIndex = *(_DWORD *)(v42 + 4056);
          v125.LowerIfNetLuid.Value = *(_QWORD *)(v42 + 4024);
        }
        v125.FilterModuleGuidName = *(_UNICODE_STRING **)(v16 + 40);
        v125.MiniportMediaSpecificAttributes = v12->MediaSpecificAttributes;
        if ( (v12->MacOptions & 0x80000001) == 0x80000001 )
        {
          MiniportPhysicalMediumType = v12->MiniportPhysicalMediumType;
          v125.MiniportMediaType = NdisMediumWan;
        }
        else if ( v33 )
        {
          v125.MiniportMediaType = v33->MediaType;
          MiniportPhysicalMediumType = v33->PhysicalMediaType;
        }
        else
        {
          v125.MiniportMediaType = v12->MiniportMediaType;
          MiniportPhysicalMediumType = v12->MiniportPhysicalMediumType;
        }
        v125.MiniportPhysicalMediaType = MiniportPhysicalMediumType;
        if ( v41 )
        {
          v125.MediaConnectState = *(_DWORD *)(v41 + 380);
          v125.MediaDuplexState = *(_DWORD *)(v41 + 384);
          v125.XmitLinkSpeed = *(_QWORD *)(v41 + 392);
          v125.RcvLinkSpeed = *(_QWORD *)(v41 + 400);
          if ( *(_QWORD *)(v41 + 656) )
          {
            v125.DefaultOffloadConfiguration = *(_NDIS_OFFLOAD **)(v41 + 656);
LABEL_95:
            HDSplitCurrentConfig = v125.HDSplitCurrentConfig;
            if ( v12->HDSplitCurrentConfig )
              HDSplitCurrentConfig = v12->HDSplitCurrentConfig;
            v125.HDSplitCurrentConfig = HDSplitCurrentConfig;
            if ( v41 )
            {
              SriovHwCapabilities = (_NDIS_SRIOV_CAPABILITIES *)(v41 + 960);
              SriovCurrentCapabilities = (_NDIS_SRIOV_CAPABILITIES *)(v41 + 972);
              NicSwitchHwCapabilities = (_NDIS_NIC_SWITCH_CAPABILITIES *)(v41 + 984);
              NicSwitchCurrentCapabilities = (_NDIS_NIC_SWITCH_CAPABILITIES *)(v41 + 1116);
              ReceiveFilterHwCapabilities = (_NDIS_RECEIVE_FILTER_CAPABILITIES *)(v41 + 1248);
              ReceiveFilterCurrentCapabilities = (_NDIS_RECEIVE_FILTER_CAPABILITIES *)(v41 + 1332);
              if ( !SriovHwCapabilities->Header.Size )
                SriovHwCapabilities = 0;
              if ( !SriovCurrentCapabilities->Header.Size )
                SriovCurrentCapabilities = 0;
              if ( !NicSwitchHwCapabilities->Header.Size )
                NicSwitchHwCapabilities = 0;
              if ( !NicSwitchCurrentCapabilities->Header.Size )
                NicSwitchCurrentCapabilities = 0;
              if ( !ReceiveFilterHwCapabilities->Header.Size )
                ReceiveFilterHwCapabilities = 0;
              if ( !ReceiveFilterCurrentCapabilities->Header.Size )
                ReceiveFilterCurrentCapabilities = 0;
            }
            else
            {
              SriovHwCapabilities = v12->SriovHwCapabilities;
              SriovCurrentCapabilities = v12->SriovCurrentCapabilities;
              NicSwitchHwCapabilities = v12->NicSwitchHwCapabilities;
              NicSwitchCurrentCapabilities = v12->NicSwitchCurrentCapabilities;
              ReceiveFilterHwCapabilities = v12->ReceiveFilterHwCapabilities;
              ReceiveFilterCurrentCapabilities = v12->ReceiveFilterCurrentCapabilities;
            }
            if ( SriovHwCapabilities )
            {
              *(_QWORD *)(v16 + 960) = *(_QWORD *)&SriovHwCapabilities->Header.Type;
              *(_DWORD *)(v16 + 968) = SriovHwCapabilities->SriovCapabilities;
            }
            if ( SriovCurrentCapabilities )
            {
              *(_QWORD *)(v16 + 972) = *(_QWORD *)&SriovCurrentCapabilities->Header.Type;
              *(_DWORD *)(v16 + 980) = SriovCurrentCapabilities->SriovCapabilities;
            }
            if ( NicSwitchHwCapabilities )
            {
              *(_OWORD *)(v16 + 984) = *(_OWORD *)&NicSwitchHwCapabilities->Header.Type;
              *(_OWORD *)(v16 + 1000) = *(_OWORD *)&NicSwitchHwCapabilities->NumMacAddressesPerPort;
              *(_OWORD *)(v16 + 1016) = *(_OWORD *)&NicSwitchHwCapabilities->NicSwitchCapabilities;
              *(_OWORD *)(v16 + 1032) = *(_OWORD *)&NicSwitchHwCapabilities->MaxNumVFs;
              *(_OWORD *)(v16 + 1048) = *(_OWORD *)&NicSwitchHwCapabilities->NdisReserved7;
              *(_OWORD *)(v16 + 1064) = *(_OWORD *)&NicSwitchHwCapabilities->NdisReserved10;
              *(_OWORD *)(v16 + 1080) = *(_OWORD *)&NicSwitchHwCapabilities->NdisReserved13;
              *(_OWORD *)(v16 + 1096) = *(_OWORD *)&NicSwitchHwCapabilities->NdisReserved17;
              *(_DWORD *)(v16 + 1112) = NicSwitchHwCapabilities->MaxNumQueuePairsForDefaultVPort;
            }
            if ( NicSwitchCurrentCapabilities )
            {
              *(_OWORD *)(v16 + 1116) = *(_OWORD *)&NicSwitchCurrentCapabilities->Header.Type;
              *(_OWORD *)(v16 + 1132) = *(_OWORD *)&NicSwitchCurrentCapabilities->NumMacAddressesPerPort;
              *(_OWORD *)(v16 + 1148) = *(_OWORD *)&NicSwitchCurrentCapabilities->NicSwitchCapabilities;
              *(_OWORD *)(v16 + 1164) = *(_OWORD *)&NicSwitchCurrentCapabilities->MaxNumVFs;
              *(_OWORD *)(v16 + 1180) = *(_OWORD *)&NicSwitchCurrentCapabilities->NdisReserved7;
              *(_OWORD *)(v16 + 1196) = *(_OWORD *)&NicSwitchCurrentCapabilities->NdisReserved10;
              *(_OWORD *)(v16 + 1212) = *(_OWORD *)&NicSwitchCurrentCapabilities->NdisReserved13;
              *(_OWORD *)(v16 + 1228) = *(_OWORD *)&NicSwitchCurrentCapabilities->NdisReserved17;
              *(_DWORD *)(v16 + 1244) = NicSwitchCurrentCapabilities->MaxNumQueuePairsForDefaultVPort;
            }
            if ( ReceiveFilterHwCapabilities )
            {
              *(_OWORD *)(v16 + 1248) = *(_OWORD *)&ReceiveFilterHwCapabilities->Header.Type;
              *(_OWORD *)(v16 + 1264) = *(_OWORD *)&ReceiveFilterHwCapabilities->NumQueues;
              *(_OWORD *)(v16 + 1280) = *(_OWORD *)&ReceiveFilterHwCapabilities->SupportedMacHeaderFields;
              *(_OWORD *)(v16 + 1296) = *(_OWORD *)&ReceiveFilterHwCapabilities->MinLookaheadSplitSize;
              *(_OWORD *)(v16 + 1312) = *(_OWORD *)&ReceiveFilterHwCapabilities->SupportedIPv6HeaderFields;
              *(_DWORD *)(v16 + 1328) = ReceiveFilterHwCapabilities->NdisReserved;
            }
            if ( ReceiveFilterCurrentCapabilities )
            {
              *(_OWORD *)(v16 + 1332) = *(_OWORD *)&ReceiveFilterCurrentCapabilities->Header.Type;
              *(_OWORD *)(v16 + 1348) = *(_OWORD *)&ReceiveFilterCurrentCapabilities->NumQueues;
              *(_OWORD *)(v16 + 1364) = *(_OWORD *)&ReceiveFilterCurrentCapabilities->SupportedMacHeaderFields;
              *(_OWORD *)(v16 + 1380) = *(_OWORD *)&ReceiveFilterCurrentCapabilities->MinLookaheadSplitSize;
              *(_OWORD *)(v16 + 1396) = *(_OWORD *)&ReceiveFilterCurrentCapabilities->SupportedIPv6HeaderFields;
              *(_DWORD *)(v16 + 1412) = ReceiveFilterCurrentCapabilities->NdisReserved;
              v125.ReceiveFilterCapabilities = ReceiveFilterCurrentCapabilities;
            }
            NicSwitchCapabilities = v125.NicSwitchCapabilities;
            if ( NicSwitchCurrentCapabilities )
              NicSwitchCapabilities = NicSwitchCurrentCapabilities;
            v125.NicSwitchCapabilities = NicSwitchCapabilities;
            if ( v40 < 4u )
            {
LABEL_130:
              IfBlock = v12->IfBlock;
              v125.MiniportPhysicalDeviceObject = v12->PhysicalDeviceObject;
              v125.MacAddressLength = IfBlock->ifPhysAddress.Length;
              memmove(v125.CurrentMacAddress, IfBlock->ifPhysAddress.Address, v125.MacAddressLength);
              MediaConnectState = v125.MediaConnectState;
              *(_DWORD *)(v16 + 348) = v125.MediaDuplexState;
              *(_QWORD *)(v16 + 352) = v125.XmitLinkSpeed;
              *(_QWORD *)(v16 + 360) = v125.RcvLinkSpeed;
              *(_DWORD *)(v16 + 344) = MediaConnectState;
              if ( MediaConnectState == MediaConnectStateConnected )
              {
                v55 = (void (__stdcall *)(PVOID))ndisFilterCancelSendNetBufferLists;
                v56 = (void (__usercall *)(struct _NDIS_OBJECT_HEADER *@<rcx>, struct _NET_BUFFER_LIST *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int))ndisFilterIndicateReceiveNetBufferLists;
                v57 = ndisFilterSendNetBufferLists;
              }
              else
              {
                ndisFilterXStateSetFlag((struct _NDIS_FILTER_BLOCK *)v16, 1u);
                v55 = NdisQueryOffloadState;
                v56 = ndisFakeFilterReceiveHandler;
                v57 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))ndisFakeFilterSendHandler;
              }
              *(_QWORD *)(v16 + 624) = v57;
              *(_QWORD *)(v16 + 632) = v56;
              *(_QWORD *)(v16 + 640) = v55;
              if ( (v12->MacOptions & 0x80000001) == 0x80000001 )
                MediaType = v12->MediaType;
              else
                MediaType = v125.MiniportMediaType;
              *(_DWORD *)(v16 + 336) = MediaType;
              *(_DWORD *)(v16 + 340) = v125.MiniportPhysicalMediaType;
              FilterAdapterRegistry = ndisIfCreateFilterInterface((struct _NDIS_FILTER_BLOCK *)v16);
              if ( !FilterAdapterRegistry )
              {
                if ( !(unsigned int)Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline()
                  || (FilterAdapterRegistry = ndisRegisterFilterTriageData(v16)) == 0 )
                {
                  if ( (byte_140121003 & 1) != 0 )
                    McTemplateK0juqjzzz_EtwWriteTransfer(
                      *(_QWORD *)(v16 + 32) + 4008,
                      *(_QWORD *)(v16 + 40),
                      v16 + 664,
                      v16 + 664,
                      *(_BYTE *)(v16 + 64),
                      6,
                      *(_QWORD *)(v16 + 32) + 4008LL,
                      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 32) + 3856LL) + 8LL),
                      *(_QWORD *)(*(_QWORD *)(v16 + 40) + 8LL),
                      *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL));
                  if ( Microsoft_Windows_Networking_CorrelationEnabled )
                  {
                    v60 = (const GUID *)(v16 + 664);
                    *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
                    p_InterfaceGuid = &v12->InterfaceGuid;
                    Data2 = 0;
                    EventDescriptor.Keyword = 0x8000000000000001uLL;
                    if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
                    {
                      *(_QWORD *)&UserData.Size = 16;
                      UserData.Ptr = (unsigned __int64)&Microsoft_Windows_Networking_ProviderId;
                      p_Data2 = &Data2;
                      v130 = 4;
                      EtwWriteTransfer(
                        Microsoft_Windows_Networking_CorrelationHandle,
                        &EventDescriptor,
                        v60,
                        p_InterfaceGuid,
                        2u,
                        &UserData);
                    }
                    else
                    {
                      EtwWriteTransfer(
                        Microsoft_Windows_Networking_CorrelationHandle,
                        &EventDescriptor,
                        v60,
                        p_InterfaceGuid,
                        0,
                        0);
                    }
                  }
                  v125.IfIndex = *(_DWORD *)(v16 + 680);
                  v125.NetLuid.Value = *(_QWORD *)(*(_QWORD *)(v16 + 688) + 1312LL);
                  v62 = ndisFInvokeAttach((struct _NDIS_FILTER_BLOCK *)v16, &v125);
                  FilterAdapterRegistry = v62;
                  v64 = &WPP_RECORDER_INITIALIZED;
                  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    WPP_RECORDER_SF_qqZddZD(
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      v14->DefaultFilterCharacteristics.MajorNdisVersion,
                      (_DWORD)v14 + 112,
                      v63,
                      UserDataCount,
                      (char)v12,
                      v16,
                      (__int64)&v14->DefaultFilterCharacteristics.FriendlyName,
                      v14->DefaultFilterCharacteristics.MajorNdisVersion,
                      v14->DefaultFilterCharacteristics.MinorNdisVersion,
                      (__int64)v12->pAdapterInstanceName,
                      v62);
                    v64 = &WPP_RECORDER_INITIALIZED;
                  }
                  if ( !FilterAdapterRegistry )
                  {
                    v71 = *(_DWORD *)(v16 + 336);
                    MiniportMediaType = v125.MiniportMediaType;
                    v107 = 0;
                    if ( v71 != v125.MiniportMediaType && (v12->MacOptions & 0x80000001) != 0x80000001 )
                    {
                      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                      {
                        LOBYTE(v64) = 4;
                        WPP_RECORDER_SF_qqLd(
                          *((_QWORD *)WPP_GLOBAL_Control + 8),
                          (int)v64,
                          13,
                          27,
                          (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
                          (char)v12,
                          v16,
                          v71,
                          v125.MiniportMediaType);
                        MiniportMediaType = v125.MiniportMediaType;
                      }
                      if ( Microsoft_Windows_NDISEnableBits < 0 )
                        McTemplateK0jqxjqxdd_EtwWriteTransfer(
                          *(_QWORD *)(v16 + 688),
                          v16 + 664,
                          (_DWORD)v12 + 4008,
                          (_DWORD)v12 + 4008,
                          v12->IfIndex,
                          v12->NetLuid.Value,
                          v16 + 664,
                          *(_DWORD *)(v16 + 680),
                          *(_QWORD *)(*(_QWORD *)(v16 + 688) + 1312LL),
                          *(_DWORD *)(v16 + 336),
                          MiniportMediaType);
                      v107 = 1;
                    }
                    v73 = *(_QWORD *)(v16 + 120);
                    if ( v73 )
                    {
                      v74 = *(_QWORD *)(v16 + 112);
                      if ( v74 )
                        IfIndex = *(_DWORD *)(v74 + 680);
                      else
                        IfIndex = v12->IfIndex;
                      NdisIfDeleteIfStackEntry(*(_DWORD *)(v73 + 680), IfIndex);
                    }
                    v76 = *(_QWORD *)(v16 + 112);
                    if ( v76 )
                      v77 = *(_DWORD *)(v76 + 680);
                    else
                      v77 = *(_DWORD *)(*(_QWORD *)(v16 + 32) + 4056LL);
                    NdisIfAddIfStackEntry(*(_DWORD *)(v16 + 680), v77);
                    v78 = *(_QWORD *)(v16 + 120);
                    if ( v78 )
                      NdisIfAddIfStackEntry(*(_DWORD *)(v78 + 680), *(_DWORD *)(v16 + 680));
                    v79 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
                    ndisIfUpdateFilterIfStack(*(struct _NDIS_MINIPORT_BLOCK **)(v16 + 32));
                    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v79);
                    v80 = *(_QWORD *)(v16 + 112);
                    if ( v80 )
                    {
                      v81 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v80 + 144));
                      *(_QWORD *)(v80 + 152) = KeGetCurrentThread();
                      v82 = v81;
                      *(_DWORD *)(v16 + 344) = *(_DWORD *)(v80 + 380);
                      *(_DWORD *)(v16 + 348) = *(_DWORD *)(v80 + 384);
                      *(_QWORD *)(v16 + 352) = *(_QWORD *)(v80 + 392);
                      *(_QWORD *)(v16 + 360) = *(_QWORD *)(v80 + 400);
                      *(_DWORD *)(v16 + 368) = *(_DWORD *)(v80 + 408);
                      *(_DWORD *)(v16 + 372) = *(_DWORD *)(v80 + 412);
                      ndisOpenRef((PKSPIN_LOCK)(v16 + 312));
                      p_Lock = (KSPIN_LOCK *)(v80 + 144);
                      *(_QWORD *)(v80 + 152) = 0;
                    }
                    else
                    {
                      v84 = KeAcquireSpinLockRaiseToDpc(&v12->Lock);
                      CurrentThread = KeGetCurrentThread();
                      v82 = v84;
                      *(_DWORD *)(v16 + 348) = v12->MiniportMediaDuplexState;
                      *(_QWORD *)(v16 + 352) = v12->MiniportXmitLinkSpeed;
                      *(_QWORD *)(v16 + 360) = v12->MiniportRcvLinkSpeed;
                      MiniportPauseFunctions = v12->MiniportPauseFunctions;
                      v12->MiniportThread = CurrentThread;
                      LODWORD(CurrentThread) = v12->MiniportMediaConnectState;
                      *(_DWORD *)(v16 + 368) = MiniportPauseFunctions;
                      MiniportAutoNegotiationFlags = v12->MiniportAutoNegotiationFlags;
                      *(_DWORD *)(v16 + 344) = (_DWORD)CurrentThread;
                      *(_DWORD *)(v16 + 372) = MiniportAutoNegotiationFlags;
                      ndisOpenRef((PKSPIN_LOCK)(v16 + 312));
                      p_Lock = &v12->Lock;
                      v12->MiniportThread = 0;
                    }
                    KeReleaseSpinLock(p_Lock, v82);
                    *(_DWORD *)(*(_QWORD *)(v16 + 688) + 1220LL) = *(_DWORD *)(v16 + 344);
                    *(_DWORD *)(*(_QWORD *)(v16 + 688) + 1224LL) = *(_DWORD *)(v16 + 348);
                    *(_QWORD *)(*(_QWORD *)(v16 + 688) + 1208LL) = *(_QWORD *)(v16 + 360);
                    *(_QWORD *)(*(_QWORD *)(v16 + 688) + 1200LL) = *(_QWORD *)(v16 + 352);
                    ndisIndicateInitialStateToFilter((struct _NDIS_FILTER_BLOCK *)v16);
                    KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 144));
                    *(_QWORD *)(v16 + 152) = KeGetCurrentThread();
                    FILTER_CLEAR_ALL_STATE_FLAGS((struct _NDIS_FILTER_BLOCK *)v16);
                    FILTER_SET_FLAG(v88, 4u);
                    if ( v107 )
                    {
                      FILTER_SET_FLAG(v89, 0x8000u);
                      MiniportPhysicalMediaType = v125.MiniportPhysicalMediaType;
                      v92 = v125.MiniportMediaType;
                      ++v12->MediaChangeFilters;
                      *(_DWORD *)(v16 + 340) = MiniportPhysicalMediaType;
                      v93 = *(_QWORD *)(v16 + 688);
                      *(_DWORD *)(v16 + 336) = v92;
                      *(_DWORD *)(v93 + 564) = v92;
                      *(_DWORD *)(*(_QWORD *)(v16 + 688) + 568LL) = *(_DWORD *)(v16 + 340);
                      *(_QWORD *)(v16 + 152) = 0;
                      KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 144), v94);
                      v95 = *(_DWORD *)(v16 + 336);
                      v96 = *(_DWORD *)(v16 + 340);
                      v12->MediaType = v95;
                      v12->PhysicalMediumType = v96;
                      if ( v95 == NdisMedium802_3
                        && EthAddConversionFilter(
                             v12->TopFilterRestartAttributes.MaxMulticastListSize,
                             v12->IfBlock->ifPhysAddress.Address,
                             v12->EthDB) )
                      {
                        v12->EthDB->Miniport = v12;
                        v12->HasConversionFilter = 1;
                      }
                    }
                    else
                    {
                      *(_QWORD *)(v16 + 152) = 0;
                      KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 144), v90);
                    }
                    v70 = (byte_140121003 & 1) == 0;
                    *(_BYTE *)(v16 + 64) = 2;
                    if ( !v70 )
                      McTemplateK0juqjzzz_EtwWriteTransfer(
                        *(_QWORD *)(v16 + 32) + 4008,
                        *(_QWORD *)(v16 + 40),
                        v16 + 664,
                        v16 + 664,
                        2,
                        8,
                        *(_QWORD *)(v16 + 32) + 4008LL,
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 32) + 3856LL) + 8LL),
                        *(_QWORD *)(*(_QWORD *)(v16 + 40) + 8LL),
                        *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL));
                    ndisPktMonFilterRegister(v16);
                    ndisReferenceMiniport(v12, MPREF_LWF_ATTACHED);
                    if ( v12->MajorNdisVersion < 6u && !v12->Miniport5HasNdis6Component )
                      v12->Miniport5HasNdis6Component = 1;
                    ndisSetupWmiNode(
                      v12,
                      *(const struct _UNICODE_STRING **)(v16 + 48),
                      v12->BindPaths->Paths[0].Length + v14->DefaultFilterCharacteristics.UniqueName.Length + 4,
                      &GUID_NDIS_NOTIFY_FILTER_ARRIVAL,
                      (struct tagWNODE_SINGLE_INSTANCE **)WnodeEventItem);
                    v97 = WnodeEventItem[0];
                    if ( WnodeEventItem[0] )
                    {
                      v98 = (char *)WnodeEventItem[0] + *((unsigned int *)WnodeEventItem[0] + 14);
                      memmove(
                        v98,
                        v14->DefaultFilterCharacteristics.UniqueName.Buffer,
                        v14->DefaultFilterCharacteristics.UniqueName.Length);
                      memmove(
                        &v98[v14->DefaultFilterCharacteristics.UniqueName.Length + 2],
                        v12->BindPaths->Paths[0].Buffer,
                        v12->BindPaths->Paths[0].Length);
                      v101 = IoWMIWriteEvent(v97);
                      if ( v101 < 0 )
                      {
                        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v99) = 2;
                          WPP_RECORDER_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 8),
                            v99,
                            1,
                            28,
                            (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids);
                        }
                        if ( (byte_140121001 & 1) != 0 )
                          McTemplateK0qqq_EtwWriteTransfer(
                            v100,
                            (unsigned int)FilterArrivalIndicationFailed,
                            v16 + 664,
                            v101,
                            1,
                            0);
                        ExFreePoolWithTag(v97, 0);
                      }
                    }
                    Ndis::BindEngine::BeginPolicyUpdates(&v12->BindEngine);
                    v13 = a4;
                    if ( Ndis::BindState::SetPause(&a4->BindState, DatapathRunning, PauseReason_InitialPause) )
                    {
                      memset(v126, 0, sizeof(v126));
                      if ( (unsigned __int8)byte_140122AD3 >= 4u )
                      {
                        ndisGetBindLinkNameForTracing(a4, (struct NDIS_PNPTRACE_LOCALS *)v126);
                        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                          WPP_RECORDER_SF_Zq(
                            *((_QWORD *)WPP_GLOBAL_Control + 8),
                            v102,
                            28,
                            29,
                            (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
                            *(__int64 *)&v126[8],
                            v126[0]);
                      }
                    }
                    Ndis::BindEngine::EndPolicyUpdates(&v12->BindEngine);
                    if ( v12->MajorNdisVersion < 6u && !v12->Miniport5HasNdis6Component )
                      v12->Miniport5HasNdis6Component = 1;
                    goto LABEL_10;
                  }
                  v13 = a4;
                  v65 = 1;
                  a4->BindState.AllowBindDespiteMandatory = v125.Flags & 1;
                  KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 144));
                  *(_QWORD *)(v16 + 152) = KeGetCurrentThread();
                  FILTER_CLEAR_ALL_STATE_FLAGS((struct _NDIS_FILTER_BLOCK *)v16);
                  if ( FILTER_TEST_FLAG(v66, 0x100u) )
                    FILTER_CLEAR_FLAG(v68, v67);
                  FILTER_SET_FLAG((struct _NDIS_FILTER_BLOCK *)v16, 8u);
                  *(_QWORD *)(v16 + 152) = 0;
                  KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 144), v69);
                  v70 = (byte_140121003 & 1) == 0;
                  *(_BYTE *)(v16 + 64) = 0;
                  if ( !v70 )
                    McTemplateK0juqjzzz_EtwWriteTransfer(
                      *(_QWORD *)(v16 + 32) + 4008,
                      *(_QWORD *)(v16 + 40),
                      v16 + 664,
                      v16 + 664,
                      0,
                      7,
                      *(_QWORD *)(v16 + 32) + 4008LL,
                      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 32) + 3856LL) + 8LL),
                      *(_QWORD *)(*(_QWORD *)(v16 + 40) + 8LL),
                      *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL));
LABEL_201:
                  if ( *(_QWORD *)(v16 + 752) )
                  {
                    Ndis::BindEngine::BeginPolicyUpdates(&v12->BindEngine);
                    Ndis::BindState::RemoveBindContext(&v13->BindState, (void *)v16);
                    Ndis::BindEngine::EndPolicyUpdates(&v12->BindEngine);
                    *(_QWORD *)(v16 + 752) = 0;
                  }
                  v103 = v12;
                  if ( !v106 )
                    v103 = 0;
                  ndisFilterAttachCleanUp((_NDIS_FILTER_BLOCK *)v16, v103, v65);
                  goto LABEL_206;
                }
                if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v59) = 2;
                  WPP_RECORDER_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    v59,
                    13,
                    25,
                    (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
                    v16,
                    FilterAdapterRegistry);
                }
              }
              goto LABEL_199;
            }
            if ( !SriovCurrentCapabilities
              || (v125.SriovCapabilities = SriovCurrentCapabilities,
                  !(unsigned int)ndisIovGetNicSwitchList(
                                   v12,
                                   NicSwitchCurrentCapabilities,
                                   SriovCurrentCapabilities,
                                   &v125.NicSwitchArray)) )
            {
              v125.BaseMiniportIfConnectorPresent = v12->IfBlock->ifConnectorPresent;
              goto LABEL_130;
            }
LABEL_198:
            FilterAdapterRegistry = -1073741823;
            goto LABEL_199;
          }
        }
        else
        {
          v125.MediaConnectState = v12->MiniportMediaConnectState;
          v125.MediaDuplexState = v12->MiniportMediaDuplexState;
          v125.XmitLinkSpeed = v12->MiniportXmitLinkSpeed;
          v125.RcvLinkSpeed = v12->MiniportRcvLinkSpeed;
          Offload = v12->Offload;
          if ( Offload && Offload->SupportsOffload )
          {
            v125.DefaultOffloadConfiguration = &Offload->MiniportCurrentConfig;
            goto LABEL_95;
          }
        }
        v125.DefaultOffloadConfiguration = 0;
        goto LABEL_95;
      }
    }
    else if ( ndisDatapathVerifierMode != 2 )
    {
      goto LABEL_49;
    }
    FILTER_SET_FLAG((struct _NDIS_FILTER_BLOCK *)v16, 0x200u);
    goto LABEL_49;
  }
  v14 = v121;
  FilterAdapterRegistry = -1073741823;
LABEL_9:
  v16 = *(_QWORD *)v120;
LABEL_10:
  if ( ndisVerifierNdisDispatch
    && v16
    && MmIsDriverVerifying(*(struct _DRIVER_OBJECT **)(*(_QWORD *)(v16 + 16) + 16LL))
    && !*(_QWORD *)(v16 + 776)
    && (*((int (__fastcall **)(_DRIVER_OBJECT *, __int64, void **))ndisVerifierNdisDispatch + 1))(
         v14->DriverObject,
         v16,
         &v14->FilterDriverContext) < 0
    && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v17,
      13,
      30,
      (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
      v16);
  }
LABEL_206:
  ndisHandleFilterHandlersChange(v12);
  if ( v125.NicSwitchArray )
  {
    ExFreePoolWithTag(v125.NicSwitchArray, 0);
    v125.NicSwitchArray = 0;
  }
  if ( FilterAdapterRegistry
    && !v13->BindState.AllowBindDespiteMandatory
    && (v13->BindDriver._p->_t.FilterBindFlags & 1) == 0 )
  {
    ndisNotifyBindFailureOnUnboundProtocols(v12);
  }
  ndisDereferenceMiniport(v12, MPREF_LWF_ATTACHING);
  ndisDereferenceFilterDriver(v14, 0, LWFDRV_ATTACHING);
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v104) = 4;
    WPP_RECORDER_SF_qql(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v104,
      1,
      31,
      (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
      (char)v14,
      (char)v12,
      FilterAdapterRegistry);
  }
  return FilterAdapterRegistry;
}

```

## disassembly

```asm
0x140186f10  push    rbp
0x140186f12  push    rbx
0x140186f13  push    rdi
0x140186f14  push    r13
0x140186f16  push    r14
0x140186f18  lea     rbp, [rsp-290h]
0x140186f20  sub     rsp, 3E0h
0x140186f27  mov     rax, cs:__security_cookie
0x140186f2e  xor     rax, rsp
0x140186f31  mov     [rbp+2B0h+var_50], rax
0x140186f38  xor     edi, edi
0x140186f3a  mov     [rbp+2B0h+var_310], r8d
0x140186f3e  mov     rbx, rdx
0x140186f41  mov     [rbp+2B0h+var_2E0], rdx
0x140186f45  mov     r13, rcx
0x140186f48  mov     [rbp+2B0h+var_318], rcx
0x140186f4c  xor     edx, edx; Val
0x140186f4e  mov     [rbp+2B0h+var_2D8], rdi
0x140186f52  mov     r8d, 0DFh; Size
0x140186f58  mov     [rbp+2B0h+var_2D0], rdi
0x140186f5c  lea     rcx, [rbp+2B0h+var_2B0.Header.Revision]; void *
0x140186f60  mov     [rbp+2B0h+var_2B0.Header.Type], dil
0x140186f64  mov     r14, r9
0x140186f67  mov     [rbp+2B0h+var_328], r9
0x140186f6b  call    memset
0x140186f70  xor     edx, edx; enum _NDIS_LWFDRV_REFTAG
0x140186f72  mov     [rbp+2B0h+var_2F0], edi
0x140186f75  mov     rcx, rbx; struct _NDIS_FILTER_DRIVER_BLOCK *
0x140186f78  mov     [rbp+2B0h+WnodeEventItem], rdi
0x140186f7c  call    ?ndisReferenceFilterDriver@@YAEPEAU_NDIS_FILTER_DRIVER_BLOCK@@W4_NDIS_LWFDRV_REFTAG@@@Z; ndisReferenceFilterDriver(_NDIS_FILTER_DRIVER_BLOCK *,_NDIS_LWFDRV_REFTAG)
0x140186f81  test    al, al
0x140186f83  jz      short loc_140186FA0
0x140186f85  mov     dl, 27h ; '''; enum _NDIS_MP_REFTAG
0x140186f87  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140186f8a  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140186f8f  test    al, al
0x140186f91  jnz     short loc_140186FAA
0x140186f93  xor     r8d, r8d; enum _NDIS_LWFDRV_REFTAG
0x140186f96  xor     edx, edx; unsigned __int8
0x140186f98  mov     rcx, rbx; this
0x140186f9b  call    ?ndisDereferenceFilterDriver@@YAXPEAU_NDIS_FILTER_DRIVER_BLOCK@@EW4_NDIS_LWFDRV_REFTAG@@@Z; ndisDereferenceFilterDriver(_NDIS_FILTER_DRIVER_BLOCK *,uchar,_NDIS_LWFDRV_REFTAG)
0x140186fa0  mov     eax, 0C0010002h
0x140186fa5  jmp     loc_14018894B
0x140186faa  mov     [rsp+400h+var_28], rsi; __annotation("TMF:",
0x140186fb2  lea     rax, WPP_RECORDER_INITIALIZED
0x140186fb9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140186fc0  lea     rcx, WPP_4f475340cee13bebfed3041a3a58f669_Traceguids
0x140186fc7  mov     [rsp+400h+var_30], r12
0x140186fcf  mov     [rsp+400h+var_38], r15
0x140186fd7  mov     qword ptr [rbp+2B0h+var_2E8], rdi
0x140186fdb  jz      short loc_140187013
0x140186fdd  lea     rax, [rbx+70h]
0x140186fe1  mov     r9d, 18h; int
0x140186fe7  mov     qword ptr [rsp+400h+var_3C8], rax; __int64
0x140186fec  mov     r8d, 1; int
0x140186ff2  mov     qword ptr [rsp+400h+var_3D0], r13; char
0x140186ff7  mov     dl, 4; int
0x140186ff9  mov     [rsp+400h+UserData], rbx; char
0x140186ffe  mov     qword ptr [rsp+400h+UserDataCount], rcx; struct _GUID *
0x140187003  mov     rcx, cs:WPP_GLOBAL_Control
0x14018700a  mov     rcx, [rcx+40h]; int
0x14018700e  call    WPP_RECORDER_SF_qqZ
0x140187013  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14018701a  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14018701f  mov     rsi, [r14+50h]
0x140187023  lea     rax, [r13+0FA8h]
0x14018702a  movzx   r14d, byte ptr [r13+0FB7h]
0x140187032  movzx   r15d, byte ptr [r13+0FB6h]
0x14018703a  movzx   r12d, byte ptr [r13+0FB5h]
0x140187042  movzx   ecx, byte ptr [rsi+26h]
0x140187046  movzx   edx, byte ptr [rsi+25h]
0x14018704a  movzx   r8d, byte ptr [rsi+24h]
0x14018704f  movzx   r9d, byte ptr [rsi+23h]
0x140187054  movzx   r10d, byte ptr [rsi+22h]
0x140187059  movzx   r11d, byte ptr [rsi+21h]
0x14018705e  movzx   ebx, byte ptr [rsi+20h]
0x140187062  movzx   edi, word ptr [rsi+1Eh]
0x140187066  movzx   r13d, byte ptr [r13+0FB4h]
0x14018706e  mov     qword ptr [rbp+2B0h+EventDescriptor.Id], rax
0x140187075  movzx   eax, byte ptr [rsi+27h]
0x140187079  mov     [rbp+2B0h+var_30C], r14d
0x14018707d  mov     r14, [rbp+2B0h+var_318]
0x140187081  mov     [rbp+2B0h+var_308], r15d
0x140187085  mov     r15, [rbp+2B0h+var_318]
0x140187089  mov     [rbp+2B0h+var_2C0], rsi
0x14018708d  movzx   r14d, byte ptr [r14+0FB3h]
0x140187095  movzx   esi, word ptr [rsi+1Ch]
0x140187099  mov     [rbp+2B0h+var_304], r14d
0x14018709d  movzx   r14d, byte ptr [r15+0FB2h]
0x1401870a5  mov     [rbp+2B0h+var_300], r14d
0x1401870a9  movzx   r14d, byte ptr [r15+0FB1h]
0x1401870b1  mov     [rbp+2B0h+var_2FC], r14d
0x1401870b5  movzx   r14d, byte ptr [r15+0FB0h]
0x1401870bd  mov     [rbp+2B0h+var_2F8], r14d
0x1401870c1  movzx   r14d, word ptr [r15+0FAEh]
0x1401870c9  mov     [rbp+2B0h+var_2F4], r14d
0x1401870cd  movzx   r14d, word ptr [r15+0FACh]
0x1401870d5  mov     r15d, [rbp+2B0h+var_308]
0x1401870d9  mov     [rbp+2B0h+var_320], r14d
0x1401870dd  mov     r14d, [rbp+2B0h+var_310]
0x1401870e1  mov     [rsp+400h+var_338], r14d
0x1401870e9  mov     r14d, [rbp+2B0h+var_30C]
0x1401870ed  mov     [rsp+400h+var_340], eax
0x1401870f4  mov     rax, [rbp+2B0h+var_2C0]
0x1401870f8  mov     [rsp+400h+var_348], ecx
0x1401870ff  lea     rcx, [rbp+2B0h+var_100]; wchar_t *
0x140187106  mov     [rsp+400h+var_350], edx
0x14018710d  mov     edx, 0A8h; unsigned __int64
0x140187112  mov     [rsp+400h+var_358], r8d
0x14018711a  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140187121  mov     eax, [rax+18h]
0x140187124  mov     [rsp+400h+var_360], r9d
0x14018712c  mov     [rsp+400h+var_368], r10d
0x140187134  mov     [rsp+400h+var_370], r11d
0x14018713c  mov     [rsp+400h+var_378], ebx
0x140187143  mov     [rsp+400h+var_380], edi
0x14018714a  mov     [rsp+400h+var_388], esi
0x14018714e  mov     [rsp+400h+var_390], eax
0x140187152  mov     eax, [rbp+2B0h+var_304]
0x140187155  mov     [rsp+400h+var_398], r14d
0x14018715a  mov     [rsp+400h+var_3A0], r15d
0x14018715f  mov     [rsp+400h+var_3A8], r12d
0x140187164  mov     dword ptr [rsp+400h+var_3B0], r13d
0x140187169  mov     dword ptr [rsp+400h+var_3B8], eax
0x14018716d  mov     eax, [rbp+2B0h+var_300]
0x140187170  mov     dword ptr [rsp+400h+var_3C0], eax
0x140187174  mov     eax, [rbp+2B0h+var_2FC]
0x140187177  mov     dword ptr [rsp+400h+var_3C8], eax
0x14018717b  mov     eax, [rbp+2B0h+var_2F8]
0x14018717e  mov     dword ptr [rsp+400h+var_3D0], eax
0x140187182  mov     eax, [rbp+2B0h+var_2F4]
0x140187185  mov     dword ptr [rsp+400h+UserData], eax
0x140187189  mov     eax, [rbp+2B0h+var_320]
0x14018718c  mov     [rsp+400h+UserDataCount], eax
0x140187190  mov     rax, qword ptr [rbp+2B0h+EventDescriptor.Id]
0x140187197  mov     r9d, [rax]
0x14018719a  call    ?RtlStringCbPrintfW@@YAJPEA_W_KPEB_WZZ; RtlStringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14018719f  mov     rdi, [rbp+2B0h+var_318]
0x1401871a3  mov     r13, [rbp+2B0h+var_328]
0x1401871a7  test    eax, eax
0x1401871a9  jns     loc_14018726C
0x1401871af  mov     r15, [rbp+2B0h+var_2E0]
0x1401871b3  mov     r14d, 0C0000001h
0x1401871b9  mov     rsi, qword ptr [rbp+2B0h+var_2E8]
0x1401871bd  cmp     cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA, 0; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x1401871c5  jz      loc_140188877
0x1401871cb  test    rsi, rsi
0x1401871ce  jz      loc_140188877
0x1401871d4  mov     rcx, [rsi+10h]
0x1401871d8  mov     rcx, [rcx+10h]; DriverObject
0x1401871dc  call    cs:__imp_MmIsDriverVerifying
0x1401871e3  nop     dword ptr [rax+rax+00h]
0x1401871e8  test    eax, eax
0x1401871ea  jz      loc_140188877
0x1401871f0  lea     r9, [rsi+308h]
0x1401871f7  cmp     qword ptr [r9], 0
0x1401871fb  jnz     loc_140188877
0x140187201  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140187208  lea     r8, [r15+20h]
0x14018720c  mov     rcx, [r15+10h]
0x140187210  mov     rdx, rsi
0x140187213  mov     rax, [rax+8]
0x140187217  call    _guard_dispatch_icall
0x14018721c  test    eax, eax
0x14018721e  jns     loc_140188877
0x140187224  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14018722b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140187232  jz      loc_14018887E
0x140187238  mov     rcx, cs:WPP_GLOBAL_Control
0x14018723f  mov     r9d, 1Eh; int
0x140187245  mov     [rsp+400h+UserData], rsi; char
0x14018724a  mov     r8d, 0Dh; int
0x140187250  lea     rsi, WPP_4f475340cee13bebfed3041a3a58f669_Traceguids
0x140187257  mov     dl, 2; int
0x140187259  mov     qword ptr [rsp+400h+UserDataCount], rsi; struct _GUID *
0x14018725e  mov     rcx, [rcx+40h]; int
0x140187262  call    WPP_RECORDER_SF_q
0x140187267  jmp     loc_140188885
0x14018726c  lea     r9, [rbp+2B0h+var_2D8]; struct _NDIS_FILTER_BLOCK **
0x140187270  mov     rdx, r13; struct NDIS_BIND_FILTER_LINK *
0x140187273  lea     r8, [rbp+2B0h+var_2D0]; struct _NDIS_FILTER_BLOCK **
0x140187277  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14018727a  mov     bl, 1
0x14018727c  call    ?ndisFindAdjacentFilters@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_BIND_FILTER_LINK@@PEAPEAU_NDIS_FILTER_BLOCK@@2@Z; ndisFindAdjacentFilters(_NDIS_MINIPORT_BLOCK *,NDIS_BIND_FILTER_LINK *,_NDIS_FILTER_BLOCK * *,_NDIS_FILTER_BLOCK * *)
0x140187281  mov     r15, [rbp+2B0h+var_2E0]
0x140187285  cmp     byte ptr [r15+64h], 6
0x14018728a  ja      short loc_140187297
0x14018728c  jnz     short loc_140187295
0x14018728e  cmp     byte ptr [r15+65h], 28h ; '('
0x140187293  jnb     short loc_140187297
0x140187295  xor     bl, bl
0x140187297  movzx   r8d, bl; unsigned __int8
0x14018729b  lea     rcx, [r15+90h]; struct _UNICODE_STRING *
0x1401872a2  mov     rdx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1401872a5  call    ?ndisCreateFilterAdapterRegistry@@YAHPEBU_UNICODE_STRING@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisCreateFilterAdapterRegistry(_UNICODE_STRING const *,_NDIS_MINIPORT_BLOCK *,uchar)
0x1401872aa  mov     r14d, eax
0x1401872ad  test    eax, eax
0x1401872af  jnz     loc_1401871B9
0x1401872b5  cmp     byte ptr [rdi+20h], 6
0x1401872b9  jnb     short loc_1401872EA
0x1401872bb  test    byte ptr [rdi+58h], 1
0x1401872bf  jnz     short loc_1401872EA
0x1401872c1  mov     [rsp+400h+var_3D0], 1; unsigned __int8
0x1401872c6  lea     r9, [rbp+2B0h+var_2F0]; void *
0x1401872ca  mov     dword ptr [rsp+400h+UserData], 1; int
0x1401872d2  mov     r8d, 10114h; unsigned int
0x1401872d8  mov     dl, 1; unsigned __int8
0x1401872da  mov     [rsp+400h+UserDataCount], 4; int
0x1401872e2  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1401872e5  call    ?ndisMDoMiniportOp@@YAJPEAU_NDIS_MINIPORT_BLOCK@@EKPEAXJJE@Z; ndisMDoMiniportOp(_NDIS_MINIPORT_BLOCK *,uchar,ulong,void *,long,long,uchar)
0x1401872ea  mov     dl, 3; enum _NDIS_LWFDRV_REFTAG
0x1401872ec  mov     rcx, r15; struct _NDIS_FILTER_DRIVER_BLOCK *
0x1401872ef  call    ?ndisReferenceFilterDriver@@YAEPEAU_NDIS_FILTER_DRIVER_BLOCK@@W4_NDIS_LWFDRV_REFTAG@@@Z; ndisReferenceFilterDriver(_NDIS_FILTER_DRIVER_BLOCK *,_NDIS_LWFDRV_REFTAG)
0x1401872f4  test    al, al
0x1401872f6  jnz     short loc_140187303
0x1401872f8  mov     r14d, 0C0010006h
0x1401872fe  jmp     loc_1401871B9
0x140187303  mov     edx, 590h
0x140187308  mov     ecx, 40h ; '@'
0x14018730d  mov     r8d, 6266444Eh
0x140187313  call    cs:__imp_ExAllocatePool2
0x14018731a  nop     dword ptr [rax+rax+00h]
0x14018731f  mov     rsi, rax
0x140187322  test    rax, rax
0x140187325  jnz     short loc_14018733F
0x140187327  mov     r8b, 3; enum _NDIS_LWFDRV_REFTAG
0x14018732a  xor     edx, edx; unsigned __int8
0x14018732c  mov     rcx, r15; this
0x14018732f  mov     r14d, 0C000009Ah
0x140187335  call    ?ndisDereferenceFilterDriver@@YAXPEAU_NDIS_FILTER_DRIVER_BLOCK@@EW4_NDIS_LWFDRV_REFTAG@@@Z; ndisDereferenceFilterDriver(_NDIS_FILTER_DRIVER_BLOCK *,uchar,_NDIS_LWFDRV_REFTAG)
0x14018733a  jmp     loc_1401871BD
0x14018733f  mov     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFFFh
0x14018734a  xorps   xmm0, xmm0
0x14018734d  xor     ecx, ecx
0x14018734f  mov     [rbp+2B0h+var_330], 0
0x140187353  mov     [rax+28h], rcx
0x140187357  xor     eax, eax
0x140187359  mov     [rsi+3C0h], rax
0x140187360  mov     [rsi+3C8h], eax
0x140187366  mov     [rsi+3CCh], rax
0x14018736d  mov     [rsi+3D4h], eax
0x140187373  movups  xmmword ptr [rsi+3D8h], xmm0
0x14018737a  movups  xmmword ptr [rsi+3E8h], xmm0
0x140187381  movups  xmmword ptr [rsi+3F8h], xmm0
0x140187388  movups  xmmword ptr [rsi+408h], xmm0
0x14018738f  movups  xmmword ptr [rsi+418h], xmm0
0x140187396  movups  xmmword ptr [rsi+428h], xmm0
0x14018739d  movups  xmmword ptr [rsi+438h], xmm0
0x1401873a4  movups  xmmword ptr [rsi+448h], xmm0
0x1401873ab  mov     [rsi+458h], eax
0x1401873b1  movups  xmmword ptr [rsi+45Ch], xmm0
0x1401873b8  movups  xmmword ptr [rsi+46Ch], xmm0
0x1401873bf  movups  xmmword ptr [rsi+47Ch], xmm0
0x1401873c6  movups  xmmword ptr [rsi+48Ch], xmm0
0x1401873cd  movups  xmmword ptr [rsi+49Ch], xmm0
0x1401873d4  movups  xmmword ptr [rsi+4ACh], xmm0
0x1401873db  movups  xmmword ptr [rsi+4BCh], xmm0
0x1401873e2  movups  xmmword ptr [rsi+4CCh], xmm0
0x1401873e9  mov     [rsi+4DCh], eax
0x1401873ef  movups  xmmword ptr [rsi+4E0h], xmm0
0x1401873f6  movups  xmmword ptr [rsi+4F0h], xmm0
0x1401873fd  movups  xmmword ptr [rsi+500h], xmm0
0x140187404  movups  xmmword ptr [rsi+510h], xmm0
0x14018740b  movups  xmmword ptr [rsi+520h], xmm0
0x140187412  mov     [rsi+530h], eax
0x140187418  movups  xmmword ptr [rsi+534h], xmm0
0x14018741f  movups  xmmword ptr [rsi+544h], xmm0
0x140187426  movups  xmmword ptr [rsi+554h], xmm0
0x14018742d  movups  xmmword ptr [rsi+564h], xmm0
0x140187434  movups  xmmword ptr [rsi+574h], xmm0
0x14018743b  mov     [rsi+584h], eax
0x140187441  mov     [rsi+588h], rcx
0x140187448  mov     dword ptr [rsi], 5900105h
0x14018744e  mov     [rsi+10h], r15
0x140187452  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x140187457  test    eax, eax
0x140187459  jz      short loc_14018747E
0x14018745b  lea     rcx, [rsi+48h]; struct _REFERENCE_EX *
0x14018745f  mov     dl, 3; unsigned __int8
0x140187461  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x140187466  lea     rcx, [rsi+138h]; struct _REFERENCE_EX *
0x14018746d  call    ?ndisInitializeZeroBasedRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeZeroBasedRef(_REFERENCE_EX *,uchar)
0x140187472  lea     rcx, [rsi+138h]; SpinLock
0x140187479  call    ?ndisCloseRef@@YAEPEAU_REFERENCE_EX@@@Z; ndisCloseRef(_REFERENCE_EX *)
0x14018747e  lea     rcx, [rbp+2B0h+var_100]; wchar_t *
0x140187485  call    ?Initialize@KString@Rtl@@SAPEAU12@PEB_W@Z; Rtl::KString::Initialize(wchar_t const *)
0x14018748a  mov     rcx, [rsi+28h]; P
0x14018748e  mov     [rsi+28h], rax
0x140187492  test    rcx, rcx
0x140187495  jz      short loc_1401874A8
0x140187497  mov     edx, 7274534Bh; Tag
0x14018749c  call    cs:__imp_ExFreePoolWithTag
0x1401874a3  nop     dword ptr [rax+rax+00h]
0x1401874a8  cmp     qword ptr [rsi+28h], 0
0x1401874ad  jnz     short loc_1401874BA
0x1401874af  mov     r14d, 0C000009Ah
0x1401874b5  jmp     loc_140188824
0x1401874ba  movzx   ecx, word ptr [r15+70h]
0x1401874bf  mov     r8d, 7473444Eh
0x1401874c5  mov     rax, [rdi+0F10h]
  ... truncated ...
```
