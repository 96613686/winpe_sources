# __imp_load_JetCreateTableW

- ea: `0x18000ce1f`
- end: `0x18000ce2b`
- name: `__imp_load_JetCreateTableW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCreateTableW` at `0x18000ce1f`

## pseudocode

```c
__int64 load_JetCreateTableW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000ce1f  lea     rax, __imp_JetCreateTableW
0x18000ce26  jmp     __tailMerge_esent_dll
```
