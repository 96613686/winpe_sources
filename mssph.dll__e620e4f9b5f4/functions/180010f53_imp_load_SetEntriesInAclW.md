# __imp_load_SetEntriesInAclW

- ea: `0x180010f53`
- end: `0x180010f5f`
- name: `__imp_load_SetEntriesInAclW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010ed4`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180010f53`

## pseudocode

```c
__int64 load_SetEntriesInAclW()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x180010f53  lea     rax, __imp_SetEntriesInAclW
0x180010f5a  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
