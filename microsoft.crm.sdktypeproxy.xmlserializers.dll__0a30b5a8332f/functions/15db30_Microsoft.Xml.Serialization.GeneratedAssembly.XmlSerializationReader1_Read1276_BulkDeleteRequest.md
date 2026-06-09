# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1276_BulkDeleteRequest

- ea: `0x15db30`
- end: `0x15e313`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1276_BulkDeleteRequest`
- size: `2019`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x79630`
- `0x7b120`
- `0xdd390`
- `0x15db30`

## string_xrefs

- `0x15dcf8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15dd06`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15e054`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15e062`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15e1c3`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15e1d1`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15de56`: `http://schemas.microsoft.com/crm/2007/WebServices:QueryBase`
- `0x15de64`: `http://schemas.microsoft.com/crm/2007/WebServices:QueryBase`
- `0x15e2be`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:QuerySet, http://schemas.microsoft.com/crm/2007/WebServices:JobName, http://schemas.microsoft.com/crm/2007/WebServices:SendEmailNotification, http://schemas.microsoft.com/crm/2007/WebServices:ToRecipients, http://schemas.microsoft.com/crm/2007/WebServices:CCRecipients, http://schemas.microsoft.com/crm/2007/WebServices:RecurrencePattern, http://schemas.microsoft.com/crm/2007/Web`
- `0x15e2cc`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:QuerySet, http://schemas.microsoft.com/crm/2007/WebServices:JobName, http://schemas.microsoft.com/crm/2007/WebServices:SendEmailNotification, http://schemas.microsoft.com/crm/2007/WebServices:ToRecipients, http://schemas.microsoft.com/crm/2007/WebServices:CCRecipients, http://schemas.microsoft.com/crm/2007/WebServices:RecurrencePattern, http://schemas.microsoft.com/crm/2007/Web`

## pseudocode

```c

```

## disassembly

