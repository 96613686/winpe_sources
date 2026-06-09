# __imp_load_SafeArrayCreate

- ea: `0x18000260c`
- end: `0x180002618`
- name: `__imp_load_SafeArrayCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000230f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000260c`

## pseudocode

```c
__int64 load_SafeArrayCreate()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000260c  lea     rax, __imp_SafeArrayCreate
0x180002613  jmp     __tailMerge_oleaut32_dll
```
