# KsSetDevicePnpAndBaseObject

- ea: `0x180055210`
- end: `0x180055392`
- name: `KsSetDevicePnpAndBaseObject`
- size: `386`
- prototype: `void __stdcall(KSDEVICE_HEADER Header, PDEVICE_OBJECT PnpDeviceObject, PDEVICE_OBJECT BaseObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039e30`
- `0x1800542d4`

## callees

- `0x180055210`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18005537a`
- `ntoskrnl!ObfDereferenceObject` at `0x18005537a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005531f`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005531f`
- `ntoskrnl!IofCallDriver` at `0x1800552af`
- `ntoskrnl!IofCallDriver` at `0x1800552af`
- `ntoskrnl!ZwClose` at `0x18005536b`
- `ntoskrnl!ZwClose` at `0x18005536b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x18005535a`
- `ntoskrnl!RtlWriteRegistryValue` at `0x18005535a`
- `ntoskrnl!IoFreeIrp` at `0x180055300`
- `ntoskrnl!IoFreeIrp` at `0x180055300`
- `ntoskrnl!IoAllocateIrp` at `0x180055241`
- `ntoskrnl!IoAllocateIrp` at `0x180055241`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800552d1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800552d1`
- `ntoskrnl!KeInitializeEvent` at `0x18005529d`
- `ntoskrnl!KeInitializeEvent` at `0x18005529d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800552f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800552f1`

## pseudocode

```c
void __stdcall KsSetDevicePnpAndBaseObject(
        KSDEVICE_HEADER Header,
        PDEVICE_OBJECT PnpDeviceObject,
        PDEVICE_OBJECT BaseObject)
{
  CCHAR StackSize; // cl
  PIRP Irp; // rax
  IRP *v6; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v8; // rcx
  _QWORD *Information; // rcx
  struct _DEVICE_OBJECT *v10; // rdi
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  void *DeviceRegKey; // [rsp+60h] [rbp+8h] BYREF

  *((_QWORD *)Header + 15) = PnpDeviceObject;
  *((_QWORD *)Header + 44) = BaseObject;
  DeviceRegKey = 0;
  StackSize = PnpDeviceObject->StackSize;
  memset(&Event, 0, sizeof(Event));
  Irp = IoAllocateIrp(StackSize, 0);
  v6 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 1819;
    CurrentStackLocation[-1].Parameters.Read.Length = 4;
    v8 = Irp->Tail.Overlay.CurrentStackLocation;
    Irp->IoStatus.Status = -1073741637;
    v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SignalCompletion;
    v8[-1].Context = &Event;
    v8[-1].Control = -32;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    IofCallDriver(PnpDeviceObject, v6);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( v6->IoStatus.Status >= 0 )
    {
      Information = (_QWORD *)v6->IoStatus.Information;
      v10 = (struct _DEVICE_OBJECT *)Information[1];
      ExFreePoolWithTag(Information, 0);
      IoFreeIrp(v6);
      if ( IoOpenDeviceRegistryKey(v10, 2u, 0x20006u, &DeviceRegKey) >= 0 )
      {
        RtlWriteRegistryValue(0x40000000u, (PCWSTR)DeviceRegKey, ValueName, 1u, a1, 4u);
        ZwClose(DeviceRegKey);
      }
      ObfDereferenceObject(v10);
    }
  }
}

