# Microsoft.Crm.Application.Utility.MailMergeUtility::ConvertToFetchXml

- ea: `0x3e910`
- end: `0x3eba8`
- name: `Microsoft.Crm.Application.Utility.MailMergeUtility::ConvertToFetchXml`
- size: `664`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3dcf0`
- `0x3de90`
- `0x3e590`
- `0x3e870`
- `0x3f090`

## callees

- `0x3e910`
- `0x3ebb0`
- `0x5a350`
- `0xa3cf0`
- `0xa3e50`
- `0xa3e60`
- `0xa3e80`
- `0xa3e90`
- `0xa3ea0`
- `0xa3eb0`
- `0xa3ec0`

## string_xrefs

- `0x3e9fb`: `link-entity`
- `0x3eab9`: `link-type`
- `0x3e9b9`: `/fetch/entity/link-entity[@name="{0}" and @from="{1}" and @to="{2}"]`

## pseudocode

```c

```

## disassembly

```asm
0x3e910  ldarg.1
0x3e911  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x3e916  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x3e91b  ldarg.1
0x3e91c  ldarg.0
0x3e91d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.MailMergeUtility::_orgContext
0x3e922  call     string Microsoft.Crm.Application.Platform.DataSource::QueryExpressionToFetchXml(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3e927  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3e92c  stloc.0
0x3e92d  ldloc.0
0x3e92e  ldstr    aFetchEntity_0// "/fetch/entity"
0x3e933  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3e938  stloc.1
0x3e939  ldarg.0
0x3e93a  ldloc.0
0x3e93b  call     instance void Microsoft.Crm.Application.Utility.MailMergeUtility::FixAlias(class [System.Xml]System.Xml.XmlDocument doc)
0x3e940  ldarg.2
0x3e941  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x3e946  stloc.3
0x3e947  br       loc_3EB49
0x3e94c  ldloca.s 3
0x3e94e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x3e953  newobj   instance void Field::.ctor(string field)
0x3e958  stloc.s  4
0x3e95a  ldloc.s  4
0x3e95c  callvirt instance bool Field::get_IsPrimaryEntityAttribute()
0x3e961  brfalse.s loc_3E9A8
0x3e963  ldloc.0
0x3e964  ldstr    aAttribute// "attribute"
0x3e969  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e96e  stloc.s  5
0x3e970  ldloc.1
0x3e971  ldloc.s  5
0x3e973  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e978  pop
0x3e979  ldloc.0
0x3e97a  ldstr    aName// "name"
0x3e97f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3e984  stloc.s  6
0x3e986  ldloc.s  5
0x3e988  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3e98d  ldloc.s  6
0x3e98f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3e994  pop
0x3e995  ldloc.s  6
0x3e997  ldloc.s  4
0x3e999  callvirt instance string Field::get_Name()
0x3e99e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3e9a3  br       loc_3EB49
0x3e9a8  ldloc.s  4
0x3e9aa  callvirt instance bool Field::get_IsSpecialAlias()
0x3e9af  brtrue   loc_3EB49
0x3e9b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3e9b9  ldstr    aFetchEntityLin_0// "/fetch/entity/link-entity[@name=\"{0}\""...
0x3e9be  ldc.i4.3
0x3e9bf  newarr   [mscorlib]System.Object
0x3e9c4  dup
0x3e9c5  ldc.i4.0
0x3e9c6  ldloc.s  4
0x3e9c8  callvirt instance string Field::get_ReferencedEntity()
0x3e9cd  stelem.ref
0x3e9ce  dup
0x3e9cf  ldc.i4.1
0x3e9d0  ldloc.s  4
0x3e9d2  callvirt instance string Field::get_ReferencedAttribute()
0x3e9d7  stelem.ref
0x3e9d8  dup
0x3e9d9  ldc.i4.2
0x3e9da  ldloc.s  4
0x3e9dc  callvirt instance string Field::get_ReferencingAttribute()
0x3e9e1  stelem.ref
0x3e9e2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3e9e7  stloc.s  7
0x3e9e9  ldloc.0
0x3e9ea  ldloc.s  7
0x3e9ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3e9f1  stloc.s  8
0x3e9f3  ldloc.s  8
0x3e9f5  brtrue   loc_3EB08
0x3e9fa  ldloc.0
0x3e9fb  ldstr    aLinkEntity// "link-entity"
0x3ea00  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3ea05  stloc.s  8
0x3ea07  ldloc.1
0x3ea08  ldloc.s  8
0x3ea0a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3ea0f  pop
0x3ea10  ldloc.0
0x3ea11  ldstr    aAlias// "alias"
0x3ea16  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3ea1b  stloc.s  0xB
0x3ea1d  ldloc.s  8
0x3ea1f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3ea24  ldloc.s  0xB
0x3ea26  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3ea2b  pop
0x3ea2c  ldloc.s  0xB
0x3ea2e  ldloc.s  4
0x3ea30  callvirt instance string Field::get_FetchAlias()
0x3ea35  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3ea3a  ldloc.0
0x3ea3b  ldstr    aName// "name"
0x3ea40  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3ea45  stloc.s  0xC
0x3ea47  ldloc.s  8
0x3ea49  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3ea4e  ldloc.s  0xC
0x3ea50  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3ea55  pop
0x3ea56  ldloc.s  0xC
0x3ea58  ldloc.s  4
0x3ea5a  callvirt instance string Field::get_ReferencedEntity()
0x3ea5f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3ea64  ldloc.0
0x3ea65  ldstr    aFrom// "from"
0x3ea6a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3ea6f  stloc.s  0xD
0x3ea71  ldloc.s  8
0x3ea73  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3ea78  ldloc.s  0xD
0x3ea7a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3ea7f  pop
0x3ea80  ldloc.s  0xD
0x3ea82  ldloc.s  4
0x3ea84  callvirt instance string Field::get_ReferencedAttribute()
0x3ea89  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3ea8e  ldloc.0
0x3ea8f  ldstr    aTo// "to"
0x3ea94  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3ea99  stloc.s  0xE
0x3ea9b  ldloc.s  8
0x3ea9d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3eaa2  ldloc.s  0xE
0x3eaa4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3eaa9  pop
0x3eaaa  ldloc.s  0xE
0x3eaac  ldloc.s  4
0x3eaae  callvirt instance string Field::get_ReferencingAttribute()
0x3eab3  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3eab8  ldloc.0
0x3eab9  ldstr    aLinkType// "link-type"
0x3eabe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3eac3  stloc.s  0xF
0x3eac5  ldloc.s  8
0x3eac7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3eacc  ldloc.s  0xF
0x3eace  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3ead3  pop
0x3ead4  ldloc.s  0xF
0x3ead6  ldstr    aOuter// "outer"
0x3eadb  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3eae0  ldloc.0
0x3eae1  ldstr    aVisible// "visible"
0x3eae6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3eaeb  stloc.s  0x10
0x3eaed  ldloc.s  8
0x3eaef  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3eaf4  ldloc.s  0x10
0x3eaf6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3eafb  pop
0x3eafc  ldloc.s  0x10
0x3eafe  ldstr    aFalse// "false"
0x3eb03  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3eb08  ldloc.0
0x3eb09  ldstr    aAttribute// "attribute"
0x3eb0e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3eb13  stloc.s  9
0x3eb15  ldloc.s  8
0x3eb17  ldloc.s  9
0x3eb19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3eb1e  pop
0x3eb1f  ldloc.0
0x3eb20  ldstr    aName// "name"
0x3eb25  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3eb2a  stloc.s  0xA
0x3eb2c  ldloc.s  9
0x3eb2e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3eb33  ldloc.s  0xA
0x3eb35  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3eb3a  pop
0x3eb3b  ldloc.s  0xA
0x3eb3d  ldloc.s  4
0x3eb3f  callvirt instance string Field::get_Name()
0x3eb44  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3eb49  ldloca.s 3
0x3eb4b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x3eb50  brtrue   loc_3E94C
0x3eb55  leave.s  loc_3EB65
0x3eb57  ldloca.s 3
0x3eb59  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x3eb5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3eb64  endfinally
0x3eb65  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3eb6a  stloc.2
0x3eb6b  ldloc.2
0x3eb6c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3eb71  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x3eb76  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x3eb7b  stloc.s  0x11
0x3eb7d  ldloc.0
0x3eb7e  ldloc.s  0x11
0x3eb80  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x3eb85  ldloc.s  0x11
0x3eb87  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x3eb8c  ldloc.s  0x11
0x3eb8e  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x3eb93  leave.s  loc_3EBA1
0x3eb95  ldloc.s  0x11
0x3eb97  brfalse.s loc_3EBA0
0x3eb99  ldloc.s  0x11
0x3eb9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3eba0  endfinally
0x3eba1  ldloc.2
0x3eba2  callvirt instance string [mscorlib]System.Object::ToString()
0x3eba7  ret
```
