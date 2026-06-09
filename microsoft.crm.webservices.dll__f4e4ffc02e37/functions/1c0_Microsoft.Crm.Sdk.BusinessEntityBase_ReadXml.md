# Microsoft.Crm.Sdk.BusinessEntityBase::ReadXml

- ea: `0x1c0`
- end: `0x26f`
- name: `Microsoft.Crm.Sdk.BusinessEntityBase::ReadXml`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1460`

## callees

- `0x1c0`
- `0x270`
- `0x4340`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.1
0x1c1  ldloca.s 0
0x1c3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x1c8  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkEntityDeserializationStrategy::GetEntityNameFromXmlReader(class [System.Xml]System.Xml.XmlReader, bool&, valuetype [mscorlib]System.Guid)
0x1cd  call     string Microsoft.Crm.Sdk.ParsingContext::GetLocalValue(string sourceValue)
0x1d2  stloc.1
0x1d3  ldloc.0
0x1d4  brfalse.s loc_226
0x1d6  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x1db  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x1e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e5  ldarg.1
0x1e6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1eb  ldarg.0
0x1ec  ldfld    string Microsoft.Crm.Sdk.BusinessEntityBase::_typeNamespace
0x1f1  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string)
0x1f6  stloc.2
0x1f7  ldarg.0
0x1f8  ldloc.2
0x1f9  ldarg.1
0x1fa  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [System.Xml]System.Xml.XmlReader)
0x1ff  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x204  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::_internalEntity
0x209  leave.s  loc_26E
0x20b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x210  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x215  ldc.i4   0x8004416F
0x21a  ldc.i4.0
0x21b  newarr   [mscorlib]System.Object
0x220  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x225  throw
0x226  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x22b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x230  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x235  ldloc.1
0x236  ldc.i4.1
0x237  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x23c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x241  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x246  stloc.3
0x247  ldloc.3
0x248  ldarg.1
0x249  ldarg.0
0x24a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy Microsoft.Crm.Sdk.BusinessEntityBase::_entityDeserializationStrategy
0x24f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize(class [System.Xml]System.Xml.XmlReader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x254  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToDynamicEntityConverter::.ctor()
0x259  stloc.s  4
0x25b  ldarg.0
0x25c  ldloc.s  4
0x25e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.BusinessEntityBase::GetConversionContext()
0x263  ldloc.3
0x264  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToDynamicEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x269  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::_internalEntity
0x26e  ret
```