```

## disassembly

```asm
0x180055210  mov     [rsp+arg_8], rbx
0x180055215  push    rdi
0x180055216  sub     rsp, 50h
0x18005521a  mov     rdi, rdx
0x18005521d  mov     [rcx+78h], rdx
0x180055221  xor     eax, eax
0x180055223  mov     [rcx+160h], r8
0x18005522a  xorps   xmm0, xmm0
0x18005522d  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x180055232  xor     edx, edx; ChargeQuota
0x180055234  mov     [rsp+58h+DeviceRegKey], rax
0x180055239  mov     cl, [rdi+4Ch]; StackSize
0x18005523c  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x180055241  call    cs:__imp_IoAllocateIrp
0x180055248  nop     dword ptr [rax+rax+00h]
0x18005524d  mov     rbx, rax
0x180055250  test    rax, rax
0x180055253  jz      loc_180055386
0x180055259  mov     rcx, [rax+0B8h]
0x180055260  xor     r8d, r8d; State
0x180055263  xor     edx, edx; Type
0x180055265  mov     word ptr [rcx-48h], 71Bh
0x18005526b  mov     dword ptr [rcx-40h], 4
0x180055272  mov     rcx, [rax+0B8h]
0x180055279  mov     dword ptr [rax+30h], 0C00000BBh
0x180055280  lea     rax, SignalCompletion
0x180055287  mov     [rcx-10h], rax
0x18005528b  lea     rax, [rsp+58h+Event]
0x180055290  mov     [rcx-8], rax
0x180055294  mov     byte ptr [rcx-45h], 0E0h
0x180055298  lea     rcx, [rsp+58h+Event]; Event
0x18005529d  call    cs:__imp_KeInitializeEvent
0x1800552a4  nop     dword ptr [rax+rax+00h]
0x1800552a9  mov     rdx, rbx; Irp
0x1800552ac  mov     rcx, rdi; DeviceObject
0x1800552af  call    cs:__imp_IofCallDriver
0x1800552b6  nop     dword ptr [rax+rax+00h]
0x1800552bb  xor     r9d, r9d; Alertable
0x1800552be  mov     [rsp+58h+Timeout], 0; Timeout
0x1800552c7  xor     r8d, r8d; WaitMode
0x1800552ca  lea     rcx, [rsp+58h+Event]; Object
0x1800552cf  xor     edx, edx; WaitReason
0x1800552d1  call    cs:__imp_KeWaitForSingleObject
0x1800552d8  nop     dword ptr [rax+rax+00h]
0x1800552dd  cmp     dword ptr [rbx+30h], 0
0x1800552e1  jl      loc_180055386
0x1800552e7  mov     rcx, [rbx+38h]; P
0x1800552eb  xor     edx, edx; Tag
0x1800552ed  mov     rdi, [rcx+8]
0x1800552f1  call    cs:__imp_ExFreePoolWithTag
0x1800552f8  nop     dword ptr [rax+rax+00h]
0x1800552fd  mov     rcx, rbx; Irp
0x180055300  call    cs:__imp_IoFreeIrp
0x180055307  nop     dword ptr [rax+rax+00h]
0x18005530c  lea     r9, [rsp+58h+DeviceRegKey]; DeviceRegKey
0x180055311  mov     edx, 2; DevInstKeyType
0x180055316  mov     r8d, 20006h; DesiredAccess
0x18005531c  mov     rcx, rdi; DeviceObject
0x18005531f  call    cs:__imp_IoOpenDeviceRegistryKey
0x180055326  nop     dword ptr [rax+rax+00h]
0x18005532b  test    eax, eax
0x18005532d  js      short loc_180055377
0x18005532f  mov     rdx, [rsp+58h+DeviceRegKey]; Path
0x180055334  lea     rax, a1; "1"
0x18005533b  mov     [rsp+58h+ValueLength], 4; ValueLength
0x180055343  lea     r8, ValueName; "KS"
0x18005534a  mov     r9d, 1; ValueType
0x180055350  mov     [rsp+58h+Timeout], rax; ValueData
0x180055355  mov     ecx, 40000000h; RelativeTo
0x18005535a  call    cs:__imp_RtlWriteRegistryValue
0x180055361  nop     dword ptr [rax+rax+00h]
0x180055366  mov     rcx, [rsp+58h+DeviceRegKey]; Handle
0x18005536b  call    cs:__imp_ZwClose
0x180055372  nop     dword ptr [rax+rax+00h]
0x180055377  mov     rcx, rdi; Object
0x18005537a  call    cs:__imp_ObfDereferenceObject
0x180055381  nop     dword ptr [rax+rax+00h]
0x180055386  mov     rbx, [rsp+58h+arg_8]
0x18005538b  add     rsp, 50h
0x18005538f  pop     rdi
0x180055390  retn
```
