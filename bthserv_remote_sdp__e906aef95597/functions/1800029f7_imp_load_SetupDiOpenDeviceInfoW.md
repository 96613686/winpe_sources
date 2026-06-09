# __imp_load_SetupDiOpenDeviceInfoW

- ea: `0x1800029f7`
- end: `0x180002a03`
- name: `__imp_load_SetupDiOpenDeviceInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002966`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x1800029f7`

## pseudocode

```c
__int64 load_SetupDiOpenDeviceInfoW()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll();
}

```

## disassembly

```asm
0x1800029f7  lea     rax, __imp_SetupDiOpenDeviceInfoW
0x1800029fe  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
```
