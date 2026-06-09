# __imp_load_RasChapExt_GetConfigIgnoreIASLogon

- ea: `0x180014820`
- end: `0x18001482c`
- name: `__imp_load_RasChapExt_GetConfigIgnoreIASLogon`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180014739`

## import_xrefs

- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigIgnoreIASLogon` at `0x180014820`

## pseudocode

```c
__int64 load_RasChapExt_GetConfigIgnoreIASLogon()
{
  return _tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014820  lea     rax, __imp_RasChapExt_GetConfigIgnoreIASLogon
0x180014827  jmp     __tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll
```
