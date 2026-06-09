# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x1800029e5`
- end: `0x1800029f1`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002966`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x1800029e5`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll();
}

```

## disassembly

```asm
0x1800029e5  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x1800029ec  jmp     __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
```
