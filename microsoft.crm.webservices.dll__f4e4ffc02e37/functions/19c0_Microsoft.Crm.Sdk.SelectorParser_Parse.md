# Microsoft.Crm.Sdk.SelectorParser::Parse

- ea: `0x19c0`
- end: `0x1a8c`
- name: `Microsoft.Crm.Sdk.SelectorParser::Parse`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1610`
- `0x19c0`
- `0x1b00`
- `0x1b40`
- `0x1ba0`
- `0x43d0`
- `0x43e0`
- `0x43f0`
- `0x44a0`
- `0x4500`
- `0x4540`
- `0x4550`
- `0x45f0`
- `0x46f0`
- `0x4920`
- `0x4a60`
- `0x4a80`

## string_xrefs

- `0x19d7`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.1
0x19c1  ldstr    aTarget// "Target"
0x19c6  ldarg.1
0x19c7  callvirt instance string Microsoft.Crm.Sdk.ParsingContext::get_CurrentNamespace()
0x19cc  callvirt instance void Microsoft.Crm.Sdk.ParsingContext::EnsureStartElement(string localName, string ns)
0x19d1  ldarg.1
0x19d2  ldstr    aType// "type"
0x19d7  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x19dc  callvirt instance string Microsoft.Crm.Sdk.ParsingContext::GetRequiredAttributeValue(string localName, string ns)
0x19e1  stloc.0
0x19e2  ldarg.1
0x19e3  ldloc.0
0x19e4  ldarg.0
0x19e5  ldarg.1
0x19e6  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x19eb  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x19f0  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_CategoryName()
0x19f5  call     instance string Microsoft.Crm.Sdk.SelectorParser::GetDynamicSelectorName(string categoryName)
0x19fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19ff  callvirt instance void Microsoft.Crm.Sdk.ParsingContext::set_IsDynamicSelector(bool value)
0x1a04  ldarg.0
0x1a05  ldarg.1
0x1a06  ldloc.0
0x1a07  call     instance string[] Microsoft.Crm.Sdk.SelectorParser::GetCategoryEntities(class Microsoft.Crm.Sdk.ParsingContext context, string selectorType)
0x1a0c  stloc.1
0x1a0d  ldarg.1
0x1a0e  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x1a13  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1a18  pop
0x1a19  ldarg.0
0x1a1a  ldarg.1
0x1a1b  ldloc.1
0x1a1c  callvirt instance object Microsoft.Crm.Sdk.SelectorParser::ParseSelectorBody(class Microsoft.Crm.Sdk.ParsingContext context, string[] entities)
0x1a21  ldarg.1
0x1a22  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x1a27  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.RequestBase::get_TargetFilter()
0x1a2c  brtrue.s loc_1A80
0x1a2e  ldarg.1
0x1a2f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x1a34  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1a39  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a3e  ldloc.1
0x1a3f  ldc.i4.0
0x1a40  ldelem.ref
0x1a41  ldc.i4.0
0x1a42  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1a47  stloc.2
0x1a48  ldloc.2
0x1a49  ldarg.1
0x1a4a  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x1a4f  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x1a54  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0x1a59  ldloc.2
0x1a5a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1a5f  call     void Microsoft.Crm.Sdk.ParserHelper::ThrowIfEntityNotFound(object entityDescriptor, string methodName, string entityName)
0x1a64  ldarg.1
0x1a65  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x1a6a  ldloc.2
0x1a6b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1a70  ldsfld   string [mscorlib]System.String::Empty
0x1a75  ldarg.1
0x1a76  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x1a7b  callvirt instance void Microsoft.Crm.Sdk.RequestBase::SetCategoryEntity(string primaryEntity, string secondaryEntity, valuetype [mscorlib]System.Guid organizationId)
0x1a80  ldarg.1
0x1a81  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x1a86  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x1a8b  ret
```
