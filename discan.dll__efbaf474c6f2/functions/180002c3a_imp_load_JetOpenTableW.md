# __imp_load_JetOpenTableW

- ea: `0x180002c3a`
- end: `0x180002c46`
- name: `__imp_load_JetOpenTableW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x180002c3a`

## pseudocode

```c
__int64 load_JetOpenTableW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002c3a  lea     rax, __imp_JetOpenTableW
0x180002c41  jmp     __tailMerge_esent_dll
```
