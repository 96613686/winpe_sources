# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::Microsoft.Crm.BusinessEntities.IMappingData.AddMapping

- ea: `0x7f80`
- end: `0x7fa2`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::Microsoft.Crm.BusinessEntities.IMappingData.AddMapping`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x67b0`
- `0x6da0`
- `0x7ff0`
- `0x10110`

## pseudocode

```c

```

## disassembly

```asm
0x7f80  ldarg.s  4
0x7f82  call     class Microsoft.Crm.Sdk.ISchemaBuilder Microsoft.Crm.Sdk.SchemaBuilderFactory::Create(class [mscorlib]System.Type type)
0x7f87  ldarg.0
0x7f88  ldfld    class Microsoft.Crm.Sdk.SchemaContext Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_context
0x7f8d  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ISchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0x7f92  newobj   instance void AttributeTypeSchemaCacheEntry::.ctor(class [System.Xml]System.Xml.XmlQualifiedName strongType)
0x7f97  stloc.0
0x7f98  ldarg.0
0x7f99  ldarg.1
0x7f9a  ldarg.2
0x7f9b  ldloc.0
0x7f9c  call     instance void Microsoft.Crm.Sdk.AttributeTypeSchemaCache::AddCacheEntry(object attributeType, class [mscorlib]System.Type clrType, class AttributeTypeSchemaCacheEntry entry)
0x7fa1  ret
```
