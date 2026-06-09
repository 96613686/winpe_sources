# __imp_load_LookupAccountSidW

- ea: `0x18000785c`
- end: `0x180007868`
- name: `__imp_load_LookupAccountSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077dd`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000785c`

## pseudocode

```c
__int64 load_LookupAccountSidW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000785c  lea     rax, __imp_LookupAccountSidW
0x180007863  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
