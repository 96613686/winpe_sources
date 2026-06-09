# __imp_load_StringFromCLSID

- ea: `0x1800592ff`
- end: `0x18005930b`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180059150`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800592ff`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800592ff  lea     rax, __imp_StringFromCLSID
0x180059306  jmp     __tailMerge_ole32_dll
```
