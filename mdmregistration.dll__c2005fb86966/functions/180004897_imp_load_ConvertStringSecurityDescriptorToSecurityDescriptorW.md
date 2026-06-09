# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x180004897`
- end: `0x1800048a3`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800041f9`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180004897`

## pseudocode

```c
__int64 load_ConvertStringSecurityDescriptorToSecurityDescriptorW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004897  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000489e  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
