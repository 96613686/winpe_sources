# __imp_load_CLSIDFromString

- ea: `0x18004e7ea`
- end: `0x18004e7f6`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004e686`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004e7ea`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004e7ea  lea     rax, __imp_CLSIDFromString
0x18004e7f1  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
