# __imp_load_LsaClose

- ea: `0x18001b71a`
- end: `0x18001b726`
- name: `__imp_load_LsaClose`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001b69b`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001b71a`

## pseudocode

```c
__int64 load_LsaClose()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001b71a  lea     rax, __imp_LsaClose
0x18001b721  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
