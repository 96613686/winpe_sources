# __imp_load_CreateCompartment

- ea: `0x1800037bf`
- end: `0x1800037cb`
- name: `__imp_load_CreateCompartment`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000370a`

## import_xrefs

- `IPHLPAPI!CreateCompartment` at `0x1800037bf`

## pseudocode

```c
__int64 load_CreateCompartment()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x1800037bf  lea     rax, __imp_CreateCompartment
0x1800037c6  jmp     __tailMerge_iphlpapi_dll
```
