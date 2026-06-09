# __imp_load_NetworkIsolationCreateAppContainer

- ea: `0x1800123ff`
- end: `0x18001240b`
- name: `__imp_load_NetworkIsolationCreateAppContainer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012380`

## import_xrefs

- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x1800123ff`

## pseudocode

```c
__int64 load_NetworkIsolationCreateAppContainer()
{
  return _tailMerge_ext_ms_win_net_isoext_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800123ff  lea     rax, __imp_NetworkIsolationCreateAppContainer
0x180012406  jmp     __tailMerge_ext_ms_win_net_isoext_l1_1_0_dll
```
