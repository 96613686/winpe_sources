# __imp_load_SetupDiOpenDeviceInterfaceW

- ea: `0x1800175a9`
- end: `0x1800175b5`
- name: `__imp_load_SetupDiOpenDeviceInterfaceW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180017506`

## import_xrefs

- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1800175a9`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInterfaceW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800175a9  lea     rax, __imp_SetupDiOpenDeviceInterfaceW
0x1800175b0  jmp     __tailMerge_setupapi_dll
```
