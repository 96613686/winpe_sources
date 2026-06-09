# __imp_load_CLSIDFromProgIDEx

- ea: `0x1800592c9`
- end: `0x1800592d5`
- name: `__imp_load_CLSIDFromProgIDEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180059150`

## import_xrefs

- `ole32!CLSIDFromProgIDEx` at `0x1800592c9`

## pseudocode

```c
__int64 load_CLSIDFromProgIDEx()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800592c9  lea     rax, __imp_CLSIDFromProgIDEx
0x1800592d0  jmp     __tailMerge_ole32_dll
```
