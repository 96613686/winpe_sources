# Microsoft.Crm.Sdk.BusinessEntityBase::WriteXml

- ea: `0x120`
- end: `0x181`
- name: `Microsoft.Crm.Sdk.BusinessEntityBase::WriteXml`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x120`
- `0x270`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::_internalEntity
0x126  brtrue.s loc_133
0x128  ldstr    aSdkBusinessent// "SDK BusinessEntity must have its intern"...
0x12d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x132  throw
0x133  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.BusinessEntityBase::GetConversionContext()
0x138  ldarg.0
0x139  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::_internalEntity
0x13e  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x143  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x148  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x14d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x152  ldarg.0
0x153  ldfld    bool Microsoft.Crm.Sdk.BusinessEntityBase::_skipOuterNode
0x158  brtrue.s loc_165
0x15a  ldarg.1
0x15b  ldstr    aBusinessentity// "BusinessEntity"
0x160  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x165  ldarg.1
0x166  ldc.i4.0
0x167  ldarg.0
0x168  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy Microsoft.Crm.Sdk.BusinessEntityBase::_entitySerializationStrategy
0x16d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x172  ldarg.0
0x173  ldfld    bool Microsoft.Crm.Sdk.BusinessEntityBase::_skipOuterNode
0x178  brtrue.s loc_180
0x17a  ldarg.1
0x17b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x180  ret
```
