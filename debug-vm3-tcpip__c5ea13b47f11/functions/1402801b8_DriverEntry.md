# DriverEntry

- ea: `0x1402801b8`
- end: `0x140280743`
- name: `DriverEntry`
- size: `1419`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140280150`

## callees

- `0x1401517c0`
- `0x140155a38`
- `0x140155da8`
- `0x140155fe4`
- `0x1401561c4`
- `0x1401563d4`
- `0x140156510`
- `0x1401565dc`
- `0x140156718`
- `0x140156a00`
- `0x140157f74`
- `0x1401581c0`
- `0x1401b5eac`
- `0x1401b64b4`
- `0x1401b66a8`
- `0x1401bc558`
- `0x1401bf4d0`
- `0x1401bfa80`
- `0x14024e594`
- `0x14024e640`
- `0x14024e674`
- `0x14024e6f8`
- `0x14024e78c`
- `0x14024eb7c`
- `0x14024ed58`
- `0x14024edac`
- `0x14024eeb4`
- `0x14024eff4`
- `0x140255be0`
- `0x140256008`
- `0x140257e2c`
- `0x140257f60`
- `0x1402801b8`
- `0x14028074c`
- `0x1402808f4`
- `0x140280ba8`
- `0x1402813d4`
- `0x140281c44`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1402803ba`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1402803ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x140280382`
- `ntoskrnl!KeWaitForSingleObject` at `0x14028054d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140280382`
- `ntoskrnl!KeWaitForSingleObject` at `0x14028054d`
- `ntoskrnl!KeInitializeEvent` at `0x1402804c0`
- `ntoskrnl!KeInitializeEvent` at `0x1402804c0`
- `ntoskrnl!IofCallDriver` at `0x140280526`
- `ntoskrnl!IofCallDriver` at `0x140280526`
- `ntoskrnl!IoCreateDevice` at `0x14028034a`
- `ntoskrnl!IoCreateDevice` at `0x14028034a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140280202`
- `ntoskrnl!PsGetCurrentProcess` at `0x140280202`
- `ntoskrnl!RtlGetVersion` at `0x1402802ae`
- `ntoskrnl!RtlGetVersion` at `0x1402802ae`
- `ntoskrnl!KeReleaseMutex` at `0x140280668`
- `ntoskrnl!KeReleaseMutex` at `0x140280730`
- `ntoskrnl!KeReleaseMutex` at `0x140280668`
- `ntoskrnl!KeReleaseMutex` at `0x140280730`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140280489`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140280489`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14028050b`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14028050b`
- `ntoskrnl!IoDeleteDevice` at `0x140280680`
- `ntoskrnl!IoDeleteDevice` at `0x140280680`
- `ntoskrnl!RtlInitUnicodeString` at `0x140280465`
- `ntoskrnl!RtlInitUnicodeString` at `0x140280465`
- `ntoskrnl!ObfDereferenceObject` at `0x14028058a`
- `ntoskrnl!ObfDereferenceObject` at `0x14028058a`
- `ntoskrnl!KeInitializeMutex` at `0x140280225`
- `ntoskrnl!KeInitializeMutex` at `0x140280225`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x140280640`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x140280640`
- `NETIO!NetioSetTriageBlock` at `0x14028027e`
- `NETIO!NetioSetTriageBlock` at `0x14028027e`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14028071b`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14028071b`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14028039f`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14028039f`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x140280653`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x140280653`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x1402803cc`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x1402803cc`
- `NETIO!RtlInvokeStartRoutines` at `0x140280434`
- `NETIO!RtlInvokeStartRoutines` at `0x140280434`
- `NETIO!RtlInvokeStopRoutines` at `0x14028062f`
- `NETIO!RtlInvokeStopRoutines` at `0x14028062f`
- `NDIS!NdisQueryDiagnosticSetting` at `0x14028025b`
- `NDIS!NdisQueryDiagnosticSetting` at `0x14028025b`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  int started; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 CurrentProcess; // rax
  int v9; // eax
  NTSTATUS DeviceObjectPointer; // ebx
  IRP *v11; // rax
  struct _KEVENT Event; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _BYTE VersionInformation[284]; // [rsp+90h] [rbp-70h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  started = wil_InitializeFeatureStaging();
  if ( started < 0 )
    goto LABEL_47;
  CurrentProcess = PsGetCurrentProcess(v4, v3, v6, v7);
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = DriverObject;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = CurrentProcess;
  KeInitializeMutex(&Mutex, 0);
  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = IsSystemRunningAsVailGuest();
  HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = GetProductType();
  LODWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) = GetPortTrackerMode();
  if ( (int)NdisQueryDiagnosticSetting(L"NblTracking", 0) > 0 )
    LOBYTE(WPP_MAIN_CB.DeviceExtension) = 1;
  NetioSetTriageBlock(1, &TcpipGlobalTriageBlock);
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  memset(&VersionInformation[4], 0, 0x118u);
  *(_DWORD *)VersionInformation = 284;
  if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && VersionInformation[282] != 1 )
    TcpipIsServerSKU = 1;
  started = TcpipStartTrace();
  if ( started < 0 )
    goto LABEL_47;
  TlgRegisterAggregateProvider(&dword_1402201F8);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140220230);
  started = PktMonClientInitialize();
  if ( started < 0 )
  {
LABEL_46:
    TraceLoggingUnregister_EtwUnregister(&dword_140220230);
    TlgUnregisterAggregateProvider(&dword_1402201F8);
    TcpipStopTrace();
LABEL_47:
    wil_UninitializeFeatureStaging();
    return started;
  }
  started = TcpipPcwStartup();
  if ( started < 0 )
  {
LABEL_45:
    PktMonClientUninitialize();
    goto LABEL_46;
  }
  started = InitializeMemoryUsageTracking();
  if ( started < 0
    || (started = IoCreateDevice(DriverObject, 0, 0, 0x12u, 0, 0, (PDEVICE_OBJECT *)&TcpipDeviceObject), started < 0) )
  {
LABEL_44:
    TcpipPcwCleanup();
    goto LABEL_45;
  }
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
    TcpipRegisterInspectionTrackers();
  KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
  started = NetioRegisterProcessorAddCallback(qword_140224458, TcpipProcessorAddCallback, 0);
  if ( started < 0 )
  {
LABEL_43:
    KeReleaseMutex(&Mutex, 0);
    TcpipDeregisterInspectionTrackers();
    IoDeleteDevice((PDEVICE_OBJECT)TcpipDeviceObject);
    goto LABEL_44;
  }
  dword_140224470 = KeQueryActiveProcessorCountEx(0xFFFFu);
  started = NetioInitializeNetBufferListLibrary();
  if ( started < 0 )
  {
LABEL_42:
    NetioUnRegisterProcessorAddCallback(qword_140224458);
    goto LABEL_43;
  }
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NETIO;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  v9 = RtlInvokeStartRoutines(&RssStartStopRoutines, 4, &RssStartedModules);
  RssPagesLocked = 0;
  started = v9;
  if ( v9 < 0 )
  {
LABEL_41:
    WppCleanupKm();
    NetioUnInitializeNetBufferListLibrary();
    goto LABEL_42;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\TcpAllocHooks");
  DeviceObjectPointer = IoGetDeviceObjectPointer(
                          &DestinationString,
                          0xC0100000,
                          (PFILE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject,
                          (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue);
  if ( DeviceObjectPointer >= 0 )
  {
    IoStatusBlock = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v11 = IoBuildDeviceIoControlRequest(
            0x120000u,
            (PDEVICE_OBJECT)WPP_MAIN_CB.Queue.ListEntry.Flink,
            0,
            0,
            &WPP_MAIN_CB.Queue.Wcb.DeviceRoutine,
            8u,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v11 )
    {
      DeviceObjectPointer = -1073741670;
LABEL_28:
      ObfDereferenceObject(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
      WPP_MAIN_CB.Queue.Wcb.DeviceObject = 0;
      WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
      goto LABEL_29;
    }
    DeviceObjectPointer = IofCallDriver((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.ListEntry.Flink, v11);
    if ( DeviceObjectPointer == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer < 0 )
    {
      WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
    }
    else if ( !WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
    {
      DeviceObjectPointer = -1073741822;
    }
    if ( DeviceObjectPointer < 0 )
      goto LABEL_28;
  }
LABEL_29:
  if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 4) != 0 )
    McTemplateK0d_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_ALLOC_HOOKS_SETUP,
      MICROSOFT_TCPIP_PROVIDER,
      (unsigned int)DeviceObjectPointer);
  started = TlStartup();
  if ( started < 0 )
    goto LABEL_40;
  started = NlStartup(DriverObject);
  if ( started < 0 )
  {
LABEL_39:
    TlCleanup();
LABEL_40:
    RtlInvokeStopRoutines(&RssStartStopRoutines, 4, &RssStartedModules);
    goto LABEL_41;
  }
  started = FlStartup();
  if ( started < 0 )
  {
LABEL_38:
    NlCleanup();
    goto LABEL_39;
  }
  started = TcpipPowerStartup();
  if ( started < 0 )
  {
LABEL_37:
    FlCleanup();
    goto LABEL_38;
  }
  started = TcpipConfigStartup();
  if ( started < 0 )
  {
    TcpipPowerCleanup();
    goto LABEL_37;
  }
  if ( (unsigned __int8)IsSystemRunningAsVailGuest() )
  {
    if ( (unsigned __int8)IsWcosLoopbackSupported() )
      IpsLbStartup();
  }
  TcpipInitializeHealthTelemetry(DriverObject);
  NetioRegisterTriageDumpDataCallback(qword_1402243D0, 3, TcpipPopulateTriageDumpData, &TcpipGlobalTriageBlock, "TCPIP");
  KeReleaseMutex(&Mutex, 0);
  return 0;
}

```

