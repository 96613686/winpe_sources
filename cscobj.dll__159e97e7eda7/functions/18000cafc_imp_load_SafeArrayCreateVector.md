# __imp_load_SafeArrayCreateVector

- ea: `0x18000cafc`
- end: `0x18000cb08`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c259`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000cafc`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000cafc  lea     rax, __imp_SafeArrayCreateVector
0x18000cb03  jmp     __tailMerge_oleaut32_dll
```
