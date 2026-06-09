# __imp_load_SetSecurityInfo

- ea: `0x180058604`
- end: `0x180058610`
- name: `__imp_load_SetSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18005807d`

## import_xrefs

- `ADVAPI32!SetSecurityInfo` at `0x180058604`

## pseudocode

```c
__int64 load_SetSecurityInfo()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180058604  lea     rax, __imp_SetSecurityInfo
0x18005860b  jmp     __tailMerge_advapi32_dll
```
