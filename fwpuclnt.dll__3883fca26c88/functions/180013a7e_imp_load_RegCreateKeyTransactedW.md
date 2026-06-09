# __imp_load_RegCreateKeyTransactedW

- ea: `0x180013a7e`
- end: `0x180013a8a`
- name: `__imp_load_RegCreateKeyTransactedW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800139ff`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180013a7e`

## pseudocode

```c
__int64 load_RegCreateKeyTransactedW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x180013a7e  lea     rax, __imp_RegCreateKeyTransactedW
0x180013a85  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
