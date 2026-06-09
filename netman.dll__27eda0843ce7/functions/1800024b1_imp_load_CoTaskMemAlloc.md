# __imp_load_CoTaskMemAlloc

- ea: `0x1800024b1`
- end: `0x1800024bd`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002432`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800024b1`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800024b1  lea     rax, __imp_CoTaskMemAlloc
0x1800024b8  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
