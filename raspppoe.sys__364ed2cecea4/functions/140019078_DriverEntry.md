# DriverEntry

- ea: `0x140019078`
- end: `0x14001941e`
- name: `DriverEntry`
- size: `934`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140019010`

## callees

- `0x140001020`
- `0x14000110c`
- `0x14000113c`
- `0x140006b40`
- `0x140007040`
- `0x14000d0c8`
- `0x14000d15c`
- `0x14000ef78`
- `0x140019078`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140019170`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140019170`
- `NDIS!NdisGetVersion` at `0x14001913a`
- `NDIS!NdisGetVersion` at `0x14001913a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001937b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001937b`
- `NDIS!NdisMRegisterMiniportDriver` at `0x140019287`
- `NDIS!NdisMRegisterMiniportDriver` at `0x140019287`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // ebx
  PVOID NdisMiniportDriverHandle; // [rsp+40h] [rbp-C0h] BYREF
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics; // [rsp+50h] [rbp-B0h] BYREF
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+F0h] [rbp-10h] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  Parameters = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids);
  }
  NdisGetVersion();
  ExInitializeNPagedLookasideList(&gl_llistWorkItems, 0, 0, 0x200u, 0x48u, 0x6D456F50u, 0);
  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  NdisMiniportDriverHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  MiniportDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)9962122;
  MiniportDriverCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)MpSetOptions;
  *(_DWORD *)&MiniportDriverCharacteristics.MajorNdisVersion = 73222;
  MiniportDriverCharacteristics.InitializeHandlerEx = (MINIPORT_INITIALIZE_HANDLER)MpInitializeEx;
  MiniportDriverCharacteristics.HaltHandlerEx = (MINIPORT_HALT_HANDLER)MpHaltEx;
  MiniportDriverCharacteristics.UnloadHandler = (MINIPORT_DRIVER_UNLOAD)MpUnload;
  MiniportDriverCharacteristics.PauseHandler = (MINIPORT_PAUSE_HANDLER)MpPause;
  MiniportDriverCharacteristics.RestartHandler = (MINIPORT_RESTART_HANDLER)MpRestart;
  MiniportDriverCharacteristics.SendNetBufferListsHandler = (MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER)PrUninstall;
  MiniportDriverCharacteristics.ReturnNetBufferListsHandler = (MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER)MpReturnNetBufferListChain;
  MiniportDriverCharacteristics.CancelSendHandler = (MINIPORT_CANCEL_SEND_HANDLER)PrUninstall;
  MiniportDriverCharacteristics.DevicePnPEventNotifyHandler = (MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER)PrUninstall;
  MiniportDriverCharacteristics.ShutdownHandlerEx = (MINIPORT_SHUTDOWN_HANDLER)PrUninstall;
  MiniportDriverCharacteristics.CancelOidRequestHandler = (MINIPORT_CANCEL_OID_REQUEST_HANDLER)PrUninstall;
  v4 = NdisMRegisterMiniportDriver(
         DriverObject,
         RegistryPath,
         0,
         &MiniportDriverCharacteristics,
         &NdisMiniportDriverHandle);
  v5 = v4;
  if ( !v4 )
    gl_NdisMiniportDriverHandle = NdisMiniportDriverHandle;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, v4);
  }
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_31;
    }
    v7 = 11;
    v8 = v5;
    goto LABEL_20;
  }
  v9 = PrRegisterProtocol();
  if ( v9 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_31;
    }
    v7 = 12;
    v8 = v9;
LABEL_20:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids, v8);
    goto LABEL_31;
  }
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  Parameters.ContextSize = 160;
  Parameters.fAllocateNetBuffer = 1;
  Parameters.PoolTag = 1665494864;
  Parameters.DataSize = 1514;
  gl_NblPoolHandle = NdisAllocateNetBufferListPool(gl_NdisMiniportDriverHandle, &Parameters);
  if ( gl_NblPoolHandle )
  {
    v10 = 0;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids);
  }
LABEL_31:
  RasPppoeCleanup();
  v10 = -1073741823;
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x140019078  mov     [rsp-8+arg_10], rbx
0x14001907d  push    rbp
0x14001907e  push    rdi
0x14001907f  push    r12
0x140019081  push    r13
0x140019083  push    r15
0x140019085  lea     rbp, [rsp-10h]
0x14001908a  sub     rsp, 110h
0x140019091  mov     rax, cs:__security_cookie
0x140019098  xor     rax, rsp
0x14001909b  mov     [rbp+30h+var_30], rax
0x14001909f  xorps   xmm0, xmm0
0x1400190a2  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400190ad  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x1400190b4  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400190bf  movups  xmmword ptr [rbp+30h+Parameters.Header.Type], xmm0
0x1400190c3  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400190ca  mov     rdi, rdx
0x1400190cd  mov     rbx, rcx
0x1400190d0  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400190db  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400190e6  call    WppLoadTracingSupport
0x1400190eb  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400190f6  call    WppInitKm
0x1400190fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140019102  lea     r15, WPP_GLOBAL_Control
0x140019109  lea     r13, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids
0x140019110  mov     r12d, 10h
0x140019116  cmp     rcx, r15
0x140019119  jz      short loc_14001913A
0x14001911b  mov     eax, [rcx+2Ch]
0x14001911e  test    r12b, al
0x140019121  jz      short loc_14001913A
0x140019123  cmp     byte ptr [rcx+29h], 3
0x140019127  jb      short loc_14001913A
0x140019129  mov     rcx, [rcx+18h]
0x14001912d  lea     edx, [r12-6]
0x140019132  mov     r8, r13
0x140019135  call    WPP_SF_
0x14001913a  call    cs:__imp_NdisGetVersion
0x140019141  nop     dword ptr [rax+rax+00h]
0x140019146  xor     eax, eax
0x140019148  lea     rcx, gl_llistWorkItems; Lookaside
0x14001914f  mov     [rsp+130h+Depth], ax; Depth
0x140019154  mov     r9d, 200h; Flags
0x14001915a  mov     [rsp+130h+Tag], 6D456F50h; Tag
0x140019162  xor     r8d, r8d; Free
0x140019165  xor     edx, edx; Allocate
0x140019167  mov     [rsp+130h+Size], 48h ; 'H'; Size
0x140019170  call    cs:__imp_ExInitializeNPagedLookasideList
0x140019177  nop     dword ptr [rax+rax+00h]
0x14001917c  xor     edx, edx; Val
0x14001917e  lea     rcx, [rsp+130h+MiniportDriverCharacteristics]; void *
0x140019183  mov     r8d, 98h; Size
0x140019189  call    memset
0x14001918e  mov     [rsp+130h+NdisMiniportDriverHandle], 0
0x140019197  mov     rcx, cs:WPP_GLOBAL_Control
0x14001919e  cmp     rcx, r15
0x1400191a1  jz      short loc_1400191C5
0x1400191a3  mov     eax, [rcx+2Ch]
0x1400191a6  test    al, 1
0x1400191a8  jz      short loc_1400191C5
0x1400191aa  cmp     byte ptr [rcx+29h], 2
0x1400191ae  jb      short loc_1400191C5
0x1400191b0  mov     rcx, [rcx+18h]
0x1400191b4  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400191bb  mov     edx, 0Ch
0x1400191c0  call    WPP_SF_
0x1400191c5  xor     edx, edx; Val
0x1400191c7  lea     rcx, [rsp+130h+MiniportDriverCharacteristics]; void *
0x1400191cc  mov     r8d, 98h; Size
0x1400191d2  call    memset
0x1400191d7  lea     rax, MpSetOptions
0x1400191de  mov     dword ptr [rsp+130h+MiniportDriverCharacteristics.Header.Type], 98028Ah
0x1400191e6  mov     [rsp+130h+MiniportDriverCharacteristics.SetOptionsHandler], rax
0x1400191eb  lea     r9, [rsp+130h+MiniportDriverCharacteristics]; MiniportDriverCharacteristics
0x1400191f0  lea     rax, MpInitializeEx
0x1400191f7  mov     dword ptr [rsp+130h+MiniportDriverCharacteristics.MajorNdisVersion], 11E06h
0x1400191ff  mov     [rsp+130h+MiniportDriverCharacteristics.InitializeHandlerEx], rax
0x140019204  xor     r8d, r8d; MiniportDriverContext
0x140019207  lea     rax, MpHaltEx
0x14001920e  mov     rdx, rdi; RegistryPath
0x140019211  mov     [rsp+130h+MiniportDriverCharacteristics.HaltHandlerEx], rax
0x140019216  mov     rcx, rbx; DriverObject
0x140019219  lea     rax, MpUnload
0x140019220  mov     [rsp+130h+MiniportDriverCharacteristics.UnloadHandler], rax
0x140019225  lea     rax, MpPause
0x14001922c  mov     [rbp+30h+MiniportDriverCharacteristics.PauseHandler], rax
0x140019230  lea     rax, MpRestart
0x140019237  mov     [rbp+30h+MiniportDriverCharacteristics.RestartHandler], rax
0x14001923b  lea     rax, PrUninstall
0x140019242  mov     [rbp+30h+MiniportDriverCharacteristics.SendNetBufferListsHandler], rax
0x140019246  lea     rax, MpReturnNetBufferListChain
0x14001924d  mov     [rbp+30h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x140019251  lea     rax, PrUninstall
0x140019258  mov     [rbp+30h+MiniportDriverCharacteristics.CancelSendHandler], rax
0x14001925c  lea     rax, PrUninstall
0x140019263  mov     [rbp+30h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x140019267  lea     rax, PrUninstall
0x14001926e  mov     [rbp+30h+MiniportDriverCharacteristics.ShutdownHandlerEx], rax
0x140019272  lea     rax, PrUninstall
0x140019279  mov     [rbp+30h+MiniportDriverCharacteristics.CancelOidRequestHandler], rax
0x14001927d  lea     rax, [rsp+130h+NdisMiniportDriverHandle]
0x140019282  mov     [rsp+130h+Size], rax; NdisMiniportDriverHandle
0x140019287  call    cs:__imp_NdisMRegisterMiniportDriver
0x14001928e  nop     dword ptr [rax+rax+00h]
0x140019293  mov     ebx, eax
0x140019295  test    eax, eax
0x140019297  jnz     short loc_1400192A5
0x140019299  mov     rcx, [rsp+130h+NdisMiniportDriverHandle]
0x14001929e  mov     cs:gl_NdisMiniportDriverHandle, rcx
0x1400192a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192ac  mov     edi, 0Dh
0x1400192b1  cmp     rcx, r15
0x1400192b4  jz      short loc_1400192D9
0x1400192b6  mov     edx, [rcx+2Ch]
0x1400192b9  test    dl, 1
0x1400192bc  jz      short loc_1400192D9
0x1400192be  cmp     byte ptr [rcx+29h], 2
0x1400192c2  jb      short loc_1400192D9
0x1400192c4  mov     rcx, [rcx+18h]
0x1400192c8  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400192cf  mov     edx, edi
0x1400192d1  mov     r9d, ebx
0x1400192d4  call    WPP_SF_d
0x1400192d9  test    ebx, ebx
0x1400192db  jz      short loc_14001931C
0x1400192dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192e4  cmp     rcx, r15
0x1400192e7  jz      loc_1400193BB
0x1400192ed  mov     eax, [rcx+2Ch]
0x1400192f0  test    r12b, al
0x1400192f3  jz      loc_1400193BB
0x1400192f9  cmp     byte ptr [rcx+29h], 1
0x1400192fd  jb      loc_1400193BB
0x140019303  mov     edx, 0Bh
0x140019308  mov     r9d, ebx
0x14001930b  mov     rcx, [rcx+18h]
0x14001930f  mov     r8, r13
0x140019312  call    WPP_SF_d
0x140019317  jmp     loc_1400193BB
0x14001931c  call    PrRegisterProtocol
0x140019321  test    eax, eax
0x140019323  jz      short loc_14001934E
0x140019325  mov     rcx, cs:WPP_GLOBAL_Control
0x14001932c  cmp     rcx, r15
0x14001932f  jz      loc_1400193BB
0x140019335  mov     r8d, [rcx+2Ch]
0x140019339  test    r12b, r8b
0x14001933c  jz      short loc_1400193BB
0x14001933e  cmp     byte ptr [rcx+29h], 1
0x140019342  jb      short loc_1400193BB
0x140019344  mov     edx, 0Ch
0x140019349  mov     r9d, eax
0x14001934c  jmp     short loc_14001930B
0x14001934e  mov     rcx, cs:gl_NdisMiniportDriverHandle; NdisHandle
0x140019355  lea     rdx, [rbp+30h+Parameters]; Parameters
0x140019359  mov     eax, 0A0h
0x14001935e  mov     dword ptr [rbp+30h+Parameters.Header.Type], 100180h
0x140019365  mov     [rbp+30h+Parameters.ContextSize], ax
0x140019369  mov     [rbp+30h+Parameters.fAllocateNetBuffer], 1
0x14001936d  mov     [rbp+30h+Parameters.PoolTag], 63456F50h
0x140019374  mov     [rbp+30h+Parameters.DataSize], 5EAh
0x14001937b  call    cs:__imp_NdisAllocateNetBufferListPool
0x140019382  nop     dword ptr [rax+rax+00h]
0x140019387  mov     cs:gl_NblPoolHandle, rax
0x14001938e  test    rax, rax
0x140019391  jnz     short loc_1400193C7
0x140019393  mov     rcx, cs:WPP_GLOBAL_Control
0x14001939a  cmp     rcx, r15
0x14001939d  jz      short loc_1400193BB
0x14001939f  mov     eax, [rcx+2Ch]
0x1400193a2  test    r12b, al
0x1400193a5  jz      short loc_1400193BB
0x1400193a7  cmp     byte ptr [rcx+29h], 1
0x1400193ab  jb      short loc_1400193BB
0x1400193ad  mov     rcx, [rcx+18h]
0x1400193b1  mov     edx, edi
0x1400193b3  mov     r8, r13
0x1400193b6  call    WPP_SF_
0x1400193bb  call    RasPppoeCleanup
0x1400193c0  mov     ebx, 0C0000001h
0x1400193c5  jmp     short loc_1400193C9
0x1400193c7  xor     ebx, ebx
0x1400193c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193d0  cmp     rcx, r15
0x1400193d3  jz      short loc_1400193F7
0x1400193d5  mov     edx, [rcx+2Ch]
0x1400193d8  test    r12b, dl
0x1400193db  jz      short loc_1400193F7
0x1400193dd  cmp     byte ptr [rcx+29h], 3
0x1400193e1  jb      short loc_1400193F7
0x1400193e3  mov     rcx, [rcx+18h]
0x1400193e7  mov     edx, 0Eh
0x1400193ec  mov     r9d, ebx
0x1400193ef  mov     r8, r13
0x1400193f2  call    WPP_SF_d
0x1400193f7  mov     eax, ebx
0x1400193f9  mov     rcx, [rbp+30h+var_30]
0x1400193fd  xor     rcx, rsp; StackCookie
0x140019400  call    __security_check_cookie
0x140019405  mov     rbx, [rsp+130h+arg_10]
0x14001940d  add     rsp, 110h
0x140019414  pop     r15
0x140019416  pop     r13
0x140019418  pop     r12
0x14001941a  pop     rdi
0x14001941b  pop     rbp
0x14001941c  retn
```
