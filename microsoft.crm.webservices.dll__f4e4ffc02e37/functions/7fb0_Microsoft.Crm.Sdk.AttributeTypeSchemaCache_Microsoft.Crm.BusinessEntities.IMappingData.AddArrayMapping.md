# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::Microsoft.Crm.BusinessEntities.IMappingData.AddArrayMapping

- ea: `0x7fb0`
- end: `0x7fe5`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::Microsoft.Crm.BusinessEntities.IMappingData.AddArrayMapping`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x6910`
- `0x6ec0`
- `0x7f00`
- `0x10110`

## pseudocode

```c

```

## disassembly

```asm
0x7fb0  ldarg.3
0x7fb1  ldarg.0
0x7fb2  call     instance string Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_CurrentNamespace()
0x7fb7  ldloca.s 0
0x7fb9  call     class [System.Xml]System.Xml.Schema.XmlSchema Microsoft.Crm.Sdk.SchemaHelper::BuildArraySchema(class [System.Xml]System.Xml.XmlQualifiedName elementName, string namespaceName, [out] class [System.Xml]System.Xml.XmlQualifiedName& typeName)
0x7fbe  stloc.1
0x7fbf  ldarg.0
0x7fc0  ldfld    class Microsoft.Crm.Sdk.SchemaContext Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_context
0x7fc5  ldloc.1
0x7fc6  callvirt instance void Microsoft.Crm.Sdk.SchemaContext::AddSchema(class [System.Xml]System.Xml.Schema.XmlSchema newSchema)
0x7fcb  ldloc.0
0x7fcc  newobj   instance void AttributeTypeSchemaCacheEntry::.ctor(class [System.Xml]System.Xml.XmlQualifiedName strongType)
0x7fd1  stloc.2
0x7fd2  ldarg.0
0x7fd3  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_attributeTypeToEntry
0x7fd8  ldarg.1
0x7fd9  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7fde  ldloc.2
0x7fdf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x7fe4  ret
```
