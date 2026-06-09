# __imp_load_OpenTraceW

- ea: `0x18000aa6b`
- end: `0x18000aa77`
- name: `__imp_load_OpenTraceW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a9ec`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000aa6b`

## pseudocode

```c
__int64 load_OpenTraceW()
{
  return _tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aa6b  lea     rax, __imp_OpenTraceW
0x18000aa72  jmp     __tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll
```
