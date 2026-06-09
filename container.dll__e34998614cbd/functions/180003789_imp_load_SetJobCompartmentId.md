# __imp_load_SetJobCompartmentId

- ea: `0x180003789`
- end: `0x180003795`
- name: `__imp_load_SetJobCompartmentId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000370a`

## import_xrefs

- `IPHLPAPI!SetJobCompartmentId` at `0x180003789`

## pseudocode

```c
__int64 load_SetJobCompartmentId()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x180003789  lea     rax, __imp_SetJobCompartmentId
0x180003790  jmp     __tailMerge_iphlpapi_dll
```
