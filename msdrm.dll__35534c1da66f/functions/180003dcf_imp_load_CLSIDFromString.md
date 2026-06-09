# __imp_load_CLSIDFromString

- ea: `0x180003dcf`
- end: `0x180003ddb`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003d3e`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180003dcf`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180003dcf  lea     rax, __imp_CLSIDFromString
0x180003dd6  jmp     __tailMerge_ole32_dll
```
