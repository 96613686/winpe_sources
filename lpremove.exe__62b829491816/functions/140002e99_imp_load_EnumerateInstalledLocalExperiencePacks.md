# __imp_load_EnumerateInstalledLocalExperiencePacks

- ea: `0x140002e99`
- end: `0x140002ea5`
- name: `__imp_load_EnumerateInstalledLocalExperiencePacks`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140002e1a`

## import_xrefs

- `ext-ms-win-resources-languageoverlay-l1-1-1!EnumerateInstalledLocalExperiencePacks` at `0x140002e99`

## pseudocode

```c
__int64 load_EnumerateInstalledLocalExperiencePacks()
{
  return _tailMerge_ext_ms_win_resources_languageoverlay_l1_1_1_dll();
}

```

## disassembly

```asm
0x140002e99  lea     rax, __imp_EnumerateInstalledLocalExperiencePacks
0x140002ea0  jmp     __tailMerge_ext_ms_win_resources_languageoverlay_l1_1_1_dll
```
