# KsCreateDevice_wrapper

- ea: `0x18006f6a0`
- end: `0x18006f713`
- name: `KsCreateDevice_wrapper`
- size: `115`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT PhysicalDeviceObject, const KSDEVICE_DESCRIPTOR *Descriptor, ULONG ExtensionSize, PKSDEVICE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019c60`
- `0x180055200`
- `0x18006f6a0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006f6bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006f6bf`

## string_xrefs

- `0x18006f6d6`: `KsCreateDevice should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
NTSTATUS __fastcall KsCreateDevice_wrapper(
        PDRIVER_OBJECT DriverObject,
        PDEVICE_OBJECT PhysicalDeviceObject,
        const KSDEVICE_DESCRIPTOR *Descriptor,
        ULONG ExtensionSize,
        PKSDEVICE *Device)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsCreateDevice should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsCreateDevice(DriverObject, PhysicalDeviceObject, Descriptor, ExtensionSize, Device);
}

```

## disassembly

```asm
0x18006f6a0  push    rbx
0x18006f6a2  push    rbp
0x18006f6a3  push    rsi
0x18006f6a4  push    rdi
0x18006f6a5  sub     rsp, 38h
0x18006f6a9  mov     eax, cs:KsXdvExtLevel
0x18006f6af  mov     ebx, r9d
0x18006f6b2  mov     rdi, r8
0x18006f6b5  mov     rsi, rdx
0x18006f6b8  mov     rbp, rcx
0x18006f6bb  test    al, 8
0x18006f6bd  jz      short loc_18006F6EB
0x18006f6bf  call    cs:__imp_KeGetCurrentIrql
0x18006f6c6  nop     dword ptr [rax+rax+00h]
0x18006f6cb  test    al, al
0x18006f6cd  jz      short loc_18006F6EB
0x18006f6cf  mov     rax, cs:KsVerifierUtilTable
0x18006f6d6  lea     rcx, aKscreatedevice; "KsCreateDevice should only be called at"...
0x18006f6dd  mov     edx, 81009h
0x18006f6e2  mov     rax, [rax+60h]
0x18006f6e6  call    _guard_dispatch_icall
0x18006f6eb  mov     rax, [rsp+58h+arg_20]
0x18006f6f3  mov     r9d, ebx; ExtensionSize
0x18006f6f6  mov     r8, rdi; Descriptor
0x18006f6f9  mov     [rsp+58h+Device], rax; Device
0x18006f6fe  mov     rdx, rsi; PhysicalDeviceObject
0x18006f701  mov     rcx, rbp; DriverObject
0x18006f704  call    KsCreateDevice
0x18006f709  add     rsp, 38h
0x18006f70d  pop     rdi
0x18006f70e  pop     rsi
0x18006f70f  pop     rbp
0x18006f710  pop     rbx
0x18006f711  retn
```
