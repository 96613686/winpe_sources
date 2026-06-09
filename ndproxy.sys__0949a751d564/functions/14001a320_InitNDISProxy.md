# InitNDISProxy

- ea: `0x14001a320`
- end: `0x14001a4ce`
- name: `InitNDISProxy`
- size: `430`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001a4d4`

## callees

- `0x140001b54`
- `0x1400084c0`
- `0x14001a100`
- `0x14001a320`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a3f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a3f9`
- `NDIS!NdisRegisterProtocolDriver` at `0x14001a454`
- `NDIS!NdisRegisterProtocolDriver` at `0x14001a454`
- `NDIS!NdisInitializeEvent` at `0x14001a410`
- `NDIS!NdisInitializeEvent` at `0x14001a410`
- `NDIS!NdisSetEvent` at `0x14001a4aa`
- `NDIS!NdisSetEvent` at `0x14001a4aa`

## pseudocode

```c
char InitNDISProxy()
{
  _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics; // [rsp+20h] [rbp-29h] BYREF

  memset(&ProtocolCharacteristics, 0, sizeof(ProtocolCharacteristics));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids);
  ProtocolCharacteristics.Header = (NDIS_OBJECT_HEADER)8389269;
  ProtocolCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)PxSetOptionsHandler;
  *(_DWORD *)&ProtocolCharacteristics.MajorNdisVersion = 73222;
  ProtocolCharacteristics.BindAdapterHandlerEx = (BIND_HANDLER_EX)PxCoBindAdapterEx;
  ProtocolCharacteristics.Flags = -1073741824;
  ProtocolCharacteristics.UnbindAdapterHandlerEx = (UNBIND_HANDLER_EX)&PxCoUnbindAdapterEx;
  ProtocolCharacteristics.OpenAdapterCompleteHandlerEx = (OPEN_ADAPTER_COMPLETE_HANDLER_EX)PxCoOpenAdaperCompleteEx;
  ProtocolCharacteristics.CloseAdapterCompleteHandlerEx = (CLOSE_ADAPTER_COMPLETE_HANDLER_EX)PxCoCloseAdapterCompleteEx;
  ProtocolCharacteristics.NetPnPEventHandler = (NET_PNP_EVENT_HANDLER)PxCoNetPnPEvent;
  ProtocolCharacteristics.OidRequestCompleteHandler = (OID_REQUEST_COMPLETE_HANDLER)PxCoOidRequestComplete;
  ProtocolCharacteristics.ReceiveNetBufferListsHandler = (RECEIVE_NET_BUFFER_LISTS_HANDLER)PxReceiveNetBufferLists;
  ProtocolCharacteristics.SendNetBufferListsCompleteHandler = (SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)PxSendNetBufferListsComplete;
  RtlInitUnicodeString(&ProtocolCharacteristics.Name, L"NDProxy");
  NdisInitializeEvent((PNDIS_EVENT)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 64));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids);
  if ( NdisRegisterProtocolDriver(0, &ProtocolCharacteristics, (PNDIS_HANDLE)WPP_MAIN_CB.Dpc.DeferredRoutine + 3) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids);
    return 0;
  }
  else
  {
    GetRegistryParameters(*((void **)WPP_MAIN_CB.Dpc.DeferredRoutine + 3));
    NdisSetEvent((PNDIS_EVENT)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 64));
    return 1;
  }
}

```

## disassembly

