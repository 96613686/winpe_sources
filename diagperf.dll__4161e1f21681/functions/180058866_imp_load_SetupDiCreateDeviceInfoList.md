# __imp_load_SetupDiCreateDeviceInfoList

- ea: `0x180058866`
- end: `0x180058872`
- name: `__imp_load_SetupDiCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800587e7`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180058866`

## pseudocode

```c
__int64 load_SetupDiCreateDeviceInfoList()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180058866  lea     rax, __imp_SetupDiCreateDeviceInfoList
0x18005886d  jmp     __tailMerge_setupapi_dll
```
