# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1275_BulkDetectDuplicatesRequest

- ea: `0x15d410`
- end: `0x15db22`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1275_BulkDetectDuplicatesRequest`
- size: `1810`
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
- `0x15d410`

## string_xrefs

- `0x15d5d9`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15d5e7`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15d863`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15d871`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15d9d2`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15d9e0`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15dacd`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:Query, http://schemas.microsoft.com/crm/2007/WebServices:JobName, http://schemas.microsoft.com/crm/2007/WebServices:SendEmailNotification, http://schemas.microsoft.com/crm/2007/WebServices:TemplateId, http://schemas.microsoft.com/crm/2007/WebServices:ToRecipients, http://schemas.microsoft.com/crm/2007/WebServices:CCRecipients, http://schemas.microsoft.com/crm/2007/WebServices:R`
- `0x15dadb`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:Query, http://schemas.microsoft.com/crm/2007/WebServices:JobName, http://schemas.microsoft.com/crm/2007/WebServices:SendEmailNotification, http://schemas.microsoft.com/crm/2007/WebServices:TemplateId, http://schemas.microsoft.com/crm/2007/WebServices:ToRecipients, http://schemas.microsoft.com/crm/2007/WebServices:CCRecipients, http://schemas.microsoft.com/crm/2007/WebServices:R`

## pseudocode

```c

```

## disassembly

