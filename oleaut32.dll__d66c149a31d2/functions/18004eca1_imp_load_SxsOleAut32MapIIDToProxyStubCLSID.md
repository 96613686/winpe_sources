# __imp_load_SxsOleAut32MapIIDToProxyStubCLSID

- ea: `0x18004eca1`
- end: `0x18004ecad`
- name: `__imp_load_SxsOleAut32MapIIDToProxyStubCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004ebfe`

## import_xrefs

- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToProxyStubCLSID` at `0x18004eca1`

## pseudocode

```c
__int64 load_SxsOleAut32MapIIDToProxyStubCLSID()
{
  return _tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004eca1  lea     rax, __imp_SxsOleAut32MapIIDToProxyStubCLSID
0x18004eca8  jmp     __tailMerge_ext_ms_win_sxs_oleautomation_l1_1_0_dll
```
