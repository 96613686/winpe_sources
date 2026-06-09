# __imp_load_JetCreateDatabaseW

- ea: `0x18000cf3f`
- end: `0x18000cf4b`
- name: `__imp_load_JetCreateDatabaseW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCreateDatabaseW` at `0x18000cf3f`

## pseudocode

```c
__int64 load_JetCreateDatabaseW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cf3f  lea     rax, __imp_JetCreateDatabaseW
0x18000cf46  jmp     __tailMerge_esent_dll
```