```asm
0x15d410  ldarg.2
0x15d411  brtrue.s loc_15D416
0x15d413  ldnull
0x15d414  br.s     loc_15D41C
0x15d416  ldarg.0
0x15d417  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x15d41c  stloc.0
0x15d41d  ldc.i4.0
0x15d41e  stloc.1
0x15d41f  ldarg.1
0x15d420  brfalse.s loc_15D429
0x15d422  ldarg.0
0x15d423  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15d428  stloc.1
0x15d429  ldarg.2
0x15d42a  brfalse.s loc_15D459
0x15d42c  ldloc.0
0x15d42d  ldnull
0x15d42e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x15d433  brtrue.s loc_15D459
0x15d435  ldloc.0
0x15d436  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x15d43b  ldarg.0
0x15d43c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1379_BulkDetectDuplicatesRequest
0x15d441  bne.un.s loc_15D451
0x15d443  ldloc.0
0x15d444  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x15d449  ldarg.0
0x15d44a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d44f  beq.s    loc_15D459
0x15d451  ldarg.0
0x15d452  ldloc.0
0x15d453  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x15d458  throw
0x15d459  ldloc.1
0x15d45a  brfalse.s loc_15D45E
0x15d45c  ldnull
0x15d45d  ret
0x15d45e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::.ctor()
0x15d463  stloc.2
0x15d464  ldc.i4.s 9
0x15d466  newarr   [mscorlib]System.Boolean
0x15d46b  stloc.3
0x15d46c  br.s     loc_15D488
0x15d46e  ldarg.0
0x15d46f  ldarg.0
0x15d470  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d475  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x15d47a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x15d47f  brtrue.s loc_15D488
0x15d481  ldarg.0
0x15d482  ldloc.2
0x15d483  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x15d488  ldarg.0
0x15d489  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d48e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x15d493  brtrue.s loc_15D46E
0x15d495  ldarg.0
0x15d496  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d49b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x15d4a0  pop
0x15d4a1  ldarg.0
0x15d4a2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4a7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15d4ac  brfalse.s loc_15D4BB
0x15d4ae  ldarg.0
0x15d4af  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4b4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15d4b9  ldloc.2
0x15d4ba  ret
0x15d4bb  ldarg.0
0x15d4bc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4c1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15d4c6  ldarg.0
0x15d4c7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4cc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15d4d1  pop
0x15d4d2  ldc.i4.0
0x15d4d3  stloc.s  4
0x15d4d5  ldarg.0
0x15d4d6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15d4db  stloc.s  5
0x15d4dd  br       loc_15DAFB
0x15d4e2  ldarg.0
0x15d4e3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4e8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15d4ed  ldc.i4.1
0x15d4ee  bne.un   loc_15DAD9
0x15d4f3  ldarg.0
0x15d4f4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d4f9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d4fe  ldarg.0
0x15d4ff  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x15d504  bne.un   loc_15D651
0x15d509  ldarg.0
0x15d50a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d50f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d514  ldarg.0
0x15d515  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d51a  bne.un   loc_15D651
0x15d51f  ldarg.0
0x15d520  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15d525  brtrue   loc_15DAE5
0x15d52a  ldnull
0x15d52b  stloc.s  6
0x15d52d  ldc.i4.0
0x15d52e  stloc.s  7
0x15d530  ldarg.0
0x15d531  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d536  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15d53b  brfalse.s loc_15D54D
0x15d53d  ldarg.0
0x15d53e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d543  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15d548  br       loc_15D62C
0x15d54d  ldarg.0
0x15d54e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d553  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15d558  ldarg.0
0x15d559  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d55e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15d563  pop
0x15d564  ldc.i4.0
0x15d565  stloc.s  8
0x15d567  ldarg.0
0x15d568  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15d56d  stloc.s  9
0x15d56f  br       loc_15D607
0x15d574  ldarg.0
0x15d575  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d57a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15d57f  ldc.i4.1
0x15d580  bne.un.s loc_15D5E5
0x15d582  ldarg.0
0x15d583  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d588  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d58d  ldarg.0
0x15d58e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x15d593  bne.un.s loc_15D5D7
0x15d595  ldarg.0
0x15d596  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d59b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d5a0  ldarg.0
0x15d5a1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d5a6  bne.un.s loc_15D5D7
0x15d5a8  ldarg.0
0x15d5a9  ldloc.s  6
0x15d5ab  ldloc.s  7
0x15d5ad  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15d5b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15d5b7  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15d5bc  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15d5c1  stloc.s  6
0x15d5c3  ldloc.s  6
0x15d5c5  ldloc.s  7
0x15d5c7  dup
0x15d5c8  ldc.i4.1
0x15d5c9  add
0x15d5ca  stloc.s  7
0x15d5cc  ldarg.0
0x15d5cd  ldc.i4.1
0x15d5ce  ldc.i4.1
0x15d5cf  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x15d5d4  stelem.ref
0x15d5d5  br.s     loc_15D5F1
0x15d5d7  ldarg.0
0x15d5d8  ldnull
0x15d5d9  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15d5de  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15d5e3  br.s     loc_15D5F1
0x15d5e5  ldarg.0
0x15d5e6  ldnull
0x15d5e7  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15d5ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15d5f1  ldarg.0
0x15d5f2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d5f7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15d5fc  pop
0x15d5fd  ldarg.0
0x15d5fe  ldloca.s 8
0x15d600  ldloca.s 9
0x15d602  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x15d607  ldarg.0
0x15d608  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d60d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15d612  ldc.i4.s 0xF
0x15d614  beq.s    loc_15D626
0x15d616  ldarg.0
0x15d617  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d61c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15d621  brtrue   loc_15D574
0x15d626  ldarg.0
0x15d627  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x15d62c  ldloc.2
0x15d62d  ldarg.0
0x15d62e  ldloc.s  6
0x15d630  ldloc.s  7
0x15d632  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15d637  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15d63c  ldc.i4.0
0x15d63d  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x15d642  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15d647  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x15d64c  br       loc_15DAE5
0x15d651  ldloc.3
0x15d652  ldc.i4.1
0x15d653  ldelem.i1
0x15d654  brtrue.s loc_15D693
0x15d656  ldarg.0
0x15d657  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d65c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d661  ldarg.0
0x15d662  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3150_Query
0x15d667  bne.un.s loc_15D693
0x15d669  ldarg.0
0x15d66a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d66f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d674  ldarg.0
0x15d675  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d67a  bne.un.s loc_15D693
0x15d67c  ldloc.2
0x15d67d  ldarg.0
0x15d67e  ldc.i4.0
0x15d67f  ldc.i4.1
0x15d680  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read577_QueryBase(bool isNullable, bool checkType)
0x15d685  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::set_Query(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase)
0x15d68a  ldloc.3
0x15d68b  ldc.i4.1
0x15d68c  ldc.i4.1
0x15d68d  stelem.i1
0x15d68e  br       loc_15DAE5
0x15d693  ldloc.3
0x15d694  ldc.i4.2
0x15d695  ldelem.i1
0x15d696  brtrue.s loc_15D6D8
0x15d698  ldarg.0
0x15d699  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d69e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d6a3  ldarg.0
0x15d6a4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3302_JobName
0x15d6a9  bne.un.s loc_15D6D8
0x15d6ab  ldarg.0
0x15d6ac  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d6b1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d6b6  ldarg.0
0x15d6b7  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d6bc  bne.un.s loc_15D6D8
0x15d6be  ldloc.2
0x15d6bf  ldarg.0
0x15d6c0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d6c5  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x15d6ca  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::set_JobName(string)
0x15d6cf  ldloc.3
0x15d6d0  ldc.i4.2
0x15d6d1  ldc.i4.1
0x15d6d2  stelem.i1
0x15d6d3  br       loc_15DAE5
0x15d6d8  ldloc.3
0x15d6d9  ldc.i4.3
0x15d6da  ldelem.i1
0x15d6db  brtrue.s loc_15D722
0x15d6dd  ldarg.0
0x15d6de  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d6e3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d6e8  ldarg.0
0x15d6e9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3303_SendEmailNotification
0x15d6ee  bne.un.s loc_15D722
0x15d6f0  ldarg.0
0x15d6f1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d6f6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d6fb  ldarg.0
0x15d6fc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d701  bne.un.s loc_15D722
0x15d703  ldloc.2
0x15d704  ldarg.0
0x15d705  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d70a  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x15d70f  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x15d714  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::set_SendEmailNotification(bool)
0x15d719  ldloc.3
0x15d71a  ldc.i4.3
0x15d71b  ldc.i4.1
0x15d71c  stelem.i1
0x15d71d  br       loc_15DAE5
0x15d722  ldloc.3
0x15d723  ldc.i4.4
0x15d724  ldelem.i1
0x15d725  brtrue.s loc_15D76C
0x15d727  ldarg.0
0x15d728  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d72d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15d732  ldarg.0
0x15d733  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3140_TemplateId
0x15d738  bne.un.s loc_15D76C
0x15d73a  ldarg.0
0x15d73b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15d740  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15d745  ldarg.0
0x15d746  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15d74b  bne.un.s loc_15D76C
  ... truncated ...
```
