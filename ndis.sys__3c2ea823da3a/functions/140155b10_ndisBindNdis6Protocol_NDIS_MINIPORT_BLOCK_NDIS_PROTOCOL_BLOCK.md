# ndisBindNdis6Protocol(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *)

- ea: `0x140155b10`
- end: `0x140156459`
- name: `?ndisBindNdis6Protocol@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@@Z`
- size: `2377`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_PROTOCOL_BLOCK *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140156950`

## callees

- `0x140014c00`
- `0x14001c050`
- `0x140035d70`
- `0x140036370`
- `0x1400371a0`
- `0x14003cde0`
- `0x1400566b0`
- `0x14005a5c0`
- `0x14005b1f0`
- `0x14005d2d0`
- `0x14005eca0`
- `0x140061cc0`
- `0x140075950`
- `0x14007d3a0`
- `0x14007e840`
- `0x140086a40`
- `0x1400e6160`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x140155090`
- `0x140155b10`
- `0x140156460`
- `0x1401564a0`
- `0x1401564e0`
- `0x140156530`
- `0x140169af0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140155cf2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140155cf2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140155d08`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140155d1e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140155d08`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140155d1e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140155c5b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140155c5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156020`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156208`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156403`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156416`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156020`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156208`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156403`
- `ntoskrnl!ExFreePoolWithTag` at `0x140156416`
- `ntoskrnl!KeInitializeEvent` at `0x140155fdc`
- `ntoskrnl!KeInitializeEvent` at `0x140155fdc`
- `ntoskrnl!ExAllocatePool2` at `0x140155cd0`
- `ntoskrnl!ExAllocatePool2` at `0x140155cd0`
- `ntoskrnl!KeBugCheckEx` at `0x1401562dc`
- `ntoskrnl!KeBugCheckEx` at `0x1401562dc`

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
            if ( (byte_14011B001 & 2) != 0 )
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
0x140155b10  push    rbp
0x140155b12  push    rbx
0x140155b13  push    rsi
0x140155b14  push    rdi
0x140155b15  push    r15
0x140155b17  lea     rbp, [rsp-170h]
0x140155b1f  sub     rsp, 270h
0x140155b26  mov     rax, cs:__security_cookie
0x140155b2d  xor     rax, rsp
0x140155b30  mov     [rbp+190h+var_40], rax
0x140155b37  mov     rdi, rdx
0x140155b3a  mov     [rbp+190h+var_180.Header.Type], 0
0x140155b3e  mov     rbx, rcx
0x140155b41  xor     eax, eax
0x140155b43  xor     edx, edx; Val
0x140155b45  mov     dword ptr [rbp+190h+var_180+4], eax
0x140155b48  lea     rcx, [rbp+190h+var_180.Header.Revision]; void *
0x140155b4c  mov     r8d, 137h; Size
0x140155b52  call    memset
0x140155b57  xor     edx, edx; Val
0x140155b59  lea     rcx, [rbp+190h+BugCheckParameter3]; void *
0x140155b5d  mov     r8d, 90h; Size
0x140155b63  call    memset
0x140155b68  xorps   xmm0, xmm0
0x140155b6b  mov     [rsp+290h+var_238], 0
0x140155b73  xorps   xmm1, xmm1
0x140155b76  movups  xmmword ptr [rsp+290h+Destination.Length], xmm0
0x140155b7b  movups  xmmword ptr [rsp+290h+Source.Length], xmm1
0x140155b80  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x140155b85  lea     rsi, WPP_RECORDER_INITIALIZED
0x140155b8c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140155b93  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x140155b9a  jnz     loc_1401562F4
0x140155ba0  cmp     byte ptr [rbx+20h], 6
0x140155ba4  jb      loc_140156326
0x140155baa  mov     [rsp+290h+arg_10], r12
0x140155bb2  mov     dl, 8; enum _NDIS_PT_REFTAG
0x140155bb4  mov     [rsp+290h+var_28], r13
0x140155bbc  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x140155bbf  mov     [rsp+290h+var_30], r14
0x140155bc7  call    ?ndisReferenceProtocol@@YAEPEAU_NDIS_PROTOCOL_BLOCK@@W4_NDIS_PT_REFTAG@@@Z; ndisReferenceProtocol(_NDIS_PROTOCOL_BLOCK *,_NDIS_PT_REFTAG)
0x140155bcc  test    al, al
0x140155bce  jz      loc_1401562E9
0x140155bd4  cmp     qword ptr [rbx+190h], 0
0x140155bdc  jz      loc_14015635F
0x140155be2  xor     r15b, r15b
0x140155be5  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x140155be8  mov     [rsp+290h+var_250], r15b
0x140155bed  xor     r14d, r14d
0x140155bf0  mov     sil, 1
0x140155bf3  call    ?WAIT_FOR_PROTO_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; WAIT_FOR_PROTO_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x140155bf8  cmp     [rdi+2Ah], r14b
0x140155bfc  jnz     loc_1401560AA
0x140155c02  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140155c05  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140155c0a  test    al, al
0x140155c0c  jz      loc_140156214
0x140155c12  mov     ecx, [rbx+5F0h]
0x140155c18  lea     eax, [rcx-1]
0x140155c1b  test    eax, 0FFFFFFFCh
0x140155c20  jnz     loc_140156214
0x140155c26  cmp     ecx, 3
0x140155c29  jz      loc_140156214
0x140155c2f  mov     r12, [rbx+0EB8h]
0x140155c36  lea     r15, [rbx+0EE0h]
0x140155c3d  add     r12, 8
0x140155c41  mov     [rdi+1B0h], r15
0x140155c48  lea     rdx, aParametersAdap; "\\Parameters\\Adapters\\"
0x140155c4f  mov     [rdi+1B8h], r12
0x140155c56  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140155c5b  call    cs:__imp_RtlInitUnicodeString
0x140155c62  nop     dword ptr [rax+rax+00h]
0x140155c67  movups  xmm0, xmmword ptr [r12]
0x140155c6c  movzx   edx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140155c73  lea     r13, [rdi+48h]
0x140155c77  mov     ecx, edx
0x140155c79  mov     r8d, 2020444Eh
0x140155c7f  movups  xmmword ptr [rsp+290h+Source.Length], xmm0
0x140155c84  sub     [rsp+290h+Source.MaximumLength], dx
0x140155c89  movd    eax, xmm0
0x140155c8d  shr     rcx, 1
0x140155c90  sub     ax, dx
0x140155c93  mov     [rsp+290h+Source.Length], ax
0x140155c98  mov     rax, [rsp+290h+Source.Buffer]
0x140155c9d  lea     rcx, [rax+rcx*2]
0x140155ca1  movzx   eax, word ptr [r13+0]
0x140155ca6  sub     ax, dx
0x140155ca9  mov     [rsp+290h+Source.Buffer], rcx
0x140155cae  add     ax, 2
0x140155cb2  mov     ecx, 40h ; '@'
0x140155cb7  add     ax, [r12]
0x140155cbc  add     ax, [rsp+290h+DestinationString.Length]
0x140155cc1  movzx   edx, ax
0x140155cc4  xor     eax, eax
0x140155cc6  mov     [rsp+290h+Destination.Length], ax
0x140155ccb  mov     [rsp+290h+Destination.MaximumLength], dx
0x140155cd0  call    cs:__imp_ExAllocatePool2
0x140155cd7  nop     dword ptr [rax+rax+00h]
0x140155cdc  mov     [rsp+290h+Destination.Buffer], rax
0x140155ce1  test    rax, rax
0x140155ce4  jz      loc_1401561CB
0x140155cea  mov     rdx, r13; SourceString
0x140155ced  lea     rcx, [rsp+290h+Destination]; DestinationString
0x140155cf2  call    cs:__imp_RtlCopyUnicodeString
0x140155cf9  nop     dword ptr [rax+rax+00h]
0x140155cfe  lea     rdx, [rsp+290h+DestinationString]; Source
0x140155d03  lea     rcx, [rsp+290h+Destination]; Destination
0x140155d08  call    cs:__imp_RtlAppendUnicodeStringToString
0x140155d0f  nop     dword ptr [rax+rax+00h]
0x140155d14  lea     rdx, [rsp+290h+Source]; Source
0x140155d19  lea     rcx, [rsp+290h+Destination]; Destination
0x140155d1e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140155d25  nop     dword ptr [rax+rax+00h]
0x140155d2a  movzx   edx, byte ptr [rdi+38h]
0x140155d2e  mov     [rbp+190h+var_180.Header.Type], 86h
0x140155d32  cmp     dl, 6
0x140155d35  ja      short loc_140155D47
0x140155d37  jnz     loc_14015627F
0x140155d3d  cmp     byte ptr [rdi+39h], 1Eh
0x140155d41  jb      loc_1401563A4
0x140155d47  mov     r8b, 4
0x140155d4a  mov     eax, 138h
0x140155d4f  mov     [rbp+190h+var_180.Header.Size], ax
0x140155d53  lea     rax, [rsp+290h+Destination]
0x140155d58  mov     [rbp+190h+var_180.ProtocolSection], rax
0x140155d5c  mov     rax, [rbx+0EF8h]
0x140155d63  mov     [rbp+190h+var_180.PhysicalDeviceObject], rax
0x140155d67  mov     eax, [rbx+238h]
0x140155d6d  and     eax, 80000001h
0x140155d72  mov     [rbp+190h+var_180.Header.Revision], r8b
0x140155d76  mov     [rbp+190h+var_180.AdapterName], r12
0x140155d7a  mov     [rbp+190h+var_180.BoundAdapterName], r15
0x140155d81  cmp     eax, 80000001h
0x140155d86  jz      loc_1401561F7
0x140155d8c  mov     eax, [rbx+1D0h]
0x140155d92  mov     [rbp+190h+var_180.MediaType], eax
0x140155d95  mov     rcx, [rbx+800h]
0x140155d9c  test    rcx, rcx
0x140155d9f  jnz     loc_140156170
0x140155da5  mov     rax, [rbx+318h]
0x140155dac  mov     rcx, [rbx+0FC8h]
0x140155db3  mov     [rbp+190h+var_180.XmitLinkSpeed], rax
0x140155db7  mov     rax, [rbx+320h]
0x140155dbe  mov     [rbp+190h+var_180.RcvLinkSpeed], rax
0x140155dc2  mov     eax, [rcx+4C4h]
0x140155dc8  mov     [rbp+190h+var_180.MediaConnectState], eax
0x140155dcb  mov     eax, [rcx+4C8h]
0x140155dd1  mov     [rbp+190h+var_180.MediaDuplexState], eax
0x140155dd4  mov     eax, [rbx+0BCCh]
0x140155dda  mov     [rbp+190h+var_180.MtuSize], eax
0x140155ddd  mov     rax, [rbx+0BD0h]
0x140155de4  mov     [rbp+190h+var_180.MaxXmitLinkSpeed], rax
0x140155de8  mov     rax, [rbx+0BD8h]
0x140155def  mov     [rbp+190h+var_180.MaxRcvLinkSpeed], rax
0x140155df3  mov     eax, [rbx+0BE0h]
0x140155df9  mov     [rbp+190h+var_180.LookaheadSize], eax
0x140155dfc  mov     eax, [rbx+0BE8h]
0x140155e02  mov     [rbp+190h+var_180.SupportedPacketFilters], eax
0x140155e05  mov     eax, [rbx+0BECh]
0x140155e0b  mov     [rbp+190h+var_180.MaxMulticastListSize], eax
0x140155e0e  mov     eax, [rbx+728h]
0x140155e14  mov     [rbp+190h+var_180.PhysicalMediumType], eax
0x140155e1a  lea     rax, [rbx+0C20h]
0x140155e21  mov     [rbp+190h+var_180.RcvScaleCapabilities], rax
0x140155e28  cmp     dl, 6
0x140155e2b  jbe     loc_140156154
0x140155e31  lea     rax, [rbx+424h]
0x140155e38  mov     [rbp+190h+var_180.PowerManagementCapabilitiesEx], rax
0x140155e3f  mov     rcx, [rbx+1000h]
0x140155e46  test    rcx, rcx
0x140155e49  jnz     loc_14015624E
0x140155e4f  mov     rcx, [rbx+10A8h]
0x140155e56  mov     rax, [rbp+190h+var_180.HDSplitCurrentConfig]
0x140155e5d  test    rcx, rcx
0x140155e60  mov     r10, [rbx+0DF8h]
0x140155e67  cmovnz  rax, rcx
0x140155e6b  mov     rcx, [rbx+0DE0h]
0x140155e72  mov     [rbp+190h+var_180.HDSplitCurrentConfig], rax
0x140155e79  test    rcx, rcx
0x140155e7c  mov     rax, [rbp+190h+var_180.ReceiveFilterCapabilities]
0x140155e83  cmovnz  rax, rcx
0x140155e87  test    r10, r10
0x140155e8a  mov     [rbp+190h+var_180.ReceiveFilterCapabilities], rax
0x140155e91  mov     rax, [rbp+190h+var_180.NicSwitchCapabilities]
0x140155e98  cmovnz  rax, r10
0x140155e9c  mov     [rbp+190h+var_180.NicSwitchCapabilities], rax
0x140155ea3  cmp     dl, 6
0x140155ea6  ja      loc_1401561D3
0x140155eac  jnz     short loc_140155EB8
0x140155eae  cmp     byte ptr [rdi+39h], 1Eh
0x140155eb2  jnb     loc_1401561D3
0x140155eb8  cmp     r8b, 4
0x140155ebc  jnb     loc_14015619A
0x140155ec2  mov     rdx, [rbx+0FC8h]
0x140155ec9  lea     rcx, [rbp+190h+var_180.CurrentMacAddress]; void *
0x140155ecd  movzx   eax, word ptr [rdx+464h]
0x140155ed4  add     rdx, 466h; Src
0x140155edb  mov     r8d, eax; Size
0x140155ede  mov     [rbp+190h+var_180.MacAddressLength], ax
0x140155ee2  call    memmove
0x140155ee7  lea     rax, [rbp+190h+var_180.LowestIfNetluid]
0x140155eee  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140155ef1  lea     r9, [rbp+190h+var_180.LowestIfIndex]; unsigned int *
0x140155ef8  mov     [rsp+290h+BugCheckParameter4], rax; union _NET_LUID_LH *
0x140155efd  lea     r8, [rbp+190h+var_180.BoundIfNetluid]; union _NET_LUID_LH *
0x140155f04  lea     rdx, [rbp+190h+var_180.BoundIfIndex]; unsigned int *
0x140155f0b  call    ?ndisIfQueryBindingMiniportIfIndex@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAKPEAT_NET_LUID_LH@@12@Z; ndisIfQueryBindingMiniportIfIndex(_NDIS_MINIPORT_BLOCK *,ulong *,_NET_LUID_LH *,ulong *,_NET_LUID_LH *)
0x140155f10  mov     rcx, [rbx+0FC8h]
0x140155f17  lea     rdx, [rbp+190h+var_180.ActivePorts]; struct _NDIS_PORT **
0x140155f1e  mov     eax, [rbx+0BF8h]
0x140155f24  mov     [rbp+190h+var_180.AccessType], eax
0x140155f2a  mov     eax, [rcx+214h]
0x140155f30  mov     [rbp+190h+var_180.DirectionType], eax
0x140155f36  mov     eax, [rbx+0C00h]
0x140155f3c  mov     [rbp+190h+var_180.ConnectionType], eax
0x140155f42  movzx   eax, word ptr [rcx+20Ch]
0x140155f49  mov     [rbp+190h+var_180.IfType], ax
0x140155f50  movzx   eax, byte ptr [rcx+22Ch]
0x140155f57  mov     [rbp+190h+var_180.IfConnectorPresent], al
0x140155f5d  mov     eax, [rbx+0C08h]
0x140155f63  mov     [rbp+190h+var_180.DataBackFillSize], eax
0x140155f69  mov     eax, [rbx+0C0Ch]
0x140155f6f  mov     [rbp+190h+var_180.ContextBackFillSize], eax
0x140155f75  mov     eax, [rbx+0BE4h]
0x140155f7b  mov     [rbp+190h+var_180.MacOptions], eax
0x140155f81  mov     eax, [rcx+240h]
0x140155f87  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140155f8a  mov     [rbp+190h+var_180.CompartmentId], eax
0x140155f90  call    ?ndisGetPortList@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAPEAU_NDIS_PORT@@@Z; ndisGetPortList(_NDIS_MINIPORT_BLOCK *,_NDIS_PORT * *)
0x140155f95  xor     edx, edx; Tag
0x140155f97  test    eax, eax
0x140155f99  jnz     loc_140156203
0x140155f9f  movzx   eax, [rsp+290h+Destination.Length]
0x140155fa4  lea     rcx, [rbp+190h+Event]; Event
0x140155fa8  mov     [rbp+190h+var_1F0], ax
0x140155fac  xor     r8d, r8d; State
0x140155faf  movzx   eax, [rsp+290h+Destination.MaximumLength]
0x140155fb4  mov     [rbp+190h+var_1EE], ax
0x140155fb8  mov     eax, dword ptr [rsp+290h+Destination+4]
0x140155fbc  mov     [rbp+190h+var_1EC], eax
0x140155fbf  mov     rax, [rsp+290h+Destination.Buffer]
0x140155fc4  mov     [rbp+190h+var_1E8], rax
0x140155fc8  mov     [rbp+190h+BugCheckParameter3], r14
0x140155fcc  mov     [rbp+190h+var_208], rdi
0x140155fd0  mov     [rbp+190h+var_1F8], rbx
0x140155fd4  mov     [rbp+190h+var_1E0], r12
0x140155fd8  mov     [rbp+190h+var_200], r14
0x140155fdc  call    cs:__imp_KeInitializeEvent
0x140155fe3  nop     dword ptr [rax+rax+00h]
0x140155fe8  lea     r8, [rbp+190h+var_180]; struct _NDIS_BIND_PARAMETERS *
0x140155fec  mov     [rdi+1C8h], rbx
0x140155ff3  lea     rdx, [rbp+190h+BugCheckParameter3]; void *
0x140155ff7  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x140155ffa  call    ?ndisInvokeBindAdapter@@YAHPEAU_NDIS_PROTOCOL_BLOCK@@PEAXPEAU_NDIS_BIND_PARAMETERS@@@Z; ndisInvokeBindAdapter(_NDIS_PROTOCOL_BLOCK *,void *,_NDIS_BIND_PARAMETERS *)
0x140155fff  mov     r14d, eax
0x140156002  cmp     eax, 103h
0x140156007  jz      loc_1401563C5
0x14015600d  test    r14d, r14d
0x140156010  jz      loc_140156221
0x140156016  mov     rcx, [rsp+290h+Destination.Buffer]; P
0x14015601b  xor     sil, sil
0x14015601e  xor     edx, edx; Tag
0x140156020  call    cs:__imp_ExFreePoolWithTag
0x140156027  nop     dword ptr [rax+rax+00h]
0x14015602c  lea     rax, WPP_RECORDER_INITIALIZED
0x140156033  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14015603a  jz      short loc_140156068
0x14015603c  mov     rcx, cs:WPP_GLOBAL_Control
0x140156043  mov     r9d, 1Ch
0x140156049  mov     rax, [rbx+0F10h]
0x140156050  mov     [rsp+290h+var_258], r14d
0x140156055  mov     qword ptr [rsp+290h+var_260], rax
0x14015605a  mov     rcx, [rcx+40h]
0x14015605e  mov     qword ptr [rsp+290h+var_268], r13
0x140156063  call    WPP_RECORDER_SF_ZZL
0x140156068  test    cs:byte_14011B001, 2
0x14015606f  jz      short loc_1401560A4
0x140156071  mov     rax, [rdi+50h]
0x140156075  lea     r8, [rbx+0FA8h]
0x14015607c  mov     [rsp+290h+var_258], r14d
0x140156081  mov     r9, r8
0x140156084  mov     qword ptr [rsp+290h+var_260], rax
0x140156089  mov     rax, [rbx+0FB8h]
0x140156090  mov     qword ptr [rsp+290h+var_268], rax
0x140156095  mov     eax, [rbx+0FD8h]
0x14015609b  mov     dword ptr [rsp+290h+BugCheckParameter4], eax
0x14015609f  call    McTemplateK0jqxzd_EtwWriteTransfer
0x1401560a4  movzx   r15d, [rsp+290h+var_250]
0x1401560aa  mov     rcx, rdi; struct _NDIS_PROTOCOL_BLOCK *
0x1401560ad  call    ?RELEASE_PROT_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; RELEASE_PROT_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x1401560b2  test    r15b, r15b
0x1401560b5  jz      short loc_1401560CA
0x1401560b7  mov     rcx, [rbp+190h+var_200]
0x1401560bb  mov     dl, 2
0x1401560bd  call    ?ndisMDereferenceOpenUnlocked@@YAXPEAU_NDIS_OPEN_BLOCK@@W4_NDIS_OPEN_REFTAG@@@Z; ndisMDereferenceOpenUnlocked(_NDIS_OPEN_BLOCK *,_NDIS_OPEN_REFTAG)
0x1401560c2  mov     [rbp+190h+var_200], 0
0x1401560ca  test    sil, sil
0x1401560cd  jnz     loc_1401563E8
0x1401560d3  mov     r8b, 8; enum _NDIS_PT_REFTAG
0x1401560d6  xor     edx, edx; unsigned __int8
  ... truncated ...
```
