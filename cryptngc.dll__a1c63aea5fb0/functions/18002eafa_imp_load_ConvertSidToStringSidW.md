# __imp_load_ConvertSidToStringSidW

- ea: `0x18002eafa`
- end: `0x18002eb06`
- name: `__imp_load_ConvertSidToStringSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002ea7b`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002eafa`

## pseudocode

```c
__int64 load_ConvertSidToStringSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002eafa  lea     rax, __imp_ConvertSidToStringSidW
0x18002eb01  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
