# DriverEntry

- ea: `0x14001f078`
- end: `0x14001f259`
- name: `DriverEntry`
- size: `481`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001f010`

## callees

- `0x1400071e0`
- `0x140007ac0`
- `0x1400159f0`
- `0x14001a484`
- `0x14001af14`
- `0x14001b440`
- `0x14001f078`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001f0b8`
- `ntoskrnl!KeInitializeEvent` at `0x14001f0b8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001f11c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001f11c`
- `NDIS!NdisMRegisterMiniportDriver` at `0x14001f1d3`
- `NDIS!NdisMRegisterMiniportDriver` at `0x14001f1d3`
- `NETIO!NmrRegisterClient` at `0x14001f0e3`
- `NETIO!NmrRegisterClient` at `0x14001f0e3`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  NDIS_STATUS started; // ebx
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics; // [rsp+30h] [rbp-69h] BYREF

  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  NsiCliTag = 1850758224;
  KeInitializeEvent(&NsiCliDriverUnloadEvent, NotificationEvent, 0);
  xmmword_14000B1A8 = NsiPptpGuid;
  result = NmrRegisterClient(&NsiCliNotify, 0, &NsiCliHandle);
  if ( !result )
  {
    _InterlockedIncrement(&NsiCliDriverRefCount);
    started = WskStartClientModule();
    if ( started )
    {
      NsiCliDeregisterClient();
      return started;
    }
    KeInitializeSpinLock(&gCallbackLock);
    MiniportDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)9962122;
    MiniportDriverCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)MiniportSetOptions;
    *(_DWORD *)&MiniportDriverCharacteristics.MajorNdisVersion = 73222;
    MiniportDriverCharacteristics.InitializeHandlerEx = (MINIPORT_INITIALIZE_HANDLER)MiniportInitializeEx;
    MiniportDriverCharacteristics.HaltHandlerEx = (MINIPORT_HALT_HANDLER)MiniportHaltEx;
    MiniportDriverCharacteristics.UnloadHandler = (MINIPORT_DRIVER_UNLOAD)MiniportUnload;
    MiniportDriverCharacteristics.PauseHandler = (MINIPORT_PAUSE_HANDLER)MiniportPause;
    MiniportDriverCharacteristics.RestartHandler = (MINIPORT_RESTART_HANDLER)MiniportRestart;
    MiniportDriverCharacteristics.SendNetBufferListsHandler = (MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER)PptpCmOidRequestComplete;
    MiniportDriverCharacteristics.ReturnNetBufferListsHandler = (MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER)&MiniportReturnNetBufferLists;
    MiniportDriverCharacteristics.CancelSendHandler = (MINIPORT_CANCEL_SEND_HANDLER)PptpCmOidRequestComplete;
    MiniportDriverCharacteristics.DevicePnPEventNotifyHandler = (MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER)PptpCmOidRequestComplete;
    MiniportDriverCharacteristics.ShutdownHandlerEx = (MINIPORT_SHUTDOWN_HANDLER)PptpCmOidRequestComplete;
    MiniportDriverCharacteristics.CancelOidRequestHandler = (MINIPORT_CANCEL_OID_REQUEST_HANDLER)PptpCmOidRequestComplete;
    started = NdisMRegisterMiniportDriver(
                DriverObject,
                RegistryPath,
                0,
                &MiniportDriverCharacteristics,
                &gMiniportDriverHandle);
    if ( started )
    {
      MiniportUnload(DriverObject);
      return started;
    }
    WPP_MAIN_CB.DeviceExtension = DriverObject;
    WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.NextDevice = 0;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (PIO_TIMER)1;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    WppInitKm();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001f078  push    rbp
