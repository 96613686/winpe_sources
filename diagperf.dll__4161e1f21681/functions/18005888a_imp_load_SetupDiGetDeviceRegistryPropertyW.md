# __imp_load_SetupDiGetDeviceRegistryPropertyW

- ea: `0x18005888a`
- end: `0x180058896`
- name: `__imp_load_SetupDiGetDeviceRegistryPropertyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800587e7`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18005888a`

## pseudocode

```c
__int64 load_SetupDiGetDeviceRegistryPropertyW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18005888a  lea     rax, __imp_SetupDiGetDeviceRegistryPropertyW
0x180058891  jmp     __tailMerge_setupapi_dll
```
