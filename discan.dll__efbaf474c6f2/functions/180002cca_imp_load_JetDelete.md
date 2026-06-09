# __imp_load_JetDelete

- ea: `0x180002cca`
- end: `0x180002cd6`
- name: `__imp_load_JetDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetDelete` at `0x180002cca`

## pseudocode

```c
__int64 load_JetDelete()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002cca  lea     rax, __imp_JetDelete
0x180002cd1  jmp     __tailMerge_esent_dll
```
