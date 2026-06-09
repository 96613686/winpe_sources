# __imp_load_EfsDllOefsCheckSupportByFilePath

- ea: `0x1800024e9`
- end: `0x1800024f5`
- name: `__imp_load_EfsDllOefsCheckSupportByFilePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x1800024e9`

## pseudocode

```c
__int64 load_EfsDllOefsCheckSupportByFilePath()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800024e9  lea     rax, __imp_EfsDllOefsCheckSupportByFilePath
0x1800024f0  jmp     __tailMerge_efscore_dll
```
