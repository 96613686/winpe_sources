# __imp_load_WlanUtf8SsidToDisplayName

- ea: `0x180013653`
- end: `0x18001365f`
- name: `__imp_load_WlanUtf8SsidToDisplayName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001358c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x180013653`

## pseudocode

```c
__int64 load_WlanUtf8SsidToDisplayName()
{
  return _tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x180013653  lea     rax, __imp_WlanUtf8SsidToDisplayName
0x18001365a  jmp     __tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll
```
