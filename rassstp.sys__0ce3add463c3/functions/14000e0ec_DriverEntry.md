# DriverEntry

- ea: `0x14000e0ec`
- end: `0x14000e74b`
- name: `DriverEntry`
- size: `1631`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001a010`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140004cc0`
- `0x140005e10`
- `0x140006240`
- `0x14000e0ec`
- `0x14000e818`
- `0x14000e89c`
- `0x14000f9d0`

## import_xrefs

- `ntoskrnl!IoCsqInitialize` at `0x14000e386`
- `ntoskrnl!IoCsqInitialize` at `0x14000e386`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1e7`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e18d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e4c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e4db`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e18d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e4c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e4db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e67b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e67b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e264`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e28c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e2ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e33d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e264`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e28c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e2ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e33d`
- `NDIS!NdisRegisterDeviceEx` at `0x14000e577`
- `NDIS!NdisRegisterDeviceEx` at `0x14000e577`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x14000e653`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x14000e653`
- `NDIS!NdisDeregisterDeviceEx` at `0x14000e622`
- `NDIS!NdisDeregisterDeviceEx` at `0x14000e622`
- `NDIS!NdisMRegisterMiniportDriver` at `0x14000e457`
- `NDIS!NdisMRegisterMiniportDriver` at `0x14000e457`
- `NETIO!HfCreateFactory` at `0x14000e2d6`
- `NETIO!HfCreateFactory` at `0x14000e2d6`
- `NETIO!HfDestroyFactory` at `0x14000e477`
- `NETIO!HfDestroyFactory` at `0x14000e63c`
- `NETIO!HfDestroyFactory` at `0x14000e477`
- `NETIO!HfDestroyFactory` at `0x14000e63c`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _DRIVER_OBJECT **Pool2; // rax
  NDIS_STATUS Factory; // edi
  _QWORD *v6; // rax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  struct _IO_CSQ *v9; // rdi
  PDEVICE_OBJECT pDeviceObject; // [rsp+40h] [rbp-C0h] BYREF
  _NDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v14; // [rsp+90h] [rbp-70h] BYREF
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics; // [rsp+A0h] [rbp-60h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+140h] [rbp+40h] BYREF
  GUID v17; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v18[28]; // [rsp+160h] [rbp+60h] BYREF

  DestinationString = 0;
  v17 = GUID_DEVCLASS_NET;
  memset(&DeviceObjectAttributes, 0, sizeof(DeviceObjectAttributes));
  memset(v18, 0, 0xD8u);
  pDeviceObject = 0;
  v13 = 0;
  v14 = 0;
  memset(&MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  RtlInitUnicodeString(&DestinationString, L"Microsoft\\Tracing\\SSTP");
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  Pool2 = (_DRIVER_OBJECT **)ExAllocatePool2(64, 584, 1768375379);
  SstpGlobals = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids);
    }
    Factory = -1073741670;
    goto LABEL_30;
  }
  *Pool2 = DriverObject;
  *((_QWORD *)SstpGlobals + 2) = 0;
  *((_QWORD *)SstpGlobals + 3) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)SstpGlobals + 55);
  *((_DWORD *)SstpGlobals + 112) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)SstpGlobals + 59);
  v6 = (char *)SstpGlobals + 480;
  *((_QWORD *)SstpGlobals + 61) = (char *)SstpGlobals + 480;
  *v6 = v6;
  KeInitializeSpinLock((PKSPIN_LOCK)SstpGlobals + 62);
  Factory = HfCreateFactory(0, (char *)SstpGlobals + 504);
  if ( Factory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v8 = 11;
    goto LABEL_12;
  }
  v9 = (struct _IO_CSQ *)SstpGlobals;
  KeInitializeSpinLock((PKSPIN_LOCK)SstpGlobals + 7);
  IoCsqInitialize(
    v9 + 1,
    CsqInsertIrp,
    CsqRemoveIrp,
    CsqPeekNextIrp,
    CsqAcquireLock,
    CsqReleaseLock,
    CsqCompleteCanceledIrp);
  v9[2].CsqInsertIrp = (PIO_CSQ_INSERT_IRP)&v9[2];
  *(_QWORD *)&v9[2].Type = v9 + 2;
  MiniportDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)9962122;
  MiniportDriverCharacteristics.SetOptionsHandler = (SET_OPTIONS_HANDLER)SmpSetOptions;
  *(_DWORD *)&MiniportDriverCharacteristics.MajorNdisVersion = 73222;
  MiniportDriverCharacteristics.HaltHandlerEx = (MINIPORT_HALT_HANDLER)SmpHaltEx;
  MiniportDriverCharacteristics.ResetHandlerEx = 0;
  MiniportDriverCharacteristics.InitializeHandlerEx = (MINIPORT_INITIALIZE_HANDLER)SmpInitializeEx;
  MiniportDriverCharacteristics.UnloadHandler = (MINIPORT_DRIVER_UNLOAD)SmpUnload;
  MiniportDriverCharacteristics.PauseHandler = (MINIPORT_PAUSE_HANDLER)SmpPause;
  MiniportDriverCharacteristics.RestartHandler = (MINIPORT_RESTART_HANDLER)SmpRestart;
  MiniportDriverCharacteristics.SendNetBufferListsHandler = (MINIPORT_SEND_NET_BUFFER_LISTS_HANDLER)SmpShutdown;
  MiniportDriverCharacteristics.ReturnNetBufferListsHandler = (MINIPORT_RETURN_NET_BUFFER_LISTS_HANDLER)&SmpReturnNetBufferListChain;
  MiniportDriverCharacteristics.CancelSendHandler = (MINIPORT_CANCEL_SEND_HANDLER)SmpShutdown;
  MiniportDriverCharacteristics.DevicePnPEventNotifyHandler = (MINIPORT_DEVICE_PNP_EVENT_NOTIFY_HANDLER)SmpShutdown;
  MiniportDriverCharacteristics.ShutdownHandlerEx = (MINIPORT_SHUTDOWN_HANDLER)SmpShutdown;
  MiniportDriverCharacteristics.CancelOidRequestHandler = (MINIPORT_CANCEL_OID_REQUEST_HANDLER)SmpShutdown;
  Factory = NdisMRegisterMiniportDriver(
              DriverObject,
              RegistryPath,
              &SstpGlobals,
              &MiniportDriverCharacteristics,
              (PNDIS_HANDLE)SstpGlobals + 5);
  if ( Factory < 0 )
  {
    HfDestroyFactory((char *)SstpGlobals + 504);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v8 = 12;
LABEL_12:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids);
LABEL_30:
    if ( SstpGlobals )
    {
      ExFreePoolWithTag(SstpGlobals, 0x69674453u);
      SstpGlobals = 0;
    }
    WppCleanupKm();
    return Factory;
  }
  RtlInitUnicodeString(&v13, L"\\Device\\SstpDrv");
  RtlInitUnicodeString(&v14, L"\\DosDevices\\SstpDrv");
  DeviceObjectAttributes.ExtensionSize = 0;
  DeviceObjectAttributes.DefaultSDDLString = (PCUNICODE_STRING)L"68";
  DeviceObjectAttributes.Header = (NDIS_OBJECT_HEADER)3670405;
  DeviceObjectAttributes.DeviceClassGuid = &v17;
  DeviceObjectAttributes.DeviceName = &v13;
  DeviceObjectAttributes.MajorFunctions = (PDRIVER_DISPATCH *)v18;
  DeviceObjectAttributes.SymbolicName = &v14;
  memset64(v18, (unsigned __int64)&TpiDispatchIrpStub, 0x1Bu);
  v18[0] = &TpiDispatchCreate;
  v18[18] = TpiDispatchCleanup;
  v18[14] = &TpiDispatchDeviceControl;
  Factory = NdisRegisterDeviceEx(
              *((NDIS_HANDLE *)SstpGlobals + 5),
              &DeviceObjectAttributes,
              &pDeviceObject,
              (PNDIS_HANDLE)SstpGlobals + 4);
  if ( Factory < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids);
    }
LABEL_29:
    HfDestroyFactory((char *)SstpGlobals + 504);
    NdisMDeregisterMiniportDriver(*((NDIS_HANDLE *)SstpGlobals + 5));
    *((_QWORD *)SstpGlobals + 5) = 0;
    goto LABEL_30;
  }
  Factory = SetupSstpAclOnDevice(pDeviceObject);
  if ( Factory < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids);
    }
    NdisDeregisterDeviceEx(*((NDIS_HANDLE *)SstpGlobals + 4));
    goto LABEL_29;
  }
  *((_QWORD *)SstpGlobals + 1) = pDeviceObject;
  *((_DWORD *)SstpGlobals + 52) = 224;
  *((_QWORD *)SstpGlobals + 36) = TpiDispatchFastIoDeviceControl;
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)((char *)SstpGlobals + 208);
  *((_BYTE *)SstpGlobals + 569) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids);
  }
  return Factory;
}

```

