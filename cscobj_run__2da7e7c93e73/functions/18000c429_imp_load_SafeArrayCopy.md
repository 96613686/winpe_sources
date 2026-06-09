# __imp_load_SafeArrayCopy

- ea: `0x18000c429`
- end: `0x18000c435`
- name: `__imp_load_SafeArrayCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c259`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000c429`

## pseudocode

```c
__int64 load_SafeArrayCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000c429  lea     rax, __imp_SafeArrayCopy
0x18000c430  jmp     __tailMerge_oleaut32_dll
```
