# __imp_load_OpenTraceW

- ea: `0x180023d91`
- end: `0x180023d9d`
- name: `__imp_load_OpenTraceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180023c63`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180023d91`

## pseudocode

```c
__int64 load_OpenTraceW()
{
  return _tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll();
}

```

## disassembly

```asm
0x180023d91  lea     rax, __imp_OpenTraceW
0x180023d98  jmp     __tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll
```
