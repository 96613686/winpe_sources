# __imp_load_SetupDiSetDeviceInstallParamsW

- ea: `0x180002dc7`
- end: `0x180002dd3`
- name: `__imp_load_SetupDiSetDeviceInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180002dc7`

## pseudocode

```c
__int64 load_SetupDiSetDeviceInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002dc7  lea     rax, __imp_SetupDiSetDeviceInstallParamsW
0x180002dce  jmp     __tailMerge_setupapi_dll
```
