# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x180002deb`
- end: `0x180002df7`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c94`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180002deb`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180002deb  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x180002df2  jmp     __tailMerge_setupapi_dll
```
