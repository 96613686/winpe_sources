# __imp_load_LookupAccountSidLocalW

- ea: `0x18001ec2d`
- end: `0x18001ec39`
- name: `__imp_load_LookupAccountSidLocalW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ebae`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ec2d`

## pseudocode

```c
__int64 load_LookupAccountSidLocalW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001ec2d  lea     rax, __imp_LookupAccountSidLocalW
0x18001ec34  jmp     __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll
```
