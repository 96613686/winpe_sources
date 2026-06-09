# __imp_load_LookupPrivilegeValueW

- ea: `0x180005bb1`
- end: `0x180005bbd`
- name: `__imp_load_LookupPrivilegeValueW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005b32`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180005bb1`

## pseudocode

```c
__int64 load_LookupPrivilegeValueW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x180005bb1  lea     rax, __imp_LookupPrivilegeValueW
0x180005bb8  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
