# __imp_load_CoTaskMemAlloc

- ea: `0x1800035a7`
- end: `0x1800035b3`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003029`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035a7`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800035a7  lea     rax, __imp_CoTaskMemAlloc
0x1800035ae  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
