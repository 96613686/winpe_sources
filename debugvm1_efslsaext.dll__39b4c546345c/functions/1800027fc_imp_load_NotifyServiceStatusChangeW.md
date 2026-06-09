# __imp_load_NotifyServiceStatusChangeW

- ea: `0x1800027fc`
- end: `0x180002808`
- name: `__imp_load_NotifyServiceStatusChangeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000276b`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800027fc`

## pseudocode

```c
__int64 load_NotifyServiceStatusChangeW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800027fc  lea     rax, __imp_NotifyServiceStatusChangeW
0x180002803  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