```asm
0x14001a320  mov     [rsp-8+arg_0], rsi
0x14001a325  mov     [rsp-8+arg_8], rdi
0x14001a32a  push    rbp
0x14001a32b  lea     rbp, [rsp-57h]
0x14001a330  sub     rsp, 0A0h
0x14001a337  xor     edx, edx; Val
0x14001a339  lea     rcx, [rbp+57h+ProtocolCharacteristics]; void *
0x14001a33d  mov     r8d, 80h; Size
0x14001a343  call    memset
0x14001a348  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a34f  lea     rdi, WPP_GLOBAL_Control
0x14001a356  cmp     rcx, rdi
0x14001a359  jz      short loc_14001A376
0x14001a35b  cmp     byte ptr [rcx+29h], 4
0x14001a35f  jb      short loc_14001A376
0x14001a361  mov     rcx, [rcx+18h]
0x14001a365  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a36c  mov     edx, 0Ah
0x14001a371  call    WPP_SF_
0x14001a376  lea     rax, PxSetOptionsHandler
0x14001a37d  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Header.Type], 800295h
0x14001a384  mov     [rbp+57h+ProtocolCharacteristics.SetOptionsHandler], rax
0x14001a388  lea     rdx, aNdproxy_0; "NDProxy"
0x14001a38f  lea     rax, PxCoBindAdapterEx
0x14001a396  mov     dword ptr [rbp+57h+ProtocolCharacteristics.MajorNdisVersion], 11E06h
0x14001a39d  mov     [rbp+57h+ProtocolCharacteristics.BindAdapterHandlerEx], rax
0x14001a3a1  lea     rcx, [rbp+57h+ProtocolCharacteristics.Name]; DestinationString
0x14001a3a5  lea     rax, PxCoUnbindAdapterEx
0x14001a3ac  mov     [rbp+57h+ProtocolCharacteristics.Flags], 0C0000000h
0x14001a3b3  mov     [rbp+57h+ProtocolCharacteristics.UnbindAdapterHandlerEx], rax
0x14001a3b7  lea     rax, PxCoOpenAdaperCompleteEx
0x14001a3be  mov     [rbp+57h+ProtocolCharacteristics.OpenAdapterCompleteHandlerEx], rax
0x14001a3c2  lea     rax, PxCoCloseAdapterCompleteEx
0x14001a3c9  mov     [rbp+57h+ProtocolCharacteristics.CloseAdapterCompleteHandlerEx], rax
0x14001a3cd  lea     rax, PxCoNetPnPEvent
0x14001a3d4  mov     [rbp+57h+ProtocolCharacteristics.NetPnPEventHandler], rax
0x14001a3d8  lea     rax, PxCoOidRequestComplete
0x14001a3df  mov     [rbp+57h+ProtocolCharacteristics.OidRequestCompleteHandler], rax
0x14001a3e3  lea     rax, PxReceiveNetBufferLists
0x14001a3ea  mov     [rbp+57h+ProtocolCharacteristics.ReceiveNetBufferListsHandler], rax
0x14001a3ee  lea     rax, PxSendNetBufferListsComplete
0x14001a3f5  mov     [rbp+57h+ProtocolCharacteristics.SendNetBufferListsCompleteHandler], rax
0x14001a3f9  call    cs:__imp_RtlInitUnicodeString
0x14001a400  nop     dword ptr [rax+rax+00h]
0x14001a405  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a40c  add     rcx, 40h ; '@'; Event
0x14001a410  call    cs:__imp_NdisInitializeEvent
0x14001a417  nop     dword ptr [rax+rax+00h]
0x14001a41c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a423  cmp     rcx, rdi
0x14001a426  jz      short loc_14001A443
0x14001a428  cmp     byte ptr [rcx+29h], 5
0x14001a42c  jb      short loc_14001A443
0x14001a42e  mov     rcx, [rcx+18h]
0x14001a432  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a439  mov     edx, 0Bh
0x14001a43e  call    WPP_SF_
0x14001a443  mov     r8, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a44a  lea     rdx, [rbp+57h+ProtocolCharacteristics]; ProtocolCharacteristics
0x14001a44e  add     r8, 18h; NdisProtocolHandle
0x14001a452  xor     ecx, ecx; ProtocolDriverContext
0x14001a454  call    cs:__imp_NdisRegisterProtocolDriver
0x14001a45b  nop     dword ptr [rax+rax+00h]
0x14001a460  test    eax, eax
0x14001a462  jz      short loc_14001A48F
0x14001a464  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a46b  cmp     rcx, rdi
0x14001a46e  jz      short loc_14001A48B
0x14001a470  cmp     byte ptr [rcx+29h], 4
0x14001a474  jb      short loc_14001A48B
0x14001a476  mov     rcx, [rcx+18h]
0x14001a47a  lea     r8, WPP_34912d7d109837df8a78d6a31dde47b4_Traceguids
0x14001a481  mov     edx, 0Ch
0x14001a486  call    WPP_SF_
0x14001a48b  xor     al, al
0x14001a48d  jmp     short loc_14001A4B8
0x14001a48f  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a496  mov     rcx, [rcx+18h]
0x14001a49a  call    GetRegistryParameters
0x14001a49f  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a4a6  add     rcx, 40h ; '@'; Event
0x14001a4aa  call    cs:__imp_NdisSetEvent
0x14001a4b1  nop     dword ptr [rax+rax+00h]
0x14001a4b6  mov     al, 1
0x14001a4b8  lea     r11, [rsp+0A0h+var_s0]
0x14001a4c0  mov     rsi, [r11+10h]
0x14001a4c4  mov     rdi, [r11+18h]
0x14001a4c8  mov     rsp, r11
0x14001a4cb  pop     rbp
0x14001a4cc  retn
```
