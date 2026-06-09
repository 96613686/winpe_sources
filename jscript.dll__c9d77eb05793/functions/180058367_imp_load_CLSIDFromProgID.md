# __imp_load_CLSIDFromProgID

- ea: `0x180058367`
- end: `0x180058373`
- name: `__imp_load_CLSIDFromProgID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180058200`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x180058367`

## pseudocode

```c
__int64 load_CLSIDFromProgID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180058367  lea     rax, __imp_CLSIDFromProgID
0x18005836e  jmp     __tailMerge_ole32_dll
```
