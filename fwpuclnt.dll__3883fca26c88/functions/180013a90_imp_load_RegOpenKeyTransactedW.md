# __imp_load_RegOpenKeyTransactedW

- ea: `0x180013a90`
- end: `0x180013a9c`
- name: `__imp_load_RegOpenKeyTransactedW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800139ff`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013a90`

## pseudocode

```c
__int64 load_RegOpenKeyTransactedW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180013a90  lea     rax, __imp_RegOpenKeyTransactedW
0x180013a97  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
