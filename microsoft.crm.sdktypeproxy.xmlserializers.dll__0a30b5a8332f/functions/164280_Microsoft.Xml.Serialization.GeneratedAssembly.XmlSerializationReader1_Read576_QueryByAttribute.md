# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read576_QueryByAttribute

- ea: `0x164280`
- end: `0x16489f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read576_QueryByAttribute`
- size: `1567`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b120`
- `0x7c020`

## callees

- `0x7b6e0`
- `0x7c020`
- `0x103c60`
- `0x11e190`
- `0x164280`

## string_xrefs

- `0x1644ec`: `http://schemas.microsoft.com/crm/2006/Query:Attribute`
- `0x1644fa`: `http://schemas.microsoft.com/crm/2006/Query:Attribute`
- `0x16464a`: `http://schemas.microsoft.com/crm/2006/Query:Value`
- `0x164658`: `http://schemas.microsoft.com/crm/2006/Query:Value`
- `0x1647f3`: `http://schemas.microsoft.com/crm/2006/Query:Order`
- `0x164801`: `http://schemas.microsoft.com/crm/2006/Query:Order`
- `0x16484a`: `http://schemas.microsoft.com/crm/2006/Query:EntityName, http://schemas.microsoft.com/crm/2006/Query:ColumnSet, http://schemas.microsoft.com/crm/2006/Query:Attributes, http://schemas.microsoft.com/crm/2006/Query:Values, http://schemas.microsoft.com/crm/2006/Query:PageInfo, http://schemas.microsoft.com/crm/2006/Query:Orders`
- `0x164858`: `http://schemas.microsoft.com/crm/2006/Query:EntityName, http://schemas.microsoft.com/crm/2006/Query:ColumnSet, http://schemas.microsoft.com/crm/2006/Query:Attributes, http://schemas.microsoft.com/crm/2006/Query:Values, http://schemas.microsoft.com/crm/2006/Query:PageInfo, http://schemas.microsoft.com/crm/2006/Query:Orders`

## pseudocode

```c

```

## disassembly

