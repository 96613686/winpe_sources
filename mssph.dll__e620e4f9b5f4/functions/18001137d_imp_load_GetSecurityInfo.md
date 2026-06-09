# __imp_load_GetSecurityInfo

- ea: `0x18001137d`
- end: `0x180011389`
- name: `__imp_load_GetSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010ed4`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18001137d`

## pseudocode

```c
__int64 load_GetSecurityInfo()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001137d  lea     rax, __imp_GetSecurityInfo
0x180011384  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
