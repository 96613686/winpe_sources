# __imp_load_JetCommitTransaction

- ea: `0x180002c94`
- end: `0x180002ca0`
- name: `__imp_load_JetCommitTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x180002c94`

## pseudocode

```c
__int64 load_JetCommitTransaction()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002c94  lea     rax, __imp_JetCommitTransaction
0x180002c9b  jmp     __tailMerge_esent_dll
```
