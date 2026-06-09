# __imp_load_EaCreateAggregatedEvent

- ea: `0x18001e44d`
- end: `0x18001e459`
- name: `__imp_load_EaCreateAggregatedEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001e3bc`

## import_xrefs

- `EventAggregation!EaCreateAggregatedEvent` at `0x18001e44d`

## pseudocode

```c
__int64 load_EaCreateAggregatedEvent()
{
  return _tailMerge_eventaggregation_dll();
}

```

## disassembly

```asm
0x18001e44d  lea     rax, __imp_EaCreateAggregatedEvent
0x18001e454  jmp     __tailMerge_eventaggregation_dll
```
