# Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Deserialize_2

- ea: `0x9d550`
- end: `0x9d5b3`
- name: `Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Deserialize_2`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9d510`
- `0x9d540`

## callees

- `0x9d550`
- `0x9d640`
- `0x9d880`
- `0x9d960`
- `0x9d970`

## string_xrefs

- `0x9d551`: `reader`
- `0x9d587`: `Cannot parse BusinessEntityCollection - XmlReader is expected to be at the element node.`

## pseudocode

```c

```

## disassembly

```asm
0x9d550  ldarg.1
0x9d551  ldstr    aReader// "reader"
0x9d556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9d55b  ldarg.2
0x9d55c  ldstr    aDeserializatio_0// "deserializationStrategy"
0x9d561  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9d566  ldarg.1
0x9d567  isinst   [System.Xml]System.Xml.XmlTextReader
0x9d56c  stloc.0
0x9d56d  ldloc.0
0x9d56e  brfalse.s loc_9D577
0x9d570  ldloc.0
0x9d571  ldc.i4.2
0x9d572  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0x9d577  ldarg.1
0x9d578  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x9d57d  pop
0x9d57e  ldarg.1
0x9d57f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9d584  ldc.i4.1
0x9d585  beq.s    loc_9D592
0x9d587  ldstr    aCannotParseBus_0// "Cannot parse BusinessEntityCollection -"...
0x9d58c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x9d591  throw
0x9d592  ldarg.0
0x9d593  ldarg.1
0x9d594  newobj   instance void Microsoft.Crm.BusinessEntities.CollectionDeserializationContext::.ctor(class Microsoft.Crm.BusinessEntities.BusinessEntityCollection collection, class [System.Xml]System.Xml.XmlReader reader)
0x9d599  stloc.1
0x9d59a  ldarg.2
0x9d59b  ldloc.1
0x9d59c  callvirt instance bool Microsoft.Crm.BusinessEntities.ICollectionDeserializationStrategy::ReadProlog(class Microsoft.Crm.BusinessEntities.CollectionDeserializationContext context)
0x9d5a1  brfalse.s loc_9D5B2
0x9d5a3  ldarg.0
0x9d5a4  ldloc.1
0x9d5a5  ldarg.2
0x9d5a6  call     instance void Microsoft.Crm.BusinessEntities.BusinessEntityCollection::DeserializeEntities(class Microsoft.Crm.BusinessEntities.CollectionDeserializationContext context, class Microsoft.Crm.BusinessEntities.ICollectionDeserializationStrategy deserializationStrategy)
0x9d5ab  ldarg.2
0x9d5ac  ldloc.1
0x9d5ad  callvirt instance void Microsoft.Crm.BusinessEntities.ICollectionDeserializationStrategy::ReadEpilog(class Microsoft.Crm.BusinessEntities.CollectionDeserializationContext context)
0x9d5b2  ret
```
