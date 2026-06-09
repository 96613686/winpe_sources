# Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize_2

- ea: `0x9c6a0`
- end: `0x9c703`
- name: `Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize_2`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9c650`
- `0x9c690`
- `0x9d640`
- `0xa6bd0`

## callees

- `0x9c6a0`
- `0x9c710`
- `0xa6950`
- `0xa6a40`
- `0xa6aa0`

## string_xrefs

- `0x9c6a1`: `reader`
- `0x9c6d7`: `Cannot parse BusinessEntity - XmlReader is expected to be at the element node.`

## pseudocode

```c

```

## disassembly

```asm
0x9c6a0  ldarg.1
0x9c6a1  ldstr    aReader// "reader"
0x9c6a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9c6ab  ldarg.2
0x9c6ac  ldstr    aDeserializatio_0// "deserializationStrategy"
0x9c6b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9c6b6  ldarg.1
0x9c6b7  isinst   [System.Xml]System.Xml.XmlTextReader
0x9c6bc  stloc.0
0x9c6bd  ldloc.0
0x9c6be  brfalse.s loc_9C6C7
0x9c6c0  ldloc.0
0x9c6c1  ldc.i4.2
0x9c6c2  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0x9c6c7  ldarg.1
0x9c6c8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x9c6cd  pop
0x9c6ce  ldarg.1
0x9c6cf  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9c6d4  ldc.i4.1
0x9c6d5  beq.s    loc_9C6E2
0x9c6d7  ldstr    aCannotParseBus// "Cannot parse BusinessEntity - XmlReader"...
0x9c6dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x9c6e1  throw
0x9c6e2  ldarg.0
0x9c6e3  ldarg.1
0x9c6e4  newobj   instance void Microsoft.Crm.BusinessEntities.EntityDeserializationContext::.ctor(class Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [System.Xml]System.Xml.XmlReader reader)
0x9c6e9  stloc.1
0x9c6ea  ldarg.2
0x9c6eb  ldloc.1
0x9c6ec  callvirt instance bool Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadProlog(class Microsoft.Crm.BusinessEntities.EntityDeserializationContext context)
0x9c6f1  brfalse.s loc_9C702
0x9c6f3  ldarg.0
0x9c6f4  ldloc.1
0x9c6f5  ldarg.2
0x9c6f6  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class Microsoft.Crm.BusinessEntities.EntityDeserializationContext context, class Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy deserializationStrategy)
0x9c6fb  ldarg.2
0x9c6fc  ldloc.1
0x9c6fd  callvirt instance void Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadEpilog(class Microsoft.Crm.BusinessEntities.EntityDeserializationContext context)
0x9c702  ret
```
