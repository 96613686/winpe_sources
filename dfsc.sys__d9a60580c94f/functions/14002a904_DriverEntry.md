# DriverEntry

- ea: `0x14002a904`
- end: `0x14002aaf5`
- name: `DriverEntry`
- size: `497`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x14002a010`

## callees

- `0x140012930`
- `0x140012c6c`
- `0x140012d00`
- `0x140019ddc`
- `0x14002a078`
- `0x14002a488`
- `0x14002a904`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002a92f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a9ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a92f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a9ae`
- `ntoskrnl!IoCreateDevice` at `0x14002a964`
- `ntoskrnl!IoCreateDevice` at `0x14002a964`
- `ntoskrnl!IoDeleteDevice` at `0x14002a991`
- `ntoskrnl!IoDeleteDevice` at `0x14002a991`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002a9bf`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002a9bf`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002a9d5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002a9d5`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-38h] BYREF

  DestinationString = 0;
  SymbolicLinkName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\DfsClient");
  result = IoCreateDevice(
             DriverObject,
             0,
             &DestinationString,
             8u,
             0x110u,
             0,
             (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
  if ( result >= 0 )
  {
    inited = DfscApplyDeviceAcl(WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    if ( inited < 0
      || (RtlInitUnicodeString(&SymbolicLinkName, L"\\Dfs"),
          IoDeleteSymbolicLink(&SymbolicLinkName),
          inited = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString),
          inited < 0) )
    {
      IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    }
    else
    {
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = (PKDPC)DriverObject;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
      DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&DfscCreate;
      DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&DfscCleanup;
      DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&DfscClose;
      DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)&DfscSystemControl;
      DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)DfscFileSystemControl;
      DriverObject->FastIoDispatch = 0;
      *((_BYTE *)WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 76) = 1;
      *((_DWORD *)WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 12) &= ~0x80u;
      WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MupLog;
      WPP_MAIN_CB.NextDevice = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension;
      *(_QWORD *)&WPP_MAIN_CB.DeviceType = WPP_ThisDir_CTLGUID_RFSMon;
      *(_QWORD *)&WPP_MAIN_CB.Type = 0;
      WPP_MAIN_CB.CurrentIrp = 0;
      WPP_MAIN_CB.Timer = (PIO_TIMER)1;
      WPP_MAIN_CB.DeviceExtension = 0;
      WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
      *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
      WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)1;
      WppLoadTracingSupport();
      WPP_MAIN_CB.CurrentIrp = 0;
      WppInitKm();
      inited = DfscInitVariables(RegistryPath);
      if ( inited < 0 || (inited = DfscInitializeTimer(), inited < 0) )
        DfscInitUnwind();
    }
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x14002a904  push    rbx
0x14002a906  push    rbp
0x14002a907  push    rsi
0x14002a908  push    rdi
0x14002a909  sub     rsp, 68h
0x14002a90d  mov     rsi, rdx
0x14002a910  mov     rdi, rcx
0x14002a913  xorps   xmm0, xmm0
0x14002a916  lea     rdx, SourceString; "\\Device\\DfsClient"
0x14002a91d  xorps   xmm1, xmm1
0x14002a920  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14002a925  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14002a92a  movups  xmmword ptr [rsp+88h+SymbolicLinkName.Length], xmm1
0x14002a92f  call    cs:__imp_RtlInitUnicodeString
0x14002a936  nop     dword ptr [rax+rax+00h]
0x14002a93b  xor     ebp, ebp
0x14002a93d  lea     rax, WPP_MAIN_CB.Queue+38h
0x14002a944  mov     [rsp+88h+DeviceObject], rax; DeviceObject
0x14002a949  lea     r8, [rsp+88h+DestinationString]; DeviceName
0x14002a94e  mov     [rsp+88h+Exclusive], bpl; Exclusive
0x14002a953  xor     edx, edx; DeviceExtensionSize
0x14002a955  mov     rcx, rdi; DriverObject
0x14002a958  mov     [rsp+88h+DeviceCharacteristics], 110h; DeviceCharacteristics
0x14002a960  lea     r9d, [rbp+8]; DeviceType
0x14002a964  call    cs:__imp_IoCreateDevice
0x14002a96b  nop     dword ptr [rax+rax+00h]
0x14002a970  test    eax, eax
0x14002a972  js      loc_14002AAEB
0x14002a978  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002a97f  call    DfscApplyDeviceAcl
0x14002a984  mov     ebx, eax
0x14002a986  test    eax, eax
0x14002a988  jns     short loc_14002A9A2
0x14002a98a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; DeviceObject
0x14002a991  call    cs:__imp_IoDeleteDevice
0x14002a998  nop     dword ptr [rax+rax+00h]
0x14002a99d  jmp     loc_14002AAE9
0x14002a9a2  lea     rdx, aDfs; "\\Dfs"
0x14002a9a9  lea     rcx, [rsp+88h+SymbolicLinkName]; DestinationString
0x14002a9ae  call    cs:__imp_RtlInitUnicodeString
0x14002a9b5  nop     dword ptr [rax+rax+00h]
0x14002a9ba  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x14002a9bf  call    cs:__imp_IoDeleteSymbolicLink
0x14002a9c6  nop     dword ptr [rax+rax+00h]
0x14002a9cb  lea     rdx, [rsp+88h+DestinationString]; DeviceName
0x14002a9d0  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x14002a9d5  call    cs:__imp_IoCreateSymbolicLink
0x14002a9dc  nop     dword ptr [rax+rax+00h]
0x14002a9e1  mov     ebx, eax
0x14002a9e3  test    eax, eax
0x14002a9e5  js      short loc_14002A98A
0x14002a9e7  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rdi
0x14002a9ee  lea     rax, DriverUnload
0x14002a9f5  mov     [rdi+68h], rax
0x14002a9f9  lea     rax, DfscCreate
0x14002aa00  mov     [rdi+70h], rax
0x14002aa04  lea     rax, DfscCleanup
0x14002aa0b  mov     [rdi+100h], rax
0x14002aa12  lea     rax, DfscClose
0x14002aa19  mov     [rdi+80h], rax
0x14002aa20  lea     rax, DfscSystemControl
0x14002aa27  mov     [rdi+128h], rax
0x14002aa2e  lea     rax, DfscFileSystemControl
0x14002aa35  mov     [rdi+0D8h], rax
0x14002aa3c  mov     [rdi+50h], rbp
0x14002aa40  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002aa47  mov     byte ptr [rax+4Ch], 1
0x14002aa4b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002aa52  btr     dword ptr [rax+30h], 7
0x14002aa57  lea     rax, WPP_ThisDir_CTLGUID_MupLog
0x14002aa5e  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14002aa65  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14002aa6c  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x14002aa73  lea     rax, WPP_ThisDir_CTLGUID_RFSMon
0x14002aa7a  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14002aa81  mov     qword ptr cs:WPP_MAIN_CB.Type, rbp
0x14002aa88  mov     cs:WPP_MAIN_CB.CurrentIrp, rbp
0x14002aa8f  mov     cs:WPP_MAIN_CB.Timer, 1
0x14002aa9a  mov     cs:WPP_MAIN_CB.DeviceExtension, rbp
0x14002aaa1  mov     qword ptr cs:WPP_MAIN_CB.Queue, rbp
0x14002aaa8  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rbp
0x14002aaaf  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, 1
0x14002aaba  call    WppLoadTracingSupport
0x14002aabf  mov     cs:WPP_MAIN_CB.CurrentIrp, rbp
0x14002aac6  call    WppInitKm
0x14002aacb  mov     rcx, rsi; SourceString
0x14002aace  call    DfscInitVariables
0x14002aad3  mov     ebx, eax
0x14002aad5  test    eax, eax
0x14002aad7  js      short loc_14002AAE4
0x14002aad9  call    DfscInitializeTimer
0x14002aade  mov     ebx, eax
0x14002aae0  test    eax, eax
0x14002aae2  jns     short loc_14002AAE9
0x14002aae4  call    DfscInitUnwind
0x14002aae9  mov     eax, ebx
0x14002aaeb  add     rsp, 68h
0x14002aaef  pop     rdi
0x14002aaf0  pop     rsi
0x14002aaf1  pop     rbp
0x14002aaf2  pop     rbx
0x14002aaf3  retn
```
