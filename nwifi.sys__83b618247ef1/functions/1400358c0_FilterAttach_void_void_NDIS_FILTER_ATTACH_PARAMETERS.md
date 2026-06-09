# FilterAttach(void *,void *,_NDIS_FILTER_ATTACH_PARAMETERS *)

- ea: `0x1400358c0`
- end: `0x140035d53`
- name: `?FilterAttach@@YAHPEAX0PEAU_NDIS_FILTER_ATTACH_PARAMETERS@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisFilterHandle, void *, struct _NDIS_FILTER_ATTACH_PARAMETERS *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000d22c`
- `0x1400145cc`
- `0x140020dc0`
- `0x140030014`
- `0x1400358c0`
- `0x1400364e0`
- `0x140036624`
- `0x1400367a8`
- `0x140036c48`
- `0x140038238`
- `0x14003afc8`
- `0x14003bc68`
- `0x14003bd08`
- `0x14003bea8`
- `0x14003c080`
- `0x14003c5e0`
- `0x14003d314`
- `0x14003d714`
- `0x1400b9ff4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140035c58`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035c58`
- `ntoskrnl!ZwClose` at `0x140035bd8`
- `ntoskrnl!ZwClose` at `0x140035bd8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140035afd`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140035afd`
- `ntoskrnl!KeSetEvent` at `0x140035cb1`
- `ntoskrnl!KeSetEvent` at `0x140035cb1`
- `NDIS!NdisCloseConfiguration` at `0x140035abf`
- `NDIS!NdisCloseConfiguration` at `0x140035abf`
- `NDIS!NdisOpenConfigurationEx` at `0x140035a99`
- `NDIS!NdisOpenConfigurationEx` at `0x140035a99`
- `NDIS!NdisFSetAttributes` at `0x140035a52`
- `NDIS!NdisFSetAttributes` at `0x140035a52`
- `NDIS!NdisMSleep` at `0x140035cea`
- `NDIS!NdisMSleep` at `0x140035cea`

## pseudocode

