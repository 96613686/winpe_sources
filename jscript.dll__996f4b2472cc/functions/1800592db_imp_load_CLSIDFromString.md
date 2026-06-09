# __imp_load_CLSIDFromString

- ea: `0x1800592db`
- end: `0x1800592e7`
- name: `__imp_load_CLSIDFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180059150`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800592db`

## pseudocode

```c
__int64 load_CLSIDFromString()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800592db  lea     rax, __imp_CLSIDFromString
0x1800592e2  jmp     __tailMerge_ole32_dll
```
