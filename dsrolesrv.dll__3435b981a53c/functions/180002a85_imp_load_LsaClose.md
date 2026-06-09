# __imp_load_LsaClose

- ea: `0x180002a85`
- end: `0x180002a91`
- name: `__imp_load_LsaClose`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a06`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180002a85`

## pseudocode

```c
__int64 load_LsaClose()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002a85  lea     rax, __imp_LsaClose
0x180002a8c  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
