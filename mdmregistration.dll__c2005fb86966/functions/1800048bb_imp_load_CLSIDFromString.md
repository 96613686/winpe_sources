# __imp_load_CLSIDFromString

- ea: `0x1800048bb`
- end: `0x1800048c7`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003c4e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800048bb`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800048bb  lea     rax, __imp_CLSIDFromString
0x1800048c2  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
