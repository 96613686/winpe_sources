# DriverEntry

- ea: `0x140021080`
- end: `0x14002130a`
- name: `DriverEntry`
- size: `650`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140021010`

## callees

- `0x140001be0`
- `0x14001d010`
- `0x14001dd40`
- `0x14001eb80`
- `0x14001ecd0`
- `0x140021080`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140021264`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002128c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140021264`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002128c`
- `ntoskrnl!KeInitializeEvent` at `0x1400210e0`
- `ntoskrnl!KeInitializeEvent` at `0x1400210e0`
- `NDIS!NdisMRegisterMiniportDriver` at `0x1400211ed`
- `NDIS!NdisMRegisterMiniportDriver` at `0x1400211ed`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002121a`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002121a`
- `NETIO!NmrRegisterClient` at `0x14002110a`
- `NETIO!NmrRegisterClient` at `0x14002110a`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  NTSTATUS started; // ebx
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics; // [rsp+30h] [rbp-49h] BYREF

  NsiCliTag = 1934897740;
  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  KeInitializeEvent(&NsiCliDriverUnloadEvent, NotificationEvent, 0);
  xmmword_14000A120 = NsiL2tpGuid;
  result = NmrRegisterClient(&NsiCliNotify, 0, &NsiCliHandle);
  if ( !result )
  {
    _InterlockedIncrement(&NsiCliDriverRefCount);
    started = WskStartClientModule();
    if ( started )
    {
      NsiCliDeregisterClient();
    }
    else
    {
      MiniportDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)9962122;
      MiniportDriverCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)LmpSetOptions;
      *(_DWORD *)&MiniportDriverCharacteristics.MajorNdisVersion = 73222;
      MiniportDriverCharacteristics.InitializeHandlerEx = (MINIPORT_INITIALIZE_HANDLER)LmpInitializeEx;
      MiniportDriverCharacteristics.HaltHandlerEx = (MINIPORT_HALT_HANDLER)LmpHaltEx;
      MiniportDriverCharacteristics.UnloadHandler = (MINIPORT_DRIVER_UNLOAD)LmpUnload;
      MiniportDriverCharacteristics.PauseHandler = (MINIPORT_PAUSE_HANDLER)LmpPause;
      MiniportDriverCharacteristics.RestartHandler = (MINIPORT_RESTART_HANDLER)LmpRestart;
      MiniportDriverCharacteristics.SendNetBufferListsHandler = (MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER)guard_check_icall_nop;
      MiniportDriverCharacteristics.ReturnNetBufferListsHandler = (MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER)&LmpReturnNetBufferListChain;
      MiniportDriverCharacteristics.CancelSendHandler = (MINIPORT_CANCEL_SEND_HANDLER)guard_check_icall_nop;
      MiniportDriverCharacteristics.DevicePnPEventNotifyHandler = (MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER)guard_check_icall_nop;
      MiniportDriverCharacteristics.ShutdownHandlerEx = (MINIPORT_SHUTDOWN_HANDLER)guard_check_icall_nop;
      MiniportDriverCharacteristics.CancelOidRequestHandler = (MINIPORT_CANCEL_OID_REQUEST_HANDLER)guard_check_icall_nop;
      started = NdisMRegisterMiniportDriver(
                  DriverObject,
                  RegistryPath,
                  0,
                  &MiniportDriverCharacteristics,
                  &WPP_MAIN_CB.DeviceExtension);
      if ( started || (started = BCryptOpenAlgorithmProvider(&ghAlgMD5, L"MD5", 0, 1u)) != 0 )
      {
        LmpUnload(DriverObject);
      }
      else
      {
        g_stats = 0;
        xmmword_14000A2D0 = 0;
        xmmword_14000A2E0 = 0;
        xmmword_14000A2F0 = 0;
        xmmword_14000A300 = 0;
        xmmword_14000A310 = 0;
        KeInitializeSpinLock(&g_lockStats);
        qword_14000A298 = (__int64)&g_listDebugPs;
        g_listDebugPs = (__int64)&g_listDebugPs;
        KeInitializeSpinLock(&g_lockDebugPs);
        g_DriverObject = (__int64)DriverObject;
        WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
        *(_QWORD *)&WPP_MAIN_CB.Type = 0;
        WPP_MAIN_CB.NextDevice = 0;
        WPP_MAIN_CB.CurrentIrp = 0;
        WPP_MAIN_CB.Timer = (PIO_TIMER)1;
        WppLoadTracingSupport();
        WPP_MAIN_CB.CurrentIrp = 0;
        WppInitKm();
      }
    }
    return started;
  }
  return result;
}

