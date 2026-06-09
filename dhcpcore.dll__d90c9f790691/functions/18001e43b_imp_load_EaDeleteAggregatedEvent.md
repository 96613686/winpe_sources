# __imp_load_EaDeleteAggregatedEvent

- ea: `0x18001e43b`
- end: `0x18001e447`
- name: `__imp_load_EaDeleteAggregatedEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001e3bc`

## import_xrefs

- `EventAggregation!EaDeleteAggregatedEvent` at `0x18001e43b`

## pseudocode

```c
__int64 load_EaDeleteAggregatedEvent()
{
  return _tailMerge_eventaggregation_dll();
}

```

## disassembly

```asm
0x18001e43b  lea     rax, __imp_EaDeleteAggregatedEvent
0x18001e442  jmp     __tailMerge_eventaggregation_dll
```
