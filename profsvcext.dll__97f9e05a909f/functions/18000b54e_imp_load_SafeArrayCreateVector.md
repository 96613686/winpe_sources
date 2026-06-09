# __imp_load_SafeArrayCreateVector

- ea: `0x18000b54e`
- end: `0x18000b55a`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000af52`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000b54e`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000b54e  lea     rax, __imp_SafeArrayCreateVector
0x18000b555  jmp     __tailMerge_oleaut32_dll
```
