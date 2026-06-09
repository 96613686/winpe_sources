# __imp_load_JetCreateIndex3W

- ea: `0x18000ce43`
- end: `0x18000ce4f`
- name: `__imp_load_JetCreateIndex3W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCreateIndex3W` at `0x18000ce43`

## pseudocode

```c
__int64 load_JetCreateIndex3W()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000ce43  lea     rax, __imp_JetCreateIndex3W
0x18000ce4a  jmp     __tailMerge_esent_dll
```