```c
__int64 __fastcall FilterAttach(NDIS_HANDLE NdisFilterHandle, void *a2, struct _NDIS_FILTER_ATTACH_PARAMETERS *a3)
{
  unsigned int v5; // ecx
  struct _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *MiniportMediaSpecificAttributes; // rbx
  const struct _UNICODE_STRING *v7; // rdx
  struct _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *v8; // r14
  int v10; // r12d
  unsigned int v11; // eax
  struct _ADAPT *v12; // rbx
  unsigned int inited; // edi
  struct _DEVICE_OBJECT *MiniportPhysicalDeviceObject; // rcx
  BOOL v15; // edi
  int v16; // eax
  struct _VELAN *v17; // rsi
  struct _VELAN *v18; // rcx
  void *v19; // r8
  struct _ADAPT **v20; // rax
  void *DeviceRegKey; // [rsp+30h] [rbp-48h] BYREF
  PVOID ConfigurationHandle; // [rsp+38h] [rbp-40h] BYREF
  NDIS_HANDLE FilterModuleContext; // [rsp+40h] [rbp-38h] BYREF
  struct _VELAN *v24; // [rsp+48h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+50h] [rbp-28h] BYREF
  _NDIS_FILTER_ATTRIBUTES FilterAttributes; // [rsp+D8h] [rbp+60h] BYREF

  FilterAttributes.Header.Type = 0;
  *(_DWORD *)&FilterAttributes.Header.Revision = 0;
  *(_WORD *)((char *)&FilterAttributes.Flags + 1) = 0;
  HIBYTE(FilterAttributes.Flags) = 0;
  FilterModuleContext = 0;
  v24 = 0;
  ConfigurationHandle = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  DeviceRegKey = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a3->BaseMiniportName);
  v5 = 0;
  while ( a3->MiniportMediaType != *((_DWORD *)&gMediumArray + v5) )
  {
    if ( ++v5 )
      return 3221225473LL;
  }
  MiniportMediaSpecificAttributes = (struct _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *)a3->MiniportMediaSpecificAttributes;
  v8 = 0;
  if ( !(unsigned int)Validate802_11AttachAttributes(MiniportMediaSpecificAttributes) )
    v8 = MiniportMediaSpecificAttributes;
  if ( !v8 )
    return 3221225473LL;
  v10 = 0;
  v11 = Dot11AllocProtocol((struct _ADAPT **)&FilterModuleContext, v7);
  v12 = (struct _ADAPT *)FilterModuleContext;
  inited = v11;
  if ( v11 )
    goto LABEL_35;
  inited = NwfDuplicate80211AttachAttributes(FilterModuleContext, v8);
  if ( inited )
    goto LABEL_35;
  v12->uMedium = a3->MiniportMediaType;
  v12->State = PT6_PAUSED;
  v12->hBinding = NdisFilterHandle;
  v12->IfIndex = a3->BaseMiniportIfIndex;
  v12->pMiniportPdo = a3->MiniportPhysicalDeviceObject;
  v12->BaseMiniportNetLuid.Value = a3->BaseMiniportNetLuid.Value;
  if ( a3->MacAddressLength != 6 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids);
  *(_DWORD *)v12->CurrentAddress = *(_DWORD *)a3->CurrentMacAddress;
  *(_WORD *)&v12->CurrentAddress[4] = *(_WORD *)&a3->CurrentMacAddress[4];
  v12->ResetRequest.bSetDefaultMIB = 1;
  v12->ResetRequest.dot11ResetType = dot11_reset_type_phy_and_mac;
  *(_DWORD *)v12->ResetRequest.dot11MacAddress = *(_DWORD *)v12->CurrentAddress;
  *(_WORD *)&v12->ResetRequest.dot11MacAddress[4] = *(_WORD *)&v12->CurrentAddress[4];
  a3->MiniportMediaType = NdisMedium802_3;
  a3->MiniportPhysicalMediaType = NdisPhysicalMediumNative802_11;
  FilterAttributes = (_NDIS_FILTER_ATTRIBUTES)524685LL;
  inited = NdisFSetAttributes(NdisFilterHandle, v12, &FilterAttributes);
  if ( inited )
    goto LABEL_35;
  inited = Dot11InitProtocol(v12);
  if ( inited )
    goto LABEL_35;
  v10 = 1;
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
  ConfigObject.NdisHandle = v12->hBinding;
  ConfigObject.Flags = 0;
  inited = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  if ( inited )
    goto LABEL_35;
  PtReadOpMode(v12, ConfigurationHandle);
  NdisCloseConfiguration(ConfigurationHandle);
  MiniportPhysicalDeviceObject = a3->MiniportPhysicalDeviceObject;
  ConfigurationHandle = 0;
  v15 = v12->pNwfAttrs->WFDAttributes != 0;
  if ( MiniportPhysicalDeviceObject
    && IoOpenDeviceRegistryKey(MiniportPhysicalDeviceObject, 2u, 0x80000000, &DeviceRegKey) >= 0 )
  {
    if ( (unsigned int)Dot11ReadULong((_DWORD)DeviceRegKey, (unsigned int)L"FastResumeReconnect", 0, 0, 1) == 1 )
      v12->bFastResumeReconnectSupported = 1;
    v12->bMgmtPacketFilterAdjustment = Dot11ReadULong(
                                         (_DWORD)DeviceRegKey,
                                         (unsigned int)L"ManagementPacketFilterAdjustment",
                                         v15,
                                         0,
                                         1) != 0;
    v12->uWFATestFlags = Dot11ReadULong((_DWORD)DeviceRegKey, (unsigned int)L"WFATestFlags", 0, 0, -1);
    v12->dot11AuthenticationFlags = Dot11ReadULong(
                                      (_DWORD)DeviceRegKey,
                                      (unsigned int)L"Dot11AuthenticationFlags",
                                      1,
                                      0,
                                      -1);
    if ( !v12->AdapterEnhancedCapabilities.uIhvWdiVersion
      && !(unsigned int)Dot11ReadULong((_DWORD)DeviceRegKey, (unsigned int)L"*IBSSSupported", 1, 0, 1) )
    {
      v12->AdapterEnhancedCapabilities.IBSSSupported = dot11_tri_state_false;
    }
    ZwClose(DeviceRegKey);
  }
  v16 = PtAllocateAndInitializeVElan(v12, a3->BaseMiniportName, &v24);
  v17 = v24;
  inited = v16;
  if ( v16
    || (v18 = v24, v24->hMiniport = NdisFilterHandle, (inited = Dot11AllocatePools(v18)) != 0)
    || (inited = Dot11InitMiniport(v17, &v12->ResetRequest, v19)) != 0 )
  {
    if ( v17 )
      PtUnlinkVElanFromAdapter(v17);
LABEL_35:
    if ( v12 )
    {
      if ( v10 )
        Dot11DeInitProtocol(v12);
      while ( v12->uOutstandingRequests )
        NdisMSleep(0x4E20u);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v12->RefCount, 0xFFFFFFFF) == 1 )
        PtDestroyAdapter(v12);
    }
    goto LABEL_42;
  }
  Pt6Pause(v12);
  Dot11BlockSend(v17, 0);
  v17->State = MP6_PAUSED;
  KeWaitForSingleObject(&WPP_MAIN_CB.DeviceExtension, Executive, 0, 0, 0);
  WPP_MAIN_CB.Queue.ListEntry.Blink = (_LIST_ENTRY *)KeGetCurrentThread();
  v20 = (struct _ADAPT **)qword_1400AFB30;
  if ( *(struct _LIST_ENTRY **)qword_1400AFB30 != &AdapterList )
    __fastfail(3u);
  v12->Link.Flink = &AdapterList;
  v12->Link.Blink = (_LIST_ENTRY *)v20;
  *v20 = v12;
  qword_1400AFB30 = (__int64)v12;
  WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
  KeSetEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, 1, 0);
  PtRegisterDevice();
LABEL_42:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids, inited);
  return inited;
}

```

