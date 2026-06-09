# __imp_load_NetworkIsolationDeleteAppContainer

- ea: `0x180012411`
- end: `0x18001241d`
- name: `__imp_load_NetworkIsolationDeleteAppContainer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012380`

## import_xrefs

- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x180012411`

## pseudocode

```c
__int64 load_NetworkIsolationDeleteAppContainer()
{
  return _tailMerge_ext_ms_win_net_isoext_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012411  lea     rax, __imp_NetworkIsolationDeleteAppContainer
0x180012418  jmp     __tailMerge_ext_ms_win_net_isoext_l1_1_0_dll
```
