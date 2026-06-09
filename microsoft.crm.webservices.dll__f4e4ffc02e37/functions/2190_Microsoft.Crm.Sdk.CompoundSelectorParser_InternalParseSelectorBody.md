# Microsoft.Crm.Sdk.CompoundSelectorParser::InternalParseSelectorBody

- ea: `0x2190`
- end: `0x22ba`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::InternalParseSelectorBody`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1460`
- `0x2190`
- `0x2410`
- `0x43d0`
- `0x43e0`
- `0x43f0`
- `0x44a0`
- `0x4530`
- `0x4550`
- `0x45e0`
- `0x4930`

## pseudocode

```c

```

## disassembly

```asm
0x2190  ldarg.1
0x2191  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.ParserHelper::ParseEntity(class Microsoft.Crm.Sdk.ParsingContext context)
0x2196  stloc.0
0x2197  ldarg.1
0x2198  callvirt instance bool Microsoft.Crm.Sdk.ParsingContext::get_IsDynamicSelector()
0x219d  brfalse.s loc_21D3
0x219f  ldarg.2
0x21a0  ldarg.1
0x21a1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x21a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x21ab  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21b0  ldloc.0
0x21b1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Name()
0x21b6  ldc.i4.1
0x21b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x21bc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x21c1  stind.ref
0x21c2  ldstr    aChildentities// "ChildEntities"
0x21c7  stloc.2
0x21c8  ldarg.0
0x21c9  ldarg.2
0x21ca  ldind.ref
0x21cb  call     instance string Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName(string parentEntityPlatformName)
0x21d0  stloc.1
0x21d1  br.s     loc_21FE
0x21d3  ldarg.1
0x21d4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x21d9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x21de  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21e3  ldarg.0
0x21e4  ldarg.2
0x21e5  ldind.ref
0x21e6  call     instance string Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName(string parentEntityPlatformName)
0x21eb  ldc.i4.0
0x21ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x21f1  dup
0x21f2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x21f7  stloc.2
0x21f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x21fd  stloc.1
0x21fe  ldarg.1
0x21ff  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x2204  ldarg.2
0x2205  ldind.ref
0x2206  ldloc.1
0x2207  ldc.i4.0
0x2208  ldarg.1
0x2209  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x220e  callvirt instance void Microsoft.Crm.Sdk.RequestBase::SetCategoryEntity(string primaryEntity, string secondaryEntity, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mappingType, valuetype [mscorlib]System.Guid organizationId)
0x2213  ldarg.1
0x2214  ldloc.2
0x2215  ldarg.1
0x2216  callvirt instance string Microsoft.Crm.Sdk.ParsingContext::get_CurrentNamespace()
0x221b  callvirt instance void Microsoft.Crm.Sdk.ParsingContext::EnsureStartElement(string localName, string ns)
0x2220  ldarg.1
0x2221  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x2226  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x222b  ldc.i4.0
0x222c  ceq
0x222e  ldarg.1
0x222f  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x2234  ldloc.2
0x2235  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement(string)
0x223a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::.ctor()
0x223f  stloc.3
0x2240  brfalse.s loc_226C
0x2242  br.s     loc_2254
0x2244  ldarg.1
0x2245  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.ParserHelper::ParseEntity(class Microsoft.Crm.Sdk.ParsingContext context)
0x224a  stloc.s  5
0x224c  ldloc.3
0x224d  ldloc.s  5
0x224f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x2254  ldarg.1
0x2255  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x225a  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x225f  brtrue.s loc_2244
0x2261  ldarg.1
0x2262  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0x2267  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x226c  ldloc.3
0x226d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::ToArray()
0x2272  stloc.s  4
0x2274  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::.ctor()
0x2279  dup
0x227a  ldloc.0
0x227b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::Add(var<u1>)
0x2280  dup
0x2281  ldloc.3
0x2282  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2287  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::ToArray()
0x228c  ldarg.1
0x228d  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x2292  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x2297  ldstr    aEntity// "Entity"
0x229c  ldloc.0
0x229d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x22a2  ldarg.1
0x22a3  callvirt instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x22a8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x22ad  ldstr    aChildentities// "ChildEntities"
0x22b2  ldloc.s  4
0x22b4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x22b9  ret
```
