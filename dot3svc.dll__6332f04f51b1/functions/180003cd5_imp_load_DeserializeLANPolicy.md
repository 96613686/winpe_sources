# __imp_load_DeserializeLANPolicy

- ea: `0x180003cd5`
- end: `0x180003ce1`
- name: `__imp_load_DeserializeLANPolicy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003c32`

## import_xrefs

- `ext-ms-win-dot3-grouppolicy-l1-1-0!DeserializeLANPolicy` at `0x180003cd5`

## pseudocode

```c
__int64 load_DeserializeLANPolicy()
{
  return _tailMerge_ext_ms_win_dot3_grouppolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003cd5  lea     rax, __imp_DeserializeLANPolicy
0x180003cdc  jmp     __tailMerge_ext_ms_win_dot3_grouppolicy_l1_1_0_dll
```
