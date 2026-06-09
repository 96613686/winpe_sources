# __imp_load_CSebCreateWellKnownEvent

- ea: `0x18001c938`
- end: `0x18001c944`
- name: `__imp_load_CSebCreateWellKnownEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c8b9`

## import_xrefs

- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x18001c938`

## pseudocode

```c
__int64 load_CSebCreateWellKnownEvent()
{
  return _tailMerge_csystemeventsbrokerclient_dll();
}

```

## disassembly

```asm
0x18001c938  lea     rax, __imp_CSebCreateWellKnownEvent
0x18001c93f  jmp     __tailMerge_csystemeventsbrokerclient_dll
```
