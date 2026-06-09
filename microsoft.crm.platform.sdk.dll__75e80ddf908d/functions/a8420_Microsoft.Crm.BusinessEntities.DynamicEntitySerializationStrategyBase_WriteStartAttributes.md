# Microsoft.Crm.BusinessEntities.DynamicEntitySerializationStrategyBase::WriteStartAttributes

- ea: `0xa8420`
- end: `0xa8488`
- name: `Microsoft.Crm.BusinessEntities.DynamicEntitySerializationStrategyBase::WriteStartAttributes`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12d50`
- `0x9c4b0`
- `0xa7170`
- `0xa7190`
- `0xa71c0`
- `0xa7300`
- `0xa7330`
- `0xa7a60`
- `0xa8420`

## string_xrefs

- `0xa8430`: `xmlns`
- `0xa845d`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xa8420  ldarg.0
0xa8421  ldarg.1
0xa8422  call     instance void Microsoft.Crm.BusinessEntities.EntitySerializationStrategyBase::WriteStartAttributes(class Microsoft.Crm.BusinessEntities.EntitySerializationContext context)
0xa8427  ldarg.0
0xa8428  ldfld    bool Microsoft.Crm.BusinessEntities.DynamicEntitySerializationStrategyBase::_overrideDefaultNamespace
0xa842d  brfalse.s loc_A8445
0xa842f  ldarg.1
0xa8430  ldstr    aXmlns// "xmlns"
0xa8435  ldarg.0
0xa8436  call     instance string Microsoft.Crm.BusinessEntities.EntitySerializationStrategyBase::get_CurrentNamespace()
0xa843b  call     string Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetBusinessEntityNamespace(string currentNamespace)
0xa8440  callvirt instance void Microsoft.Crm.BusinessEntities.EntitySerializationContext::WriteAttributeString(string attributeName, string value)
0xa8445  ldarg.0
0xa8446  ldfld    bool Microsoft.Crm.BusinessEntities.DynamicEntitySerializationStrategyBase::_useBaseName
0xa844b  brfalse.s loc_A846C
0xa844d  ldarg.1
0xa844e  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0xa8453  ldstr    aXsi// "xsi"
0xa8458  ldstr    aType// "type"
0xa845d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0xa8462  ldstr    aDynamicentity// "DynamicEntity"
0xa8467  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xa846c  ldarg.1
0xa846d  ldstr    aName// "Name"
0xa8472  ldarg.1
0xa8473  callvirt instance class Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Entity()
0xa8478  callvirt instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xa847d  callvirt instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa8482  callvirt instance void Microsoft.Crm.BusinessEntities.EntitySerializationContext::WriteAttributeString(string attributeName, string value)
0xa8487  ret
```
