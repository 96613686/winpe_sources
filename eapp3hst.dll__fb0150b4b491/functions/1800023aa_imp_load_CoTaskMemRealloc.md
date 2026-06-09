# __imp_load_CoTaskMemRealloc

- ea: `0x1800023aa`
- end: `0x1800023b6`
- name: `__imp_load_CoTaskMemRealloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002142`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800023aa`

## pseudocode

```c
__int64 load_CoTaskMemRealloc()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800023aa  lea     rax, __imp_CoTaskMemRealloc
0x1800023b1  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
