# __imp_load_EdpIsFileAccessAllowed

- ea: `0x18000333b`
- end: `0x180003347`
- name: `__imp_load_EdpIsFileAccessAllowed`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800032aa`

## import_xrefs

- `ext-ms-win-edputil-policy-l1-1-0!EdpIsFileAccessAllowed` at `0x18000333b`

## pseudocode

```c
__int64 load_EdpIsFileAccessAllowed()
{
  return _tailMerge_ext_ms_win_edputil_policy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000333b  lea     rax, __imp_EdpIsFileAccessAllowed
0x180003342  jmp     __tailMerge_ext_ms_win_edputil_policy_l1_1_0_dll
```
