# __imp_load_WlanUtf8SsidToDisplayName

- ea: `0x1800038d9`
- end: `0x1800038e5`
- name: `__imp_load_WlanUtf8SsidToDisplayName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003848`

## import_xrefs

- `wlanapi!WlanUtf8SsidToDisplayName` at `0x1800038d9`

## pseudocode

```c
__int64 load_WlanUtf8SsidToDisplayName()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800038d9  lea     rax, __imp_WlanUtf8SsidToDisplayName
0x1800038e0  jmp     __tailMerge_wlanapi_dll
```
