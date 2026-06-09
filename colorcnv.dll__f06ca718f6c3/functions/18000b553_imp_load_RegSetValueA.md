# __imp_load_RegSetValueA

- ea: `0x18000b553`
- end: `0x18000b55f`
- name: `__imp_load_RegSetValueA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b4c2`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000b553`

## pseudocode

```c
__int64 load_RegSetValueA()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000b553  lea     rax, __imp_RegSetValueA
0x18000b55a  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
