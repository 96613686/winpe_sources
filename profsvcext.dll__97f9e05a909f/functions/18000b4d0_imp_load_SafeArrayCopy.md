# __imp_load_SafeArrayCopy

- ea: `0x18000b4d0`
- end: `0x18000b4dc`
- name: `__imp_load_SafeArrayCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000af52`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000b4d0`

## pseudocode

```c
__int64 load_SafeArrayCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000b4d0  lea     rax, __imp_SafeArrayCopy
0x18000b4d7  jmp     __tailMerge_oleaut32_dll
```