```

## disassembly

```asm
0x140021080  mov     [rsp-8+arg_8], rsi
0x140021085  mov     [rsp-8+arg_10], rdi
0x14002108a  push    rbp
0x14002108b  lea     rbp, [rsp-57h]
0x140021090  sub     rsp, 0D0h
0x140021097  xorps   xmm0, xmm0
0x14002109a  mov     cs:NsiCliTag, 7354324Ch
0x1400210a4  mov     rsi, rdx
0x1400210a7  mov     rdi, rcx
0x1400210aa  xor     eax, eax
0x1400210ac  lea     rcx, NsiCliDriverUnloadEvent; Event
0x1400210b3  xor     edx, edx; Type
0x1400210b5  mov     [rbp+57h+MiniportDriverCharacteristics.CancelDirectOidRequestHandler], rax
0x1400210b9  xor     r8d, r8d; State
0x1400210bc  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.Header.Type], xmm0
0x1400210c0  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.SetOptionsHandler], xmm0
0x1400210c4  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.HaltHandlerEx], xmm0
0x1400210c8  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.PauseHandler], xmm0
0x1400210cc  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.OidRequestHandler], xmm0
0x1400210d0  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], xmm0
0x1400210d4  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.CheckForHangHandlerEx], xmm0
0x1400210d8  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], xmm0
0x1400210dc  movups  xmmword ptr [rbp+57h+MiniportDriverCharacteristics.CancelOidRequestHandler], xmm0
0x1400210e0  call    cs:__imp_KeInitializeEvent
0x1400210e7  nop     dword ptr [rax+rax+00h]
0x1400210ec  movups  xmm0, cs:NsiL2tpGuid
0x1400210f3  lea     r8, NsiCliHandle; NmrClientHandle
0x1400210fa  xor     edx, edx; ClientContext
0x1400210fc  lea     rcx, NsiCliNotify; ClientCharacteristics
0x140021103  movups  cs:xmmword_14000A120, xmm0
0x14002110a  call    cs:__imp_NmrRegisterClient
0x140021111  nop     dword ptr [rax+rax+00h]
0x140021116  test    eax, eax
0x140021118  jnz     loc_1400212F4
0x14002111e  mov     [rsp+0D0h+arg_0], rbx
0x140021126  lock inc cs:NsiCliDriverRefCount
0x14002112d  call    WskStartClientModule
0x140021132  mov     ebx, eax
0x140021134  test    eax, eax
0x140021136  jz      short loc_140021142
0x140021138  call    NsiCliDeregisterClient
0x14002113d  jmp     loc_1400212EA
0x140021142  lea     rax, LmpSetOptions
0x140021149  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.Header.Type], 98028Ah
0x140021150  mov     [rbp+57h+MiniportDriverCharacteristics.SetOptionsHandler], rax
0x140021154  lea     r9, [rbp+57h+MiniportDriverCharacteristics]; MiniportDriverCharacteristics
0x140021158  lea     rax, LmpInitializeEx
0x14002115f  mov     dword ptr [rbp+57h+MiniportDriverCharacteristics.MajorNdisVersion], 11E06h
0x140021166  mov     [rbp+57h+MiniportDriverCharacteristics.InitializeHandlerEx], rax
0x14002116a  xor     r8d, r8d; MiniportDriverContext
0x14002116d  lea     rax, LmpHaltEx
0x140021174  mov     rdx, rsi; RegistryPath
0x140021177  mov     [rbp+57h+MiniportDriverCharacteristics.HaltHandlerEx], rax
0x14002117b  mov     rcx, rdi; DriverObject
0x14002117e  lea     rax, LmpUnload
0x140021185  mov     [rbp+57h+MiniportDriverCharacteristics.UnloadHandler], rax
0x140021189  lea     rax, LmpPause
0x140021190  mov     [rbp+57h+MiniportDriverCharacteristics.PauseHandler], rax
0x140021194  lea     rax, LmpRestart
0x14002119b  mov     [rbp+57h+MiniportDriverCharacteristics.RestartHandler], rax
0x14002119f  lea     rax, _guard_check_icall_nop
0x1400211a6  mov     [rbp+57h+MiniportDriverCharacteristics.SendNetBufferListsHandler], rax
0x1400211aa  lea     rax, LmpReturnNetBufferListChain
0x1400211b1  mov     [rbp+57h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x1400211b5  lea     rax, _guard_check_icall_nop
0x1400211bc  mov     [rbp+57h+MiniportDriverCharacteristics.CancelSendHandler], rax
0x1400211c0  lea     rax, _guard_check_icall_nop
0x1400211c7  mov     [rbp+57h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x1400211cb  lea     rax, _guard_check_icall_nop
0x1400211d2  mov     [rbp+57h+MiniportDriverCharacteristics.ShutdownHandlerEx], rax
0x1400211d6  lea     rax, _guard_check_icall_nop
0x1400211dd  mov     [rbp+57h+MiniportDriverCharacteristics.CancelOidRequestHandler], rax
0x1400211e1  lea     rax, WPP_MAIN_CB.DeviceExtension
0x1400211e8  mov     [rsp+0D0h+NdisMiniportDriverHandle], rax; NdisMiniportDriverHandle
0x1400211ed  call    cs:__imp_NdisMRegisterMiniportDriver
0x1400211f4  nop     dword ptr [rax+rax+00h]
0x1400211f9  mov     ebx, eax
0x1400211fb  test    eax, eax
0x1400211fd  jnz     loc_1400212E2
0x140021203  mov     r9d, 1; dwFlags
0x140021209  lea     rdx, pszAlgId; "MD5"
0x140021210  xor     r8d, r8d; pszImplementation
0x140021213  lea     rcx, ghAlgMD5; phAlgorithm
0x14002121a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140021221  nop     dword ptr [rax+rax+00h]
0x140021226  mov     ebx, eax
0x140021228  test    eax, eax
0x14002122a  jnz     loc_1400212E2
0x140021230  xorps   xmm0, xmm0
0x140021233  lea     rcx, g_lockStats; SpinLock
0x14002123a  movups  cs:g_stats, xmm0
0x140021241  movups  cs:xmmword_14000A2D0, xmm0
0x140021248  movups  cs:xmmword_14000A2E0, xmm0
0x14002124f  movups  cs:xmmword_14000A2F0, xmm0
0x140021256  movups  cs:xmmword_14000A300, xmm0
0x14002125d  movups  cs:xmmword_14000A310, xmm0
0x140021264  call    cs:__imp_KeInitializeSpinLock
0x14002126b  nop     dword ptr [rax+rax+00h]
0x140021270  lea     rax, g_listDebugPs
0x140021277  lea     rcx, g_lockDebugPs; SpinLock
0x14002127e  mov     cs:qword_14000A298, rax
0x140021285  mov     cs:g_listDebugPs, rax
0x14002128c  call    cs:__imp_KeInitializeSpinLock
0x140021293  nop     dword ptr [rax+rax+00h]
0x140021298  mov     cs:g_DriverObject, rdi
0x14002129f  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x1400212a6  xor     edi, edi
0x1400212a8  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400212af  mov     qword ptr cs:WPP_MAIN_CB.Type, rdi
0x1400212b6  mov     cs:WPP_MAIN_CB.NextDevice, rdi
0x1400212bd  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x1400212c4  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400212cf  call    WppLoadTracingSupport
0x1400212d4  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x1400212db  call    WppInitKm
0x1400212e0  jmp     short loc_1400212EA
0x1400212e2  mov     rcx, rdi
0x1400212e5  call    LmpUnload
0x1400212ea  mov     eax, ebx
0x1400212ec  mov     rbx, [rsp+0D0h+arg_0]
0x1400212f4  lea     r11, [rsp+0D0h+var_s0]
0x1400212fc  mov     rsi, [r11+18h]
0x140021300  mov     rdi, [r11+20h]
0x140021304  mov     rsp, r11
0x140021307  pop     rbp
0x140021308  retn
```
