# DoProtocolInit

- ea: `0x140039970`
- end: `0x140039a4a`
- name: `DoProtocolInit`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140039008`

## import_xrefs

- `NDIS!NdisRegisterProtocolDriver` at `0x140039a34`
- `NDIS!NdisRegisterProtocolDriver` at `0x140039a34`

## pseudocode

```c
NDIS_STATUS DoProtocolInit()
{
  _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics; // [rsp+20h] [rbp-29h] BYREF

  ProtocolCharacteristics.Header = (NDIS_OBJECT_HEADER)8389269;
  *(_QWORD *)&ProtocolCharacteristics.Flags = 0;
  ProtocolCharacteristics.DirectOidRequestCompleteHandler = 0;
  ProtocolCharacteristics.Name.Buffer = L"NdisWan";
  ProtocolCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)ProtoSetOptions;
  ProtocolCharacteristics.BindAdapterHandlerEx = (BIND_HANDLER_EX)ProtoBindAdapterEx;
  ProtocolCharacteristics.UnbindAdapterHandlerEx = (UNBIND_HANDLER_EX)&ProtoUnbindAdapterEx;
  ProtocolCharacteristics.OpenAdapterCompleteHandlerEx = (OPEN_ADAPTER_COMPLETE_HANDLER_EX)ProtoOpenAdapterComplete;
  ProtocolCharacteristics.CloseAdapterCompleteHandlerEx = (CLOSE_ADAPTER_COMPLETE_HANDLER_EX)ProtoCloseAdapterComplete;
  ProtocolCharacteristics.NetPnPEventHandler = (NET_PNP_EVENT_HANDLER)ProtoPnPEvent;
  ProtocolCharacteristics.UninstallHandler = (UNINSTALL_PROTOCOL_HANDLER)ProtoUninstall;
  ProtocolCharacteristics.OidRequestCompleteHandler = (OID_REQUEST_COMPLETE_HANDLER)ProtoRequestComplete;
  ProtocolCharacteristics.StatusHandlerEx = (STATUS_HANDLER_EX)ProtoIndicateStatus;
  ProtocolCharacteristics.ReceiveNetBufferListsHandler = (RECEIVE_NET_BUFFER_LISTS_HANDLER)ProtoSendNetBufferListsComplete;
  ProtocolCharacteristics.SendNetBufferListsCompleteHandler = (SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)ProtoSendNetBufferListsComplete;
  *(_DWORD *)&ProtocolCharacteristics.MajorNdisVersion = 16850438;
  *(_QWORD *)&ProtocolCharacteristics.Name.Length = 1048590;
  return NdisRegisterProtocolDriver(&NdisWanCB, &ProtocolCharacteristics, &NdisProtocolHandle);
}

```

## disassembly

```asm
0x140039970  push    rbp
0x140039972  lea     rbp, [rsp-57h]
0x140039977  sub     rsp, 0A0h
0x14003997e  xor     eax, eax
0x140039980  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Header.Type], 800295h
0x140039987  mov     qword ptr [rbp+57h+ProtocolCharacteristics.Flags], rax
0x14003998b  mov     [rbp+57h+ProtocolCharacteristics.DirectOidRequestCompleteHandler], rax
0x14003998f  lea     rax, aNdiswan; "NdisWan"
0x140039996  mov     [rbp+57h+ProtocolCharacteristics.Name.Buffer], rax
0x14003999a  lea     rax, ProtoSetOptions
0x1400399a1  mov     [rbp+57h+ProtocolCharacteristics.SetOptionsHandler], rax
0x1400399a5  lea     rax, ProtoBindAdapterEx
0x1400399ac  mov     [rbp+57h+ProtocolCharacteristics.BindAdapterHandlerEx], rax
0x1400399b0  lea     rax, ProtoUnbindAdapterEx
0x1400399b7  mov     [rbp+57h+ProtocolCharacteristics.UnbindAdapterHandlerEx], rax
0x1400399bb  lea     rax, ProtoOpenAdapterComplete
0x1400399c2  mov     [rbp+57h+ProtocolCharacteristics.OpenAdapterCompleteHandlerEx], rax
0x1400399c6  lea     rax, ProtoCloseAdapterComplete
0x1400399cd  mov     [rbp+57h+ProtocolCharacteristics.CloseAdapterCompleteHandlerEx], rax
0x1400399d1  lea     rax, ProtoPnPEvent
0x1400399d8  mov     [rbp+57h+ProtocolCharacteristics.NetPnPEventHandler], rax
0x1400399dc  lea     rax, ProtoUninstall
0x1400399e3  mov     [rbp+57h+ProtocolCharacteristics.UninstallHandler], rax
0x1400399e7  lea     rax, ProtoRequestComplete
0x1400399ee  mov     [rbp+57h+ProtocolCharacteristics.OidRequestCompleteHandler], rax
0x1400399f2  lea     rax, ProtoIndicateStatus
0x1400399f9  mov     [rbp+57h+ProtocolCharacteristics.StatusHandlerEx], rax
0x1400399fd  lea     rax, ProtoSendNetBufferListsComplete
0x140039a04  mov     [rbp+57h+ProtocolCharacteristics.ReceiveNetBufferListsHandler], rax
0x140039a08  lea     rax, ProtoSendNetBufferListsComplete
0x140039a0f  mov     [rbp+57h+ProtocolCharacteristics.SendNetBufferListsCompleteHandler], rax
0x140039a13  mov     dword ptr [rbp+57h+ProtocolCharacteristics.MajorNdisVersion], 1011E06h
0x140039a1a  mov     qword ptr [rbp+57h+ProtocolCharacteristics.Name.Length], 10000Eh
0x140039a22  lea     r8, NdisProtocolHandle; NdisProtocolHandle
0x140039a29  lea     rdx, [rbp+57h+ProtocolCharacteristics]; ProtocolCharacteristics
0x140039a2d  lea     rcx, NdisWanCB; ProtocolDriverContext
0x140039a34  call    cs:__imp_NdisRegisterProtocolDriver
0x140039a3b  nop     dword ptr [rax+rax+00h]
0x140039a40  add     rsp, 0A0h
0x140039a47  pop     rbp
0x140039a48  retn
```
