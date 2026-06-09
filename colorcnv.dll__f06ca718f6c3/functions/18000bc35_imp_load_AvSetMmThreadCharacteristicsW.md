# __imp_load_AvSetMmThreadCharacteristicsW

- ea: `0x18000bc35`
- end: `0x18000bc41`
- name: `__imp_load_AvSetMmThreadCharacteristicsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bba4`

## import_xrefs

- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000bc35`

## pseudocode

```c
__int64 load_AvSetMmThreadCharacteristicsW()
{
  return _tailMerge_avrt_dll();
}

```

## disassembly

```asm
0x18000bc35  lea     rax, __imp_AvSetMmThreadCharacteristicsW
0x18000bc3c  jmp     __tailMerge_avrt_dll
```
