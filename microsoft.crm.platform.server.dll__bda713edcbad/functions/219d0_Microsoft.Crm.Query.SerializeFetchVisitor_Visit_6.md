# Microsoft.Crm.Query.SerializeFetchVisitor::Visit_6

- ea: `0x219d0`
- end: `0x21ae7`
- name: `Microsoft.Crm.Query.SerializeFetchVisitor::Visit_6`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1a850`
- `0x1a8f0`
- `0x1b0c0`
- `0x1b0d0`
- `0x1b0e0`
- `0x1b110`
- `0x1b130`
- `0x1b140`
- `0x1b160`
- `0x1b220`
- `0x1b280`
- `0x1b2b0`
- `0x219d0`

## string_xrefs

- `0x219e1`: `link-entity`
- `0x21a50`: `link-type`

## pseudocode

```c

```

## disassembly

```asm
0x219d0  ldarg.1
0x219d1  ldstr    aLink// "link"
0x219d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x219db  ldarg.0
0x219dc  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x219e1  ldstr    aLinkEntity// "link-entity"
0x219e6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x219eb  ldarg.1
0x219ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x219f1  ldarg.1
0x219f2  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_EntityName()
0x219f7  ldc.i4.0
0x219f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x219fd  stloc.0
0x219fe  ldarg.0
0x219ff  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21a04  ldstr    aName// "name"
0x21a09  ldloc.0
0x21a0a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x21a0f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x21a14  ldarg.0
0x21a15  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21a1a  ldstr    aTo// "to"
0x21a1f  ldarg.1
0x21a20  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x21a25  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x21a2a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x21a2f  ldarg.0
0x21a30  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21a35  ldstr    aFrom_0// "from"
0x21a3a  ldarg.1
0x21a3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x21a40  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x21a45  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x21a4a  ldarg.0
0x21a4b  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21a50  ldstr    aLinkType// "link-type"
0x21a55  ldarg.1
0x21a56  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator Microsoft.Crm.Query.LinkEntityExpression::get_JoinOperator()
0x21a5b  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.QuerySerializationUtil::JoinOperatorToXmlString(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x21a60  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x21a65  ldarg.1
0x21a66  callvirt instance bool Microsoft.Crm.Query.LinkEntityExpression::get_FetchAliasWasSpecified()
0x21a6b  brfalse.s loc_21A83
0x21a6d  ldarg.0
0x21a6e  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21a73  ldstr    aAlias// "alias"
0x21a78  ldarg.1
0x21a79  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x21a7e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x21a83  ldarg.1
0x21a84  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x21a89  ldarg.0
0x21a8a  callvirt instance void Microsoft.Crm.Query.Expression::Serialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x21a8f  ldarg.1
0x21a90  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x21a95  ldarg.0
0x21a96  callvirt instance void Microsoft.Crm.Query.Expression::Serialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x21a9b  ldarg.1
0x21a9c  callvirt instance class Microsoft.Crm.Query.OrderExpression Microsoft.Crm.Query.LinkEntityExpression::get_Order()
0x21aa1  ldarg.0
0x21aa2  callvirt instance void Microsoft.Crm.Query.Expression::Serialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x21aa7  ldarg.1
0x21aa8  callvirt instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.LinkEntityExpression::get_LinkedEntities()
0x21aad  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::GetEnumerator()
0x21ab2  stloc.1
0x21ab3  br.s     loc_21AC2
0x21ab5  ldloca.s 1
0x21ab7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LinkEntityExpression>::get_Current()
0x21abc  ldarg.0
0x21abd  callvirt instance void Microsoft.Crm.Query.Expression::Serialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x21ac2  ldloca.s 1
0x21ac4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LinkEntityExpression>::MoveNext()
0x21ac9  brtrue.s loc_21AB5
0x21acb  leave.s  loc_21ADB
0x21acd  ldloca.s 1
0x21acf  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LinkEntityExpression>
0x21ad5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21ada  endfinally
0x21adb  ldarg.0
0x21adc  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Query.SerializeFetchVisitor::writer
0x21ae1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x21ae6  ret
```
