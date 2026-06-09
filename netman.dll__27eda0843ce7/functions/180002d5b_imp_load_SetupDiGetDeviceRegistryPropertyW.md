# __imp_load_SetupDiGetDeviceRegistryPropertyW

- ea: `0x180002d5b`
- end: `0x180002d67`
- name: `__imp_load_SetupDiGetDeviceRegistryPropertyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180002d5b`

## pseudocode

```c
__int64 load_SetupDiGetDeviceRegistryPropertyW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002d5b  lea     rax, __imp_SetupDiGetDeviceRegistryPropertyW
0x180002d62  jmp     __tailMerge_setupapi_dll
```
