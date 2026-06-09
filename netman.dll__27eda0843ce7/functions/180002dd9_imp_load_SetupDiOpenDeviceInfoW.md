# __imp_load_SetupDiOpenDeviceInfoW

- ea: `0x180002dd9`
- end: `0x180002de5`
- name: `__imp_load_SetupDiOpenDeviceInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180002dd9`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInfoW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002dd9  lea     rax, __imp_SetupDiOpenDeviceInfoW
0x180002de0  jmp     __tailMerge_setupapi_dll
```
