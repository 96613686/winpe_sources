# __imp_load_JetCreateInstance2W

- ea: `0x180002b62`
- end: `0x180002b6e`
- name: `__imp_load_JetCreateInstance2W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetCreateInstance2W` at `0x180002b62`

## pseudocode

```c
__int64 load_JetCreateInstance2W()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002b62  lea     rax, __imp_JetCreateInstance2W
0x180002b69  jmp     __tailMerge_esent_dll
```
