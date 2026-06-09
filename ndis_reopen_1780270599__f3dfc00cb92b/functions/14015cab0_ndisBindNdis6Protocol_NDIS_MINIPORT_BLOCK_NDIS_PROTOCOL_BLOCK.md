# ndisBindNdis6Protocol(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *)

- ea: `0x14015cab0`
- end: `0x14015d3f9`
- name: `?ndisBindNdis6Protocol@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@@Z`
- size: `2377`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_PROTOCOL_BLOCK *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14015d8f0`

## callees

- `0x140004bf0`
- `0x140005140`
- `0x140005ea0`
- `0x1400100f0`
- `0x1400212a0`
- `0x14003f590`
- `0x14005aef0`
- `0x14005eaa0`
- `0x14005f7e0`
- `0x140063240`
- `0x140066680`
- `0x1400678b0`
- `0x14007b030`
- `0x140082c90`
- `0x140084030`
- `0x14008bd30`
- `0x1400eb380`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14015c030`
- `0x14015cab0`
- `0x14015d400`
- `0x14015d440`
- `0x14015d480`
- `0x14015d4d0`
- `0x1401709e0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14015cc92`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14015cc92`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14015cca8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14015ccbe`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14015cca8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14015ccbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14015cbfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14015cbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cfc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d1a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d3a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d3b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cfc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d1a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d3a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d3b6`
- `ntoskrnl!KeInitializeEvent` at `0x14015cf7c`
- `ntoskrnl!KeInitializeEvent` at `0x14015cf7c`
- `ntoskrnl!ExAllocatePool2` at `0x14015cc70`
- `ntoskrnl!ExAllocatePool2` at `0x14015cc70`
- `ntoskrnl!KeBugCheckEx` at `0x14015d27c`
- `ntoskrnl!KeBugCheckEx` at `0x14015d27c`

## pseudocode

```c
__int64 __fastcall ndisBindNdis6Protocol(struct _NDIS_MINIPORT_BLOCK *a1, struct _NDIS_PROTOCOL_BLOCK *a2)
{
  int v4; // edx
  int v5; // edx
  char v6; // r15
  unsigned int Blink; // r14d
  char v8; // si
  _NDIS_PNP_DEVICE_STATE PnPDeviceState; // ecx
  _UNICODE_STRING *Paths; // r12
  UNICODE_STRING v11; // xmm0
  __int16 v12; // ax
  __int64 v13; // rdx
  unsigned __int8 MajorNdisVersion; // dl
  UCHAR v15; // r8
  USHORT v16; // ax
  unsigned int v17; // eax
  _NDIS_FILTER_BLOCK *HighestFilter; // rcx
  _NDIS_IF_BLOCK *IfBlock; // rcx
  _NET_IF_MEDIA_DUPLEX_STATE MediaDuplexStateIndicateUp; // eax
  _NDIS_MINIPORT_OFFLOAD *Offload; // rcx
  _NDIS_HD_SPLIT_CURRENT_CONFIG *HDSplitCurrentConfig; // rax
  struct _NDIS_NIC_SWITCH_CAPABILITIES *TopNicSwitchCurrentCapabilities; // r10
  _NDIS_RECEIVE_FILTER_CAPABILITIES *TopReceiveFilterCurrentCapabilities; // rcx
  _NDIS_RECEIVE_FILTER_CAPABILITIES *ReceiveFilterCapabilities; // rax
  _NDIS_NIC_SWITCH_CAPABILITIES *NicSwitchCapabilities; // rax
  _NDIS_IF_BLOCK *v27; // rdx
  _NDIS_IF_BLOCK *v28; // rcx
  __int64 v29; // rdx
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  __int64 v33; // rdx
  struct _NDIS_SRIOV_CAPABILITIES *TopSriovCurrentCapabilities; // r8
  struct _NDIS_NDK_BLOCK *NDKBlock; // rax
  __int64 v37; // rcx
  unsigned __int8 v38; // cl
  __int64 v39; // rdx
  int BugCheckParameter4; // [rsp+20h] [rbp-E0h]
  char v41; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _KEVENT BugCheckParameter3[6]; // [rsp+80h] [rbp-80h] BYREF
  struct _NDIS_BIND_PARAMETERS v47; // [rsp+110h] [rbp+10h] BYREF

  memset(&v47, 0, sizeof(v47));
  memset(BugCheckParameter3, 0, sizeof(BugCheckParameter3));
  v43 = 0;
  Destination = 0;
  Source = 0;
  DestinationString = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      6,
      26,
      (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
      (char)a1,
      (char)a2);
  }
  if ( a1->MajorNdisVersion < 6u && (a1->LinkStateIndicationFlags & 1) == 0 )
    ndisMDoMiniportOp(a1, 1u, 0x10114u, &v43, 4, 1, 1u);
  if ( ndisReferenceProtocol(a2, PTREF_BINDINGX) )
  {
    if ( !a1->EthDB )
    {
      Blink = -1073741823;
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v5,
          6,
          27,
          (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
          (char)a1,
          (char)a2);
      }
      goto LABEL_44;
    }
    v6 = 0;
    v41 = 0;
    Blink = 0;
    v8 = 1;
    WAIT_FOR_PROTO_MUTEX(a2);
    if ( a2->Ref.Closing )
      goto LABEL_41;
    if ( !ndisIsMiniportStarted(a1) )
      goto LABEL_63;
    PnPDeviceState = a1->PnPDeviceState;
    if ( ((PnPDeviceState - 1) & 0xFFFFFFFC) != 0 || PnPDeviceState == NdisPnPDeviceStopped )
      goto LABEL_63;
    Paths = a1->BindPaths->Paths;
    a2->BindDeviceName = &a1->MiniportName;
    a2->RootDeviceName = Paths;
    RtlInitUnicodeString(&DestinationString, L"\\Parameters\\Adapters\\");
    Source = *Paths;
    v11 = Source;
    Source.MaximumLength -= ndisDeviceStr.Length;
    Source.Length = _mm_cvtsi128_si32((__m128i)v11) - ndisDeviceStr.Length;
    v12 = a2->Name.Length - ndisDeviceStr.Length;
    Source.Buffer += (unsigned __int64)ndisDeviceStr.Length >> 1;
    v13 = (unsigned __int16)(DestinationString.Length + Paths->Length + v12 + 2);
    Destination.Length = 0;
    Destination.MaximumLength = v13;
    Destination.Buffer = (wchar_t *)ExAllocatePool2(64, v13, 538985550);
    if ( !Destination.Buffer )
    {
LABEL_58:
      v6 = 0;
LABEL_41:
      RELEASE_PROT_MUTEX(a2);
      if ( v6 )
      {
        LOBYTE(v33) = 2;
        ndisMDereferenceOpenUnlocked(BugCheckParameter3[0].Header.WaitListHead.Blink, v33);
        BugCheckParameter3[0].Header.WaitListHead.Blink = 0;
      }
      if ( v8 && Blink )
        ndisNotifyBindFailure(a1, a2);
      goto LABEL_44;
    }
    RtlCopyUnicodeString(&Destination, &a2->Name);
    RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    RtlAppendUnicodeStringToString(&Destination, &Source);
    MajorNdisVersion = a2->MajorNdisVersion;
    v47.Header.Type = -122;
    if ( MajorNdisVersion > 6u )
      goto LABEL_14;
    if ( MajorNdisVersion == 6 )
    {
      if ( a2->MinorNdisVersion >= 0x1Eu )
      {
LABEL_14:
        v15 = 4;
        v16 = 312;
LABEL_15:
        v47.Header.Size = v16;
        v47.ProtocolSection = &Destination;
        v47.PhysicalDeviceObject = a1->PhysicalDeviceObject;
        v17 = a1->MacOptions & 0x80000001;
        v47.Header.Revision = v15;
        v47.AdapterName = Paths;
        v47.BoundAdapterName = &a1->MiniportName;
        if ( v17 == -2147483647 )
          v47.MediaType = NdisMediumWan;
        else
          v47.MediaType = a1->MediaType;
        HighestFilter = a1->HighestFilter;
        if ( HighestFilter )
        {
          v47.XmitLinkSpeed = HighestFilter->XmitLinkSpeedIndicateUp;
          v47.RcvLinkSpeed = HighestFilter->RcvLinkSpeedIndicateUp;
          v47.MediaConnectState = HighestFilter->MediaConnectStateIndicateUp;
          MediaDuplexStateIndicateUp = HighestFilter->MediaDuplexStateIndicateUp;
        }
        else
        {
          IfBlock = a1->IfBlock;
          v47.XmitLinkSpeed = a1->XmitLinkSpeed;
          v47.RcvLinkSpeed = a1->RcvLinkSpeed;
          v47.MediaConnectState = IfBlock->MediaConnectState;
          MediaDuplexStateIndicateUp = IfBlock->MediaDuplexState;
        }
        v47.MediaDuplexState = MediaDuplexStateIndicateUp;
        v47.MtuSize = a1->TopFilterRestartAttributes.MtuSize;
        v47.MaxXmitLinkSpeed = a1->TopFilterRestartAttributes.MaxXmitLinkSpeed;
        v47.MaxRcvLinkSpeed = a1->TopFilterRestartAttributes.MaxRcvLinkSpeed;
        v47.LookaheadSize = a1->TopFilterRestartAttributes.LookaheadSize;
        v47.SupportedPacketFilters = a1->TopFilterRestartAttributes.SupportedPacketFilters;
        v47.MaxMulticastListSize = a1->TopFilterRestartAttributes.MaxMulticastListSize;
        v47.PhysicalMediumType = a1->PhysicalMediumType;
        v47.RcvScaleCapabilities = &a1->TopRecvScaleCapabilities;
        if ( MajorNdisVersion > 6u || MajorNdisVersion == 6 && a2->MinorNdisVersion >= 0x14u )
          v47.PowerManagementCapabilitiesEx = &a1->PMAdvertisedCapabilities;
        else
          v47.PowerManagementCapabilities = &a1->PMCapabilities61;
        Offload = a1->Offload;
        if ( Offload )
        {
          if ( Offload->SupportsTopOffload == 1 )
            v47.DefaultOffloadConfiguration = &Offload->TopCapabilities;
          if ( Offload->SupportsTopTcpConnectionOffload == 1 )
            v47.TcpConnectionOffloadCapabilities = &Offload->TopTcpConnectionOffloadCapabilities;
        }
        HDSplitCurrentConfig = v47.HDSplitCurrentConfig;
        TopNicSwitchCurrentCapabilities = a1->TopNicSwitchCurrentCapabilities;
        if ( a1->HDSplitCurrentConfig )
          HDSplitCurrentConfig = a1->HDSplitCurrentConfig;
        TopReceiveFilterCurrentCapabilities = a1->TopReceiveFilterCurrentCapabilities;
        v47.HDSplitCurrentConfig = HDSplitCurrentConfig;
        ReceiveFilterCapabilities = v47.ReceiveFilterCapabilities;
        if ( TopReceiveFilterCurrentCapabilities )
          ReceiveFilterCapabilities = TopReceiveFilterCurrentCapabilities;
        v47.ReceiveFilterCapabilities = ReceiveFilterCapabilities;
        NicSwitchCapabilities = v47.NicSwitchCapabilities;
        if ( TopNicSwitchCurrentCapabilities )
          NicSwitchCapabilities = TopNicSwitchCurrentCapabilities;
        v47.NicSwitchCapabilities = NicSwitchCapabilities;
        if ( MajorNdisVersion > 6u || MajorNdisVersion == 6 && a2->MinorNdisVersion >= 0x1Eu )
        {
          NDKBlock = ndisGetNDKBlock(a1);
          if ( NDKBlock )
          {
            v38 = *((_BYTE *)NDKBlock + 24);
            v47.NDKCapabilities = (_NDIS_NDK_CAPABILITIES *)((char *)NDKBlock + 32);
            v47.NDKEnabled = v38;
          }
          else
          {
            v47.NDKEnabled = 0;
            v47.NDKCapabilities = 0;
          }
        }
        if ( v15 >= 4u )
        {
          TopSriovCurrentCapabilities = a1->TopSriovCurrentCapabilities;
          if ( TopSriovCurrentCapabilities )
          {
            v47.SriovCapabilities = a1->TopSriovCurrentCapabilities;
            if ( (unsigned int)ndisIovGetNicSwitchList(
                                 a1,
                                 TopNicSwitchCurrentCapabilities,
                                 TopSriovCurrentCapabilities,
                                 &v47.NicSwitchArray) )
              goto LABEL_58;
          }
        }
        v27 = a1->IfBlock;
        v47.MacAddressLength = v27->ifPhysAddress.Length;
        memmove(v47.CurrentMacAddress, v27->ifPhysAddress.Address, v47.MacAddressLength);
        ndisIfQueryBindingMiniportIfIndex(
          a1,
          &v47.BoundIfIndex,
          &v47.BoundIfNetluid,
          &v47.LowestIfIndex,
          &v47.LowestIfNetluid);
        v28 = a1->IfBlock;
        v47.AccessType = a1->TopFilterRestartAttributes.AccessType;
        v47.DirectionType = v28->DirectionType;
        v47.ConnectionType = a1->TopFilterRestartAttributes.ConnectionType;
        v47.IfType = v28->ifType;
        v47.IfConnectorPresent = v28->ifConnectorPresent;
        v47.DataBackFillSize = a1->TopFilterRestartAttributes.DataBackFillSize;
        v47.ContextBackFillSize = a1->TopFilterRestartAttributes.ContextBackFillSize;
        v47.MacOptions = a1->TopFilterRestartAttributes.MacOptions;
        v47.CompartmentId = v28->CompartmentId;
        if ( !(unsigned int)ndisGetPortList(a1, &v47.ActivePorts) )
        {
          BugCheckParameter3[1].Header.WaitListHead = (_LIST_ENTRY)Destination;
          *(_QWORD *)&BugCheckParameter3[0].Header.Lock = 0;
          BugCheckParameter3[0].Header.WaitListHead.Flink = (_LIST_ENTRY *)a2;
          *(_QWORD *)&BugCheckParameter3[1].Header.Lock = a1;
          *(_QWORD *)&BugCheckParameter3[2].Header.Lock = Paths;
          BugCheckParameter3[0].Header.WaitListHead.Blink = 0;
          KeInitializeEvent(&BugCheckParameter3[4], NotificationEvent, 0);
          a2->BindingAdapter = a1;
          Blink = ndisInvokeBindAdapter(a2, BugCheckParameter3, &v47);
          if ( Blink == 259 )
          {
            ndisWaitForKernelObject(&BugCheckParameter3[4]);
            Blink = (unsigned int)BugCheckParameter3[3].Header.WaitListHead.Blink;
          }
          if ( Blink )
            goto LABEL_36;
          if ( BugCheckParameter3[0].Header.WaitListHead.Blink )
          {
            LOBYTE(v29) = 2;
            if ( !(unsigned __int8)ndisReferenceOpenByHandle(BugCheckParameter3[0].Header.WaitListHead.Blink, v29) )
              KeBugCheckEx(
                0x7Cu,
                0x16u,
                (ULONG_PTR)a2,
                (ULONG_PTR)BugCheckParameter3,
                (ULONG_PTR)BugCheckParameter3[0].Header.WaitListHead.Blink);
            v41 = 1;
            ndisIndicateInitialStateToBinding((struct _NDIS_OPEN_BLOCK *)BugCheckParameter3[0].Header.WaitListHead.Blink);
          }
          if ( MiniportSupportsReceiveThrottle(a1) )
          {
LABEL_66:
            ndisNotifyWmiBindUnbind(a1, a2, 1u);
LABEL_36:
            v8 = 0;
            ExFreePoolWithTag(Destination.Buffer, 0);
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_ZZL(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v30,
                v32,
                28,
                BugCheckParameter4,
                (__int64)&a2->Name,
                (__int64)a1->pAdapterInstanceName,
                Blink);
            if ( (byte_140121001 & 2) != 0 )
              McTemplateK0jqxzd_EtwWriteTransfer(
                v31,
                v30,
                (_DWORD)a1 + 4008,
                (_DWORD)a1 + 4008,
                a1->IfIndex,
                a1->NetLuid.Value,
                (__int64)a2->Name.Buffer,
                Blink);
            v6 = v41;
            goto LABEL_41;
          }
          if ( a2->IsIPv4 == 1 )
          {
            v39 = 0;
          }
          else if ( a2->IsIPv6 == 1 )
          {
            v39 = 1;
          }
          else
          {
            if ( a2->IsNdisTest6 != 1 )
              goto LABEL_66;
            v39 = 2;
          }
          ndisBindUnbindPeriodicReceives(v37, v39);
          goto LABEL_66;
        }
        ExFreePoolWithTag(Destination.Buffer, 0);
LABEL_63:
        RELEASE_PROT_MUTEX(a2);
LABEL_44:
        ndisDereferenceProtocol(a2, 0, PTREF_BINDINGX);
        goto LABEL_45;
      }
      if ( a2->MinorNdisVersion >= 0x14u )
      {
        v15 = 3;
        v16 = 280;
        goto LABEL_15;
      }
      if ( a2->MinorNdisVersion )
      {
        v15 = 2;
        v16 = 256;
        goto LABEL_15;
      }
    }
    v15 = 1;
    v16 = 248;
    goto LABEL_15;
  }
  Blink = -1073741823;
