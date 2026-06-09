# __imp_load_InitializeCompartmentEntry

- ea: `0x18000379b`
- end: `0x1800037a7`
- name: `__imp_load_InitializeCompartmentEntry`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000370a`

## import_xrefs

- `IPHLPAPI!InitializeCompartmentEntry` at `0x18000379b`

## pseudocode

```c
__int64 load_InitializeCompartmentEntry()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18000379b  lea     rax, __imp_InitializeCompartmentEntry
0x1800037a2  jmp     __tailMerge_iphlpapi_dll
```
