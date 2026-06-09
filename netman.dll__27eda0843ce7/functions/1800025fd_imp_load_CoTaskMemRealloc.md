# __imp_load_CoTaskMemRealloc

- ea: `0x1800025fd`
- end: `0x180002609`
- name: `__imp_load_CoTaskMemRealloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002432`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800025fd`

## pseudocode

```c
__int64 load_CoTaskMemRealloc()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800025fd  lea     rax, __imp_CoTaskMemRealloc
0x180002604  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
