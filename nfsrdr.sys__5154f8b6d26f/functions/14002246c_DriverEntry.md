# DriverEntry

- ea: `0x14002246c`
- end: `0x140022c53`
- name: `DriverEntry`
- size: `2023`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140047010`

## callees

- `0x140001010`
- `0x1400010c0`
- `0x1400159cc`
- `0x1400159fc`
- `0x14002246c`
- `0x14002d428`
- `0x14002edd4`
- `0x140038550`
- `0x14003866c`
- `0x14003aba0`
- `0x14003b0c0`
- `0x140046008`
- `0x1400460b4`
- `0x1400460ec`
- `0x140046170`
- `0x140046204`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140022be6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140022be6`
- `ntoskrnl!KeInitializeEvent` at `0x1400225a6`
- `ntoskrnl!KeInitializeEvent` at `0x1400225a6`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400229a9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400229a9`
- `ntoskrnl!NtCreateFile` at `0x140022a4a`
- `ntoskrnl!NtCreateFile` at `0x140022a4a`
- `ntoskrnl!NtClose` at `0x140022bc1`
- `ntoskrnl!NtClose` at `0x140022bc1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002255e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022575`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002258c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002255e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022575`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002258c`
- `rdbss!RxUnregisterMinirdr` at `0x140022ba1`
- `rdbss!RxUnregisterMinirdr` at `0x140022ba1`
- `rdbss!RxRegisterMinirdr` at `0x1400228c7`
- `rdbss!RxRegisterMinirdr` at `0x1400228c7`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v3; // si
  int v4; // edi
  NTSTATUS inited; // edi
  char v6; // bl
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int16 SystemDefaultLangId; // ax
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  NTSTATUS v16; // [rsp+64h] [rbp-9Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v20; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+D8h] [rbp-28h] BYREF
  NTSTATUS *v23; // [rsp+F8h] [rbp-8h]
  __int64 v24; // [rsp+100h] [rbp+0h]

  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  v15 = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NfsRdrGuid;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  IoStatusBlock = 0;
  v3 = 0;
  WPP_MAIN_CB.NextDevice = 0;
  memset(&ObjectAttributes, 0, 44);
  WPP_MAIN_CB.CurrentIrp = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  v20 = 0;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  memset(&WPP_MAIN_CB.DeviceExtension, 0, 0x308u);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\MRxNfs");
  RtlInitUnicodeString(&v20, L"\\Device\\FsWrap");
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\NfsRdr");
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  if ( (int)NfsReadRegistry(
              &stru_140041060,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v15,
              4) >= 0 )
  {
    v4 = v15;
  }
  else
  {
    v4 = 0;
    v15 = 0;
  }
  memset(&WPP_MAIN_CB.DeviceExtension, 0, 0x2D8u);
  WPP_MAIN_CB.DeviceExtension = (PVOID)0x802D8EBFFLL;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)MdaStart;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = MdaStop;
  qword_1400415F8 = (__int64)MdaDevFcbXXXControlFile;
  qword_1400415E0 = (__int64)&MdaCreateSrvCall;
  qword_1400415F0 = (__int64)MdaFinalizeSrvCall;
  qword_140041560[0] = (__int64)MdaCreateVNetRoot;
  qword_1400415A0 = (__int64)MdaUpdateNetRootState;
  qword_1400415A8[0] = (__int64)&MdaExtractNetRootName;
  qword_140041598 = (__int64)MdaFinalizeNetRoot;
  qword_140041590 = (__int64)MdaFinalizeVNetRoot;
  WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)MdaIsLockRealizable;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = MdaCreate;
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = MdaCheckForCollapsibleOpen;
  WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = (PKDPC)MdaCollapseOpen;
  qword_140041548 = (__int64)MdaExtendFile;
  qword_140041550[0] = (__int64)MdaExtendFile;
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = MdaTruncate;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = (struct _LIST_ENTRY *)MdaCleanupFobx;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)MdaCloseSrvOpen;
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = MdaFlush;
  WPP_MAIN_CB.Dpc.DeferredRoutine = (PKDEFERRED_ROUTINE)MdaForcedClose;
  WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)MdaDeallocateForFcb;
  WPP_MAIN_CB.Dpc.DpcListEntry.Next = (struct _SINGLE_LIST_ENTRY *)MdaDeallocateForFobx;
  *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = MdaIsValidDirectory;
  WPP_MAIN_CB.Dpc.DpcData = MdaQueryDirectory;
  qword_1400414D0[0] = (__int64)MdaQueryVolumeInformation;
  WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)MdaQueryEaInformation;
  WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)MdaSetEaInformation;
  *(_QWORD *)&WPP_MAIN_CB.SectorSize = MdaQuerySecurityInformation;
  WPP_MAIN_CB.DeviceObjectExtension = (struct _DEVOBJ_EXTENSION *)MdaSetSecurityInformation;
  *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = MdaQueryFileInformation;
  WPP_MAIN_CB.SecurityDescriptor = MdaSetFileInformation;
  *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = MdaSetFileInformationAtCleanup;
  qword_1400414E0 = (__int64)MdaIsValidDirectory;
  qword_1400414E8 = (__int64)MdaComputeNewBufferingState;
  qword_1400414F0 = (__int64)MdaRead;
  *(_QWORD *)&WPP_MAIN_CB.StackSize = 0;
  HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) = 0;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
  qword_1400414F8 = (__int64)MdaWrite;
  qword_140041520 = (__int64)MdaFsctl;
  dword_140041690 = v4;
  qword_140041528 = (__int64)MdaIoctl;
  qword_140041530[0] = (__int64)MdaNotifyChangeDirectory;
  qword_140041670 = (__int64)MdaTrampoline;
  xmmword_140041500 = (__int128)_mm_movelh_ps((__m128)(unsigned __int64)MdaLocks, (__m128)(unsigned __int64)MdaLocks);
  xmmword_140041510 = xmmword_140041500;
  inited = RxRegisterMinirdr(
             &StartContext,
             DriverObject,
             (PMINIRDR_DISPATCH)&WPP_MAIN_CB.DeviceExtension,
             0x402u,
             &DestinationString,
             0x420u,
             0x14u,
             0x110u);
  if ( inited >= 0 )
  {
    memset(&StartContext->RxNetNameTableInDeviceObject.HashBuckets[30].Blink, 0, 0x420u);
    StartContext[1].DeviceName.Buffer = (PWSTR)-1LL;
    inited = InitNfsRedir((char *)StartContext);
    if ( inited >= 0 )
    {
      v9 = 27;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)MdaDriverUnload;
      v3 = 1;
      memset64(DriverObject->MajorFunction, (unsigned __int64)MdaNtDispatch, 0x1Bu);
      v6 = 1;
      do
        --v9;
      while ( v9 );
      inited = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
      if ( inited >= 0 )
      {
        byte_1400416C0 = 1;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = &v20;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        inited = NtCreateFile(&Handle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 1u, 0, 2u, 0x60u, 0, 0);
        if ( inited < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v8 = 18;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v8 = 17;
          goto LABEL_26;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
      v6 = 1;
    }
  }
  else
  {
    v6 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v8 = 15;
LABEL_26:
      WPP_SF_d(v7->AttachedDevice, v8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
    }
  }
  if ( (unsigned int)dword_140041028 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v16 = inited;
    v23 = &v16;
    v24 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_14003E431, v11, v12, 3u, &v22);
  }
  if ( inited < 0 )
  {
    if ( StartContext )
    {
      _InterlockedOr((volatile signed __int32 *)&StartContext[1].DispatcherContext.pTearDownEvent + 1, 8u);
      if ( v3 )
        UnInitNfsRedir(StartContext);
      if ( v6 )
        RxUnregisterMinirdr(StartContext);
      StartContext = 0;
    }
    if ( Handle != (HANDLE)-1LL )
    {
      NtClose(Handle);
      Handle = (HANDLE)-1LL;
    }
    if ( byte_1400416C0 )
      IoDeleteSymbolicLink(&DestinationString);
    TraceLoggingUnregister_EtwUnregister();
    WppCleanupKm();
    goto LABEL_53;
  }
  _InterlockedOr((volatile signed __int32 *)&StartContext[1].DispatcherContext.pTearDownEvent + 1, 0x10u);
  SystemDefaultLangId = NfsGetSystemDefaultLangId();
  switch ( SystemDefaultLangId )
  {
    case 1041:
      gfCodeModeFlags |= 8u;
      break;
    case 1028:
      gfCodeModeFlags |= 0x20u;
      break;
    case 2052:
      gfCodeModeFlags |= 0x40u;
      break;
    case 1042:
      gfCodeModeFlags |= 0x10u;
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      NfsGetSystemDefaultLangId();
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
    }
LABEL_53:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  }
  return inited;
}

```

