# __imp_load_CoImpersonateClient

- ea: `0x180002ca6`
- end: `0x180002cb2`
- name: `__imp_load_CoImpersonateClient`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002a3e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180002ca6`

## pseudocode

```c
__int64 load_CoImpersonateClient()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002ca6  lea     rax, __imp_CoImpersonateClient
0x180002cad  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
