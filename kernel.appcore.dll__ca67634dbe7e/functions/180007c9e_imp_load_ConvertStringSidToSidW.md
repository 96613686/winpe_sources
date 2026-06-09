# __imp_load_ConvertStringSidToSidW

- ea: `0x180007c9e`
- end: `0x180007caa`
- name: `__imp_load_ConvertStringSidToSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007b5e`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180007c9e`

## pseudocode

```c
__int64 load_ConvertStringSidToSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007c9e  lea     rax, __imp_ConvertStringSidToSidW
0x180007ca5  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
