# __imp_load_LsaDelete

- ea: `0x180002b58`
- end: `0x180002b64`
- name: `__imp_load_LsaDelete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ad9`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x180002b58`

## pseudocode

```c
__int64 load_LsaDelete()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_1_dll();
}

```

## disassembly

```asm
0x180002b58  lea     rax, __imp_LsaDelete
0x180002b5f  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_1_dll
```
