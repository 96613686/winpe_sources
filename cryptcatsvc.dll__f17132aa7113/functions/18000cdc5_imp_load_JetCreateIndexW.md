# __imp_load_JetCreateIndexW

- ea: `0x18000cdc5`
- end: `0x18000cdd1`
- name: `__imp_load_JetCreateIndexW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCreateIndexW` at `0x18000cdc5`

## pseudocode

```c
__int64 load_JetCreateIndexW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cdc5  lea     rax, __imp_JetCreateIndexW
0x18000cdcc  jmp     __tailMerge_esent_dll
```
