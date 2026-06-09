# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress_1

- ea: `0x68720`
- end: `0x68bb7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress_1`
- size: `1175`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1e7a0`
- `0x4d8a0`
- `0x577f0`
- `0x586e0`
- `0x5aa20`
- `0x5ac40`
- `0x5b2a0`
- `0x5b560`
- `0x5bc10`
- `0x5be30`
- `0x68700`

## callees

- `0x33df0`
- `0x68380`
- `0x68720`
- `0x68bc0`
- `0x68c00`
- `0x68d20`
- `0x68db0`

## string_xrefs

- `0x68a82`: `importexportxml`
- `0x68aa3`: `importexportxml`
- `0x68aff`: `importexportxml`

## pseudocode

```c

```

## disassembly

```asm
0x68720  ldarg.0
0x68721  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68726  brfalse  loc_68BB6
0x6872b  ldarg.1
0x6872c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x68731  brtrue   loc_68BB6
0x68736  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6873b  box      [mscorlib]System.Guid
0x68740  ldarg.0
0x68741  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_importJobId
0x68746  box      [mscorlib]System.Guid
0x6874b  call     bool [mscorlib]System.Object::Equals(object, object)
0x68750  brtrue   loc_68BB6
0x68755  ldarg.0
0x68756  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x6875b  ldarg.1
0x6875c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x68761  brtrue   loc_6887E
0x68766  ldarg.2
0x68767  ldstr    aFailure// "failure"
0x6876c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x68771  brtrue.s loc_68790
0x68773  ldarg.2
0x68774  ldstr    aWarning// "warning"
0x68779  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6877e  brtrue.s loc_68790
0x68780  ldarg.2
0x68781  ldstr    aSuccess// "success"
0x68786  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6878b  brfalse  loc_6887E
0x68790  ldarg.1
0x68791  ldc.i4.4
0x68792  newarr   [mscorlib]System.Char
0x68797  dup
0x68798  ldtoken  int64 <PrivateImplementationDetails>::'9E2D3E38C1E888B263516D4D589318C940EA3CD4'
0x6879d  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x687a2  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x687a7  stloc.0
0x687a8  ldarg.0
0x687a9  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x687ae  ldloc.0
0x687af  ldc.i4.1
0x687b0  ldelem.ref
0x687b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x687b6  stloc.1
0x687b7  ldloc.1
0x687b8  brfalse  loc_6887E
0x687bd  ldloc.0
0x687be  ldlen
0x687bf  conv.i4
0x687c0  ldc.i4.3
0x687c1  ble      loc_6887E
0x687c6  ldloc.1
0x687c7  ldloc.0
0x687c8  ldc.i4.2
0x687c9  ldelem.ref
0x687ca  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x687cf  stloc.2
0x687d0  ldloc.2
0x687d1  brtrue.s loc_687F0
0x687d3  ldarg.0
0x687d4  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x687d9  ldc.i4.1
0x687da  ldloc.0
0x687db  ldc.i4.2
0x687dc  ldelem.ref
0x687dd  ldsfld   string [mscorlib]System.String::Empty
0x687e2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x687e7  stloc.2
0x687e8  ldloc.1
0x687e9  ldloc.2
0x687ea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x687ef  pop
0x687f0  ldloc.2
0x687f1  brfalse  loc_6887E
0x687f6  ldarg.0
0x687f7  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x687fc  ldc.i4.1
0x687fd  ldloc.0
0x687fe  ldc.i4.3
0x687ff  ldelem.ref
0x68800  ldsfld   string [mscorlib]System.String::Empty
0x68805  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x6880a  stloc.3
0x6880b  ldloc.2
0x6880c  ldloc.3
0x6880d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x68812  pop
0x68813  ldloc.3
0x68814  brfalse.s loc_6887E
0x68816  ldloc.0
0x68817  ldlen
0x68818  conv.i4
0x68819  ldc.i4.5
0x6881a  ble.s    loc_6887E
0x6881c  ldarg.0
0x6881d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68822  ldc.i4.2
0x68823  ldstr    aProcessed// "processed"
0x68828  ldsfld   string [mscorlib]System.String::Empty
0x6882d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68832  stloc.s  4
0x68834  ldloc.s  4
0x68836  ldstr    aFalse// "false"
0x6883b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68840  ldloc.3
0x68841  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x68846  ldloc.s  4
0x68848  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x6884d  pop
0x6884e  ldarg.0
0x6884f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68854  ldc.i4.2
0x68855  ldstr    aId// "id"
0x6885a  ldsfld   string [mscorlib]System.String::Empty
0x6885f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68864  stloc.s  5
0x68866  ldloc.s  5
0x68868  ldloc.0
0x68869  ldc.i4.5
0x6886a  ldelem.ref
0x6886b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68870  ldloc.3
0x68871  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x68876  ldloc.s  5
0x68878  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x6887d  pop
0x6887e  ldarg.0
0x6887f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68884  ldarg.1
0x68885  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6888a  stloc.s  6
0x6888c  ldloc.s  6
0x6888e  brfalse  loc_68BA8
0x68893  ldloc.s  6
0x68895  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6889a  stloc.s  7
0x6889c  br       loc_68A59
0x688a1  ldloc.s  7
0x688a3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x688a8  castclass [System.Xml]System.Xml.XmlNode
0x688ad  stloc.s  8
0x688af  ldloc.s  8
0x688b1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x688b6  ldstr    aProcessed// "processed"
0x688bb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x688c0  stloc.s  9
0x688c2  ldloc.s  9
0x688c4  brfalse.s loc_688DD
0x688c6  ldloc.s  9
0x688c8  ldarg.s  4
0x688ca  brtrue.s loc_688D3
0x688cc  ldstr    aFalse// "false"
0x688d1  br.s     loc_688D8
0x688d3  ldstr    aTrue// "true"
0x688d8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x688dd  ldarg.s  5
0x688df  brfalse.s loc_688ED
0x688e1  ldloc.s  8
0x688e3  ldsfld   string [mscorlib]System.String::Empty
0x688e8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x688ed  ldarg.0
0x688ee  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x688f3  ldc.i4.1
0x688f4  ldstr    aResult// "result"
0x688f9  ldsfld   string [mscorlib]System.String::Empty
0x688fe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68903  stloc.s  0xA
0x68905  ldloc.s  8
0x68907  ldloc.s  0xA
0x68909  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6890e  pop
0x6890f  ldarg.0
0x68910  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68915  ldc.i4.2
0x68916  ldstr    aResult// "result"
0x6891b  ldsfld   string [mscorlib]System.String::Empty
0x68920  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68925  stloc.s  0xB
0x68927  ldloc.s  0xB
0x68929  ldarg.2
0x6892a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x6892f  ldloc.s  0xA
0x68931  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x68936  ldloc.s  0xB
0x68938  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x6893d  pop
0x6893e  ldarg.0
0x6893f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68944  ldc.i4.2
0x68945  ldstr    aErrorcode_0// "errorcode"
0x6894a  ldsfld   string [mscorlib]System.String::Empty
0x6894f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68954  stloc.s  0xC
0x68956  ldloc.s  0xC
0x68958  ldarg.0
0x68959  ldarg.3
0x6895a  ldarg.s  7
0x6895c  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetExceptionCode(class [mscorlib]System.Exception ex, [opt] int32 errorCode)
0x68961  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68966  ldloc.s  0xA
0x68968  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6896d  ldloc.s  0xC
0x6896f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x68974  pop
0x68975  ldarg.0
0x68976  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x6897b  ldc.i4.2
0x6897c  ldstr    aErrortext_0// "errortext"
0x68981  ldsfld   string [mscorlib]System.String::Empty
0x68986  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x6898b  stloc.s  0xD
0x6898d  ldloc.s  0xD
0x6898f  ldarg.0
0x68990  ldarg.3
0x68991  ldarg.s  6
0x68993  ldarg.s  7
0x68995  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetErrorText(class [mscorlib]System.Exception ex, bool ignoreInnerException, [opt] int32 errorCode)
0x6899a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x6899f  ldloc.s  0xA
0x689a1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x689a6  ldloc.s  0xD
0x689a8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x689ad  pop
0x689ae  ldarg.0
0x689af  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x689b4  ldc.i4.2
0x689b5  ldstr    aDatetime_0// "datetime"
0x689ba  ldsfld   string [mscorlib]System.String::Empty
0x689bf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x689c4  stloc.s  0xE
0x689c6  ldloc.s  0xE
0x689c8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x689cd  stloc.s  0x10
0x689cf  ldloca.s 0x10
0x689d1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x689d6  stloc.s  0x10
0x689d8  ldloca.s 0x10
0x689da  ldstr    aHhMmSsFf// "HH:mm:ss.ff"
0x689df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x689e4  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x689e9  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x689ee  ldloc.s  0xA
0x689f0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x689f5  ldloc.s  0xE
0x689f7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x689fc  pop
0x689fd  ldarg.0
0x689fe  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68a03  ldc.i4.2
0x68a04  ldstr    aDatetimeticks// "datetimeticks"
0x68a09  ldsfld   string [mscorlib]System.String::Empty
0x68a0e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x68a13  stloc.s  0xF
0x68a15  ldloc.s  0xF
0x68a17  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x68a1c  stloc.s  0x10
0x68a1e  ldloca.s 0x10
0x68a20  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x68a25  stloc.s  0x10
0x68a27  ldloca.s 0x10
0x68a29  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x68a2e  stloc.s  0x11
0x68a30  ldloca.s 0x11
0x68a32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68a37  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x68a3c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68a41  ldloc.s  0xA
0x68a43  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x68a48  ldloc.s  0xF
0x68a4a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x68a4f  pop
0x68a50  ldarg.0
0x68a51  ldloc.s  0xA
0x68a53  ldarg.3
0x68a54  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetParameters(class [System.Xml]System.Xml.XmlNode resultNode, class [mscorlib]System.Exception ex)
0x68a59  ldloc.s  7
0x68a5b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x68a60  brtrue   loc_688A1
0x68a65  leave.s  loc_68A7C
0x68a67  ldloc.s  7
0x68a69  isinst   [mscorlib]System.IDisposable
0x68a6e  stloc.s  0x12
0x68a70  ldloc.s  0x12
0x68a72  brfalse.s loc_68A7B
0x68a74  ldloc.s  0x12
0x68a76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68a7b  endfinally
0x68a7c  ldarg.0
0x68a7d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68a82  ldstr    aImportexportxm_95// "importexportxml"
0x68a87  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x68a8c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x68a91  ldstr    aStop// "stop"
0x68a96  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x68a9b  brfalse.s loc_68ADD
0x68a9d  ldarg.0
0x68a9e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68aa3  ldstr    aImportexportxm_95// "importexportxml"
0x68aa8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
  ... truncated ...
```
