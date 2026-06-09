# Microsoft.Crm.Sdk.BusinessEntityCollectionBase::ReadXml

- ea: `0x3a0`
- end: `0x3ee`
- name: `Microsoft.Crm.Sdk.BusinessEntityCollectionBase::ReadXml`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1770`

## callees

- `0x3a0`
- `0x3f0`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x3a5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(valuetype [mscorlib]System.Guid)
0x3aa  stloc.0
0x3ab  ldloc.0
0x3ac  ldarg.1
0x3ad  ldarg.0
0x3ae  ldfld    string Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_typeNamespace
0x3b3  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_IsEmpty()
0x3b8  brtrue.s loc_3C6
0x3ba  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_CurrentSoapContext()
0x3bf  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_CrmMethodName()
0x3c4  br.s     loc_3CB
0x3c6  ldsfld   string [mscorlib]System.String::Empty
0x3cb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkCollectionDeserializationStrategy::.ctor(string, string)
0x3d0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Deserialize(class [System.Xml]System.Xml.XmlReader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICollectionDeserializationStrategy)
0x3d5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionToDynamicEntityCollectionConverter::.ctor()
0x3da  stloc.1
0x3db  ldarg.0
0x3dc  ldloc.1
0x3dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.BusinessEntityCollectionBase::GetConversionContext()
0x3e2  ldloc.0
0x3e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionToDynamicEntityCollectionConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x3e8  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection Microsoft.Crm.Sdk.BusinessEntityCollectionBase::_internalEntityCollection
0x3ed  ret
```
