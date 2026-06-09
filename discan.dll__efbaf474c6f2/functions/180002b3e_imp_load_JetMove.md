# __imp_load_JetMove

- ea: `0x180002b3e`
- end: `0x180002b4a`
- name: `__imp_load_JetMove`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetMove` at `0x180002b3e`

## pseudocode

```c
__int64 load_JetMove()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002b3e  lea     rax, __imp_JetMove
0x180002b45  jmp     __tailMerge_esent_dll
```
