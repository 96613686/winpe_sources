# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x180002202`
- end: `0x18000220e`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800020bd`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180002202`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002202  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x180002209  jmp     __tailMerge_setupapi_dll
```
