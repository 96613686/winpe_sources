# __imp_load_AvRevertMmThreadCharacteristics

- ea: `0x18000bc23`
- end: `0x18000bc2f`
- name: `__imp_load_AvRevertMmThreadCharacteristics`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bba4`

## import_xrefs

- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000bc23`

## pseudocode

```c
__int64 load_AvRevertMmThreadCharacteristics()
{
  return _tailMerge_avrt_dll();
}

```

## disassembly

```asm
0x18000bc23  lea     rax, __imp_AvRevertMmThreadCharacteristics
0x18000bc2a  jmp     __tailMerge_avrt_dll
```
