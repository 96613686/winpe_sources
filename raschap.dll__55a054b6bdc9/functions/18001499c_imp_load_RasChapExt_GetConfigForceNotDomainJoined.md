# __imp_load_RasChapExt_GetConfigForceNotDomainJoined

- ea: `0x18001499c`
- end: `0x1800149a8`
- name: `__imp_load_RasChapExt_GetConfigForceNotDomainJoined`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180014739`

## import_xrefs

- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x18001499c`

## pseudocode

```c
__int64 load_RasChapExt_GetConfigForceNotDomainJoined()
{
  return _tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001499c  lea     rax, __imp_RasChapExt_GetConfigForceNotDomainJoined
0x1800149a3  jmp     __tailMerge_ext_ms_win_raschapext_eap_l1_1_0_dll
```
