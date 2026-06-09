# __imp_load_JetOpenTableW

- ea: `0x18000ce55`
- end: `0x18000ce61`
- name: `__imp_load_JetOpenTableW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x18000ce55`

## pseudocode

```c
__int64 load_JetOpenTableW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000ce55  lea     rax, __imp_JetOpenTableW
0x18000ce5c  jmp     __tailMerge_esent_dll
```
