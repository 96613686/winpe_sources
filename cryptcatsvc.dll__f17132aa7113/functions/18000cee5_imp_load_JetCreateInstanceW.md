# __imp_load_JetCreateInstanceW

- ea: `0x18000cee5`
- end: `0x18000cef1`
- name: `__imp_load_JetCreateInstanceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ccec`

## import_xrefs

- `ESENT!JetCreateInstanceW` at `0x18000cee5`

## pseudocode

```c
__int64 load_JetCreateInstanceW()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x18000cee5  lea     rax, __imp_JetCreateInstanceW
0x18000ceec  jmp     __tailMerge_esent_dll
```
