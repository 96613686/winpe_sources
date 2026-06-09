# __imp_load_RegDeleteKeyW

- ea: `0x180009bf9`
- end: `0x180009c05`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180009b56`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180009bf9`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180009bf9  lea     rax, __imp_RegDeleteKeyW
0x180009c00  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
