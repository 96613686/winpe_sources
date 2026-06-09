# __imp_load_EnumerateInstalledSystemLanguagePacks

- ea: `0x140002f24`
- end: `0x140002f30`
- name: `__imp_load_EnumerateInstalledSystemLanguagePacks`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x140002ea5`

## import_xrefs

- `ext-ms-win-resources-languageoverlay-l1-1-4!EnumerateInstalledSystemLanguagePacks` at `0x140002f24`

## pseudocode

```c
__int64 load_EnumerateInstalledSystemLanguagePacks()
{
  return _tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll();
}

```

## disassembly

```asm
0x140002f24  lea     rax, __imp_EnumerateInstalledSystemLanguagePacks
0x140002f2b  jmp     __tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll
```
