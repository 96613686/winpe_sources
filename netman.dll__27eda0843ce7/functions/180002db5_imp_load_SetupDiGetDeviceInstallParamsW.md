# __imp_load_SetupDiGetDeviceInstallParamsW

- ea: `0x180002db5`
- end: `0x180002dc1`
- name: `__imp_load_SetupDiGetDeviceInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180002db5`

## pseudocode

```c
__int64 load_SetupDiGetDeviceInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002db5  lea     rax, __imp_SetupDiGetDeviceInstallParamsW
0x180002dbc  jmp     __tailMerge_setupapi_dll
```