## disassembly

```asm
0x14000e0ec  mov     [rsp-8+arg_10], rbx
0x14000e0f1  push    rbp
0x14000e0f2  push    rsi
0x14000e0f3  push    rdi
0x14000e0f4  push    r13
0x14000e0f6  push    r15
0x14000e0f8  lea     rbp, [rsp-150h]
0x14000e100  sub     rsp, 250h
0x14000e107  mov     rax, cs:__security_cookie
0x14000e10e  xor     rax, rsp
0x14000e111  mov     [rbp+170h+var_30], rax
0x14000e118  xorps   xmm1, xmm1
0x14000e11b  xorps   xmm0, xmm0
0x14000e11e  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x14000e122  mov     rsi, rdx
0x14000e125  mov     rbx, rcx
0x14000e128  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NET.Data1
0x14000e12f  xor     eax, eax
0x14000e131  lea     rcx, [rbp+170h+var_110]; void *
0x14000e135  xor     edx, edx; Val
0x14000e137  mov     [rsp+270h+DeviceObjectAttributes.DeviceClassGuid], rax
0x14000e13c  mov     r8d, 0D8h; Size
0x14000e142  movdqu  [rbp+170h+var_120], xmm0
0x14000e147  movups  xmmword ptr [rsp+270h+DeviceObjectAttributes.Header.Type], xmm1
0x14000e14c  movups  xmmword ptr [rsp+270h+DeviceObjectAttributes.SymbolicName], xmm1
0x14000e151  movups  xmmword ptr [rsp+270h+DeviceObjectAttributes.ExtensionSize], xmm1
0x14000e156  call    memset
0x14000e15b  xorps   xmm0, xmm0
0x14000e15e  lea     rcx, [rbp+170h+MiniportDriverCharacteristics]; void *
0x14000e162  xorps   xmm1, xmm1
0x14000e165  xor     r15d, r15d
0x14000e168  xor     edx, edx; Val
0x14000e16a  mov     [rsp+270h+pDeviceObject], r15
0x14000e16f  mov     r8d, 98h; Size
0x14000e175  movups  xmmword ptr [rbp+170h+var_1F0.Length], xmm0
0x14000e179  movups  xmmword ptr [rbp+170h+var_1E0.Length], xmm1
0x14000e17d  call    memset
0x14000e182  lea     rdx, SourceString; "Microsoft\\Tracing\\SSTP"
0x14000e189  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x14000e18d  call    cs:__imp_RtlInitUnicodeString
0x14000e194  nop     dword ptr [rax+rax+00h]
0x14000e199  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14000e1a0  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x14000e1a7  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000e1ae  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x14000e1b5  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14000e1bc  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000e1c7  call    WppLoadTracingSupport
0x14000e1cc  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14000e1d3  call    WppInitKm
0x14000e1d8  mov     edx, 248h
0x14000e1dd  lea     ecx, [r15+40h]
0x14000e1e1  mov     r8d, 69674453h
0x14000e1e7  call    cs:__imp_ExAllocatePool2
0x14000e1ee  nop     dword ptr [rax+rax+00h]
0x14000e1f3  mov     cs:SstpGlobals, rax
0x14000e1fa  test    rax, rax
0x14000e1fd  jnz     short loc_14000E23D
0x14000e1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e206  lea     rax, WPP_GLOBAL_Control
0x14000e20d  cmp     rcx, rax
0x14000e210  jz      short loc_14000E233
0x14000e212  mov     eax, [rcx+2Ch]
0x14000e215  test    al, 1
0x14000e217  jz      short loc_14000E233
0x14000e219  cmp     byte ptr [rcx+29h], 1
0x14000e21d  jb      short loc_14000E233
0x14000e21f  mov     rcx, [rcx+18h]
0x14000e223  lea     edx, [r15+0Ah]
0x14000e227  lea     r8, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids
0x14000e22e  call    WPP_SF_
0x14000e233  mov     edi, 0C000009Ah
0x14000e238  jmp     loc_14000E66A
0x14000e23d  mov     [rax], rbx
0x14000e240  mov     rax, cs:SstpGlobals
0x14000e247  mov     [rax+10h], r15
0x14000e24b  mov     rax, cs:SstpGlobals
0x14000e252  mov     [rax+18h], r15
0x14000e256  mov     rcx, cs:SstpGlobals
0x14000e25d  add     rcx, 1B8h; SpinLock
0x14000e264  call    cs:__imp_KeInitializeSpinLock
0x14000e26b  nop     dword ptr [rax+rax+00h]
0x14000e270  mov     rax, cs:SstpGlobals
0x14000e277  mov     [rax+1C0h], r15d
0x14000e27e  mov     rcx, cs:SstpGlobals
0x14000e285  add     rcx, 1D8h; SpinLock
0x14000e28c  call    cs:__imp_KeInitializeSpinLock
0x14000e293  nop     dword ptr [rax+rax+00h]
0x14000e298  mov     rax, cs:SstpGlobals
0x14000e29f  add     rax, 1E0h
0x14000e2a5  mov     [rax+8], rax
0x14000e2a9  mov     [rax], rax
0x14000e2ac  mov     rcx, cs:SstpGlobals
0x14000e2b3  add     rcx, 1F0h; SpinLock
0x14000e2ba  call    cs:__imp_KeInitializeSpinLock
0x14000e2c1  nop     dword ptr [rax+rax+00h]
0x14000e2c6  mov     rdx, cs:SstpGlobals
0x14000e2cd  xor     ecx, ecx
0x14000e2cf  add     rdx, 1F8h
0x14000e2d6  call    cs:__imp_HfCreateFactory
0x14000e2dd  nop     dword ptr [rax+rax+00h]
0x14000e2e2  mov     edi, eax
0x14000e2e4  test    eax, eax
0x14000e2e6  jns     short loc_14000E332
0x14000e2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2ef  lea     rax, WPP_GLOBAL_Control
0x14000e2f6  cmp     rcx, rax
0x14000e2f9  jz      loc_14000E66A
0x14000e2ff  mov     edx, [rcx+2Ch]
0x14000e302  test    dl, 1
0x14000e305  jz      loc_14000E66A
0x14000e30b  cmp     byte ptr [rcx+29h], 1
0x14000e30f  jb      loc_14000E66A
0x14000e315  mov     edx, 0Bh
0x14000e31a  mov     rcx, [rcx+18h]
0x14000e31e  lea     r8, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids
0x14000e325  mov     r9d, edi
0x14000e328  call    WPP_SF_d
0x14000e32d  jmp     loc_14000E66A
0x14000e332  mov     rdi, cs:SstpGlobals
0x14000e339  lea     rcx, [rdi+38h]; SpinLock
0x14000e33d  call    cs:__imp_KeInitializeSpinLock
0x14000e344  nop     dword ptr [rax+rax+00h]
0x14000e349  lea     rax, CsqCompleteCanceledIrp
0x14000e350  mov     [rsp+270h+CsqCompleteCanceledIrp], rax; CsqCompleteCanceledIrp
0x14000e355  lea     rcx, [rdi+40h]; Csq
0x14000e359  lea     rax, CsqReleaseLock
0x14000e360  mov     [rsp+270h+CsqReleaseLock], rax; CsqReleaseLock
0x14000e365  lea     r9, CsqPeekNextIrp; CsqPeekNextIrp
0x14000e36c  lea     rax, CsqAcquireLock
0x14000e373  lea     r8, CsqRemoveIrp; CsqRemoveIrp
0x14000e37a  mov     [rsp+270h+CsqAcquireLock], rax; CsqAcquireLock
0x14000e37f  lea     rdx, CsqInsertIrp; CsqInsertIrp
0x14000e386  call    cs:__imp_IoCsqInitialize
0x14000e38d  nop     dword ptr [rax+rax+00h]
0x14000e392  lea     rax, [rdi+80h]
0x14000e399  mov     [rax+8], rax
0x14000e39d  mov     [rax], rax
0x14000e3a0  lea     rax, SmpSetOptions
0x14000e3a7  mov     dword ptr [rbp+170h+MiniportDriverCharacteristics.Header.Type], 98028Ah
0x14000e3ae  mov     [rbp+170h+MiniportDriverCharacteristics.SetOptionsHandler], rax
0x14000e3b2  lea     r9, [rbp+170h+MiniportDriverCharacteristics]; MiniportDriverCharacteristics
0x14000e3b6  lea     rax, SmpHaltEx
0x14000e3bd  mov     dword ptr [rbp+170h+MiniportDriverCharacteristics.MajorNdisVersion], 11E06h
0x14000e3c4  mov     [rbp+170h+MiniportDriverCharacteristics.HaltHandlerEx], rax
0x14000e3c8  lea     r8, SstpGlobals; MiniportDriverContext
0x14000e3cf  lea     rax, SmpInitializeEx
0x14000e3d6  mov     [rbp+170h+MiniportDriverCharacteristics.ResetHandlerEx], r15
0x14000e3da  mov     [rbp+170h+MiniportDriverCharacteristics.InitializeHandlerEx], rax
0x14000e3de  mov     rdx, rsi; RegistryPath
0x14000e3e1  lea     rax, SmpUnload
0x14000e3e8  mov     rcx, rbx; DriverObject
0x14000e3eb  mov     [rbp+170h+MiniportDriverCharacteristics.UnloadHandler], rax
0x14000e3ef  lea     rax, SmpPause
0x14000e3f6  mov     [rbp+170h+MiniportDriverCharacteristics.PauseHandler], rax
0x14000e3fa  lea     rax, SmpRestart
0x14000e401  mov     [rbp+170h+MiniportDriverCharacteristics.RestartHandler], rax
0x14000e405  lea     rax, SmpShutdown
0x14000e40c  mov     [rbp+170h+MiniportDriverCharacteristics.SendNetBufferListsHandler], rax
0x14000e410  lea     rax, SmpReturnNetBufferListChain
0x14000e417  mov     [rbp+170h+MiniportDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x14000e41b  lea     rax, SmpShutdown
0x14000e422  mov     [rbp+170h+MiniportDriverCharacteristics.CancelSendHandler], rax
0x14000e426  lea     rax, SmpShutdown
0x14000e42d  mov     [rbp+170h+MiniportDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x14000e431  lea     rax, SmpShutdown
0x14000e438  mov     [rbp+170h+MiniportDriverCharacteristics.ShutdownHandlerEx], rax
0x14000e43c  lea     rax, SmpShutdown
0x14000e443  mov     [rbp+170h+MiniportDriverCharacteristics.CancelOidRequestHandler], rax
0x14000e447  mov     rax, cs:SstpGlobals
0x14000e44e  add     rax, 28h ; '('
0x14000e452  mov     [rsp+270h+CsqAcquireLock], rax; NdisMiniportDriverHandle
0x14000e457  call    cs:__imp_NdisMRegisterMiniportDriver
0x14000e45e  nop     dword ptr [rax+rax+00h]
0x14000e463  mov     edi, eax
0x14000e465  test    eax, eax
0x14000e467  jns     short loc_14000E4B9
0x14000e469  mov     rcx, cs:SstpGlobals
0x14000e470  add     rcx, 1F8h
0x14000e477  call    cs:__imp_HfDestroyFactory
0x14000e47e  nop     dword ptr [rax+rax+00h]
0x14000e483  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e48a  lea     rax, WPP_GLOBAL_Control
0x14000e491  cmp     rcx, rax
0x14000e494  jz      loc_14000E66A
0x14000e49a  mov     eax, [rcx+2Ch]
0x14000e49d  test    al, 1
0x14000e49f  jz      loc_14000E66A
0x14000e4a5  cmp     byte ptr [rcx+29h], 1
0x14000e4a9  jb      loc_14000E66A
0x14000e4af  mov     edx, 0Ch
0x14000e4b4  jmp     loc_14000E31A
0x14000e4b9  lea     rdx, aDeviceSstpdrv; "\\Device\\SstpDrv"
0x14000e4c0  lea     rcx, [rbp+170h+var_1F0]; DestinationString
0x14000e4c4  call    cs:__imp_RtlInitUnicodeString
0x14000e4cb  nop     dword ptr [rax+rax+00h]
0x14000e4d0  lea     rdx, aDosdevicesSstp; "\\DosDevices\\SstpDrv"
0x14000e4d7  lea     rcx, [rbp+170h+var_1E0]; DestinationString
0x14000e4db  call    cs:__imp_RtlInitUnicodeString
0x14000e4e2  nop     dword ptr [rax+rax+00h]
0x14000e4e7  lea     rax, SDDL_LS_ALL; "68"
0x14000e4ee  mov     [rsp+270h+DeviceObjectAttributes.ExtensionSize], r15d
0x14000e4f3  mov     [rsp+270h+DeviceObjectAttributes.DefaultSDDLString], rax
0x14000e4f8  lea     rdi, [rbp+170h+var_110]
0x14000e4fc  lea     rax, [rbp+170h+var_120]
0x14000e500  mov     dword ptr [rsp+270h+DeviceObjectAttributes.Header.Type], 380185h
0x14000e508  mov     [rsp+270h+DeviceObjectAttributes.DeviceClassGuid], rax
0x14000e50d  lea     r8, [rsp+270h+pDeviceObject]; pDeviceObject
0x14000e512  lea     rax, [rbp+170h+var_1F0]
0x14000e516  mov     ecx, 1Bh
0x14000e51b  mov     [rsp+270h+DeviceObjectAttributes.DeviceName], rax
0x14000e520  lea     rdx, [rsp+270h+DeviceObjectAttributes]; DeviceObjectAttributes
0x14000e525  lea     rax, [rbp+170h+var_110]
0x14000e529  mov     [rsp+270h+DeviceObjectAttributes.MajorFunctions], rax
0x14000e52e  lea     rax, [rbp+170h+var_1E0]
0x14000e532  mov     [rsp+270h+DeviceObjectAttributes.SymbolicName], rax
0x14000e537  lea     rax, TpiDispatchIrpStub
0x14000e53e  rep stosq
0x14000e541  mov     rcx, cs:SstpGlobals
0x14000e548  lea     rax, TpiDispatchCreate
0x14000e54f  mov     [rbp+170h+var_110], rax
0x14000e553  lea     rax, TpiDispatchCleanup
0x14000e55a  mov     [rbp+170h+var_80], rax
0x14000e561  lea     rax, TpiDispatchDeviceControl
0x14000e568  mov     [rbp+170h+var_A0], rax
0x14000e56f  lea     r9, [rcx+20h]; NdisDeviceHandle
0x14000e573  mov     rcx, [rcx+28h]; NdisHandle
0x14000e577  call    cs:__imp_NdisRegisterDeviceEx
0x14000e57e  nop     dword ptr [rax+rax+00h]
0x14000e583  mov     edi, eax
0x14000e585  test    eax, eax
0x14000e587  jns     short loc_14000E5CB
0x14000e589  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e590  lea     rax, WPP_GLOBAL_Control
0x14000e597  cmp     rcx, rax
0x14000e59a  jz      loc_14000E62E
0x14000e5a0  mov     eax, [rcx+2Ch]
0x14000e5a3  test    al, 1
0x14000e5a5  jz      loc_14000E62E
0x14000e5ab  cmp     byte ptr [rcx+29h], 1
0x14000e5af  jb      short loc_14000E62E
0x14000e5b1  mov     rcx, [rcx+18h]
0x14000e5b5  lea     r8, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids
0x14000e5bc  mov     edx, 0Dh
0x14000e5c1  mov     r9d, edi
0x14000e5c4  call    WPP_SF_d
0x14000e5c9  jmp     short loc_14000E62E
0x14000e5cb  mov     rcx, [rsp+270h+pDeviceObject]; Object
0x14000e5d0  call    SetupSstpAclOnDevice
0x14000e5d5  mov     edi, eax
0x14000e5d7  test    eax, eax
0x14000e5d9  jns     loc_14000E698
0x14000e5df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5e6  lea     rax, WPP_GLOBAL_Control
0x14000e5ed  cmp     rcx, rax
0x14000e5f0  jz      short loc_14000E617
0x14000e5f2  mov     eax, [rcx+2Ch]
0x14000e5f5  test    al, 1
0x14000e5f7  jz      short loc_14000E617
0x14000e5f9  cmp     byte ptr [rcx+29h], 1
0x14000e5fd  jb      short loc_14000E617
0x14000e5ff  mov     rcx, [rcx+18h]
0x14000e603  lea     r8, WPP_f90ff6d3edf13da5b70a76da5ff20990_Traceguids
0x14000e60a  mov     edx, 0Eh
0x14000e60f  mov     r9d, edi
0x14000e612  call    WPP_SF_d
0x14000e617  mov     rcx, cs:SstpGlobals
0x14000e61e  mov     rcx, [rcx+20h]; NdisDeviceHandle
0x14000e622  call    cs:__imp_NdisDeregisterDeviceEx
0x14000e629  nop     dword ptr [rax+rax+00h]
0x14000e62e  mov     rcx, cs:SstpGlobals
0x14000e635  add     rcx, 1F8h
0x14000e63c  call    cs:__imp_HfDestroyFactory
0x14000e643  nop     dword ptr [rax+rax+00h]
0x14000e648  mov     rcx, cs:SstpGlobals
0x14000e64f  mov     rcx, [rcx+28h]; NdisMiniportDriverHandle
0x14000e653  call    cs:__imp_NdisMDeregisterMiniportDriver
0x14000e65a  nop     dword ptr [rax+rax+00h]
0x14000e65f  mov     rax, cs:SstpGlobals
0x14000e666  mov     [rax+28h], r15
0x14000e66a  mov     rcx, cs:SstpGlobals; P
0x14000e671  test    rcx, rcx
0x14000e674  jz      short loc_14000E68E
0x14000e676  mov     edx, 69674453h; Tag
0x14000e67b  call    cs:__imp_ExFreePoolWithTag
0x14000e682  nop     dword ptr [rax+rax+00h]
0x14000e687  mov     cs:SstpGlobals, r15
0x14000e68e  call    WppCleanupKm
0x14000e693  jmp     loc_14000E722
0x14000e698  mov     rax, cs:SstpGlobals
0x14000e69f  mov     rcx, [rsp+270h+pDeviceObject]
0x14000e6a4  mov     [rax+8], rcx
0x14000e6a8  lea     rcx, TpiDispatchFastIoDeviceControl
0x14000e6af  mov     rax, cs:SstpGlobals
0x14000e6b6  mov     dword ptr [rax+0D0h], 0E0h
0x14000e6c0  mov     rax, cs:SstpGlobals
0x14000e6c7  mov     [rax+120h], rcx
0x14000e6ce  mov     rax, cs:SstpGlobals
0x14000e6d5  add     rax, 0D0h
0x14000e6db  mov     [rbx+50h], rax
  ... truncated ...
```
