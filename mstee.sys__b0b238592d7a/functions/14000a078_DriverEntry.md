# DriverEntry

- ea: `0x14000a078`
- end: `0x14000a095`
- name: `DriverEntry`
- size: `29`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000a010`

## import_xrefs

- `ks!KsInitializeDriver` at `0x14000a083`
- `ks!KsInitializeDriver` at `0x14000a083`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  return KsInitializeDriver(DriverObject, RegistryPath, &DeviceDescriptor);
}

```

## disassembly

```asm
0x14000a078  sub     rsp, 28h
0x14000a07c  lea     r8, DeviceDescriptor; Descriptor
0x14000a083  call    cs:__imp_KsInitializeDriver
0x14000a08a  nop     dword ptr [rax+rax+00h]
0x14000a08f  add     rsp, 28h
0x14000a093  retn
```
