# __imp_load_GetAdaptersAddresses

- ea: `0x180001325`
- end: `0x180001331`
- name: `__imp_load_GetAdaptersAddresses`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001294`

## import_xrefs

- `IPHLPAPI!GetAdaptersAddresses` at `0x180001325`

## pseudocode

```c
__int64 __fastcall load_GetAdaptersAddresses(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_iphlpapi_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001325  lea     rax, __imp_GetAdaptersAddresses
0x18000132c  jmp     __tailMerge_iphlpapi_dll
```