```asm
0x15db30  ldarg.2
0x15db31  brtrue.s loc_15DB36
0x15db33  ldnull
0x15db34  br.s     loc_15DB3C
0x15db36  ldarg.0
0x15db37  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x15db3c  stloc.0
0x15db3d  ldc.i4.0
0x15db3e  stloc.1
0x15db3f  ldarg.1
0x15db40  brfalse.s loc_15DB49
0x15db42  ldarg.0
0x15db43  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15db48  stloc.1
0x15db49  ldarg.2
0x15db4a  brfalse.s loc_15DB79
0x15db4c  ldloc.0
0x15db4d  ldnull
0x15db4e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x15db53  brtrue.s loc_15DB79
0x15db55  ldloc.0
0x15db56  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x15db5b  ldarg.0
0x15db5c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1378_BulkDeleteRequest
0x15db61  bne.un.s loc_15DB71
0x15db63  ldloc.0
0x15db64  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x15db69  ldarg.0
0x15db6a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15db6f  beq.s    loc_15DB79
0x15db71  ldarg.0
0x15db72  ldloc.0
0x15db73  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x15db78  throw
0x15db79  ldloc.1
0x15db7a  brfalse.s loc_15DB7E
0x15db7c  ldnull
0x15db7d  ret
0x15db7e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::.ctor()
0x15db83  stloc.2
0x15db84  ldc.i4.8
0x15db85  newarr   [mscorlib]System.Boolean
0x15db8a  stloc.3
0x15db8b  br.s     loc_15DBA7
0x15db8d  ldarg.0
0x15db8e  ldarg.0
0x15db8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15db94  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x15db99  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x15db9e  brtrue.s loc_15DBA7
0x15dba0  ldarg.0
0x15dba1  ldloc.2
0x15dba2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x15dba7  ldarg.0
0x15dba8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbad  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x15dbb2  brtrue.s loc_15DB8D
0x15dbb4  ldarg.0
0x15dbb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbba  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x15dbbf  pop
0x15dbc0  ldarg.0
0x15dbc1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbc6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15dbcb  brfalse.s loc_15DBDA
0x15dbcd  ldarg.0
0x15dbce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbd3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15dbd8  ldloc.2
0x15dbd9  ret
0x15dbda  ldarg.0
0x15dbdb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbe0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15dbe5  ldarg.0
0x15dbe6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dbeb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15dbf0  pop
0x15dbf1  ldc.i4.0
0x15dbf2  stloc.s  4
0x15dbf4  ldarg.0
0x15dbf5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15dbfa  stloc.s  5
0x15dbfc  br       loc_15E2EC
0x15dc01  ldarg.0
0x15dc02  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc07  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15dc0c  ldc.i4.1
0x15dc0d  bne.un   loc_15E2CA
0x15dc12  ldarg.0
0x15dc13  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc18  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15dc1d  ldarg.0
0x15dc1e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x15dc23  bne.un   loc_15DD70
0x15dc28  ldarg.0
0x15dc29  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc2e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15dc33  ldarg.0
0x15dc34  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15dc39  bne.un   loc_15DD70
0x15dc3e  ldarg.0
0x15dc3f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15dc44  brtrue   loc_15E2D6
0x15dc49  ldnull
0x15dc4a  stloc.s  6
0x15dc4c  ldc.i4.0
0x15dc4d  stloc.s  7
0x15dc4f  ldarg.0
0x15dc50  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc55  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15dc5a  brfalse.s loc_15DC6C
0x15dc5c  ldarg.0
0x15dc5d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc62  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15dc67  br       loc_15DD4B
0x15dc6c  ldarg.0
0x15dc6d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc72  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15dc77  ldarg.0
0x15dc78  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc7d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15dc82  pop
0x15dc83  ldc.i4.0
0x15dc84  stloc.s  8
0x15dc86  ldarg.0
0x15dc87  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15dc8c  stloc.s  9
0x15dc8e  br       loc_15DD26
0x15dc93  ldarg.0
0x15dc94  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dc99  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15dc9e  ldc.i4.1
0x15dc9f  bne.un.s loc_15DD04
0x15dca1  ldarg.0
0x15dca2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dca7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15dcac  ldarg.0
0x15dcad  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x15dcb2  bne.un.s loc_15DCF6
0x15dcb4  ldarg.0
0x15dcb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dcba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15dcbf  ldarg.0
0x15dcc0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15dcc5  bne.un.s loc_15DCF6
0x15dcc7  ldarg.0
0x15dcc8  ldloc.s  6
0x15dcca  ldloc.s  7
0x15dccc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15dcd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15dcd6  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15dcdb  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15dce0  stloc.s  6
0x15dce2  ldloc.s  6
0x15dce4  ldloc.s  7
0x15dce6  dup
0x15dce7  ldc.i4.1
0x15dce8  add
0x15dce9  stloc.s  7
0x15dceb  ldarg.0
0x15dcec  ldc.i4.1
0x15dced  ldc.i4.1
0x15dcee  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x15dcf3  stelem.ref
0x15dcf4  br.s     loc_15DD10
0x15dcf6  ldarg.0
0x15dcf7  ldnull
0x15dcf8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15dcfd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15dd02  br.s     loc_15DD10
0x15dd04  ldarg.0
0x15dd05  ldnull
0x15dd06  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15dd0b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15dd10  ldarg.0
0x15dd11  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dd16  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15dd1b  pop
0x15dd1c  ldarg.0
0x15dd1d  ldloca.s 8
0x15dd1f  ldloca.s 9
0x15dd21  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x15dd26  ldarg.0
0x15dd27  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dd2c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15dd31  ldc.i4.s 0xF
0x15dd33  beq.s    loc_15DD45
0x15dd35  ldarg.0
0x15dd36  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dd3b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15dd40  brtrue   loc_15DC93
0x15dd45  ldarg.0
0x15dd46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x15dd4b  ldloc.2
0x15dd4c  ldarg.0
0x15dd4d  ldloc.s  6
0x15dd4f  ldloc.s  7
0x15dd51  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15dd56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15dd5b  ldc.i4.0
0x15dd5c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x15dd61  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15dd66  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x15dd6b  br       loc_15E2D6
0x15dd70  ldarg.0
0x15dd71  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dd76  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15dd7b  ldarg.0
0x15dd7c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3306_QuerySet
0x15dd81  bne.un   loc_15DECE
0x15dd86  ldarg.0
0x15dd87  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dd8c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15dd91  ldarg.0
0x15dd92  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15dd97  bne.un   loc_15DECE
0x15dd9c  ldarg.0
0x15dd9d  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15dda2  brtrue   loc_15E2D6
0x15dda7  ldnull
0x15dda8  stloc.s  0xA
0x15ddaa  ldc.i4.0
0x15ddab  stloc.s  0xB
0x15ddad  ldarg.0
0x15ddae  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ddb3  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15ddb8  brfalse.s loc_15DDCA
0x15ddba  ldarg.0
0x15ddbb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ddc0  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15ddc5  br       loc_15DEA9
0x15ddca  ldarg.0
0x15ddcb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ddd0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15ddd5  ldarg.0
0x15ddd6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15dddb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15dde0  pop
0x15dde1  ldc.i4.0
0x15dde2  stloc.s  0xC
0x15dde4  ldarg.0
0x15dde5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15ddea  stloc.s  0xD
0x15ddec  br       loc_15DE84
0x15ddf1  ldarg.0
0x15ddf2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ddf7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15ddfc  ldc.i4.1
0x15ddfd  bne.un.s loc_15DE62
0x15ddff  ldarg.0
0x15de00  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15de05  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15de0a  ldarg.0
0x15de0b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id366_QueryBase
0x15de10  bne.un.s loc_15DE54
0x15de12  ldarg.0
0x15de13  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15de18  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15de1d  ldarg.0
0x15de1e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15de23  bne.un.s loc_15DE54
0x15de25  ldarg.0
0x15de26  ldloc.s  0xA
0x15de28  ldloc.s  0xB
0x15de2a  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase
0x15de2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15de34  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15de39  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase[]
0x15de3e  stloc.s  0xA
0x15de40  ldloc.s  0xA
0x15de42  ldloc.s  0xB
0x15de44  dup
0x15de45  ldc.i4.1
0x15de46  add
0x15de47  stloc.s  0xB
0x15de49  ldarg.0
0x15de4a  ldc.i4.1
0x15de4b  ldc.i4.1
0x15de4c  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read577_QueryBase(bool isNullable, bool checkType)
0x15de51  stelem.ref
0x15de52  br.s     loc_15DE6E
0x15de54  ldarg.0
0x15de55  ldnull
0x15de56  ldstr    aHttpSchemasMic_73// "http://schemas.microsoft.com/crm/2007/W"...
0x15de5b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15de60  br.s     loc_15DE6E
0x15de62  ldarg.0
0x15de63  ldnull
0x15de64  ldstr    aHttpSchemasMic_73// "http://schemas.microsoft.com/crm/2007/W"...
0x15de69  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15de6e  ldarg.0
0x15de6f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15de74  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15de79  pop
0x15de7a  ldarg.0
0x15de7b  ldloca.s 0xC
0x15de7d  ldloca.s 0xD
0x15de7f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x15de84  ldarg.0
0x15de85  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
  ... truncated ...
```
