# __imp_load_RegDeleteKeyW

- ea: `0x140002c6c`
- end: `0x140002c78`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400029b6`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140002c6c`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x140002c6c  lea     rax, __imp_RegDeleteKeyW
0x140002c73  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
