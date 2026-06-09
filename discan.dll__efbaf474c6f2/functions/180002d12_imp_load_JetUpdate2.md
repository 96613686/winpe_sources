# __imp_load_JetUpdate2

- ea: `0x180002d12`
- end: `0x180002d1e`
- name: `__imp_load_JetUpdate2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetUpdate2` at `0x180002d12`

## pseudocode

```c
__int64 load_JetUpdate2()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002d12  lea     rax, __imp_JetUpdate2
0x180002d19  jmp     __tailMerge_esent_dll
```
