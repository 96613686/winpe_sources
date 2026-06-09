# __imp_load_LsaOpenPolicy

- ea: `0x18001b72c`
- end: `0x18001b738`
- name: `__imp_load_LsaOpenPolicy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001b69b`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001b72c`

## pseudocode

```c
__int64 load_LsaOpenPolicy()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001b72c  lea     rax, __imp_LsaOpenPolicy
0x18001b733  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
