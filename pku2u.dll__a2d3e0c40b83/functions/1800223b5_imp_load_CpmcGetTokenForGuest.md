# __imp_load_CpmcGetTokenForGuest

- ea: `0x1800223b5`
- end: `0x1800223c1`
- name: `__imp_load_CpmcGetTokenForGuest`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022336`

## import_xrefs

- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x1800223b5`

## pseudocode

```c
__int64 load_CpmcGetTokenForGuest()
{
  return _tailMerge_ext_ms_win_containers_policymanagercli_l1_1_1_dll();
}

```

## disassembly

```asm
0x1800223b5  lea     rax, __imp_CpmcGetTokenForGuest
0x1800223bc  jmp     __tailMerge_ext_ms_win_containers_policymanagercli_l1_1_1_dll
```