0x14001f07a  push    rbx
0x14001f07b  push    rsi
0x14001f07c  push    rdi
0x14001f07d  push    r15
0x14001f07f  lea     rbp, [rsp-37h]
0x14001f084  sub     rsp, 0D0h
0x14001f08b  mov     rsi, rdx
0x14001f08e  mov     rdi, rcx
0x14001f091  xor     edx, edx; Val
0x14001f093  lea     rcx, [rbp+57h+MiniportDriverCharacteristics]; void *
0x14001f097  mov     r8d, 98h; Size
0x14001f09d  call    memset
0x14001f0a2  xor     r8d, r8d; State
0x14001f0a5  mov     cs:NsiCliTag, 6E505450h
0x14001f0af  xor     edx, edx; Type
0x14001f0b1  lea     rcx, NsiCliDriverUnloadEvent; Event
0x14001f0b8  call    cs:__imp_KeInitializeEvent
0x14001f0bf  nop     dword ptr [rax+rax+00h]
0x14001f0c4  movups  xmm0, cs:NsiPptpGuid
0x14001f0cb  lea     r8, NsiCliHandle; NmrClientHandle
0x14001f0d2  xor     edx, edx; ClientContext
0x14001f0d4  lea     rcx, NsiCliNotify; ClientCharacteristics
0x14001f0db  movdqu  cs:xmmword_14000B1A8, xmm0
0x14001f0e3  call    cs:__imp_NmrRegisterClient
0x14001f0ea  nop     dword ptr [rax+rax+00h]
0x14001f0ef  test    eax, eax
0x14001f0f1  jnz     loc_14001F24A
0x14001f0f7  lock inc cs:NsiCliDriverRefCount
0x14001f0fe  call    WskStartClientModule
0x14001f103  mov     ebx, eax
0x14001f105  test    eax, eax
0x14001f107  jz      short loc_14001F115
0x14001f109  call    NsiCliDeregisterClient
0x14001f10e  mov     eax, ebx
0x14001f110  jmp     loc_14001F24A
0x14001f115  lea     rcx, gCallbackLock; SpinLock
0x14001f11c  call    cs:__imp_KeInitializeSpinLock
0x14001f123  nop     dword ptr [rax+rax+00h]
0x14001f128  lea     rax, MiniportSetOptions
0x14001f12f  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.Header.Type], 98028Ah
0x14001f136  mov     [rbp+57h+MiniportDriverCharacteristics.SetOptionsHandler], rax
0x14001f13a  lea     r9, [rbp+57h+MiniportDriverCharacteristics]; MiniportDriverCharacteristics
0x14001f13e  lea     rax, MiniportInitializeEx
0x14001f145  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.MajorNdisVersion], 11E06h
0x14001f14c  mov     [rbp+57h+MiniportDriverCharacteristics.InitializeHandlerEx], rax
0x14001f150  xor     r8d, r8d; MiniportDriverContext
0x14001f153  lea     rax, MiniportHaltEx
0x14001f15a  mov     rdx, rsi; RegistryPath
0x14001f15d  mov     [rbp+57h+MiniportDriverCharacteristics.HaltHandlerEx], rax
0x14001f161  mov     rcx, rdi; DriverObject
0x14001f164  lea     rax, MiniportUnload
0x14001f16b  mov     [rbp+57h+MiniportDriverCharacteristics.UnloadHandler], rax
0x14001f16f  lea     rax, MiniportPause
0x14001f176  mov     [rbp+57h+MiniportDriverCharacteristics.PauseHandler], rax
0x14001f17a  lea     rax, MiniportRestart
0x14001f181  mov     [rbp+57h+MiniportDriverCharacteristics.RestartHandler], rax
0x14001f185  lea     rax, PptpCmOidRequestComplete
0x14001f18c  mov     [rbp+57h+MiniportDriverCharacteristics.SendNetBufferListsHandler], rax
0x14001f190  lea     rax, MiniportReturnNetBufferLists
0x14001f197  mov     [rbp+57h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x14001f19b  lea     rax, PptpCmOidRequestComplete
0x14001f1a2  mov     [rbp+57h+MiniportDriverCharacteristics.CancelSendHandler], rax
0x14001f1a6  lea     rax, PptpCmOidRequestComplete
0x14001f1ad  mov     [rbp+57h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x14001f1b1  lea     rax, PptpCmOidRequestComplete
0x14001f1b8  mov     [rbp+57h+MiniportDriverCharacteristics.ShutdownHandlerEx], rax
0x14001f1bc  lea     rax, PptpCmOidRequestComplete
0x14001f1c3  mov     [rbp+57h+MiniportDriverCharacteristics.CancelOidRequestHandler], rax
0x14001f1c7  lea     rax, gMiniportDriverHandle
0x14001f1ce  mov     [rsp+0F0h+NdisMiniportDriverHandle], rax; NdisMiniportDriverHandle
0x14001f1d3  call    cs:__imp_NdisMRegisterMiniportDriver
0x14001f1da  nop     dword ptr [rax+rax+00h]
0x14001f1df  mov     ebx, eax
0x14001f1e1  test    eax, eax
0x14001f1e3  jz      short loc_14001F1F2
0x14001f1e5  mov     rcx, rdi
0x14001f1e8  call    MiniportUnload
0x14001f1ed  jmp     loc_14001F10E
0x14001f1f2  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14001f1f9  mov     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x14001f200  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001f207  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14001f212  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001f21d  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001f228  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001f233  call    WppLoadTracingSupport
0x14001f238  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001f243  call    WppInitKm
0x14001f248  xor     eax, eax
0x14001f24a  add     rsp, 0D0h
0x14001f251  pop     r15
0x14001f253  pop     rdi
0x14001f254  pop     rsi
0x14001f255  pop     rbx
0x14001f256  pop     rbp
0x14001f257  retn
```
