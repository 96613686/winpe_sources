# __imp_load_CLSIDFromString

- ea: `0x18005838b`
- end: `0x180058397`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180058200`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18005838b`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18005838b  lea     rax, __imp_CLSIDFromString
0x180058392  jmp     __tailMerge_ole32_dll
```
