# __imp_load_RegDeleteKeyW

- ea: `0x1800151c1`
- end: `0x1800151cd`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180015142`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800151c1`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800151c1  lea     rax, __imp_RegDeleteKeyW
0x1800151c8  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
