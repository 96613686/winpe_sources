# __imp_load_GetNetworkAccountBindingDeviceInterfacePath

- ea: `0x180009011`
- end: `0x18000901d`
- name: `__imp_load_GetNetworkAccountBindingDeviceInterfacePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f80`

## import_xrefs

- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x180009011`

## pseudocode

```c
__int64 load_GetNetworkAccountBindingDeviceInterfacePath()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180009011  lea     rax, __imp_GetNetworkAccountBindingDeviceInterfacePath
0x180009018  jmp     __tailMerge_mobilenetworking_dll
```
