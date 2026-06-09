# __imp_load_SafeArrayCreate

- ea: `0x1800042c5`
- end: `0x1800042d1`
- name: `__imp_load_SafeArrayCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003f54`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800042c5`

## pseudocode

```c
__int64 load_SafeArrayCreate()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800042c5  lea     rax, __imp_SafeArrayCreate
0x1800042cc  jmp     __tailMerge_oleaut32_dll
```
