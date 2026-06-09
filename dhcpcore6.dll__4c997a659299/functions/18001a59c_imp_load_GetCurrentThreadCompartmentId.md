# __imp_load_GetCurrentThreadCompartmentId

- ea: `0x18001a59c`
- end: `0x18001a5a8`
- name: `__imp_load_GetCurrentThreadCompartmentId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001a4f9`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18001a59c`

## pseudocode

```c
__int64 load_GetCurrentThreadCompartmentId()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18001a59c  lea     rax, __imp_GetCurrentThreadCompartmentId
0x18001a5a3  jmp     __tailMerge_iphlpapi_dll
```
