# __imp_load_GetJobCompartmentId

- ea: `0x1800037d1`
- end: `0x1800037dd`
- name: `__imp_load_GetJobCompartmentId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000370a`

## import_xrefs

- `IPHLPAPI!GetJobCompartmentId` at `0x1800037d1`

## pseudocode

```c
__int64 load_GetJobCompartmentId()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x1800037d1  lea     rax, __imp_GetJobCompartmentId
0x1800037d8  jmp     __tailMerge_iphlpapi_dll
```
