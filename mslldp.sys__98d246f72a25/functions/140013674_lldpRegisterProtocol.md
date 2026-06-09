# lldpRegisterProtocol

- ea: `0x140013674`
- end: `0x140013790`
- name: `lldpRegisterProtocol`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013350`

## callees

- `0x140004b00`
- `0x140013674`

## import_xrefs

- `NDIS!NdisRegisterProtocolDriver` at `0x140013739`
- `NDIS!NdisRegisterProtocolDriver` at `0x140013739`

## pseudocode

```c
__int64 lldpRegisterProtocol()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics; // [rsp+20h] [rbp-29h] BYREF

  *(_QWORD *)&ProtocolCharacteristics.Flags = 2;
  ProtocolCharacteristics.Name.Buffer = L"MsLldp";
  v0 = 0;
  *(_QWORD *)&ProtocolCharacteristics.Name.Length = 917516;
  ProtocolCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)lldpProtSetOptions;
  ProtocolCharacteristics.BindAdapterHandlerEx = (BIND_HANDLER_EX)&lldpProtBindAdapter;
  ProtocolCharacteristics.UnbindAdapterHandlerEx = (UNBIND_HANDLER_EX)&lldpProtUnbindAdapter;
  ProtocolCharacteristics.OpenAdapterCompleteHandlerEx = (OPEN_ADAPTER_COMPLETE_HANDLER_EX)lldpProtOpenAdapterComplete;
  ProtocolCharacteristics.CloseAdapterCompleteHandlerEx = (CLOSE_ADAPTER_COMPLETE_HANDLER_EX)lldpProtCloseAdapterComplete;
  ProtocolCharacteristics.NetPnPEventHandler = (NET_PNP_EVENT_HANDLER)lldpProtNetPnPEvent;
  ProtocolCharacteristics.OidRequestCompleteHandler = (OID_REQUEST_COMPLETE_HANDLER)lldpProtOidRequestComplete;
  ProtocolCharacteristics.StatusHandlerEx = (STATUS_HANDLER_EX)lldpProtStatus;
  ProtocolCharacteristics.ReceiveNetBufferListsHandler = (RECEIVE_NET_BUFFER_LISTS_HANDLER)&lldpProtReceiveNetBufferLists;
  ProtocolCharacteristics.SendNetBufferListsCompleteHandler = (SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)lldpProtSendNetBufferListsComplete;
  ProtocolCharacteristics.Header = (NDIS_OBJECT_HEADER)8389269;
  *(_DWORD *)&ProtocolCharacteristics.MajorNdisVersion = 678150;
  ProtocolCharacteristics.UninstallHandler = 0;
  ProtocolCharacteristics.DirectOidRequestCompleteHandler = 0;
  v1 = NdisRegisterProtocolDriver(
         &WPP_MAIN_CB.DeviceExtension,
         &ProtocolCharacteristics,
         (PNDIS_HANDLE)&WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( v1 )
  {
    v0 = v1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_acd65dca497b3543092d0321cbce568c_Traceguids, v1);
  }
  return v0;
}

```

## disassembly

```asm
0x140013674  mov     [rsp-8+arg_0], rbx
0x140013679  push    rbp
0x14001367a  lea     rbp, [rsp-57h]
0x14001367f  sub     rsp, 0A0h
0x140013686  lea     rax, aMslldp; "MsLldp"
0x14001368d  mov     qword ptr [rbp+57h+ProtocolCharacteristics.Flags], 2
0x140013695  mov     [rbp+57h+ProtocolCharacteristics.Name.Buffer], rax
0x140013699  xor     ebx, ebx
0x14001369b  lea     rax, lldpProtSetOptions
0x1400136a2  mov     qword ptr [rbp+57h+ProtocolCharacteristics.Name.Length], 0E000Ch
0x1400136aa  mov     [rbp+57h+ProtocolCharacteristics.SetOptionsHandler], rax
0x1400136ae  lea     rax, lldpProtBindAdapter
0x1400136b5  mov     [rbp+57h+ProtocolCharacteristics.BindAdapterHandlerEx], rax
0x1400136b9  lea     rax, lldpProtUnbindAdapter
0x1400136c0  mov     [rbp+57h+ProtocolCharacteristics.UnbindAdapterHandlerEx], rax
0x1400136c4  lea     rax, lldpProtOpenAdapterComplete
0x1400136cb  mov     [rbp+57h+ProtocolCharacteristics.OpenAdapterCompleteHandlerEx], rax
0x1400136cf  lea     rax, lldpProtCloseAdapterComplete
0x1400136d6  mov     [rbp+57h+ProtocolCharacteristics.CloseAdapterCompleteHandlerEx], rax
0x1400136da  lea     rax, lldpProtNetPnPEvent
0x1400136e1  mov     [rbp+57h+ProtocolCharacteristics.NetPnPEventHandler], rax
0x1400136e5  lea     rax, lldpProtOidRequestComplete
0x1400136ec  mov     [rbp+57h+ProtocolCharacteristics.OidRequestCompleteHandler], rax
0x1400136f0  lea     rax, lldpProtStatus
0x1400136f7  mov     [rbp+57h+ProtocolCharacteristics.StatusHandlerEx], rax
0x1400136fb  lea     rax, lldpProtReceiveNetBufferLists
0x140013702  mov     [rbp+57h+ProtocolCharacteristics.ReceiveNetBufferListsHandler], rax
0x140013706  lea     rax, lldpProtSendNetBufferListsComplete
0x14001370d  mov     [rbp+57h+ProtocolCharacteristics.SendNetBufferListsCompleteHandler], rax
0x140013711  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Header.Type], 800295h
0x140013718  mov     dword ptr [rbp+57h+ProtocolCharacteristics.MajorNdisVersion], 0A5906h
0x14001371f  mov     [rbp+57h+ProtocolCharacteristics.UninstallHandler], rbx
0x140013723  mov     [rbp+57h+ProtocolCharacteristics.DirectOidRequestCompleteHandler], rbx
0x140013727  lea     r8, WPP_MAIN_CB.Queue; NdisProtocolHandle
0x14001372e  lea     rdx, [rbp+57h+ProtocolCharacteristics]; ProtocolCharacteristics
0x140013732  lea     rcx, WPP_MAIN_CB.DeviceExtension; ProtocolDriverContext
0x140013739  call    cs:__imp_NdisRegisterProtocolDriver
0x140013740  nop     dword ptr [rax+rax+00h]
0x140013745  test    eax, eax
0x140013747  jz      short loc_14001377C
0x140013749  mov     ebx, eax
0x14001374b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013752  lea     r8, WPP_GLOBAL_Control
0x140013759  cmp     rcx, r8
0x14001375c  jz      short loc_14001377C
0x14001375e  cmp     byte ptr [rcx+29h], 2
0x140013762  jb      short loc_14001377C
0x140013764  mov     rcx, [rcx+18h]
0x140013768  lea     r8, WPP_acd65dca497b3543092d0321cbce568c_Traceguids
0x14001376f  mov     edx, 0Ah
0x140013774  mov     r9d, eax
0x140013777  call    WPP_SF_d
0x14001377c  mov     eax, ebx
0x14001377e  mov     rbx, [rsp+0A0h+arg_0]
0x140013786  add     rsp, 0A0h
0x14001378d  pop     rbp
0x14001378e  retn
```
