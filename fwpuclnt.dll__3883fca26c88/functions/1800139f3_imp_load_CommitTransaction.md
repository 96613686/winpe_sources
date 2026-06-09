# __imp_load_CommitTransaction

- ea: `0x1800139f3`
- end: `0x1800139ff`
- name: `__imp_load_CommitTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013962`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x1800139f3`

## pseudocode

```c
__int64 load_CommitTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x1800139f3  lea     rax, __imp_CommitTransaction
0x1800139fa  jmp     __tailMerge_ktmw32_dll
```
