# __imp_load_JetOpenDatabaseW

- ea: `0x18000cde9`
- end: `0x18000cdf5`
- name: `__imp_load_JetOpenDatabaseW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetOpenDatabaseW` at `0x18000cde9`

## pseudocode

```c
__int64 load_JetOpenDatabaseW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cde9  lea     rax, __imp_JetOpenDatabaseW
0x18000cdf0  jmp     __tailMerge_esent_dll
```