## disassembly

```asm
0x1402801b8  push    rbp
0x1402801ba  push    rbx
0x1402801bb  push    rsi
0x1402801bc  push    rdi
0x1402801bd  lea     rbp, [rsp-0C8h]
0x1402801c5  sub     rsp, 1C8h
0x1402801cc  mov     rax, cs:__security_cookie
0x1402801d3  xor     rax, rsp
0x1402801d6  mov     [rbp+0E0h+var_30], rax
0x1402801dd  mov     rdi, rcx
0x1402801e0  xor     edx, edx; Val
0x1402801e2  lea     rcx, [rbp+0E0h+VersionInformation]; void *
0x1402801e6  mov     r8d, 11Ch; Size
0x1402801ec  call    memset
0x1402801f1  call    wil_InitializeFeatureStaging
0x1402801f6  xor     esi, esi
0x1402801f8  mov     ebx, eax
0x1402801fa  test    eax, eax
0x1402801fc  js      loc_1402806B3
0x140280202  call    cs:__imp_PsGetCurrentProcess
0x140280209  nop     dword ptr [rax+rax+00h]
0x14028020e  xor     edx, edx; Level
0x140280210  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rdi
0x140280217  lea     rcx, Mutex; Mutex
0x14028021e  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x140280225  call    cs:__imp_KeInitializeMutex
0x14028022c  nop     dword ptr [rax+rax+00h]
0x140280231  call    IsSystemRunningAsVailGuest
0x140280236  mov     byte ptr cs:WPP_MAIN_CB.Queue+8, al
0x14028023c  call    GetProductType
0x140280241  mov     dword ptr cs:WPP_MAIN_CB.Queue+0Ch, eax
0x140280247  call    GetPortTrackerMode
0x14028024c  xor     edx, edx
0x14028024e  mov     dword ptr cs:WPP_MAIN_CB.Queue+40h, eax
0x140280254  lea     rcx, aNbltracking; "NblTracking"
0x14028025b  call    cs:__imp_NdisQueryDiagnosticSetting
0x140280262  nop     dword ptr [rax+rax+00h]
0x140280267  test    eax, eax
0x140280269  jle     short loc_140280272
0x14028026b  mov     byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140280272  lea     rdx, TcpipGlobalTriageBlock
0x140280279  mov     ecx, 1
0x14028027e  call    cs:__imp_NetioSetTriageBlock
0x140280285  nop     dword ptr [rax+rax+00h]
0x14028028a  mov     rcx, rdi
0x14028028d  call    InitializeTelemetryAssertsKMByDriverObject
0x140280292  xor     edx, edx; Val
0x140280294  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x140280298  mov     r8d, 118h; Size
0x14028029e  call    memset
0x1402802a3  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x1402802a7  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1402802ae  call    cs:__imp_RtlGetVersion
0x1402802b5  nop     dword ptr [rax+rax+00h]
0x1402802ba  test    eax, eax
0x1402802bc  js      short loc_1402802CE
0x1402802be  cmp     [rbp+0E0h+var_36], 1
0x1402802c5  jz      short loc_1402802CE
0x1402802c7  mov     cs:TcpipIsServerSKU, 1
0x1402802ce  call    TcpipStartTrace
0x1402802d3  mov     ebx, eax
0x1402802d5  test    eax, eax
0x1402802d7  js      loc_1402806B3
0x1402802dd  lea     rcx, dword_1402201F8
0x1402802e4  call    TlgRegisterAggregateProvider
0x1402802e9  xor     r8d, r8d
0x1402802ec  lea     rcx, dword_140220230; CallbackContext
0x1402802f3  xor     edx, edx
0x1402802f5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1402802fa  call    PktMonClientInitialize
0x1402802ff  mov     ebx, eax
0x140280301  test    eax, eax
0x140280303  js      loc_140280696
0x140280309  call    TcpipPcwStartup
0x14028030e  mov     ebx, eax
0x140280310  test    eax, eax
0x140280312  js      loc_140280691
0x140280318  call    InitializeMemoryUsageTracking
0x14028031d  mov     ebx, eax
0x14028031f  test    eax, eax
0x140280321  js      loc_14028068C
0x140280327  lea     rax, TcpipDeviceObject
0x14028032e  mov     r9d, 12h; DeviceType
0x140280334  mov     [rsp+1E0h+DeviceObject], rax; DeviceObject
0x140280339  xor     r8d, r8d; DeviceName
0x14028033c  mov     [rsp+1E0h+Exclusive], sil; Exclusive
0x140280341  xor     edx, edx; DeviceExtensionSize
0x140280343  mov     rcx, rdi; DriverObject
0x140280346  mov     [rsp+1E0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x14028034a  call    cs:__imp_IoCreateDevice
0x140280351  nop     dword ptr [rax+rax+00h]
0x140280356  mov     ebx, eax
0x140280358  test    eax, eax
0x14028035a  js      loc_14028068C
0x140280360  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, sil
0x140280367  jz      short loc_14028036E
0x140280369  call    TcpipRegisterInspectionTrackers
0x14028036e  xor     r9d, r9d; Alertable
0x140280371  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rsi; Timeout
0x140280376  xor     r8d, r8d; WaitMode
0x140280379  lea     rcx, Mutex; Object
0x140280380  xor     edx, edx; WaitReason
0x140280382  call    cs:__imp_KeWaitForSingleObject
0x140280389  nop     dword ptr [rax+rax+00h]
0x14028038e  xor     r8d, r8d
0x140280391  lea     rdx, TcpipProcessorAddCallback
0x140280398  lea     rcx, qword_140224458
0x14028039f  call    cs:__imp_NetioRegisterProcessorAddCallback
0x1402803a6  nop     dword ptr [rax+rax+00h]
0x1402803ab  mov     ebx, eax
0x1402803ad  test    eax, eax
0x1402803af  js      loc_14028065F
0x1402803b5  mov     ecx, 0FFFFh; GroupNumber
0x1402803ba  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1402803c1  nop     dword ptr [rax+rax+00h]
0x1402803c6  mov     cs:dword_140224470, eax
0x1402803cc  call    cs:__imp_NetioInitializeNetBufferListLibrary
0x1402803d3  nop     dword ptr [rax+rax+00h]
0x1402803d8  mov     ebx, eax
0x1402803da  test    eax, eax
0x1402803dc  js      loc_14028064C
0x1402803e2  lea     rax, WPP_ThisDir_CTLGUID_NETIO
0x1402803e9  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x1402803f0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1402803f7  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x1402803fe  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x140280405  mov     cs:WPP_MAIN_CB.Timer, 1
0x140280410  call    WppLoadTracingSupport
0x140280415  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14028041c  call    WppInitKm
0x140280421  lea     r8, RssStartedModules
0x140280428  mov     edx, 4
0x14028042d  lea     rcx, RssStartStopRoutines
0x140280434  call    cs:__imp_RtlInvokeStartRoutines
0x14028043b  nop     dword ptr [rax+rax+00h]
0x140280440  mov     cs:RssPagesLocked, sil
0x140280447  mov     ebx, eax
0x140280449  test    eax, eax
0x14028044b  js      loc_14028063B
0x140280451  xorps   xmm0, xmm0
0x140280454  lea     rdx, aDeviceTcpalloc; "\\Device\\TcpAllocHooks"
0x14028045b  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x140280460  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x140280465  call    cs:__imp_RtlInitUnicodeString
0x14028046c  nop     dword ptr [rax+rax+00h]
0x140280471  lea     r9, WPP_MAIN_CB.Queue; DeviceObject
0x140280478  mov     edx, 0C0100000h; DesiredAccess
0x14028047d  lea     r8, WPP_MAIN_CB.Queue+30h; FileObject
0x140280484  lea     rcx, [rsp+1E0h+DestinationString]; ObjectName
0x140280489  call    cs:__imp_IoGetDeviceObjectPointer
0x140280490  nop     dword ptr [rax+rax+00h]
0x140280495  mov     ebx, eax
0x140280497  test    eax, eax
0x140280499  js      loc_1402805A4
0x14028049f  xorps   xmm0, xmm0
0x1402804a2  lea     rcx, [rsp+1E0h+Event]; Event
0x1402804a7  xorps   xmm1, xmm1
0x1402804aa  xor     eax, eax
0x1402804ac  xor     r8d, r8d; State
0x1402804af  mov     [rsp+1E0h+Event.Header.WaitListHead.Blink], rax
0x1402804b4  xor     edx, edx; Type
0x1402804b6  movups  xmmword ptr [rsp+1E0h+var_168], xmm0
0x1402804bb  movups  xmmword ptr [rsp+1E0h+Event.Header], xmm1
0x1402804c0  call    cs:__imp_KeInitializeEvent
0x1402804c7  nop     dword ptr [rax+rax+00h]
0x1402804cc  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue; DeviceObject
0x1402804d3  lea     rax, [rsp+1E0h+var_168]
0x1402804d8  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x1402804dd  xor     r9d, r9d; InputBufferLength
0x1402804e0  lea     rax, [rsp+1E0h+Event]
0x1402804e5  xor     r8d, r8d; InputBuffer
0x1402804e8  mov     [rsp+1E0h+var_1A8], rax; Event
0x1402804ed  mov     ecx, 120000h; IoControlCode
0x1402804f2  mov     byte ptr [rsp+1E0h+DeviceObject], sil; InternalDeviceIoControl
0x1402804f7  lea     rax, WPP_MAIN_CB.Queue+18h
0x1402804fe  mov     dword ptr [rsp+1E0h+Exclusive], 8; OutputBufferLength
0x140280506  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; OutputBuffer
0x14028050b  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140280512  nop     dword ptr [rax+rax+00h]
0x140280517  test    rax, rax
0x14028051a  jz      short loc_14028057E
0x14028051c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; DeviceObject
0x140280523  mov     rdx, rax; Irp
0x140280526  call    cs:__imp_IofCallDriver
0x14028052d  nop     dword ptr [rax+rax+00h]
0x140280532  mov     ebx, eax
0x140280534  cmp     eax, 103h
0x140280539  jnz     short loc_14028055D
0x14028053b  xor     r9d, r9d; Alertable
0x14028053e  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rsi; Timeout
0x140280543  xor     r8d, r8d; WaitMode
0x140280546  lea     rcx, [rsp+1E0h+Event]; Object
0x14028054b  xor     edx, edx; WaitReason
0x14028054d  call    cs:__imp_KeWaitForSingleObject
0x140280554  nop     dword ptr [rax+rax+00h]
0x140280559  mov     ebx, dword ptr [rsp+1E0h+var_168]
0x14028055d  test    ebx, ebx
0x14028055f  js      short loc_140280571
0x140280561  cmp     qword ptr cs:WPP_MAIN_CB.Queue+18h, rsi
0x140280568  jnz     short loc_140280578
0x14028056a  mov     ebx, 0C0000002h
0x14028056f  jmp     short loc_140280578
0x140280571  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rsi
0x140280578  test    ebx, ebx
0x14028057a  jns     short loc_1402805A4
0x14028057c  jmp     short loc_140280583
0x14028057e  mov     ebx, 0C000009Ah
0x140280583  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+30h; Object
0x14028058a  call    cs:__imp_ObfDereferenceObject
0x140280591  nop     dword ptr [rax+rax+00h]
0x140280596  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rsi
0x14028059d  mov     qword ptr cs:WPP_MAIN_CB.Queue, rsi
0x1402805a4  test    byte ptr cs:WPP_MAIN_CB+14Dh, 4
0x1402805ab  jz      short loc_1402805CA
0x1402805ad  mov     r9d, ebx
0x1402805b0  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1402805b7  lea     rdx, TCPIP_ALLOC_HOOKS_SETUP
0x1402805be  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1402805c5  call    McTemplateK0d_EtwWriteTransfer
0x1402805ca  call    TlStartup
0x1402805cf  mov     ebx, eax
0x1402805d1  test    eax, eax
0x1402805d3  js      short loc_14028061C
0x1402805d5  mov     rcx, rdi; DriverObject
0x1402805d8  call    NlStartup
0x1402805dd  mov     ebx, eax
0x1402805df  test    eax, eax
0x1402805e1  js      short loc_140280617
0x1402805e3  call    FlStartup
0x1402805e8  mov     ebx, eax
0x1402805ea  test    eax, eax
0x1402805ec  js      short loc_140280612
0x1402805ee  call    TcpipPowerStartup
0x1402805f3  mov     ebx, eax
0x1402805f5  test    eax, eax
0x1402805f7  js      short loc_14028060D
0x1402805f9  call    TcpipConfigStartup
0x1402805fe  mov     ebx, eax
0x140280600  test    eax, eax
0x140280602  jns     loc_1402806D6
0x140280608  call    TcpipPowerCleanup
0x14028060d  call    FlCleanup
0x140280612  call    NlCleanup
0x140280617  call    TlCleanup
0x14028061c  lea     r8, RssStartedModules
0x140280623  mov     edx, 4
0x140280628  lea     rcx, RssStartStopRoutines
0x14028062f  call    cs:__imp_RtlInvokeStopRoutines
0x140280636  nop     dword ptr [rax+rax+00h]
0x14028063b  call    WppCleanupKm
0x140280640  call    cs:__imp_NetioUnInitializeNetBufferListLibrary
0x140280647  nop     dword ptr [rax+rax+00h]
0x14028064c  lea     rcx, qword_140224458
0x140280653  call    cs:__imp_NetioUnRegisterProcessorAddCallback
0x14028065a  nop     dword ptr [rax+rax+00h]
0x14028065f  xor     edx, edx; Wait
0x140280661  lea     rcx, Mutex; Mutex
0x140280668  call    cs:__imp_KeReleaseMutex
0x14028066f  nop     dword ptr [rax+rax+00h]
0x140280674  call    TcpipDeregisterInspectionTrackers
0x140280679  mov     rcx, cs:TcpipDeviceObject; DeviceObject
0x140280680  call    cs:__imp_IoDeleteDevice
0x140280687  nop     dword ptr [rax+rax+00h]
0x14028068c  call    TcpipPcwCleanup
0x140280691  call    PktMonClientUninitialize
0x140280696  lea     rcx, dword_140220230
0x14028069d  call    TraceLoggingUnregister_EtwUnregister
0x1402806a2  lea     rcx, dword_1402201F8
0x1402806a9  call    TlgUnregisterAggregateProvider
0x1402806ae  call    TcpipStopTrace
0x1402806b3  call    wil_UninitializeFeatureStaging
0x1402806b8  mov     eax, ebx
0x1402806ba  mov     rcx, [rbp+0E0h+var_30]
0x1402806c1  xor     rcx, rsp; StackCookie
0x1402806c4  call    __security_check_cookie
0x1402806c9  add     rsp, 1C8h
0x1402806d0  pop     rdi
0x1402806d1  pop     rsi
0x1402806d2  pop     rbx
0x1402806d3  pop     rbp
0x1402806d4  retn
0x1402806d6  call    IsSystemRunningAsVailGuest
0x1402806db  test    al, al
0x1402806dd  jz      short loc_1402806ED
0x1402806df  call    IsWcosLoopbackSupported
0x1402806e4  test    al, al
0x1402806e6  jz      short loc_1402806ED
0x1402806e8  call    IpsLbStartup
0x1402806ed  mov     rcx, rdi
0x1402806f0  call    TcpipInitializeHealthTelemetry
0x1402806f5  lea     rax, aTcpip_0; "TCPIP"
0x1402806fc  mov     edx, 3
0x140280701  lea     r9, TcpipGlobalTriageBlock
0x140280708  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax
0x14028070d  lea     r8, TcpipPopulateTriageDumpData
0x140280714  lea     rcx, qword_1402243D0
0x14028071b  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x140280722  nop     dword ptr [rax+rax+00h]
0x140280727  xor     edx, edx; Wait
0x140280729  lea     rcx, Mutex; Mutex
  ... truncated ...
```