## disassembly

```asm
0x1400358c0  push    rbp
0x1400358c2  push    rbx
0x1400358c3  push    rsi
0x1400358c4  push    rdi
0x1400358c5  push    r12
0x1400358c7  push    r13
0x1400358c9  push    r14
0x1400358cb  push    r15
0x1400358cd  mov     rbp, rsp
0x1400358d0  sub     rsp, 78h
0x1400358d4  xor     r13d, r13d
0x1400358d7  xorps   xmm0, xmm0
0x1400358da  xor     eax, eax
0x1400358dc  mov     [rbp+FilterAttributes.Header.Type], r13b
0x1400358e0  movups  xmmword ptr [rbp+ConfigObject.Header.Revision], xmm0
0x1400358e4  mov     dword ptr [rbp+FilterAttributes.Header.Revision], eax
0x1400358e7  mov     rsi, r8
0x1400358ea  mov     word ptr [rbp+FilterAttributes.Flags+1], ax
0x1400358ee  mov     r15, rcx
0x1400358f1  mov     byte ptr [rbp+FilterAttributes.Flags+3], al
0x1400358f4  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x1400358f8  mov     [rbp+FilterModuleContext], r13
0x1400358fc  mov     [rbp+var_30], r13
0x140035900  mov     [rbp+ConfigurationHandle], r13
0x140035904  mov     [rbp+ConfigObject.Header.Type], r13b
0x140035908  mov     [rbp+DeviceRegKey], r13
0x14003590c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035913  lea     rax, WPP_GLOBAL_Control
0x14003591a  cmp     rcx, rax
0x14003591d  jz      short loc_14003592C
0x14003591f  mov     r9, [r8+28h]
0x140035923  mov     rcx, [rcx+18h]
0x140035927  call    WPP_SF_Z
0x14003592c  mov     edx, [rsi+48h]
0x14003592f  mov     ecx, r13d
0x140035932  mov     eax, ecx
0x140035934  lea     r8, ?gMediumArray@@3PAW4_NDIS_MEDIUM@@A; _NDIS_MEDIUM near * gMediumArray
0x14003593b  cmp     edx, [r8+rax*4]
0x14003593f  jz      short loc_14003594A
0x140035941  inc     ecx
0x140035943  cmp     ecx, 1
0x140035946  jb      short loc_140035932
0x140035948  jmp     short loc_140035964
0x14003594a  mov     rbx, [rsi+50h]
0x14003594e  mov     rcx, rbx; struct _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *
0x140035951  call    ?Validate802_11AttachAttributes@@YAHPEAU_NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES@@@Z; Validate802_11AttachAttributes(_NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *)
0x140035956  test    eax, eax
0x140035958  mov     r14, r13
0x14003595b  cmovz   r14, rbx
0x14003595f  test    r14, r14
0x140035962  jnz     short loc_14003596E
0x140035964  mov     eax, 0C0000001h
0x140035969  jmp     loc_140035D41
0x14003596e  lea     rcx, [rbp+FilterModuleContext]; struct _ADAPT **
0x140035972  mov     r12d, r13d
0x140035975  call    ?Dot11AllocProtocol@@YAHPEAPEAU_ADAPT@@PEBU_UNICODE_STRING@@@Z; Dot11AllocProtocol(_ADAPT * *,_UNICODE_STRING const *)
0x14003597a  mov     rbx, [rbp+FilterModuleContext]
0x14003597e  mov     edi, eax
0x140035980  test    eax, eax
0x140035982  jnz     loc_140035CD1
0x140035988  mov     rdx, r14
0x14003598b  mov     rcx, rbx
0x14003598e  call    NwfDuplicate80211AttachAttributes
0x140035993  mov     edi, eax
0x140035995  test    eax, eax
0x140035997  jnz     loc_140035CD1
0x14003599d  mov     eax, [rsi+48h]
0x1400359a0  mov     [rbx+58h], eax
0x1400359a3  mov     dword ptr [rbx+14h], 4
0x1400359aa  mov     [rbx+50h], r15
0x1400359ae  mov     eax, [rsi+18h]
0x1400359b1  mov     [rbx+6ACh], eax
0x1400359b7  mov     rax, [rsi+0B8h]
0x1400359be  mov     [rbx+430h], rax
0x1400359c5  mov     rax, [rsi+88h]
0x1400359cc  mov     [rbx+6A0h], rax
0x1400359d3  lea     eax, [rdi+6]
0x1400359d6  cmp     ax, [rsi+60h]
0x1400359da  jz      short loc_140035A02
0x1400359dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400359e3  lea     rax, WPP_GLOBAL_Control
0x1400359ea  cmp     rcx, rax
0x1400359ed  jz      short loc_140035A02
0x1400359ef  mov     rcx, [rcx+18h]
0x1400359f3  lea     edx, [rdi+0Bh]
0x1400359f6  lea     r8, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids
0x1400359fd  call    WPP_SF_
0x140035a02  mov     eax, [rsi+62h]
0x140035a05  mov     [rbx+110h], eax
0x140035a0b  movzx   eax, word ptr [rsi+66h]
0x140035a0f  mov     [rbx+114h], ax
0x140035a16  mov     byte ptr [rbx+4Eh], 1
0x140035a1a  mov     dword ptr [rbx+44h], 3
0x140035a21  mov     eax, [rbx+110h]
0x140035a27  mov     [rbx+48h], eax
0x140035a2a  movzx   eax, word ptr [rbx+114h]
0x140035a31  mov     [rbx+4Ch], ax
0x140035a35  mov     [rsi+48h], r13d
0x140035a39  mov     dword ptr [rsi+4Ch], 9
0x140035a40  mov     qword ptr [rbp+FilterAttributes.Header.Type], 8018Dh
0x140035a48  lea     r8, [rbp+FilterAttributes]; FilterAttributes
0x140035a4c  mov     rdx, rbx; FilterModuleContext
0x140035a4f  mov     rcx, r15; NdisFilterHandle
0x140035a52  call    cs:__imp_NdisFSetAttributes
0x140035a59  nop     dword ptr [rax+rax+00h]
0x140035a5e  mov     edi, eax
0x140035a60  test    eax, eax
0x140035a62  jnz     loc_140035CD1
0x140035a68  mov     rcx, rbx; struct _ADAPT *
0x140035a6b  call    ?Dot11InitProtocol@@YAHPEAU_ADAPT@@@Z; Dot11InitProtocol(_ADAPT *)
0x140035a70  mov     edi, eax
0x140035a72  test    eax, eax
0x140035a74  jnz     loc_140035CD1
0x140035a7a  lea     r12d, [rax+1]
0x140035a7e  mov     dword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x140035a85  mov     rax, [rbx+50h]
0x140035a89  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140035a8d  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x140035a91  mov     [rbp+ConfigObject.NdisHandle], rax
0x140035a95  mov     [rbp+ConfigObject.Flags], r13d
0x140035a99  call    cs:__imp_NdisOpenConfigurationEx
0x140035aa0  nop     dword ptr [rax+rax+00h]
0x140035aa5  mov     edi, eax
0x140035aa7  test    eax, eax
0x140035aa9  jnz     loc_140035CD1
0x140035aaf  mov     rdx, [rbp+ConfigurationHandle]; void *
0x140035ab3  mov     rcx, rbx; struct _ADAPT *
0x140035ab6  call    ?PtReadOpMode@@YAHPEAU_ADAPT@@PEAX@Z; PtReadOpMode(_ADAPT *,void *)
0x140035abb  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140035abf  call    cs:__imp_NdisCloseConfiguration
0x140035ac6  nop     dword ptr [rax+rax+00h]
0x140035acb  mov     rcx, [rsi+0B8h]; DeviceObject
0x140035ad2  mov     edi, r13d
0x140035ad5  mov     [rbp+ConfigurationHandle], r13
0x140035ad9  mov     rax, [rbx+18h]
0x140035add  cmp     [rax+38h], r13
0x140035ae1  setnz   dil
0x140035ae5  test    rcx, rcx
0x140035ae8  jz      loc_140035BE4
0x140035aee  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140035af2  mov     r8d, 80000000h; DesiredAccess
0x140035af8  lea     edx, [r12+1]; DevInstKeyType
0x140035afd  call    cs:__imp_IoOpenDeviceRegistryKey
0x140035b04  nop     dword ptr [rax+rax+00h]
0x140035b09  test    eax, eax
0x140035b0b  js      loc_140035BE4
0x140035b11  mov     rcx, [rbp+DeviceRegKey]
0x140035b15  lea     rdx, aFastresumereco; "FastResumeReconnect"
0x140035b1c  xor     r9d, r9d
0x140035b1f  mov     dword ptr [rsp+78h+Timeout], r12d
0x140035b24  xor     r8d, r8d
0x140035b27  call    Dot11ReadULong
0x140035b2c  mov     ecx, r12d
0x140035b2f  cmp     eax, r12d
0x140035b32  jnz     short loc_140035B3A
0x140035b34  mov     [rbx+414h], ecx
0x140035b3a  mov     dword ptr [rsp+78h+Timeout], ecx
0x140035b3e  lea     rdx, aManagementpack; "ManagementPacketFilterAdjustment"
0x140035b45  mov     rcx, [rbp+DeviceRegKey]
0x140035b49  xor     r9d, r9d
0x140035b4c  mov     r8d, edi
0x140035b4f  call    Dot11ReadULong
0x140035b54  mov     ecx, r13d
0x140035b57  lea     rdx, aWfatestflags; "WFATestFlags"
0x140035b5e  test    eax, eax
0x140035b60  setnz   cl
0x140035b63  or      edi, 0FFFFFFFFh
0x140035b66  mov     [rbx+418h], ecx
0x140035b6c  xor     r9d, r9d
0x140035b6f  mov     rcx, [rbp+DeviceRegKey]
0x140035b73  xor     r8d, r8d
0x140035b76  mov     dword ptr [rsp+78h+Timeout], edi
0x140035b7a  call    Dot11ReadULong
0x140035b7f  mov     [rbx+420h], eax
0x140035b85  lea     rdx, aDot11authentic; "Dot11AuthenticationFlags"
0x140035b8c  mov     rcx, [rbp+DeviceRegKey]
0x140035b90  xor     r9d, r9d
0x140035b93  mov     r8d, r12d
0x140035b96  mov     dword ptr [rsp+78h+Timeout], edi
0x140035b9a  call    Dot11ReadULong
0x140035b9f  mov     [rbx+424h], eax
0x140035ba5  cmp     [rbx+53Ch], r13d
0x140035bac  jnz     short loc_140035BD4
0x140035bae  mov     rcx, [rbp+DeviceRegKey]
0x140035bb2  lea     rdx, aIbsssupported; "*IBSSSupported"
0x140035bb9  xor     r9d, r9d
0x140035bbc  mov     dword ptr [rsp+78h+Timeout], r12d
0x140035bc1  mov     r8d, r12d
0x140035bc4  call    Dot11ReadULong
0x140035bc9  test    eax, eax
0x140035bcb  jnz     short loc_140035BD4
0x140035bcd  mov     [rbx+548h], r13d
0x140035bd4  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140035bd8  call    cs:__imp_ZwClose
0x140035bdf  nop     dword ptr [rax+rax+00h]
0x140035be4  mov     rdx, [rsi+28h]; struct _UNICODE_STRING *
0x140035be8  lea     r8, [rbp+var_30]; struct _VELAN **
0x140035bec  mov     rcx, rbx; struct _ADAPT *
0x140035bef  call    ?PtAllocateAndInitializeVElan@@YAHPEAU_ADAPT@@PEAU_UNICODE_STRING@@PEAPEAU_VELAN@@@Z; PtAllocateAndInitializeVElan(_ADAPT *,_UNICODE_STRING *,_VELAN * *)
0x140035bf4  mov     rsi, [rbp+var_30]
0x140035bf8  mov     edi, eax
0x140035bfa  test    eax, eax
0x140035bfc  jnz     loc_140035CC4
0x140035c02  mov     rcx, rsi; struct _VELAN *
0x140035c05  mov     [rsi+20h], r15
0x140035c09  call    ?Dot11AllocatePools@@YAHPEAU_VELAN@@@Z; Dot11AllocatePools(_VELAN *)
0x140035c0e  mov     edi, eax
0x140035c10  test    eax, eax
0x140035c12  jnz     loc_140035CC4
0x140035c18  lea     rdx, [rbx+44h]; struct _DOT11_RESET_REQUEST *
0x140035c1c  mov     rcx, rsi; struct _VELAN *
0x140035c1f  call    ?Dot11InitMiniport@@YAHPEAU_VELAN@@PEAU_DOT11_RESET_REQUEST@@PEAX@Z; Dot11InitMiniport(_VELAN *,_DOT11_RESET_REQUEST *,void *)
0x140035c24  mov     edi, eax
0x140035c26  test    eax, eax
0x140035c28  jnz     loc_140035CC4
0x140035c2e  mov     rcx, rbx; struct _ADAPT *
0x140035c31  call    ?Pt6Pause@@YAXPEAU_ADAPT@@@Z; Pt6Pause(_ADAPT *)
0x140035c36  xor     edx, edx; int
0x140035c38  mov     rcx, rsi; struct _VELAN *
0x140035c3b  call    ?Dot11BlockSend@@YAXPEAU_VELAN@@H@Z; Dot11BlockSend(_VELAN *,int)
0x140035c40  xor     r9d, r9d; Alertable
0x140035c43  mov     [rsi+18h], r12d
0x140035c47  xor     r8d, r8d; WaitMode
0x140035c4a  mov     [rsp+78h+Timeout], r13; Timeout
0x140035c4f  xor     edx, edx; WaitReason
0x140035c51  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x140035c58  call    cs:__imp_KeWaitForSingleObject
0x140035c5f  nop     dword ptr [rax+rax+00h]
0x140035c64  mov     rax, gs:188h
0x140035c6d  lea     rdx, ?AdapterList@@3U_LIST_ENTRY@@A; _LIST_ENTRY AdapterList
0x140035c74  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140035c7b  mov     rax, cs:qword_1400AFB30
0x140035c82  cmp     [rax], rdx
0x140035c85  jz      short loc_140035C8C
0x140035c87  lea     ecx, [rdi+3]
0x140035c8a  int     29h; Win8: RtlFailFast(ecx)
0x140035c8c  mov     [rbx], rdx
0x140035c8f  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x140035c96  mov     [rbx+8], rax
0x140035c9a  mov     edx, r12d; Increment
0x140035c9d  mov     [rax], rbx
0x140035ca0  xor     r8d, r8d; Wait
0x140035ca3  mov     cs:qword_1400AFB30, rbx
0x140035caa  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, r13
0x140035cb1  call    cs:__imp_KeSetEvent
0x140035cb8  nop     dword ptr [rax+rax+00h]
0x140035cbd  call    ?PtRegisterDevice@@YAHXZ; PtRegisterDevice(void)
0x140035cc2  jmp     short loc_140035D14
0x140035cc4  test    rsi, rsi
0x140035cc7  jz      short loc_140035CD1
0x140035cc9  mov     rcx, rsi; struct _VELAN *
0x140035ccc  call    ?PtUnlinkVElanFromAdapter@@YAXPEAU_VELAN@@@Z; PtUnlinkVElanFromAdapter(_VELAN *)
0x140035cd1  test    rbx, rbx
0x140035cd4  jz      short loc_140035D14
0x140035cd6  test    r12d, r12d
0x140035cd9  jz      short loc_140035CF6
0x140035cdb  mov     rcx, rbx; struct _ADAPT *
0x140035cde  call    ?Dot11DeInitProtocol@@YAXPEAU_ADAPT@@@Z; Dot11DeInitProtocol(_ADAPT *)
0x140035ce3  jmp     short loc_140035CF6
0x140035ce5  mov     ecx, 4E20h; MicrosecondsToSleep
0x140035cea  call    cs:__imp_NdisMSleep
0x140035cf1  nop     dword ptr [rax+rax+00h]
0x140035cf6  cmp     [rbx+0F0h], r13d
0x140035cfd  jnz     short loc_140035CE5
0x140035cff  or      eax, 0FFFFFFFFh
0x140035d02  lock xadd [rbx+10h], eax
0x140035d07  cmp     eax, 1
0x140035d0a  jnz     short loc_140035D14
0x140035d0c  mov     rcx, rbx; struct _ADAPT *
0x140035d0f  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x140035d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140035d1b  lea     rax, WPP_GLOBAL_Control
0x140035d22  cmp     rcx, rax
0x140035d25  jz      short loc_140035D3F
0x140035d27  mov     rcx, [rcx+18h]
0x140035d2b  lea     r8, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids
0x140035d32  mov     edx, 0Ch
0x140035d37  mov     r9d, edi
0x140035d3a  call    WPP_SF_d
0x140035d3f  mov     eax, edi
0x140035d41  add     rsp, 78h
0x140035d45  pop     r15
0x140035d47  pop     r14
0x140035d49  pop     r13
0x140035d4b  pop     r12
0x140035d4d  pop     rdi
0x140035d4e  pop     rsi
0x140035d4f  pop     rbx
0x140035d50  pop     rbp
0x140035d51  retn
```
