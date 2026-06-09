# __imp_load_GetTokenInformation

- ea: `0x180015c55`
- end: `0x180015c61`
- name: `__imp_load_GetTokenInformation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001586b`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015c55`

## pseudocode

```c
__int64 load_GetTokenInformation()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180015c55  lea     rax, __imp_GetTokenInformation
0x180015c5c  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
