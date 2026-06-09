# __imp_load_JetDeleteTableW

- ea: `0x180002d24`
- end: `0x180002d30`
- name: `__imp_load_JetDeleteTableW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetDeleteTableW` at `0x180002d24`

## pseudocode

```c
__int64 load_JetDeleteTableW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002d24  lea     rax, __imp_JetDeleteTableW
0x180002d2b  jmp     __tailMerge_esent_dll
```
