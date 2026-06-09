# Microsoft.Crm.BusinessEntities.SdkEntitySerializationStrategy::WriteStartAttributes

- ea: `0xa8140`
- end: `0xa81d1`
- name: `Microsoft.Crm.BusinessEntities.SdkEntitySerializationStrategy::WriteStartAttributes`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12d50`
- `0x9c4b0`
- `0xa7170`
- `0xa7190`
- `0xa7300`
- `0xa7330`
- `0xa7a60`
- `0xa8140`

## string_xrefs

- `0xa8155`: `xmlns`
- `0xa8170`: `xmlns`
- `0xa8196`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xa8140  ldarg.0
0xa8141  ldarg.1
0xa8142  call     instance void Microsoft.Crm.BusinessEntities.EntitySerializationStrategyBase::WriteStartAttributes(class Microsoft.Crm.BusinessEntities.EntitySerializationContext context)
0xa8147  ldarg.0
0xa8148  ldfld    bool Microsoft.Crm.BusinessEntities.SdkEntitySerializationStrategy::_overrideDefaultNameSpace
0xa814d  brfalse.s loc_A816A
0xa814f  ldarg.1
0xa8150  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0xa8155  ldstr    aXmlns// "xmlns"
0xa815a  ldarg.0
0xa815b  call     instance string Microsoft.Crm.BusinessEntities.EntitySerializationStrategyBase::get_CurrentNamespace()
0xa8160  call     string Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetBusinessEntityNamespace(string currentNamespace)
0xa8165  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa816a  ldarg.1
0xa816b  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0xa8170  ldstr    aXmlns// "xmlns"
0xa8175  ldstr    aQ1// "q1"
0xa817a  ldnull
0xa817b  ldarg.0
0xa817c  call     instance string Microsoft.Crm.BusinessEntities.EntitySerializationStrategyBase::get_CurrentNamespace()
0xa8181  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xa8186  ldarg.1
0xa8187  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0xa818c  ldstr    aXsi// "xsi"
0xa8191  ldstr    aType// "type"
0xa8196  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0xa819b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa81a0  ldstr    a01_8// "{0}:{1}"
0xa81a5  ldc.i4.2
0xa81a6  newarr   [mscorlib]System.Object
0xa81ab  dup
0xa81ac  ldc.i4.0
0xa81ad  ldstr    aQ1// "q1"
0xa81b2  stelem.ref
0xa81b3  dup
0xa81b4  ldc.i4.1
0xa81b5  ldarg.1
0xa81b6  callvirt instance class Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Entity()
0xa81bb  callvirt instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xa81c0  callvirt instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa81c5  stelem.ref
0xa81c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa81cb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xa81d0  ret
```
