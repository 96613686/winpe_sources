# __imp_load_JetMove

- ea: `0x18000cfbd`
- end: `0x18000cfc9`
- name: `__imp_load_JetMove`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetMove` at `0x18000cfbd`

## pseudocode

```c
__int64 load_JetMove()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cfbd  lea     rax, __imp_JetMove
0x18000cfc4  jmp     __tailMerge_esent_dll
```
