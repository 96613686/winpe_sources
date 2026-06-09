# __imp_load_JetOpenDatabaseW

- ea: `0x180002c04`
- end: `0x180002c10`
- name: `__imp_load_JetOpenDatabaseW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetOpenDatabaseW` at `0x180002c04`

## pseudocode

```c
__int64 load_JetOpenDatabaseW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002c04  lea     rax, __imp_JetOpenDatabaseW
0x180002c0b  jmp     __tailMerge_esent_dll
```
