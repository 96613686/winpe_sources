# __imp_load_AllocateAndInitializeSid

- ea: `0x1800166a4`
- end: `0x1800166b0`
- name: `__imp_load_AllocateAndInitializeSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001620b`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800166a4`

## pseudocode

```c
__int64 load_AllocateAndInitializeSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800166a4  lea     rax, __imp_AllocateAndInitializeSid
0x1800166ab  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
