# __imp_load_ConvertSidToStringSidW

- ea: `0x18000ae2b`
- end: `0x18000ae37`
- name: `__imp_load_ConvertSidToStringSidW`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000aa9b`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ae2b`

## pseudocode

```c
__int64 __fastcall load_ConvertSidToStringSidW(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ae2b  lea     rax, __imp_ConvertSidToStringSidW
0x18000ae32  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
