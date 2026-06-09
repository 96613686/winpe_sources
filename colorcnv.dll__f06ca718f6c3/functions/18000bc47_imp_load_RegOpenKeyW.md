# __imp_load_RegOpenKeyW

- ea: `0x18000bc47`
- end: `0x18000bc53`
- name: `__imp_load_RegOpenKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b4c2`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000bc47`

## pseudocode

```c
__int64 load_RegOpenKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000bc47  lea     rax, __imp_RegOpenKeyW
0x18000bc4e  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
