# Microsoft.Crm.Extensibility.OData.TypeConverters.EntityReferenceAttributeTypeConverter::ConvertToCrmTypeInternal

- ea: `0x276f0`
- end: `0x27706`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EntityReferenceAttributeTypeConverter::ConvertToCrmTypeInternal`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x276f5`: `CRM do not support direct update of Entity Reference properties, Use Navigation properties instead.`

## pseudocode

```c

```

## disassembly

```asm
0x276f0  ldc.i4   0x190
0x276f5  ldstr    aCrmDoNotSuppor// "CRM do not support direct update of Ent"...
0x276fa  ldc.i4.0
0x276fb  newarr   [mscorlib]System.Object
0x27700  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x27705  throw
```
