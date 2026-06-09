# Microsoft.Crm.Extensibility.OData.TypeConverters.MetadataEntityReferenceAttributeTypeConverter::ConvertToCrmTypeInternal

- ea: `0x27740`
- end: `0x27756`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.MetadataEntityReferenceAttributeTypeConverter::ConvertToCrmTypeInternal`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x27745`: `CRM do not support direct update of Entity Reference properties, Use Navigation properties instead.`

## pseudocode

```c

```

## disassembly

```asm
0x27740  ldc.i4   0x190
0x27745  ldstr    aCrmDoNotSuppor// "CRM do not support direct update of Ent"...
0x2774a  ldc.i4.0
0x2774b  newarr   [mscorlib]System.Object
0x27750  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x27755  throw
```
