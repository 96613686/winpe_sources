# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x18000ab1a`
- end: `0x18000ab26`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000aa9b`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ab1a`

## pseudocode

```c
__int64 __fastcall load_ConvertStringSecurityDescriptorToSecurityDescriptorW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ab1a  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000ab21  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
