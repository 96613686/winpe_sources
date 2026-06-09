# __imp_load_WlanGetProfileSsidList

- ea: `0x1800136ad`
- end: `0x1800136b9`
- name: `__imp_load_WlanGetProfileSsidList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001358c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileSsidList` at `0x1800136ad`

## pseudocode

```c
__int64 load_WlanGetProfileSsidList()
{
  return _tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800136ad  lea     rax, __imp_WlanGetProfileSsidList
0x1800136b4  jmp     __tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll
```
