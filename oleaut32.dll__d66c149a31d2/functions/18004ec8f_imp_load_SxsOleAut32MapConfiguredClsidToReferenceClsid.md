# __imp_load_SxsOleAut32MapConfiguredClsidToReferenceClsid

- ea: `0x18004ec8f`
- end: `0x18004ec9b`
- name: `__imp_load_SxsOleAut32MapConfiguredClsidToReferenceClsid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18004ebfe`

## import_xrefs

- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapConfiguredClsidToReferenceClsid` at `0x18004ec8f`

## pseudocode

```c
__int64 load_SxsOleAut32MapConfiguredClsidToReferenceClsid()
{
  return _tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004ec8f  lea     rax, __imp_SxsOleAut32MapConfiguredClsidToReferenceClsid
0x18004ec96  jmp     __tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll
```
