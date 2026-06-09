# __imp_load_GetIfEntry2

- ea: `0x180001313`
- end: `0x18000131f`
- name: `__imp_load_GetIfEntry2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001294`

## import_xrefs

- `IPHLPAPI!GetIfEntry2` at `0x180001313`

## pseudocode

```c
__int64 __fastcall load_GetIfEntry2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_iphlpapi_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001313  lea     rax, __imp_GetIfEntry2
0x18000131a  jmp     __tailMerge_iphlpapi_dll
```
