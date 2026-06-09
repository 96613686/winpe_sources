# __imp_load_CheckTokenMembership

- ea: `0x180002d31`
- end: `0x180002d3d`
- name: `__imp_load_CheckTokenMembership`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cb2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180002d31`

## pseudocode

```c
__int64 load_CheckTokenMembership()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002d31  lea     rax, __imp_CheckTokenMembership
0x180002d38  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
