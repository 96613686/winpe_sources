# __imp_load_EnumerateInstalledLanguages

- ea: `0x140002faf`
- end: `0x140002fbb`
- name: `__imp_load_EnumerateInstalledLanguages`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140002f30`

## import_xrefs

- `ext-ms-win-resources-languageoverlay-l1-1-5!EnumerateInstalledLanguages` at `0x140002faf`

## pseudocode

```c
__int64 load_EnumerateInstalledLanguages()
{
  return _tailMerge_ext_ms_win_resources_languageoverlay_l1_1_5_dll();
}

```

## disassembly

```asm
0x140002faf  lea     rax, __imp_EnumerateInstalledLanguages
0x140002fb6  jmp     __tailMerge_ext_ms_win_resources_languageoverlay_l1_1_5_dll
```
