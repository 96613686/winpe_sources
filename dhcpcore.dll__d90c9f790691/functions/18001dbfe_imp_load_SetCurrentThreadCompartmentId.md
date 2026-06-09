# __imp_load_SetCurrentThreadCompartmentId

- ea: `0x18001dbfe`
- end: `0x18001dc0a`
- name: `__imp_load_SetCurrentThreadCompartmentId`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daef`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18001dbfe`

## pseudocode

```c
__int64 load_SetCurrentThreadCompartmentId()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18001dbfe  lea     rax, __imp_SetCurrentThreadCompartmentId
0x18001dc05  jmp     __tailMerge_iphlpapi_dll
```
