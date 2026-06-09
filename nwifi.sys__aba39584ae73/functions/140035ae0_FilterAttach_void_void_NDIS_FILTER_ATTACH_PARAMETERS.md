# FilterAttach(void *,void *,_NDIS_FILTER_ATTACH_PARAMETERS *)

- ea: `0x140035ae0`
- end: `0x140035f73`
- name: `?FilterAttach@@YAHPEAX0PEAU_NDIS_FILTER_ATTACH_PARAMETERS@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisFilterHandle, void *, struct _NDIS_FILTER_ATTACH_PARAMETERS *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000d21c`
- `0x1400145bc`
- `0x140020dc0`
- `0x1400302a4`
- `0x140035ae0`
- `0x140036700`
- `0x140036844`
- `0x1400369c8`
- `0x140036e68`
- `0x140038458`
- `0x14003b1e8`
- `0x14003be88`
- `0x14003bf28`
- `0x14003c0c8`
- `0x14003c2a0`
- `0x14003c800`
- `0x14003d534`
- `0x14003d934`
- `0x1400bcfa4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140035e78`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035e78`
- `ntoskrnl!ZwClose` at `0x140035df8`
- `ntoskrnl!ZwClose` at `0x140035df8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140035d1d`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140035d1d`
- `ntoskrnl!KeSetEvent` at `0x140035ed1`
- `ntoskrnl!KeSetEvent` at `0x140035ed1`
- `NDIS!NdisCloseConfiguration` at `0x140035cdf`
- `NDIS!NdisCloseConfiguration` at `0x140035cdf`
- `NDIS!NdisOpenConfigurationEx` at `0x140035cb9`
- `NDIS!NdisOpenConfigurationEx` at `0x140035cb9`
- `NDIS!NdisFSetAttributes` at `0x140035c72`
- `NDIS!NdisFSetAttributes` at `0x140035c72`
- `NDIS!NdisMSleep` at `0x140035f0a`
- `NDIS!NdisMSleep` at `0x140035f0a`

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
  v20 = (struct _ADAPT **)qword_1400B2B70;
  if ( *(struct _LIST_ENTRY **)qword_1400B2B70 != &AdapterList )
    __fastfail(3u);
  v12->Link.Flink = &AdapterList;
  v12->Link.Blink = (_LIST_ENTRY *)v20;
  *v20 = v12;
  qword_1400B2B70 = (__int64)v12;
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
0x140035ae0  push    rbp
0x140035ae2  push    rbx
0x140035ae3  push    rsi
0x140035ae4  push    rdi
0x140035ae5  push    r12
0x140035ae7  push    r13
0x140035ae9  push    r14
0x140035aeb  push    r15
0x140035aed  mov     rbp, rsp
0x140035af0  sub     rsp, 78h
0x140035af4  xor     r13d, r13d
0x140035af7  xorps   xmm0, xmm0
0x140035afa  xor     eax, eax
0x140035afc  mov     [rbp+FilterAttributes.Header.Type], r13b
0x140035b00  movups  xmmword ptr [rbp+ConfigObject.Header.Revision], xmm0
0x140035b04  mov     dword ptr [rbp+FilterAttributes.Header.Revision], eax
0x140035b07  mov     rsi, r8
0x140035b0a  mov     word ptr [rbp+FilterAttributes.Flags+1], ax
0x140035b0e  mov     r15, rcx
0x140035b11  mov     byte ptr [rbp+FilterAttributes.Flags+3], al
0x140035b14  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x140035b18  mov     [rbp+FilterModuleContext], r13
0x140035b1c  mov     [rbp+var_30], r13
0x140035b20  mov     [rbp+ConfigurationHandle], r13
0x140035b24  mov     [rbp+ConfigObject.Header.Type], r13b
0x140035b28  mov     [rbp+DeviceRegKey], r13
0x140035b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b33  lea     rax, WPP_GLOBAL_Control
0x140035b3a  cmp     rcx, rax
0x140035b3d  jz      short loc_140035B4C
0x140035b3f  mov     r9, [r8+28h]
0x140035b43  mov     rcx, [rcx+18h]
0x140035b47  call    WPP_SF_Z
0x140035b4c  mov     edx, [rsi+48h]
0x140035b4f  mov     ecx, r13d
0x140035b52  mov     eax, ecx
0x140035b54  lea     r8, ?gMediumArray@@3PAW4_NDIS_MEDIUM@@A; _NDIS_MEDIUM near * gMediumArray
0x140035b5b  cmp     edx, [r8+rax*4]
0x140035b5f  jz      short loc_140035B6A
0x140035b61  inc     ecx
0x140035b63  cmp     ecx, 1
0x140035b66  jb      short loc_140035B52
0x140035b68  jmp     short loc_140035B84
0x140035b6a  mov     rbx, [rsi+50h]
0x140035b6e  mov     rcx, rbx; struct _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *
0x140035b71  call    ?Validate802_11AttachAttributes@@YAHPEAU_NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES@@@Z; Validate802_11AttachAttributes(_NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *)
0x140035b76  test    eax, eax
0x140035b78  mov     r14, r13
0x140035b7b  cmovz   r14, rbx
0x140035b7f  test    r14, r14
0x140035b82  jnz     short loc_140035B8E
0x140035b84  mov     eax, 0C0000001h
0x140035b89  jmp     loc_140035F61
0x140035b8e  lea     rcx, [rbp+FilterModuleContext]; struct _ADAPT **
0x140035b92  mov     r12d, r13d
0x140035b95  call    ?Dot11AllocProtocol@@YAHPEAPEAU_ADAPT@@PEBU_UNICODE_STRING@@@Z; Dot11AllocProtocol(_ADAPT * *,_UNICODE_STRING const *)
0x140035b9a  mov     rbx, [rbp+FilterModuleContext]
0x140035b9e  mov     edi, eax
0x140035ba0  test    eax, eax
0x140035ba2  jnz     loc_140035EF1
0x140035ba8  mov     rdx, r14
0x140035bab  mov     rcx, rbx
0x140035bae  call    NwfDuplicate80211AttachAttributes
0x140035bb3  mov     edi, eax
0x140035bb5  test    eax, eax
0x140035bb7  jnz     loc_140035EF1
0x140035bbd  mov     eax, [rsi+48h]
0x140035bc0  mov     [rbx+58h], eax
0x140035bc3  mov     dword ptr [rbx+14h], 4
0x140035bca  mov     [rbx+50h], r15
0x140035bce  mov     eax, [rsi+18h]
0x140035bd1  mov     [rbx+6ACh], eax
0x140035bd7  mov     rax, [rsi+0B8h]
0x140035bde  mov     [rbx+430h], rax
0x140035be5  mov     rax, [rsi+88h]
0x140035bec  mov     [rbx+6A0h], rax
0x140035bf3  lea     eax, [rdi+6]
0x140035bf6  cmp     ax, [rsi+60h]
0x140035bfa  jz      short loc_140035C22
0x140035bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140035c03  lea     rax, WPP_GLOBAL_Control
0x140035c0a  cmp     rcx, rax
0x140035c0d  jz      short loc_140035C22
0x140035c0f  mov     rcx, [rcx+18h]
0x140035c13  lea     edx, [rdi+0Bh]
0x140035c16  lea     r8, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids
0x140035c1d  call    WPP_SF_
0x140035c22  mov     eax, [rsi+62h]
0x140035c25  mov     [rbx+110h], eax
0x140035c2b  movzx   eax, word ptr [rsi+66h]
0x140035c2f  mov     [rbx+114h], ax
0x140035c36  mov     byte ptr [rbx+4Eh], 1
0x140035c3a  mov     dword ptr [rbx+44h], 3
0x140035c41  mov     eax, [rbx+110h]
0x140035c47  mov     [rbx+48h], eax
0x140035c4a  movzx   eax, word ptr [rbx+114h]
0x140035c51  mov     [rbx+4Ch], ax
0x140035c55  mov     [rsi+48h], r13d
0x140035c59  mov     dword ptr [rsi+4Ch], 9
0x140035c60  mov     qword ptr [rbp+FilterAttributes.Header.Type], 8018Dh
0x140035c68  lea     r8, [rbp+FilterAttributes]; FilterAttributes
0x140035c6c  mov     rdx, rbx; FilterModuleContext
0x140035c6f  mov     rcx, r15; NdisFilterHandle
0x140035c72  call    cs:__imp_NdisFSetAttributes
0x140035c79  nop     dword ptr [rax+rax+00h]
0x140035c7e  mov     edi, eax
0x140035c80  test    eax, eax
0x140035c82  jnz     loc_140035EF1
0x140035c88  mov     rcx, rbx; struct _ADAPT *
0x140035c8b  call    ?Dot11InitProtocol@@YAHPEAU_ADAPT@@@Z; Dot11InitProtocol(_ADAPT *)
0x140035c90  mov     edi, eax
0x140035c92  test    eax, eax
0x140035c94  jnz     loc_140035EF1
0x140035c9a  lea     r12d, [rax+1]
0x140035c9e  mov     dword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x140035ca5  mov     rax, [rbx+50h]
0x140035ca9  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140035cad  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x140035cb1  mov     [rbp+ConfigObject.NdisHandle], rax
0x140035cb5  mov     [rbp+ConfigObject.Flags], r13d
0x140035cb9  call    cs:__imp_NdisOpenConfigurationEx
0x140035cc0  nop     dword ptr [rax+rax+00h]
0x140035cc5  mov     edi, eax
0x140035cc7  test    eax, eax
0x140035cc9  jnz     loc_140035EF1
0x140035ccf  mov     rdx, [rbp+ConfigurationHandle]; void *
0x140035cd3  mov     rcx, rbx; struct _ADAPT *
0x140035cd6  call    ?PtReadOpMode@@YAHPEAU_ADAPT@@PEAX@Z; PtReadOpMode(_ADAPT *,void *)
0x140035cdb  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140035cdf  call    cs:__imp_NdisCloseConfiguration
0x140035ce6  nop     dword ptr [rax+rax+00h]
0x140035ceb  mov     rcx, [rsi+0B8h]; DeviceObject
0x140035cf2  mov     edi, r13d
0x140035cf5  mov     [rbp+ConfigurationHandle], r13
0x140035cf9  mov     rax, [rbx+18h]
0x140035cfd  cmp     [rax+38h], r13
0x140035d01  setnz   dil
0x140035d05  test    rcx, rcx
0x140035d08  jz      loc_140035E04
0x140035d0e  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140035d12  mov     r8d, 80000000h; DesiredAccess
0x140035d18  lea     edx, [r12+1]; DevInstKeyType
0x140035d1d  call    cs:__imp_IoOpenDeviceRegistryKey
0x140035d24  nop     dword ptr [rax+rax+00h]
0x140035d29  test    eax, eax
0x140035d2b  js      loc_140035E04
0x140035d31  mov     rcx, [rbp+DeviceRegKey]
0x140035d35  lea     rdx, aFastresumereco; "FastResumeReconnect"
0x140035d3c  xor     r9d, r9d
0x140035d3f  mov     dword ptr [rsp+78h+Timeout], r12d
0x140035d44  xor     r8d, r8d
0x140035d47  call    Dot11ReadULong
0x140035d4c  mov     ecx, r12d
0x140035d4f  cmp     eax, r12d
0x140035d52  jnz     short loc_140035D5A
0x140035d54  mov     [rbx+414h], ecx
0x140035d5a  mov     dword ptr [rsp+78h+Timeout], ecx
0x140035d5e  lea     rdx, aManagementpack; "ManagementPacketFilterAdjustment"
0x140035d65  mov     rcx, [rbp+DeviceRegKey]
0x140035d69  xor     r9d, r9d
0x140035d6c  mov     r8d, edi
0x140035d6f  call    Dot11ReadULong
0x140035d74  mov     ecx, r13d
0x140035d77  lea     rdx, aWfatestflags; "WFATestFlags"
0x140035d7e  test    eax, eax
0x140035d80  setnz   cl
0x140035d83  or      edi, 0FFFFFFFFh
0x140035d86  mov     [rbx+418h], ecx
0x140035d8c  xor     r9d, r9d
0x140035d8f  mov     rcx, [rbp+DeviceRegKey]
0x140035d93  xor     r8d, r8d
0x140035d96  mov     dword ptr [rsp+78h+Timeout], edi
0x140035d9a  call    Dot11ReadULong
0x140035d9f  mov     [rbx+420h], eax
0x140035da5  lea     rdx, aDot11authentic; "Dot11AuthenticationFlags"
0x140035dac  mov     rcx, [rbp+DeviceRegKey]
0x140035db0  xor     r9d, r9d
0x140035db3  mov     r8d, r12d
0x140035db6  mov     dword ptr [rsp+78h+Timeout], edi
0x140035dba  call    Dot11ReadULong
0x140035dbf  mov     [rbx+424h], eax
0x140035dc5  cmp     [rbx+53Ch], r13d
0x140035dcc  jnz     short loc_140035DF4
0x140035dce  mov     rcx, [rbp+DeviceRegKey]
0x140035dd2  lea     rdx, aIbsssupported; "*IBSSSupported"
0x140035dd9  xor     r9d, r9d
0x140035ddc  mov     dword ptr [rsp+78h+Timeout], r12d
0x140035de1  mov     r8d, r12d
0x140035de4  call    Dot11ReadULong
0x140035de9  test    eax, eax
0x140035deb  jnz     short loc_140035DF4
0x140035ded  mov     [rbx+548h], r13d
0x140035df4  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140035df8  call    cs:__imp_ZwClose
0x140035dff  nop     dword ptr [rax+rax+00h]
0x140035e04  mov     rdx, [rsi+28h]; struct _UNICODE_STRING *
0x140035e08  lea     r8, [rbp+var_30]; struct _VELAN **
0x140035e0c  mov     rcx, rbx; struct _ADAPT *
0x140035e0f  call    ?PtAllocateAndInitializeVElan@@YAHPEAU_ADAPT@@PEAU_UNICODE_STRING@@PEAPEAU_VELAN@@@Z; PtAllocateAndInitializeVElan(_ADAPT *,_UNICODE_STRING *,_VELAN * *)
0x140035e14  mov     rsi, [rbp+var_30]
0x140035e18  mov     edi, eax
0x140035e1a  test    eax, eax
0x140035e1c  jnz     loc_140035EE4
0x140035e22  mov     rcx, rsi; struct _VELAN *
0x140035e25  mov     [rsi+20h], r15
0x140035e29  call    ?Dot11AllocatePools@@YAHPEAU_VELAN@@@Z; Dot11AllocatePools(_VELAN *)
0x140035e2e  mov     edi, eax
0x140035e30  test    eax, eax
0x140035e32  jnz     loc_140035EE4
0x140035e38  lea     rdx, [rbx+44h]; struct _DOT11_RESET_REQUEST *
0x140035e3c  mov     rcx, rsi; struct _VELAN *
0x140035e3f  call    ?Dot11InitMiniport@@YAHPEAU_VELAN@@PEAU_DOT11_RESET_REQUEST@@PEAX@Z; Dot11InitMiniport(_VELAN *,_DOT11_RESET_REQUEST *,void *)
0x140035e44  mov     edi, eax
0x140035e46  test    eax, eax
0x140035e48  jnz     loc_140035EE4
0x140035e4e  mov     rcx, rbx; struct _ADAPT *
0x140035e51  call    ?Pt6Pause@@YAXPEAU_ADAPT@@@Z; Pt6Pause(_ADAPT *)
0x140035e56  xor     edx, edx; int
0x140035e58  mov     rcx, rsi; struct _VELAN *
0x140035e5b  call    ?Dot11BlockSend@@YAXPEAU_VELAN@@H@Z; Dot11BlockSend(_VELAN *,int)
0x140035e60  xor     r9d, r9d; Alertable
0x140035e63  mov     [rsi+18h], r12d
0x140035e67  xor     r8d, r8d; WaitMode
0x140035e6a  mov     [rsp+78h+Timeout], r13; Timeout
0x140035e6f  xor     edx, edx; WaitReason
0x140035e71  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x140035e78  call    cs:__imp_KeWaitForSingleObject
0x140035e7f  nop     dword ptr [rax+rax+00h]
0x140035e84  mov     rax, gs:188h
0x140035e8d  lea     rdx, ?AdapterList@@3U_LIST_ENTRY@@A; _LIST_ENTRY AdapterList
0x140035e94  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140035e9b  mov     rax, cs:qword_1400B2B70
0x140035ea2  cmp     [rax], rdx
0x140035ea5  jz      short loc_140035EAC
0x140035ea7  lea     ecx, [rdi+3]
0x140035eaa  int     29h; Win8: RtlFailFast(ecx)
0x140035eac  mov     [rbx], rdx
0x140035eaf  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x140035eb6  mov     [rbx+8], rax
0x140035eba  mov     edx, r12d; Increment
0x140035ebd  mov     [rax], rbx
0x140035ec0  xor     r8d, r8d; Wait
0x140035ec3  mov     cs:qword_1400B2B70, rbx
0x140035eca  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, r13
0x140035ed1  call    cs:__imp_KeSetEvent
0x140035ed8  nop     dword ptr [rax+rax+00h]
0x140035edd  call    ?PtRegisterDevice@@YAHXZ; PtRegisterDevice(void)
0x140035ee2  jmp     short loc_140035F34
0x140035ee4  test    rsi, rsi
0x140035ee7  jz      short loc_140035EF1
0x140035ee9  mov     rcx, rsi; struct _VELAN *
0x140035eec  call    ?PtUnlinkVElanFromAdapter@@YAXPEAU_VELAN@@@Z; PtUnlinkVElanFromAdapter(_VELAN *)
0x140035ef1  test    rbx, rbx
0x140035ef4  jz      short loc_140035F34
0x140035ef6  test    r12d, r12d
0x140035ef9  jz      short loc_140035F16
0x140035efb  mov     rcx, rbx; struct _ADAPT *
0x140035efe  call    ?Dot11DeInitProtocol@@YAXPEAU_ADAPT@@@Z; Dot11DeInitProtocol(_ADAPT *)
0x140035f03  jmp     short loc_140035F16
0x140035f05  mov     ecx, 4E20h; MicrosecondsToSleep
0x140035f0a  call    cs:__imp_NdisMSleep
0x140035f11  nop     dword ptr [rax+rax+00h]
0x140035f16  cmp     [rbx+0F0h], r13d
0x140035f1d  jnz     short loc_140035F05
0x140035f1f  or      eax, 0FFFFFFFFh
0x140035f22  lock xadd [rbx+10h], eax
0x140035f27  cmp     eax, 1
0x140035f2a  jnz     short loc_140035F34
0x140035f2c  mov     rcx, rbx; struct _ADAPT *
0x140035f2f  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x140035f34  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f3b  lea     rax, WPP_GLOBAL_Control
0x140035f42  cmp     rcx, rax
0x140035f45  jz      short loc_140035F5F
0x140035f47  mov     rcx, [rcx+18h]
0x140035f4b  lea     r8, WPP_437f3cffd22139440bee3b0a13636e97_Traceguids
0x140035f52  mov     edx, 0Ch
0x140035f57  mov     r9d, edi
0x140035f5a  call    WPP_SF_d
0x140035f5f  mov     eax, edi
0x140035f61  add     rsp, 78h
0x140035f65  pop     r15
0x140035f67  pop     r14
0x140035f69  pop     r13
0x140035f6b  pop     r12
0x140035f6d  pop     rdi
0x140035f6e  pop     rsi
0x140035f6f  pop     rbx
0x140035f70  pop     rbp
0x140035f71  retn
```
