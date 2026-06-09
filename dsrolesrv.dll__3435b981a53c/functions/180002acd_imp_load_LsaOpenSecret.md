# __imp_load_LsaOpenSecret

- ea: `0x180002acd`
- end: `0x180002ad9`
- name: `__imp_load_LsaOpenSecret`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a06`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenSecret` at `0x180002acd`

## pseudocode

```c
__int64 load_LsaOpenSecret()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002acd  lea     rax, __imp_LsaOpenSecret
0x180002ad4  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
