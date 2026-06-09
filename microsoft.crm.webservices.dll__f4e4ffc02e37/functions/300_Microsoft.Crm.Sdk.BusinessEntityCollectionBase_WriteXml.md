# Microsoft.Crm.Sdk.BusinessEntityCollectionBase::WriteXml

- ea: `0x300`
- end: `0x361`
- name: `Microsoft.Crm.Sdk.BusinessEntityCollectionBase::WriteXml`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x300`
- `0x3f0`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.0
0x301  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_internalEntityCollection
0x306  brtrue.s loc_313
0x308  ldstr    aSdkBusinessent_0// "SDK BusinessEntityCollection must have "...
0x30d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x312  throw
0x313  ldarg.0
0x314  ldfld    bool Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_skipOuterNode
0x319  brtrue.s loc_326
0x31b  ldarg.1
0x31c  ldstr    aBusinessentity_1// "BusinessEntityCollection"
0x321  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x326  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.BusinessEntityCollectionBase::GetConversionContext()
0x32b  ldarg.0
0x32c  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_internalEntityCollection
0x331  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection
0x336  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33b  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x340  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection
0x345  ldarg.1
0x346  ldc.i4.0
0x347  ldarg.0
0x348  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICollectionSerializationStrategy Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_serializationStrategy
0x34d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICollectionSerializationStrategy)
0x352  ldarg.0
0x353  ldfld    bool Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_skipOuterNode
0x358  brtrue.s loc_360
0x35a  ldarg.1
0x35b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x360  ret
```
