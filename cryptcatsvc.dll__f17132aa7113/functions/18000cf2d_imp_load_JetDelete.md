# __imp_load_JetDelete

- ea: `0x18000cf2d`
- end: `0x18000cf39`
- name: `__imp_load_JetDelete`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetDelete` at `0x18000cf2d`

## pseudocode

```c
__int64 load_JetDelete()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cf2d  lea     rax, __imp_JetDelete
0x18000cf34  jmp     __tailMerge_esent_dll
```
