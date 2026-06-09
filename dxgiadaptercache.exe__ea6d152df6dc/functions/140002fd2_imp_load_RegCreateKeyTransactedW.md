# __imp_load_RegCreateKeyTransactedW

- ea: `0x140002fd2`
- end: `0x140002fde`
- name: `__imp_load_RegCreateKeyTransactedW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140002f53`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140002fd2`

## pseudocode

```c
__int64 load_RegCreateKeyTransactedW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x140002fd2  lea     rax, __imp_RegCreateKeyTransactedW
0x140002fd9  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
