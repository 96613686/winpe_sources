# __imp_load_BuildExplicitAccessWithNameW

- ea: `0x180010ec8`
- end: `0x180010ed4`
- name: `__imp_load_BuildExplicitAccessWithNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010e49`

## import_xrefs

- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180010ec8`

## pseudocode

```c
__int64 load_BuildExplicitAccessWithNameW()
{
  return _tailMerge_api_ms_win_security_trustee_l1_1_1_dll();
}

```

## disassembly

```asm
0x180010ec8  lea     rax, __imp_BuildExplicitAccessWithNameW
0x180010ecf  jmp     __tailMerge_api_ms_win_security_trustee_l1_1_1_dll
```