LABEL_45:
  if ( v47.ActivePorts )
    ExFreePoolWithTag(v47.ActivePorts, 0);
  if ( v47.NicSwitchArray )
    ExFreePoolWithTag(v47.NicSwitchArray, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      6,
      29,
      (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
      (char)a1,
      (char)a2);
  }
  return Blink;
}

```

## disassembly

```asm
0x14015cab0  push    rbp
0x14015cab2  push    rbx
0x14015cab3  push    rsi
0x14015cab4  push    rdi
0x14015cab5  push    r15
0x14015cab7  lea     rbp, [rsp-170h]
0x14015cabf  sub     rsp, 270h
0x14015cac6  mov     rax, cs:__security_cookie
0x14015cacd  xor     rax, rsp
0x14015cad0  mov     [rbp+190h+var_40], rax
0x14015cad7  mov     rdi, rdx
0x14015cada  mov     [rbp+190h+var_180.Header.Type], 0
0x14015cade  mov     rbx, rcx
0x14015cae1  xor     eax, eax
0x14015cae3  xor     edx, edx; Val
0x14015cae5  mov     dword ptr [rbp+190h+var_180+4], eax
0x14015cae8  lea     rcx, [rbp+190h+var_180.Header.Revision]; void *
0x14015caec  mov     r8d, 137h; Size
0x14015caf2  call    memset
0x14015caf7  xor     edx, edx; Val
0x14015caf9  lea     rcx, [rbp+190h+BugCheckParameter3]; void *
0x14015cafd  mov     r8d, 90h; Size
0x14015cb03  call    memset
0x14015cb08  xorps   xmm0, xmm0
0x14015cb0b  mov     [rsp+290h+var_238], 0
0x14015cb13  xorps   xmm1, xmm1
0x14015cb16  movups  xmmword ptr [rsp+290h+Destination.Length], xmm0
0x14015cb1b  movups  xmmword ptr [rsp+290h+Source.Length], xmm1
0x14015cb20  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x14015cb25  lea     rsi, WPP_RECORDER_INITIALIZED
0x14015cb2c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14015cb33  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x14015cb3a  jnz     loc_14015D294
0x14015cb40  cmp     byte ptr [rbx+20h], 6
0x14015cb44  jb      loc_14015D2C6
0x14015cb4a  mov     [rsp+290h+arg_10], r12
0x14015cb52  mov     dl, 8; enum _NDIS_PT_REFTAG
0x14015cb54  mov     [rsp+290h+var_28], r13
0x14015cb5c  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x14015cb5f  mov     [rsp+290h+var_30], r14
0x14015cb67  call    ?ndisReferenceProtocol@@YAEPEAU_NDIS_PROTOCOL_BLOCK@@W4_NDIS_PT_REFTAG@@@Z; ndisReferenceProtocol(_NDIS_PROTOCOL_BLOCK *,_NDIS_PT_REFTAG)
0x14015cb6c  test    al, al
0x14015cb6e  jz      loc_14015D289
0x14015cb74  cmp     qword ptr [rbx+190h], 0
0x14015cb7c  jz      loc_14015D2FF
0x14015cb82  xor     r15b, r15b
0x14015cb85  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x14015cb88  mov     [rsp+290h+var_250], r15b
0x14015cb8d  xor     r14d, r14d
0x14015cb90  mov     sil, 1
0x14015cb93  call    ?WAIT_FOR_PROTO_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; WAIT_FOR_PROTO_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x14015cb98  cmp     [rdi+2Ah], r14b
0x14015cb9c  jnz     loc_14015D04A
0x14015cba2  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14015cba5  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x14015cbaa  test    al, al
0x14015cbac  jz      loc_14015D1B4
0x14015cbb2  mov     ecx, [rbx+5F0h]
0x14015cbb8  lea     eax, [rcx-1]
0x14015cbbb  test    eax, 0FFFFFFFCh
0x14015cbc0  jnz     loc_14015D1B4
0x14015cbc6  cmp     ecx, 3
0x14015cbc9  jz      loc_14015D1B4
0x14015cbcf  mov     r12, [rbx+0EB8h]
0x14015cbd6  lea     r15, [rbx+0EE0h]
0x14015cbdd  add     r12, 8
0x14015cbe1  mov     [rdi+1B0h], r15
0x14015cbe8  lea     rdx, aParametersAdap; "\\Parameters\\Adapters\\"
0x14015cbef  mov     [rdi+1B8h], r12
0x14015cbf6  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x14015cbfb  call    cs:__imp_RtlInitUnicodeString
0x14015cc02  nop     dword ptr [rax+rax+00h]
0x14015cc07  movups  xmm0, xmmword ptr [r12]
0x14015cc0c  movzx   edx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x14015cc13  lea     r13, [rdi+48h]
0x14015cc17  mov     ecx, edx
0x14015cc19  mov     r8d, 2020444Eh
0x14015cc1f  movups  xmmword ptr [rsp+290h+Source.Length], xmm0
0x14015cc24  sub     [rsp+290h+Source.MaximumLength], dx
0x14015cc29  movd    eax, xmm0
0x14015cc2d  shr     rcx, 1
0x14015cc30  sub     ax, dx
0x14015cc33  mov     [rsp+290h+Source.Length], ax
0x14015cc38  mov     rax, [rsp+290h+Source.Buffer]
0x14015cc3d  lea     rcx, [rax+rcx*2]
0x14015cc41  movzx   eax, word ptr [r13+0]
0x14015cc46  sub     ax, dx
0x14015cc49  mov     [rsp+290h+Source.Buffer], rcx
0x14015cc4e  add     ax, 2
0x14015cc52  mov     ecx, 40h ; '@'
0x14015cc57  add     ax, [r12]
0x14015cc5c  add     ax, [rsp+290h+DestinationString.Length]
0x14015cc61  movzx   edx, ax
0x14015cc64  xor     eax, eax
0x14015cc66  mov     [rsp+290h+Destination.Length], ax
0x14015cc6b  mov     [rsp+290h+Destination.MaximumLength], dx
0x14015cc70  call    cs:__imp_ExAllocatePool2
0x14015cc77  nop     dword ptr [rax+rax+00h]
0x14015cc7c  mov     [rsp+290h+Destination.Buffer], rax
0x14015cc81  test    rax, rax
0x14015cc84  jz      loc_14015D16B
0x14015cc8a  mov     rdx, r13; SourceString
0x14015cc8d  lea     rcx, [rsp+290h+Destination]; DestinationString
0x14015cc92  call    cs:__imp_RtlCopyUnicodeString
0x14015cc99  nop     dword ptr [rax+rax+00h]
0x14015cc9e  lea     rdx, [rsp+290h+DestinationString]; Source
0x14015cca3  lea     rcx, [rsp+290h+Destination]; Destination
0x14015cca8  call    cs:__imp_RtlAppendUnicodeStringToString
0x14015ccaf  nop     dword ptr [rax+rax+00h]
0x14015ccb4  lea     rdx, [rsp+290h+Source]; Source
0x14015ccb9  lea     rcx, [rsp+290h+Destination]; Destination
0x14015ccbe  call    cs:__imp_RtlAppendUnicodeStringToString
0x14015ccc5  nop     dword ptr [rax+rax+00h]
0x14015ccca  movzx   edx, byte ptr [rdi+38h]
0x14015ccce  mov     [rbp+190h+var_180.Header.Type], 86h
0x14015ccd2  cmp     dl, 6
0x14015ccd5  ja      short loc_14015CCE7
0x14015ccd7  jnz     loc_14015D21F
0x14015ccdd  cmp     byte ptr [rdi+39h], 1Eh
0x14015cce1  jb      loc_14015D344
0x14015cce7  mov     r8b, 4
0x14015ccea  mov     eax, 138h
0x14015ccef  mov     [rbp+190h+var_180.Header.Size], ax
0x14015ccf3  lea     rax, [rsp+290h+Destination]
0x14015ccf8  mov     [rbp+190h+var_180.ProtocolSection], rax
0x14015ccfc  mov     rax, [rbx+0EF8h]
0x14015cd03  mov     [rbp+190h+var_180.PhysicalDeviceObject], rax
0x14015cd07  mov     eax, [rbx+238h]
0x14015cd0d  and     eax, 80000001h
0x14015cd12  mov     [rbp+190h+var_180.Header.Revision], r8b
0x14015cd16  mov     [rbp+190h+var_180.AdapterName], r12
0x14015cd1a  mov     [rbp+190h+var_180.BoundAdapterName], r15
0x14015cd21  cmp     eax, 80000001h
0x14015cd26  jz      loc_14015D197
0x14015cd2c  mov     eax, [rbx+1D0h]
0x14015cd32  mov     [rbp+190h+var_180.MediaType], eax
0x14015cd35  mov     rcx, [rbx+800h]
0x14015cd3c  test    rcx, rcx
0x14015cd3f  jnz     loc_14015D110
0x14015cd45  mov     rax, [rbx+318h]
0x14015cd4c  mov     rcx, [rbx+0FC8h]
0x14015cd53  mov     [rbp+190h+var_180.XmitLinkSpeed], rax
0x14015cd57  mov     rax, [rbx+320h]
0x14015cd5e  mov     [rbp+190h+var_180.RcvLinkSpeed], rax
0x14015cd62  mov     eax, [rcx+4C4h]
0x14015cd68  mov     [rbp+190h+var_180.MediaConnectState], eax
0x14015cd6b  mov     eax, [rcx+4C8h]
0x14015cd71  mov     [rbp+190h+var_180.MediaDuplexState], eax
0x14015cd74  mov     eax, [rbx+0BCCh]
0x14015cd7a  mov     [rbp+190h+var_180.MtuSize], eax
0x14015cd7d  mov     rax, [rbx+0BD0h]
0x14015cd84  mov     [rbp+190h+var_180.MaxXmitLinkSpeed], rax
0x14015cd88  mov     rax, [rbx+0BD8h]
0x14015cd8f  mov     [rbp+190h+var_180.MaxRcvLinkSpeed], rax
0x14015cd93  mov     eax, [rbx+0BE0h]
0x14015cd99  mov     [rbp+190h+var_180.LookaheadSize], eax
0x14015cd9c  mov     eax, [rbx+0BE8h]
0x14015cda2  mov     [rbp+190h+var_180.SupportedPacketFilters], eax
0x14015cda5  mov     eax, [rbx+0BECh]
0x14015cdab  mov     [rbp+190h+var_180.MaxMulticastListSize], eax
0x14015cdae  mov     eax, [rbx+728h]
0x14015cdb4  mov     [rbp+190h+var_180.PhysicalMediumType], eax
0x14015cdba  lea     rax, [rbx+0C20h]
0x14015cdc1  mov     [rbp+190h+var_180.RcvScaleCapabilities], rax
0x14015cdc8  cmp     dl, 6
0x14015cdcb  jbe     loc_14015D0F4
0x14015cdd1  lea     rax, [rbx+424h]
0x14015cdd8  mov     [rbp+190h+var_180.PowerManagementCapabilitiesEx], rax
0x14015cddf  mov     rcx, [rbx+1000h]
0x14015cde6  test    rcx, rcx
0x14015cde9  jnz     loc_14015D1EE
0x14015cdef  mov     rcx, [rbx+10A8h]
0x14015cdf6  mov     rax, [rbp+190h+var_180.HDSplitCurrentConfig]
0x14015cdfd  test    rcx, rcx
0x14015ce00  mov     r10, [rbx+0DF8h]
0x14015ce07  cmovnz  rax, rcx
0x14015ce0b  mov     rcx, [rbx+0DE0h]
0x14015ce12  mov     [rbp+190h+var_180.HDSplitCurrentConfig], rax
0x14015ce19  test    rcx, rcx
0x14015ce1c  mov     rax, [rbp+190h+var_180.ReceiveFilterCapabilities]
0x14015ce23  cmovnz  rax, rcx
0x14015ce27  test    r10, r10
0x14015ce2a  mov     [rbp+190h+var_180.ReceiveFilterCapabilities], rax
0x14015ce31  mov     rax, [rbp+190h+var_180.NicSwitchCapabilities]
0x14015ce38  cmovnz  rax, r10
0x14015ce3c  mov     [rbp+190h+var_180.NicSwitchCapabilities], rax
0x14015ce43  cmp     dl, 6
0x14015ce46  ja      loc_14015D173
0x14015ce4c  jnz     short loc_14015CE58
0x14015ce4e  cmp     byte ptr [rdi+39h], 1Eh
0x14015ce52  jnb     loc_14015D173
0x14015ce58  cmp     r8b, 4
0x14015ce5c  jnb     loc_14015D13A
0x14015ce62  mov     rdx, [rbx+0FC8h]
0x14015ce69  lea     rcx, [rbp+190h+var_180.CurrentMacAddress]; void *
0x14015ce6d  movzx   eax, word ptr [rdx+464h]
0x14015ce74  add     rdx, 466h; Src
0x14015ce7b  mov     r8d, eax; Size
0x14015ce7e  mov     [rbp+190h+var_180.MacAddressLength], ax
0x14015ce82  call    memmove
0x14015ce87  lea     rax, [rbp+190h+var_180.LowestIfNetluid]
0x14015ce8e  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14015ce91  lea     r9, [rbp+190h+var_180.LowestIfIndex]; unsigned int *
0x14015ce98  mov     [rsp+290h+BugCheckParameter4], rax; union _NET_LUID_LH *
0x14015ce9d  lea     r8, [rbp+190h+var_180.BoundIfNetluid]; union _NET_LUID_LH *
0x14015cea4  lea     rdx, [rbp+190h+var_180.BoundIfIndex]; unsigned int *
0x14015ceab  call    ?ndisIfQueryBindingMiniportIfIndex@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAKPEAT_NET_LUID_LH@@12@Z; ndisIfQueryBindingMiniportIfIndex(_NDIS_MINIPORT_BLOCK *,ulong *,_NET_LUID_LH *,ulong *,_NET_LUID_LH *)
0x14015ceb0  mov     rcx, [rbx+0FC8h]
0x14015ceb7  lea     rdx, [rbp+190h+var_180.ActivePorts]; struct _NDIS_PORT **
0x14015cebe  mov     eax, [rbx+0BF8h]
0x14015cec4  mov     [rbp+190h+var_180.AccessType], eax
0x14015ceca  mov     eax, [rcx+214h]
0x14015ced0  mov     [rbp+190h+var_180.DirectionType], eax
0x14015ced6  mov     eax, [rbx+0C00h]
0x14015cedc  mov     [rbp+190h+var_180.ConnectionType], eax
0x14015cee2  movzx   eax, word ptr [rcx+20Ch]
0x14015cee9  mov     [rbp+190h+var_180.IfType], ax
0x14015cef0  movzx   eax, byte ptr [rcx+22Ch]
0x14015cef7  mov     [rbp+190h+var_180.IfConnectorPresent], al
0x14015cefd  mov     eax, [rbx+0C08h]
0x14015cf03  mov     [rbp+190h+var_180.DataBackFillSize], eax
0x14015cf09  mov     eax, [rbx+0C0Ch]
0x14015cf0f  mov     [rbp+190h+var_180.ContextBackFillSize], eax
0x14015cf15  mov     eax, [rbx+0BE4h]
0x14015cf1b  mov     [rbp+190h+var_180.MacOptions], eax
0x14015cf21  mov     eax, [rcx+240h]
0x14015cf27  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14015cf2a  mov     [rbp+190h+var_180.CompartmentId], eax
0x14015cf30  call    ?ndisGetPortList@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAPEAU_NDIS_PORT@@@Z; ndisGetPortList(_NDIS_MINIPORT_BLOCK *,_NDIS_PORT * *)
0x14015cf35  xor     edx, edx; Tag
0x14015cf37  test    eax, eax
0x14015cf39  jnz     loc_14015D1A3
0x14015cf3f  movzx   eax, [rsp+290h+Destination.Length]
0x14015cf44  lea     rcx, [rbp+190h+Event]; Event
0x14015cf48  mov     [rbp+190h+var_1F0], ax
0x14015cf4c  xor     r8d, r8d; State
0x14015cf4f  movzx   eax, [rsp+290h+Destination.MaximumLength]
0x14015cf54  mov     [rbp+190h+var_1EE], ax
0x14015cf58  mov     eax, dword ptr [rsp+290h+Destination+4]
0x14015cf5c  mov     [rbp+190h+var_1EC], eax
0x14015cf5f  mov     rax, [rsp+290h+Destination.Buffer]
0x14015cf64  mov     [rbp+190h+var_1E8], rax
0x14015cf68  mov     [rbp+190h+BugCheckParameter3], r14
0x14015cf6c  mov     [rbp+190h+var_208], rdi
0x14015cf70  mov     [rbp+190h+var_1F8], rbx
0x14015cf74  mov     [rbp+190h+var_1E0], r12
0x14015cf78  mov     [rbp+190h+var_200], r14
0x14015cf7c  call    cs:__imp_KeInitializeEvent
0x14015cf83  nop     dword ptr [rax+rax+00h]
0x14015cf88  lea     r8, [rbp+190h+var_180]; struct _NDIS_BIND_PARAMETERS *
0x14015cf8c  mov     [rdi+1C8h], rbx
0x14015cf93  lea     rdx, [rbp+190h+BugCheckParameter3]; void *
0x14015cf97  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x14015cf9a  call    ?ndisInvokeBindAdapter@@YAHPEAU_NDIS_PROTOCOL_BLOCK@@PEAXPEAU_NDIS_BIND_PARAMETERS@@@Z; ndisInvokeBindAdapter(_NDIS_PROTOCOL_BLOCK *,void *,_NDIS_BIND_PARAMETERS *)
0x14015cf9f  mov     r14d, eax
0x14015cfa2  cmp     eax, 103h
0x14015cfa7  jz      loc_14015D365
0x14015cfad  test    r14d, r14d
0x14015cfb0  jz      loc_14015D1C1
0x14015cfb6  mov     rcx, [rsp+290h+Destination.Buffer]; P
0x14015cfbb  xor     sil, sil
0x14015cfbe  xor     edx, edx; Tag
0x14015cfc0  call    cs:__imp_ExFreePoolWithTag
0x14015cfc7  nop     dword ptr [rax+rax+00h]
0x14015cfcc  lea     rax, WPP_RECORDER_INITIALIZED
0x14015cfd3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14015cfda  jz      short loc_14015D008
0x14015cfdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14015cfe3  mov     r9d, 1Ch
0x14015cfe9  mov     rax, [rbx+0F10h]
0x14015cff0  mov     [rsp+290h+var_258], r14d
0x14015cff5  mov     qword ptr [rsp+290h+var_260], rax
0x14015cffa  mov     rcx, [rcx+40h]
0x14015cffe  mov     qword ptr [rsp+290h+var_268], r13
0x14015d003  call    WPP_RECORDER_SF_ZZL
0x14015d008  test    cs:byte_140121001, 2
0x14015d00f  jz      short loc_14015D044
0x14015d011  mov     rax, [rdi+50h]
0x14015d015  lea     r8, [rbx+0FA8h]
0x14015d01c  mov     [rsp+290h+var_258], r14d
0x14015d021  mov     r9, r8
0x14015d024  mov     qword ptr [rsp+290h+var_260], rax
0x14015d029  mov     rax, [rbx+0FB8h]
0x14015d030  mov     qword ptr [rsp+290h+var_268], rax
0x14015d035  mov     eax, [rbx+0FD8h]
0x14015d03b  mov     dword ptr [rsp+290h+BugCheckParameter4], eax
0x14015d03f  call    McTemplateK0jqxzd_EtwWriteTransfer
0x14015d044  movzx   r15d, [rsp+290h+var_250]
0x14015d04a  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x14015d04d  call    ?RELEASE_PROT_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; RELEASE_PROT_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x14015d052  test    r15b, r15b
0x14015d055  jz      short loc_14015D06A
0x14015d057  mov     rcx, [rbp+190h+var_200]
0x14015d05b  mov     dl, 2
0x14015d05d  call    ?ndisMDereferenceOpenUnlocked@@YAXPEAU_NDIS_OPEN_BLOCK@@W4_NDIS_OPEN_REFTAG@@@Z; ndisMDereferenceOpenUnlocked(_NDIS_OPEN_BLOCK *,_NDIS_OPEN_REFTAG)
0x14015d062  mov     [rbp+190h+var_200], 0
0x14015d06a  test    sil, sil
0x14015d06d  jnz     loc_14015D388
0x14015d073  mov     r8b, 8; enum _NDIS_PT_REFTAG
0x14015d076  xor     edx, edx; unsigned __int8
  ... truncated ...
```
