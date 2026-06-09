# __imp_load_FreeSid

- ea: `0x180016692`
- end: `0x18001669e`
- name: `__imp_load_FreeSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001620b`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016692`

## pseudocode

```c
__int64 load_FreeSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180016692  lea     rax, __imp_FreeSid
0x180016699  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
