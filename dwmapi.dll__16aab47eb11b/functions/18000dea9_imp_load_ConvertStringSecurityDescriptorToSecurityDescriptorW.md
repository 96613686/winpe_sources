# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x18000dea9`
- end: `0x18000deb5`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000de2a`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dea9`

## pseudocode

```c
__int64 load_ConvertStringSecurityDescriptorToSecurityDescriptorW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000dea9  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000deb0  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
