# __imp_load_EaCreateAggregation

- ea: `0x18001c9c3`
- end: `0x18001c9cf`
- name: `__imp_load_EaCreateAggregation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c944`

## import_xrefs

- `EventAggregation!EaCreateAggregation` at `0x18001c9c3`

## pseudocode

```c
__int64 load_EaCreateAggregation()
{
  return _tailMerge_eventaggregation_dll();
}

```

## disassembly

```asm
0x18001c9c3  lea     rax, __imp_EaCreateAggregation
0x18001c9ca  jmp     __tailMerge_eventaggregation_dll
```
