# Microsoft.Crm.CrmCacheUtility::IsRefreshableMetadataCacheEnabled

- ea: `0x1bc80`
- end: `0x1bc99`
- name: `Microsoft.Crm.CrmCacheUtility::IsRefreshableMetadataCacheEnabled`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1bc10`

## string_xrefs

- `0x1bc80`: `EnablePartialLoadMetadataCache`

## pseudocode

```c

```

## disassembly

```asm
0x1bc80  ldstr    aEnablepartiall// "EnablePartialLoadMetadataCache"
0x1bc85  ldc.i4.1
0x1bc86  box      [mscorlib]System.Int32
0x1bc8b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1bc90  unbox.any [mscorlib]System.Int32
0x1bc95  ldc.i4.1
0x1bc96  ceq
0x1bc98  ret
```
