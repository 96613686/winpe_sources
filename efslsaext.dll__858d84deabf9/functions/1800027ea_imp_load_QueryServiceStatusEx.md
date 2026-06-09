# __imp_load_QueryServiceStatusEx

- ea: `0x1800027ea`
- end: `0x1800027f6`
- name: `__imp_load_QueryServiceStatusEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000276b`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800027ea`

## pseudocode

```c
__int64 load_QueryServiceStatusEx()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800027ea  lea     rax, __imp_QueryServiceStatusEx
0x1800027f1  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