## disassembly

```asm
0x14002246c  mov     [rsp-8+arg_8], rbx
0x140022471  mov     [rsp-8+arg_10], rsi
0x140022476  push    rbp
0x140022477  push    rdi
0x140022478  push    r13
0x14002247a  push    r14
0x14002247c  push    r15
0x14002247e  lea     rbp, [rsp-10h]
0x140022483  sub     rsp, 110h
0x14002248a  mov     rax, cs:__security_cookie
0x140022491  xor     rax, rsp
0x140022494  mov     [rbp+30h+var_28], rax
0x140022498  xorps   xmm0, xmm0
0x14002249b  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400224a6  xor     r15d, r15d
0x1400224a9  xor     eax, eax
0x1400224ab  lea     rax, WPP_ThisDir_CTLGUID_NfsRdrGuid
0x1400224b2  mov     dword ptr [rsp+130h+var_D0], r15d
0x1400224b7  xorps   xmm1, xmm1
0x1400224ba  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400224c1  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x1400224c5  mov     rbx, rcx
0x1400224c8  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x1400224cf  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x1400224d3  mov     sil, r15b
0x1400224d6  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x1400224dd  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x1400224e2  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x1400224e9  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x1400224ed  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1400224f2  movups  xmmword ptr [rbp+30h+SymbolicLinkName.Length], xmm1
0x1400224f6  movups  xmmword ptr [rbp+30h+var_78.Length], xmm0
0x1400224fa  call    WppLoadTracingSupport
0x1400224ff  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x140022506  call    WppInitKm
0x14002250b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140022510  mov     rcx, cs:WPP_GLOBAL_Control
0x140022517  lea     r13, WPP_GLOBAL_Control
0x14002251e  cmp     rcx, r13
0x140022521  jz      short loc_14002253E
0x140022523  mov     eax, [rcx+2Ch]
0x140022526  test    al, 8
0x140022528  jz      short loc_14002253E
0x14002252a  mov     rcx, [rcx+18h]
0x14002252e  lea     edx, [r15+0Eh]
0x140022532  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022539  call    WPP_SF_
0x14002253e  xor     edx, edx; Val
0x140022540  lea     rcx, WPP_MAIN_CB.DeviceExtension; void *
0x140022547  mov     r8d, 308h; Size
0x14002254d  call    memset
0x140022552  lea     rdx, aDeviceMrxnfs; "\\Device\\MRxNfs"
0x140022559  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14002255e  call    cs:__imp_RtlInitUnicodeString
0x140022565  nop     dword ptr [rax+rax+00h]
0x14002256a  lea     rdx, aDeviceFswrap; "\\Device\\FsWrap"
0x140022571  lea     rcx, [rbp+30h+var_78]; DestinationString
0x140022575  call    cs:__imp_RtlInitUnicodeString
0x14002257c  nop     dword ptr [rax+rax+00h]
0x140022581  lea     rdx, aDosdevicesNfsr; "\\DosDevices\\NfsRdr"
0x140022588  lea     rcx, [rbp+30h+SymbolicLinkName]; DestinationString
0x14002258c  call    cs:__imp_RtlInitUnicodeString
0x140022593  nop     dword ptr [rax+rax+00h]
0x140022598  xor     r8d, r8d; State
0x14002259b  lea     rcx, Event; Event
0x1400225a2  lea     edx, [r8+1]; Type
0x1400225a6  call    cs:__imp_KeInitializeEvent
0x1400225ad  nop     dword ptr [rax+rax+00h]
0x1400225b2  mov     ecx, 4
0x1400225b7  lea     rax, [rsp+130h+var_D0]
0x1400225bc  mov     [rsp+130h+DeviceExtensionSize], ecx; int
0x1400225c0  lea     r8, aScavengertimel; "ScavengerTimeLimit"
0x1400225c7  mov     r9d, ecx
0x1400225ca  mov     [rsp+130h+DeviceName], rax; __int64
0x1400225cf  lea     rcx, stru_140041060; SourceString
0x1400225d6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1400225dd  call    NfsReadRegistry
0x1400225e2  test    eax, eax
0x1400225e4  jns     short loc_1400225F0
0x1400225e6  mov     edi, r15d
0x1400225e9  mov     dword ptr [rsp+130h+var_D0], r15d
0x1400225ee  jmp     short loc_1400225F4
0x1400225f0  mov     edi, dword ptr [rsp+130h+var_D0]
0x1400225f4  xor     edx, edx; Val
0x1400225f6  lea     rcx, WPP_MAIN_CB.DeviceExtension; void *
0x1400225fd  mov     r8d, 2D8h; Size
0x140022603  call    memset
0x140022608  lea     rax, MdaStart
0x14002260f  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 2D8EBFFh
0x140022619  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140022620  mov     r14d, 8
0x140022626  lea     rax, MdaStop
0x14002262d  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension+4, r14d
0x140022634  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x14002263b  lea     rax, MdaDevFcbXXXControlFile
0x140022642  mov     cs:qword_1400415F8, rax
0x140022649  lea     rax, MdaCreateSrvCall
0x140022650  mov     cs:qword_1400415E0, rax
0x140022657  lea     rax, MdaFinalizeSrvCall
0x14002265e  mov     cs:qword_1400415F0, rax
0x140022665  lea     rax, MdaCreateVNetRoot
0x14002266c  mov     cs:qword_140041560, rax
0x140022673  lea     rax, MdaUpdateNetRootState
0x14002267a  mov     cs:qword_1400415A0, rax
0x140022681  lea     rax, MdaExtractNetRootName
0x140022688  mov     cs:qword_1400415A8, rax
0x14002268f  lea     rax, MdaFinalizeNetRoot
0x140022696  mov     cs:qword_140041598, rax
0x14002269d  lea     rax, MdaFinalizeVNetRoot
0x1400226a4  mov     cs:qword_140041590, rax
0x1400226ab  lea     rax, MdaIsLockRealizable
0x1400226b2  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x1400226b9  lea     rax, MdaCreate
0x1400226c0  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x1400226c7  lea     rax, MdaCheckForCollapsibleOpen
0x1400226ce  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x1400226d5  lea     rax, MdaCollapseOpen
0x1400226dc  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rax
0x1400226e3  lea     rax, MdaExtendFile
0x1400226ea  mov     cs:qword_140041548, rax
0x1400226f1  mov     cs:qword_140041550, rax
0x1400226f8  lea     rax, MdaTruncate
0x1400226ff  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x140022706  lea     rax, MdaCleanupFobx
0x14002270d  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rax
0x140022714  lea     rax, MdaCloseSrvOpen
0x14002271b  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x140022722  lea     rax, MdaFlush
0x140022729  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rax
0x140022730  lea     rax, MdaForcedClose
0x140022737  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rax
0x14002273e  lea     rax, MdaDeallocateForFcb
0x140022745  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x14002274c  lea     rax, MdaDeallocateForFobx
0x140022753  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x14002275a  lea     rax, MdaIsValidDirectory
0x140022761  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x140022768  lea     rax, MdaQueryDirectory
0x14002276f  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rax
0x140022776  lea     rax, MdaQueryVolumeInformation
0x14002277d  mov     cs:qword_1400414D0, rax
0x140022784  lea     rax, MdaQueryEaInformation
0x14002278b  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rax
0x140022792  lea     rax, MdaSetEaInformation
0x140022799  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, rax
0x1400227a0  lea     rax, MdaQuerySecurityInformation
0x1400227a7  mov     qword ptr cs:WPP_MAIN_CB.SectorSize, rax
0x1400227ae  lea     rax, MdaSetSecurityInformation
0x1400227b5  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, rax
0x1400227bc  lea     rax, MdaQueryFileInformation
0x1400227c3  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rax
0x1400227ca  lea     rax, MdaSetFileInformation
0x1400227d1  mov     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x1400227d8  lea     rax, MdaSetFileInformationAtCleanup
0x1400227df  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header, rax
0x1400227e6  lea     rax, MdaIsValidDirectory
0x1400227ed  mov     cs:qword_1400414E0, rax
0x1400227f4  lea     rax, MdaComputeNewBufferingState
0x1400227fb  mov     cs:qword_1400414E8, rax
0x140022802  lea     rax, MdaRead
0x140022809  mov     cs:qword_1400414F0, rax
0x140022810  mov     qword ptr cs:WPP_MAIN_CB.StackSize, r15
0x140022817  mov     dword ptr cs:WPP_MAIN_CB.Queue+4, r15d
0x14002281e  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, r15
0x140022825  mov     [rsp+130h+DeviceCharacteristics], 110h; DeviceCharacteristics
0x14002282d  lea     rax, MdaWrite
0x140022834  mov     cs:qword_1400414F8, rax
0x14002283b  lea     r8, WPP_MAIN_CB.DeviceExtension; MrdrDispatch
0x140022842  lea     rax, MdaLocks
0x140022849  mov     [rsp+130h+DeviceType], 14h; DeviceType
0x140022851  movq    xmm0, rax
0x140022856  mov     [rsp+130h+DeviceExtensionSize], 420h; DeviceExtensionSize
0x14002285e  movlhps xmm0, xmm0
0x140022861  lea     rax, MdaFsctl
0x140022868  mov     cs:qword_140041520, rax
0x14002286f  lea     rcx, StartContext; DeviceObject
0x140022876  lea     rax, MdaIoctl
0x14002287d  mov     cs:dword_140041690, edi
0x140022883  mov     cs:qword_140041528, rax
0x14002288a  mov     r9d, 402h; Controls
0x140022890  lea     rax, MdaNotifyChangeDirectory
0x140022897  mov     rdx, rbx; DriverObject
0x14002289a  mov     cs:qword_140041530, rax
0x1400228a1  lea     rax, MdaTrampoline
0x1400228a8  mov     cs:qword_140041670, rax
0x1400228af  lea     rax, [rsp+130h+DestinationString]
0x1400228b4  mov     [rsp+130h+DeviceName], rax; DeviceName
0x1400228b9  movups  cs:xmmword_140041500, xmm0
0x1400228c0  movups  cs:xmmword_140041510, xmm0
0x1400228c7  call    cs:__imp_RxRegisterMinirdr
0x1400228ce  nop     dword ptr [rax+rax+00h]
0x1400228d3  mov     edi, eax
0x1400228d5  test    eax, eax
0x1400228d7  jns     short loc_140022904
0x1400228d9  mov     bl, r15b
0x1400228dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228e3  cmp     rcx, r13
0x1400228e6  jz      loc_140022A87
0x1400228ec  mov     edx, [rcx+2Ch]
0x1400228ef  test    dl, 1
0x1400228f2  jz      loc_140022A87
0x1400228f8  lea     edx, [r14+7]
0x1400228fc  mov     r9d, eax
0x1400228ff  jmp     loc_140022A77
0x140022904  mov     rcx, cs:StartContext
0x14002290b  xor     edx, edx; Val
0x14002290d  add     rcx, 520h; void *
0x140022914  mov     r8d, 420h; Size
0x14002291a  call    memset
0x14002291f  mov     rax, cs:StartContext
0x140022926  mov     qword ptr [rax+7E8h], 0FFFFFFFFFFFFFFFFh
0x140022931  mov     rcx, cs:StartContext; StartContext
0x140022938  call    InitNfsRedir
0x14002293d  mov     edi, eax
0x14002293f  test    eax, eax
0x140022941  jns     short loc_140022975
0x140022943  mov     rcx, cs:WPP_GLOBAL_Control
0x14002294a  cmp     rcx, r13
0x14002294d  jz      short loc_14002296E
0x14002294f  mov     eax, [rcx+2Ch]
0x140022952  test    al, 1
0x140022954  jz      short loc_14002296E
0x140022956  mov     rcx, [rcx+18h]
0x14002295a  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022961  mov     edx, 10h
0x140022966  mov     r9d, edi
0x140022969  call    WPP_SF_d
0x14002296e  mov     bl, 1
0x140022970  jmp     loc_140022A87
0x140022975  lea     rax, MdaDriverUnload
0x14002297c  mov     edx, 1Bh
0x140022981  mov     [rbx+68h], rax
0x140022985  lea     rdi, [rbx+70h]
0x140022989  lea     rax, MdaNtDispatch
0x140022990  mov     ecx, edx
0x140022992  mov     sil, 1
0x140022995  rep stosq
0x140022998  mov     bl, sil
0x14002299b  add     edx, 0FFFFFFFFh
0x14002299e  jnz     short loc_14002299B
0x1400229a0  lea     rdx, [rsp+130h+DestinationString]; DeviceName
0x1400229a5  lea     rcx, [rbp+30h+SymbolicLinkName]; SymbolicLinkName
0x1400229a9  call    cs:__imp_IoCreateSymbolicLink
0x1400229b0  nop     dword ptr [rax+rax+00h]
0x1400229b5  mov     edi, eax
0x1400229b7  test    eax, eax
0x1400229b9  jns     short loc_1400229E0
0x1400229bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400229c2  cmp     rcx, r13
0x1400229c5  jz      loc_140022A87
0x1400229cb  mov     eax, [rcx+2Ch]
0x1400229ce  test    bl, al
0x1400229d0  jz      loc_140022A87
0x1400229d6  mov     edx, 11h
0x1400229db  jmp     loc_140022A74
0x1400229e0  mov     [rsp+130h+EaLength], r15d; EaLength
0x1400229e5  lea     rax, [rbp+30h+var_78]
0x1400229e9  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x1400229ee  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x1400229f2  mov     [rsp+130h+CreateOptions], 60h ; '`'; CreateOptions
0x1400229fa  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1400229ff  mov     [rsp+130h+DeviceCharacteristics], 2; CreateDisposition
0x140022a07  lea     rcx, Handle; FileHandle
0x140022a0e  mov     [rsp+130h+DeviceType], r15d; ShareAccess
0x140022a13  xorps   xmm0, xmm0
0x140022a16  mov     [rsp+130h+DeviceExtensionSize], 1; FileAttributes
0x140022a1e  mov     edx, 0C0100000h; DesiredAccess
0x140022a23  mov     [rsp+130h+DeviceName], r15; AllocationSize
0x140022a28  mov     cs:byte_1400416C0, bl
0x140022a2e  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x140022a36  mov     [rbp+30h+ObjectAttributes.RootDirectory], r15
0x140022a3a  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x140022a41  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x140022a45  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x140022a4a  call    cs:__imp_NtCreateFile
0x140022a51  nop     dword ptr [rax+rax+00h]
0x140022a56  mov     edi, eax
0x140022a58  test    eax, eax
0x140022a5a  jns     short loc_140022A87
0x140022a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a63  cmp     rcx, r13
0x140022a66  jz      short loc_140022A87
0x140022a68  mov     eax, [rcx+2Ch]
0x140022a6b  test    bl, al
0x140022a6d  jz      short loc_140022A87
0x140022a6f  mov     edx, 12h
0x140022a74  mov     r9d, edi
0x140022a77  mov     rcx, [rcx+18h]
0x140022a7b  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022a82  call    WPP_SF_d
0x140022a87  mov     eax, cs:dword_140041028
0x140022a8d  cmp     eax, 5
0x140022a90  jbe     short loc_140022ACD
0x140022a92  call    _tlgKeywordOn
0x140022a97  test    al, al
0x140022a99  jz      short loc_140022ACD
0x140022a9b  lea     rax, [rsp+130h+var_D0+4]
0x140022aa0  mov     dword ptr [rsp+130h+var_D0+4], edi
0x140022aa4  mov     [rbp+30h+var_38], rax
0x140022aa8  lea     rdx, byte_14003E431; int
  ... truncated ...
```
