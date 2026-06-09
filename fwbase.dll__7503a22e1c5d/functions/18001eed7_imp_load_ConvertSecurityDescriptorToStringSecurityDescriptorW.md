# __imp_load_ConvertSecurityDescriptorToStringSecurityDescriptorW

- ea: `0x18001eed7`
- end: `0x18001eee3`
- name: `__imp_load_ConvertSecurityDescriptorToStringSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001edda`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001eed7`

## pseudocode

```c
__int64 load_ConvertSecurityDescriptorToStringSecurityDescriptorW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001eed7  lea     rax, __imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001eede  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
