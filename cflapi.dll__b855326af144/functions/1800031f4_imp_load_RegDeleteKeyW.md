# __imp_load_RegDeleteKeyW

- ea: `0x1800031f4`
- end: `0x180003200`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003175`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800031f4`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800031f4  lea     rax, __imp_RegDeleteKeyW
0x1800031fb  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
