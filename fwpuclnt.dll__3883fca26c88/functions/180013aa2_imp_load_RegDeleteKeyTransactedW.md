# __imp_load_RegDeleteKeyTransactedW

- ea: `0x180013aa2`
- end: `0x180013aae`
- name: `__imp_load_RegDeleteKeyTransactedW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800139ff`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x180013aa2`

## pseudocode

```c
__int64 load_RegDeleteKeyTransactedW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180013aa2  lea     rax, __imp_RegDeleteKeyTransactedW
0x180013aa9  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
