# __imp_load_RegisterDataSharingServiceExtensions

- ea: `0x180003121`
- end: `0x18000312d`
- name: `__imp_load_RegisterDataSharingServiceExtensions`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800030a2`

## import_xrefs

- `ext-ms-win-appmodel-datasharingservice-extensions-l1-1-0!RegisterDataSharingServiceExtensions` at `0x180003121`

## pseudocode

```c
__int64 load_RegisterDataSharingServiceExtensions()
{
  return _tailMerge_ext_ms_win_appmodel_datasharingservice_extensions_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003121  lea     rax, __imp_RegisterDataSharingServiceExtensions
0x180003128  jmp     __tailMerge_ext_ms_win_appmodel_datasharingservice_extensions_l1_1_0_dll
```
