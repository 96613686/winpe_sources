# __imp_load_DeleteCompartment

- ea: `0x1800037ad`
- end: `0x1800037b9`
- name: `__imp_load_DeleteCompartment`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000370a`

## import_xrefs

- `IPHLPAPI!DeleteCompartment` at `0x1800037ad`

## pseudocode

```c
__int64 load_DeleteCompartment()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x1800037ad  lea     rax, __imp_DeleteCompartment
0x1800037b4  jmp     __tailMerge_iphlpapi_dll
```
