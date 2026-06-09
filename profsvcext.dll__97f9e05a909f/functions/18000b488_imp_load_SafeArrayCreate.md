# __imp_load_SafeArrayCreate

- ea: `0x18000b488`
- end: `0x18000b494`
- name: `__imp_load_SafeArrayCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000af52`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b488`

## pseudocode

```c
__int64 load_SafeArrayCreate()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000b488  lea     rax, __imp_SafeArrayCreate
0x18000b48f  jmp     __tailMerge_oleaut32_dll
```
