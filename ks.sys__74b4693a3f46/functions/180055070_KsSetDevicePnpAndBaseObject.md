# KsSetDevicePnpAndBaseObject

- ea: `0x180055070`
- end: `0x1800551f2`
- name: `KsSetDevicePnpAndBaseObject`
- size: `386`
- prototype: `void __stdcall(KSDEVICE_HEADER Header, PDEVICE_OBJECT PnpDeviceObject, PDEVICE_OBJECT BaseObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039de0`
- `0x180054134`

## callees

- `0x180055070`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800551da`
- `ntoskrnl!ObfDereferenceObject` at `0x1800551da`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005517f`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005517f`
- `ntoskrnl!IofCallDriver` at `0x18005510f`
- `ntoskrnl!IofCallDriver` at `0x18005510f`
- `ntoskrnl!ZwClose` at `0x1800551cb`
- `ntoskrnl!ZwClose` at `0x1800551cb`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800551ba`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800551ba`
- `ntoskrnl!IoFreeIrp` at `0x180055160`
- `ntoskrnl!IoFreeIrp` at `0x180055160`
- `ntoskrnl!IoAllocateIrp` at `0x1800550a1`
- `ntoskrnl!IoAllocateIrp` at `0x1800550a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180055131`
- `ntoskrnl!KeWaitForSingleObject` at `0x180055131`
- `ntoskrnl!KeInitializeEvent` at `0x1800550fd`
- `ntoskrnl!KeInitializeEvent` at `0x1800550fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180055151`
- `ntoskrnl!ExFreePoolWithTag` at `0x180055151`

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
    v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&SignalCompletion;
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
0x180055070  mov     [rsp+arg_8], rbx
0x180055075  push    rdi
0x180055076  sub     rsp, 50h
0x18005507a  mov     rdi, rdx
0x18005507d  mov     [rcx+78h], rdx
0x180055081  xor     eax, eax
0x180055083  mov     [rcx+160h], r8
0x18005508a  xorps   xmm0, xmm0
0x18005508d  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x180055092  xor     edx, edx; ChargeQuota
0x180055094  mov     [rsp+58h+DeviceRegKey], rax
0x180055099  mov     cl, [rdi+4Ch]; StackSize
0x18005509c  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1800550a1  call    cs:__imp_IoAllocateIrp
0x1800550a8  nop     dword ptr [rax+rax+00h]
0x1800550ad  mov     rbx, rax
0x1800550b0  test    rax, rax
0x1800550b3  jz      loc_1800551E6
0x1800550b9  mov     rcx, [rax+0B8h]
0x1800550c0  xor     r8d, r8d; State
0x1800550c3  xor     edx, edx; Type
0x1800550c5  mov     word ptr [rcx-48h], 71Bh
0x1800550cb  mov     dword ptr [rcx-40h], 4
0x1800550d2  mov     rcx, [rax+0B8h]
0x1800550d9  mov     dword ptr [rax+30h], 0C00000BBh
0x1800550e0  lea     rax, SignalCompletion
0x1800550e7  mov     [rcx-10h], rax
0x1800550eb  lea     rax, [rsp+58h+Event]
0x1800550f0  mov     [rcx-8], rax
0x1800550f4  mov     byte ptr [rcx-45h], 0E0h
0x1800550f8  lea     rcx, [rsp+58h+Event]; Event
0x1800550fd  call    cs:__imp_KeInitializeEvent
0x180055104  nop     dword ptr [rax+rax+00h]
0x180055109  mov     rdx, rbx; Irp
0x18005510c  mov     rcx, rdi; DeviceObject
0x18005510f  call    cs:__imp_IofCallDriver
0x180055116  nop     dword ptr [rax+rax+00h]
0x18005511b  xor     r9d, r9d; Alertable
0x18005511e  mov     [rsp+58h+Timeout], 0; Timeout
0x180055127  xor     r8d, r8d; WaitMode
0x18005512a  lea     rcx, [rsp+58h+Event]; Object
0x18005512f  xor     edx, edx; WaitReason
0x180055131  call    cs:__imp_KeWaitForSingleObject
0x180055138  nop     dword ptr [rax+rax+00h]
0x18005513d  cmp     dword ptr [rbx+30h], 0
0x180055141  jl      loc_1800551E6
0x180055147  mov     rcx, [rbx+38h]; P
0x18005514b  xor     edx, edx; Tag
0x18005514d  mov     rdi, [rcx+8]
0x180055151  call    cs:__imp_ExFreePoolWithTag
0x180055158  nop     dword ptr [rax+rax+00h]
0x18005515d  mov     rcx, rbx; Irp
0x180055160  call    cs:__imp_IoFreeIrp
0x180055167  nop     dword ptr [rax+rax+00h]
0x18005516c  lea     r9, [rsp+58h+DeviceRegKey]; DeviceRegKey
0x180055171  mov     edx, 2; DevInstKeyType
0x180055176  mov     r8d, 20006h; DesiredAccess
0x18005517c  mov     rcx, rdi; DeviceObject
0x18005517f  call    cs:__imp_IoOpenDeviceRegistryKey
0x180055186  nop     dword ptr [rax+rax+00h]
0x18005518b  test    eax, eax
0x18005518d  js      short loc_1800551D7
0x18005518f  mov     rdx, [rsp+58h+DeviceRegKey]; Path
0x180055194  lea     rax, a1; "1"
0x18005519b  mov     [rsp+58h+ValueLength], 4; ValueLength
0x1800551a3  lea     r8, ValueName; "KS"
0x1800551aa  mov     r9d, 1; ValueType
0x1800551b0  mov     [rsp+58h+Timeout], rax; ValueData
0x1800551b5  mov     ecx, 40000000h; RelativeTo
0x1800551ba  call    cs:__imp_RtlWriteRegistryValue
0x1800551c1  nop     dword ptr [rax+rax+00h]
0x1800551c6  mov     rcx, [rsp+58h+DeviceRegKey]; Handle
0x1800551cb  call    cs:__imp_ZwClose
0x1800551d2  nop     dword ptr [rax+rax+00h]
0x1800551d7  mov     rcx, rdi; Object
0x1800551da  call    cs:__imp_ObfDereferenceObject
0x1800551e1  nop     dword ptr [rax+rax+00h]
0x1800551e6  mov     rbx, [rsp+58h+arg_8]
0x1800551eb  add     rsp, 50h
0x1800551ef  pop     rdi
0x1800551f0  retn
```
