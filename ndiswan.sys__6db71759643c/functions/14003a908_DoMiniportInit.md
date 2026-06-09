# DoMiniportInit

- ea: `0x14003a908`
- end: `0x14003aa13`
- name: `DoMiniportInit`
- size: `267`
- prototype: `__int64 __fastcall(PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x140039008`

## callees

- `0x140016700`

## import_xrefs

- `NDIS!NdisMRegisterMiniportDriver` at `0x14003a9f1`
- `NDIS!NdisMRegisterMiniportDriver` at `0x14003a9f1`

## pseudocode

```c
NDIS_STATUS __fastcall DoMiniportInit(PUNICODE_STRING RegistryPath)
{
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics; // [rsp+30h] [rbp-49h] BYREF

  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  MiniportDriverCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)MPSetOptions;
  MiniportDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)9962122;
  MiniportDriverCharacteristics.HaltHandlerEx = (MINIPORT_HALT_HANDLER)MPHaltEx;
  *(_DWORD *)&MiniportDriverCharacteristics.MajorNdisVersion = 16850438;
  MiniportDriverCharacteristics.InitializeHandlerEx = (MINIPORT_INITIALIZE_HANDLER)MPInitializeEx;
  MiniportDriverCharacteristics.UnloadHandler = (MINIPORT_DRIVER_UNLOAD)NdisWanUnload;
  MiniportDriverCharacteristics.PauseHandler = (MINIPORT_PAUSE_HANDLER)MPPause;
  MiniportDriverCharacteristics.RestartHandler = (MINIPORT_RESTART_HANDLER)MPRestart;
  MiniportDriverCharacteristics.SendNetBufferListsHandler = (MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER)MPSendNetBufferListChain;
  MiniportDriverCharacteristics.ReturnNetBufferListsHandler = (MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER)&MPReturnNetBufferListChain;
  MiniportDriverCharacteristics.CancelSendHandler = (MINIPORT_CANCEL_SEND_HANDLER)BwcEtwTraceQosPacketDrop;
  MiniportDriverCharacteristics.DevicePnPEventNotifyHandler = (MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER)BwcEtwTraceQosPacketDrop;
  MiniportDriverCharacteristics.ShutdownHandlerEx = (MINIPORT_SHUTDOWN_HANDLER)BwcEtwTraceQosPacketDrop;
  MiniportDriverCharacteristics.OidRequestHandler = (MINIPORT_OID_REQUEST_HANDLER)MPOidRequest;
  MiniportDriverCharacteristics.CancelOidRequestHandler = (MINIPORT_CANCEL_OID_REQUEST_HANDLER)BwcEtwTraceQosPacketDrop;
  return NdisMRegisterMiniportDriver(
           DriverObject,
           RegistryPath,
           &NdisWanCB,
           &MiniportDriverCharacteristics,
           &NdisMiniportDriverHandle);
}

```

## disassembly

```asm
0x14003a908  mov     [rsp-8+arg_0], rbx
0x14003a90d  mov     [rsp-8+arg_8], rdi
0x14003a912  push    rbp
0x14003a913  lea     rbp, [rsp-57h]
0x14003a918  sub     rsp, 0D0h
0x14003a91f  mov     rbx, rcx
0x14003a922  xor     edx, edx; Val
0x14003a924  lea     rcx, [rbp+57h+MiniportDriverCharacteristics]; void *
0x14003a928  mov     r8d, 98h; Size
0x14003a92e  call    memset
0x14003a933  mov     rcx, cs:DriverObject; DriverObject
0x14003a93a  lea     rax, MPSetOptions
0x14003a941  mov     [rbp+57h+MiniportDriverCharacteristics.SetOptionsHandler], rax
0x14003a945  lea     r9, [rbp+57h+MiniportDriverCharacteristics]; MiniportDriverCharacteristics
0x14003a949  lea     rax, MPHaltEx
0x14003a950  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.Header.Type], 98028Ah
0x14003a957  mov     [rbp+57h+MiniportDriverCharacteristics.HaltHandlerEx], rax
0x14003a95b  lea     r8, NdisWanCB; MiniportDriverContext
0x14003a962  lea     rax, MPInitializeEx
0x14003a969  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.MajorNdisVersion], 1011E06h
0x14003a970  mov     [rbp+57h+MiniportDriverCharacteristics.InitializeHandlerEx], rax
0x14003a974  mov     rdx, rbx; RegistryPath
0x14003a977  lea     rax, NdisWanUnload
0x14003a97e  mov     [rbp+57h+MiniportDriverCharacteristics.UnloadHandler], rax
0x14003a982  lea     rax, MPPause
0x14003a989  mov     [rbp+57h+MiniportDriverCharacteristics.PauseHandler], rax
0x14003a98d  lea     rax, MPRestart
0x14003a994  mov     [rbp+57h+MiniportDriverCharacteristics.RestartHandler], rax
0x14003a998  lea     rax, MPSendNetBufferListChain
0x14003a99f  mov     [rbp+57h+MiniportDriverCharacteristics.SendNetBufferListsHandler], rax
0x14003a9a3  lea     rax, MPReturnNetBufferListChain
0x14003a9aa  mov     [rbp+57h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x14003a9ae  lea     rax, BwcEtwTraceQosPacketDrop
0x14003a9b5  mov     [rbp+57h+MiniportDriverCharacteristics.CancelSendHandler], rax
0x14003a9b9  lea     rax, BwcEtwTraceQosPacketDrop
0x14003a9c0  mov     [rbp+57h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x14003a9c4  lea     rax, BwcEtwTraceQosPacketDrop
0x14003a9cb  mov     [rbp+57h+MiniportDriverCharacteristics.ShutdownHandlerEx], rax
0x14003a9cf  lea     rax, MPOidRequest
0x14003a9d6  mov     [rbp+57h+MiniportDriverCharacteristics.OidRequestHandler], rax
0x14003a9da  lea     rax, BwcEtwTraceQosPacketDrop
0x14003a9e1  mov     [rbp+57h+MiniportDriverCharacteristics.CancelOidRequestHandler], rax
0x14003a9e5  lea     rax, NdisMiniportDriverHandle
0x14003a9ec  mov     [rsp+0D0h+NdisMiniportDriverHandle], rax; NdisMiniportDriverHandle
0x14003a9f1  call    cs:__imp_NdisMRegisterMiniportDriver
0x14003a9f8  nop     dword ptr [rax+rax+00h]
0x14003a9fd  lea     r11, [rsp+0D0h+var_s0]
0x14003aa05  mov     rbx, [r11+10h]
0x14003aa09  mov     rdi, [r11+18h]
0x14003aa0d  mov     rsp, r11
0x14003aa10  pop     rbp
0x14003aa11  retn
```
