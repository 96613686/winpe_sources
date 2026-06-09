# __imp_load_LookupAccountSidW

- ea: `0x1800145a2`
- end: `0x1800145ae`
- name: `__imp_load_LookupAccountSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180014523`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800145a2`

## pseudocode

```c
__int64 load_LookupAccountSidW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800145a2  lea     rax, __imp_LookupAccountSidW
0x1800145a9  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
