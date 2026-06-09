# Microsoft.Crm.RegControl::IsInCrmDBToolContext

- ea: `0x33bd0`
- end: `0x33c0c`
- name: `Microsoft.Crm.RegControl::IsInCrmDBToolContext`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5c60`
- `0xe6d0`

## callees

- `0x33c40`

## string_xrefs

- `0x33be8`: `CrmMergeBaseAndExtensionTableTool.exe`
- `0x33bf0`: `CrmMergeBaseAndExtensionTableTool.vshost.exe`
- `0x33bf8`: `MetadataXmlValidatorForURs.exe`
- `0x33c00`: `MetadataXmlValidatorForURs.vshost.exe`

## pseudocode

```c

```

## disassembly

```asm
0x33bd0  ldc.i4.6
0x33bd1  newarr   [mscorlib]System.String
0x33bd6  dup
0x33bd7  ldc.i4.0
0x33bd8  ldstr    aCrmdbtoolExe// "CrmDbTool.EXE"
0x33bdd  stelem.ref
0x33bde  dup
0x33bdf  ldc.i4.1
0x33be0  ldstr    aCrmdbtoolVshos// "crmdbtool.vshost.exe"
0x33be5  stelem.ref
0x33be6  dup
0x33be7  ldc.i4.2
0x33be8  ldstr    aCrmmergebasean// "CrmMergeBaseAndExtensionTableTool.exe"
0x33bed  stelem.ref
0x33bee  dup
0x33bef  ldc.i4.3
0x33bf0  ldstr    aCrmmergebasean_0// "CrmMergeBaseAndExtensionTableTool.vshos"...
0x33bf5  stelem.ref
0x33bf6  dup
0x33bf7  ldc.i4.4
0x33bf8  ldstr    aMetadataxmlval// "MetadataXmlValidatorForURs.exe"
0x33bfd  stelem.ref
0x33bfe  dup
0x33bff  ldc.i4.5
0x33c00  ldstr    aMetadataxmlval_0// "MetadataXmlValidatorForURs.vshost.exe"
0x33c05  stelem.ref
0x33c06  call     bool Microsoft.Crm.RegControl::IsInCrmInternalToolContext(string[] executionHandle)
0x33c0b  ret
```
