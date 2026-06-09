# PmUnload(_DRIVER_OBJECT *)

- ea: `0x14001c880`
- end: `0x14001c99f`
- name: `?PmUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `287`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400292a4`

## callees

- `0x14000c114`
- `0x14001c880`
- `0x14001c9a8`
- `0x140020518`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c917`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c95a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c917`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c95a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8d8`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001c8b7`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001c8b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c92f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c92f`
- `ntoskrnl!IoDeleteDevice` at `0x14001c96d`
- `ntoskrnl!IoDeleteDevice` at `0x14001c96d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c940`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c940`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8fd`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8fd`

## pseudocode

```c
void __fastcall PmUnload(struct _DRIVER_OBJECT *a1)
{
  char *DeviceExtension; // rbx
  void *v2; // rcx
  struct _CONTROL_EXTENSION *v3; // rcx
  struct _VOLUME_MANAGER **i; // rdi
  void *v5; // rcx
  void *v6; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( PmControlObject )
  {
    DeviceExtension = (char *)PmControlObject->DeviceExtension;
    v2 = (void *)*((_QWORD *)DeviceExtension + 51);
    if ( v2 )
      IoUnregisterPlugPlayNotification(v2);
    KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
    for ( i = (struct _VOLUME_MANAGER **)(DeviceExtension + 72);
          *i != (struct _VOLUME_MANAGER *)i;
          PmVolumeManagerRemoval(v3, *i) )
    {
      ;
    }
    KeReleaseMutex((PRKMUTEX)(DeviceExtension + 16), 0);
    v5 = (void *)*((_QWORD *)DeviceExtension + 53);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\PartmgrControl");
    IoDeleteSymbolicLink(&DestinationString);
    v6 = (void *)*((_QWORD *)DeviceExtension + 24);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    IoDeleteDevice(PmControlObject);
    PmControlObject = 0;
  }
  McGenEventUnregister_EtwUnregister(a1);
  TraceLoggingUnregister_EtwUnregister();
}

```

## disassembly

```asm
0x14001c880  mov     [rsp+arg_0], rbx
0x14001c885  mov     [rsp+arg_8], rsi
0x14001c88a  push    rdi
0x14001c88b  sub     rsp, 40h
0x14001c88f  mov     rbx, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14001c896  xorps   xmm0, xmm0
0x14001c899  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001c89e  test    rbx, rbx
0x14001c8a1  jz      loc_14001C984
0x14001c8a7  mov     rbx, [rbx+40h]
0x14001c8ab  mov     rcx, [rbx+198h]; NotificationEntry
0x14001c8b2  test    rcx, rcx
0x14001c8b5  jz      short loc_14001C8C3
0x14001c8b7  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14001c8be  nop     dword ptr [rax+rax+00h]
0x14001c8c3  xor     r9d, r9d; Alertable
0x14001c8c6  mov     [rsp+48h+Timeout], 0; Timeout
0x14001c8cf  xor     r8d, r8d; WaitMode
0x14001c8d2  lea     rcx, [rbx+10h]; Object
0x14001c8d6  xor     edx, edx; WaitReason
0x14001c8d8  call    cs:__imp_KeWaitForSingleObject
0x14001c8df  nop     dword ptr [rax+rax+00h]
0x14001c8e4  lea     rdi, [rbx+48h]
0x14001c8e8  mov     rdx, [rdi]; struct _VOLUME_MANAGER *
0x14001c8eb  cmp     rdx, rdi
0x14001c8ee  jz      short loc_14001C8F7
0x14001c8f0  call    ?PmVolumeManagerRemoval@@YAJPEAU_CONTROL_EXTENSION@@PEAU_VOLUME_MANAGER@@@Z; PmVolumeManagerRemoval(_CONTROL_EXTENSION *,_VOLUME_MANAGER *)
0x14001c8f5  jmp     short loc_14001C8E8
0x14001c8f7  xor     edx, edx; Wait
0x14001c8f9  lea     rcx, [rbx+10h]; Mutex
0x14001c8fd  call    cs:__imp_KeReleaseMutex
0x14001c904  nop     dword ptr [rax+rax+00h]
0x14001c909  mov     rcx, [rbx+1A8h]; P
0x14001c910  test    rcx, rcx
0x14001c913  jz      short loc_14001C923
0x14001c915  xor     edx, edx; Tag
0x14001c917  call    cs:__imp_ExFreePoolWithTag
0x14001c91e  nop     dword ptr [rax+rax+00h]
0x14001c923  lea     rdx, aDosdevicesPart; "\\DosDevices\\PartmgrControl"
0x14001c92a  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001c92f  call    cs:__imp_RtlInitUnicodeString
0x14001c936  nop     dword ptr [rax+rax+00h]
0x14001c93b  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x14001c940  call    cs:__imp_IoDeleteSymbolicLink
0x14001c947  nop     dword ptr [rax+rax+00h]
0x14001c94c  mov     rcx, [rbx+0C0h]; P
0x14001c953  test    rcx, rcx
0x14001c956  jz      short loc_14001C966
0x14001c958  xor     edx, edx; Tag
0x14001c95a  call    cs:__imp_ExFreePoolWithTag
0x14001c961  nop     dword ptr [rax+rax+00h]
0x14001c966  mov     rcx, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; DeviceObject
0x14001c96d  call    cs:__imp_IoDeleteDevice
0x14001c974  nop     dword ptr [rax+rax+00h]
0x14001c979  mov     cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA, 0; _DEVICE_OBJECT * PmControlObject
0x14001c984  call    McGenEventUnregister_EtwUnregister
0x14001c989  call    TraceLoggingUnregister_EtwUnregister
0x14001c98e  mov     rbx, [rsp+48h+arg_0]
0x14001c993  mov     rsi, [rsp+48h+arg_8]
0x14001c998  add     rsp, 40h
0x14001c99c  pop     rdi
0x14001c99d  retn
```
