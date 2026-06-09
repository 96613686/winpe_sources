# Microsoft.Crm.CrmCacheUtility::IsStagedMetadataCacheEnabled

- ea: `0x1bc60`
- end: `0x1bc79`
- name: `Microsoft.Crm.CrmCacheUtility::IsStagedMetadataCacheEnabled`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1bc10`

## string_xrefs

- `0x1bc60`: `UseMetadataCacheForStagedData`

## pseudocode

```c

```

## disassembly

```asm
0x1bc60  ldstr    aUsemetadatacac// "UseMetadataCacheForStagedData"
0x1bc65  ldc.i4.1
0x1bc66  box      [mscorlib]System.Int32
0x1bc6b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1bc70  unbox.any [mscorlib]System.Int32
0x1bc75  ldc.i4.1
0x1bc76  ceq
0x1bc78  ret
```
