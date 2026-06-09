# __imp_load_JetCommitTransaction

- ea: `0x18000cdb3`
- end: `0x18000cdbf`
- name: `__imp_load_JetCommitTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x18000cdb3`

## pseudocode

```c
__int64 load_JetCommitTransaction()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cdb3  lea     rax, __imp_JetCommitTransaction
0x18000cdba  jmp     __tailMerge_esent_dll
```