```asm
0x164280  ldarg.2
0x164281  brtrue.s loc_164286
0x164283  ldnull
0x164284  br.s     loc_16428C
0x164286  ldarg.0
0x164287  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x16428c  stloc.0
0x16428d  ldc.i4.0
0x16428e  stloc.1
0x16428f  ldarg.1
0x164290  brfalse.s loc_164299
0x164292  ldarg.0
0x164293  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x164298  stloc.1
0x164299  ldarg.2
0x16429a  brfalse.s loc_1642C9
0x16429c  ldloc.0
0x16429d  ldnull
0x16429e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1642a3  brtrue.s loc_1642C9
0x1642a5  ldloc.0
0x1642a6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1642ab  ldarg.0
0x1642ac  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id420_QueryByAttribute
0x1642b1  bne.un.s loc_1642C1
0x1642b3  ldloc.0
0x1642b4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1642b9  ldarg.0
0x1642ba  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x1642bf  beq.s    loc_1642C9
0x1642c1  ldarg.0
0x1642c2  ldloc.0
0x1642c3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x1642c8  throw
0x1642c9  ldloc.1
0x1642ca  brfalse.s loc_1642CE
0x1642cc  ldnull
0x1642cd  ret
0x1642ce  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::.ctor()
0x1642d3  stloc.2
0x1642d4  ldloc.2
0x1642d5  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_Orders()
0x1642da  brtrue.s loc_1642E7
0x1642dc  ldloc.2
0x1642dd  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x1642e2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::set_Orders(class [mscorlib]System.Collections.ArrayList)
0x1642e7  ldloc.2
0x1642e8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_Orders()
0x1642ed  pop
0x1642ee  ldc.i4.6
0x1642ef  newarr   [mscorlib]System.Boolean
0x1642f4  stloc.3
0x1642f5  br.s     loc_164311
0x1642f7  ldarg.0
0x1642f8  ldarg.0
0x1642f9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1642fe  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x164303  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x164308  brtrue.s loc_164311
0x16430a  ldarg.0
0x16430b  ldloc.2
0x16430c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x164311  ldarg.0
0x164312  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164317  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x16431c  brtrue.s loc_1642F7
0x16431e  ldarg.0
0x16431f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164324  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x164329  pop
0x16432a  ldarg.0
0x16432b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164330  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x164335  brfalse.s loc_164344
0x164337  ldarg.0
0x164338  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16433d  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x164342  ldloc.2
0x164343  ret
0x164344  ldarg.0
0x164345  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16434a  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x16434f  ldarg.0
0x164350  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164355  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x16435a  pop
0x16435b  ldc.i4.0
0x16435c  stloc.s  4
0x16435e  ldarg.0
0x16435f  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x164364  stloc.s  5
0x164366  br       loc_164878
0x16436b  ldarg.0
0x16436c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164371  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x164376  ldc.i4.1
0x164377  bne.un   loc_164856
0x16437c  ldloc.3
0x16437d  ldc.i4.0
0x16437e  ldelem.i1
0x16437f  brtrue.s loc_1643C1
0x164381  ldarg.0
0x164382  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164387  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x16438c  ldarg.0
0x16438d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id337_EntityName
0x164392  bne.un.s loc_1643C1
0x164394  ldarg.0
0x164395  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16439a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x16439f  ldarg.0
0x1643a0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x1643a5  bne.un.s loc_1643C1
0x1643a7  ldloc.2
0x1643a8  ldarg.0
0x1643a9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1643ae  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1643b3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0x1643b8  ldloc.3
0x1643b9  ldc.i4.0
0x1643ba  ldc.i4.1
0x1643bb  stelem.i1
0x1643bc  br       loc_164862
0x1643c1  ldloc.3
0x1643c2  ldc.i4.1
0x1643c3  ldelem.i1
0x1643c4  brtrue.s loc_164403
0x1643c6  ldarg.0
0x1643c7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1643cc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1643d1  ldarg.0
0x1643d2  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id422_ColumnSet
0x1643d7  bne.un.s loc_164403
0x1643d9  ldarg.0
0x1643da  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1643df  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1643e4  ldarg.0
0x1643e5  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x1643ea  bne.un.s loc_164403
0x1643ec  ldloc.2
0x1643ed  ldarg.0
0x1643ee  ldc.i4.0
0x1643ef  ldc.i4.1
0x1643f0  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read565_ColumnSetBase(bool isNullable, bool checkType)
0x1643f5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x1643fa  ldloc.3
0x1643fb  ldc.i4.1
0x1643fc  ldc.i4.1
0x1643fd  stelem.i1
0x1643fe  br       loc_164862
0x164403  ldarg.0
0x164404  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164409  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x16440e  ldarg.0
0x16440f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id71_Attributes
0x164414  bne.un   loc_164564
0x164419  ldarg.0
0x16441a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16441f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x164424  ldarg.0
0x164425  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x16442a  bne.un   loc_164564
0x16442f  ldarg.0
0x164430  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x164435  brtrue   loc_164862
0x16443a  ldnull
0x16443b  stloc.s  6
0x16443d  ldc.i4.0
0x16443e  stloc.s  7
0x164440  ldarg.0
0x164441  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164446  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x16444b  brfalse.s loc_16445D
0x16444d  ldarg.0
0x16444e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164453  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x164458  br       loc_16453F
0x16445d  ldarg.0
0x16445e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164463  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x164468  ldarg.0
0x164469  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16446e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x164473  pop
0x164474  ldc.i4.0
0x164475  stloc.s  8
0x164477  ldarg.0
0x164478  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x16447d  stloc.s  9
0x16447f  br       loc_16451A
0x164484  ldarg.0
0x164485  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16448a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x16448f  ldc.i4.1
0x164490  bne.un.s loc_1644F8
0x164492  ldarg.0
0x164493  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164498  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x16449d  ldarg.0
0x16449e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id72_Attribute
0x1644a3  bne.un.s loc_1644EA
0x1644a5  ldarg.0
0x1644a6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1644ab  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1644b0  ldarg.0
0x1644b1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x1644b6  bne.un.s loc_1644EA
0x1644b8  ldarg.0
0x1644b9  ldloc.s  6
0x1644bb  ldloc.s  7
0x1644bd  ldtoken  [mscorlib]System.String
0x1644c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1644c7  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1644cc  castclass string[]
0x1644d1  stloc.s  6
0x1644d3  ldloc.s  6
0x1644d5  ldloc.s  7
0x1644d7  dup
0x1644d8  ldc.i4.1
0x1644d9  add
0x1644da  stloc.s  7
0x1644dc  ldarg.0
0x1644dd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1644e2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1644e7  stelem.ref
0x1644e8  br.s     loc_164504
0x1644ea  ldarg.0
0x1644eb  ldnull
0x1644ec  ldstr    aHttpSchemasMic_53// "http://schemas.microsoft.com/crm/2006/Q"...
0x1644f1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1644f6  br.s     loc_164504
0x1644f8  ldarg.0
0x1644f9  ldnull
0x1644fa  ldstr    aHttpSchemasMic_53// "http://schemas.microsoft.com/crm/2006/Q"...
0x1644ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x164504  ldarg.0
0x164505  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16450a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x16450f  pop
0x164510  ldarg.0
0x164511  ldloca.s 8
0x164513  ldloca.s 9
0x164515  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x16451a  ldarg.0
0x16451b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164520  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x164525  ldc.i4.s 0xF
0x164527  beq.s    loc_164539
0x164529  ldarg.0
0x16452a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16452f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x164534  brtrue   loc_164484
0x164539  ldarg.0
0x16453a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x16453f  ldloc.2
0x164540  ldarg.0
0x164541  ldloc.s  6
0x164543  ldloc.s  7
0x164545  ldtoken  [mscorlib]System.String
0x16454a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16454f  ldc.i4.0
0x164550  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x164555  castclass string[]
0x16455a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::set_Attributes(string[])
0x16455f  br       loc_164862
0x164564  ldarg.0
0x164565  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16456a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x16456f  ldarg.0
0x164570  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id436_Values
0x164575  bne.un   loc_1646C2
0x16457a  ldarg.0
0x16457b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x164580  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x164585  ldarg.0
0x164586  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id309_Item
0x16458b  bne.un   loc_1646C2
0x164590  ldarg.0
0x164591  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x164596  brtrue   loc_164862
0x16459b  ldnull
0x16459c  stloc.s  0xA
0x16459e  ldc.i4.0
0x16459f  stloc.s  0xB
0x1645a1  ldarg.0
0x1645a2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1645a7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1645ac  brfalse.s loc_1645BE
0x1645ae  ldarg.0
0x1645af  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1645b4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1645b9  br       loc_16469D
0x1645be  ldarg.0
0x1645bf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1645c4  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1645c9  ldarg.0
0x1645ca  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1645cf  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1645d4  pop
0x1645d5  ldc.i4.0
  ... truncated ...
```
