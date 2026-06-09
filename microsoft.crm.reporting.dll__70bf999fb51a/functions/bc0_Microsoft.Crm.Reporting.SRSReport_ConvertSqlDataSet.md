# Microsoft.Crm.Reporting.SRSReport::ConvertSqlDataSet

- ea: `0xbc0`
- end: `0xe8b`
- name: `Microsoft.Crm.Reporting.SRSReport::ConvertSqlDataSet`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x9b0`

## callees

- `0xbc0`
- `0xeb0`
- `0x15f0`
- `0x16c0`
- `0x1800`

## string_xrefs

- `0xbcb`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0xbc0  ldarg.1
0xbc1  ldstr    aQuery// "Query"
0xbc6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xbcb  ldstr    aCommandtext// "CommandText"
0xbd0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xbd5  stloc.0
0xbd6  ldloc.0
0xbd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xbdc  stloc.1
0xbdd  ldarg.0
0xbde  ldarg.1
0xbdf  ldarg.s  7
0xbe1  call     instance void Microsoft.Crm.Reporting.SRSReport::StoreOriginalCommandText(class [System.Xml]System.Xml.XmlNode dataset, class [System.Xml]System.Xml.XmlWriter writerOrgCommands)
0xbe6  ldstr    aW// "^\\w*="
0xbeb  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string)
0xbf0  ldloc.1
0xbf1  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0xbf6  brfalse.s loc_BF9
0xbf8  ret
0xbf9  ldstr    aSW02// "\\s+(\\w+\\.){0,2}"
0xbfe  ldstr    aFiltered// "Filtered"
0xc03  call     string [mscorlib]System.String::Concat(string, string)
0xc08  ldstr    aEntitynameWSAs// "(?<EntityName>\\w+)(\\s+as)?\\s+crmaf_"...
0xc0d  call     string [mscorlib]System.String::Concat(string, string)
0xc12  ldc.i4.3
0xc13  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xc18  ldloc.1
0xc19  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0xc1e  stloc.2
0xc1f  ldstr    asc_A38C// "="
0xc24  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xc29  stloc.3
0xc2a  ldc.i4.0
0xc2b  stloc.s  4
0xc2d  ldarg.0
0xc2e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0xc33  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xc38  ldstr    aReportparamete// "ReportParameters"
0xc3d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xc42  stloc.s  5
0xc44  ldloc.s  5
0xc46  stloc.s  6
0xc48  br       loc_E4A
0xc4d  ldstr    aCrmafDW// "crmaf_(\\d+_)?\\w+"
0xc52  ldc.i4.3
0xc53  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xc58  ldloc.1
0xc59  ldloc.2
0xc5a  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xc5f  ldloc.2
0xc60  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xc65  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32, int32)
0xc6a  stloc.s  7
0xc6c  ldloc.1
0xc6d  ldloc.s  7
0xc6f  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xc74  ldloc.s  7
0xc76  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xc7b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xc80  stloc.s  8
0xc82  ldarg.s  6
0xc84  ldloc.s  8
0xc86  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xc8b  brtrue   loc_DAC
0xc90  br.s     loc_C9A
0xc92  ldarg.s  9
0xc94  ldarg.s  9
0xc96  ldind.i4
0xc97  ldc.i4.1
0xc98  add
0xc99  stind.i4
0xc9a  ldarg.0
0xc9b  ldloc.s  5
0xc9d  ldarg.s  9
0xc9f  ldind.i4
0xca0  call     instance bool Microsoft.Crm.Reporting.SRSReport::FindFilterParam(class [System.Xml]System.Xml.XmlNode rdlParams, int32 idParam)
0xca5  brtrue.s loc_C92
0xca7  ldstr    aP// "P"
0xcac  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xcb1  dup
0xcb2  ldarg.s  9
0xcb4  ldind.i4
0xcb5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0xcba  pop
0xcbb  ldloc.2
0xcbc  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0xcc1  ldstr    aEntityname// "EntityName"
0xcc6  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0xccb  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0xcd0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xcd5  ldstr    aD_0// "_\\d+_"
0xcda  ldc.i4.3
0xcdb  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xce0  ldloc.1
0xce1  ldloc.s  7
0xce3  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xce8  ldloc.s  7
0xcea  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xcef  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32, int32)
0xcf4  stloc.s  9
0xcf6  ldnull
0xcf7  stloc.s  0xA
0xcf9  ldloc.s  9
0xcfb  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0xd00  brfalse.s loc_D2B
0xd02  ldloc.1
0xd03  ldloc.s  9
0xd05  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xd0a  ldc.i4.1
0xd0b  add
0xd0c  ldloc.s  9
0xd0e  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xd13  ldc.i4.2
0xd14  sub
0xd15  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xd1a  callvirt instance string [mscorlib]System.Object::ToString()
0xd1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd24  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xd29  stloc.s  0xA
0xd2b  callvirt instance string [mscorlib]System.Object::ToString()
0xd30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd35  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xd3a  stloc.s  0xB
0xd3c  callvirt instance string [mscorlib]System.Object::ToString()
0xd41  stloc.s  0xC
0xd43  ldarg.0
0xd44  ldarg.s  8
0xd46  ldarg.s  4
0xd48  ldarg.2
0xd49  ldarg.3
0xd4a  ldloc.s  0xB
0xd4c  ldloc.s  0xA
0xd4e  ldloc.s  0xC
0xd50  ldarg.s  5
0xd52  call     instance string Microsoft.Crm.Reporting.SRSReport::AddDefaultFilterEntity(class [System.Xml]System.Xml.XmlDocument defaultFilterDoc, class Microsoft.Crm.Reporting.ReportQueryBuilder rptQueryBuilder, class [System.Xml]System.Xml.XmlNode origFilterNode, class [System.Xml]System.Xml.XmlNode storedFilterNode, string entityName, string afNumber, string paramName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd57  stloc.s  0xD
0xd59  ldloc.s  0xD
0xd5b  brfalse.s loc_DAC
0xd5d  ldloc.s  6
0xd5f  brtrue.s loc_D91
0xd61  ldarg.0
0xd62  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0xd67  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xd6c  stloc.s  0xE
0xd6e  ldarg.0
0xd6f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0xd74  ldstr    aReportparamete// "ReportParameters"
0xd79  ldloc.s  0xE
0xd7b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0xd80  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xd85  stloc.s  6
0xd87  ldloc.s  0xE
0xd89  ldloc.s  6
0xd8b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xd90  pop
0xd91  ldarg.s  9
0xd93  ldarg.0
0xd94  ldloc.s  6
0xd96  ldarg.s  9
0xd98  ldind.i4
0xd99  ldloc.s  0xD
0xd9b  call     instance int32 Microsoft.Crm.Reporting.SRSReport::AddFilterParam(class [System.Xml]System.Xml.XmlElement parentParam, int32 idParam, string strDefault)
0xda0  stind.i4
0xda1  ldarg.s  6
0xda3  ldloc.s  8
0xda5  ldloc.s  0xC
0xda7  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xdac  ldarg.s  6
0xdae  ldloc.s  8
0xdb0  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xdb5  brfalse  loc_E43
0xdba  ldarg.s  6
0xdbc  ldloc.s  8
0xdbe  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xdc3  castclass [mscorlib]System.String
0xdc8  stloc.s  0xF
0xdca  ldloc.3
0xdcb  ldloc.1
0xdcc  ldloc.s  4
0xdce  ldloc.2
0xdcf  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xdd4  ldloc.s  4
0xdd6  sub
0xdd7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xddc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmVBScriptEncode(string)
0xde1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xde6  pop
0xde7  ldloc.3
0xde8  ldstr    aParameters// " & \" (\" & Parameters!"
0xded  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdf2  pop
0xdf3  ldloc.3
0xdf4  ldloc.s  0xF
0xdf6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdfb  pop
0xdfc  ldloc.3
0xdfd  ldstr    aValueAs// ".Value & \") as \" & "
0xe02  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe07  pop
0xe08  ldloc.3
0xe09  ldloc.1
0xe0a  ldloc.s  7
0xe0c  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xe11  ldloc.s  7
0xe13  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xe18  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe1d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmVBScriptEncode(string)
0xe22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe27  pop
0xe28  ldloc.3
0xe29  ldstr    asc_A44E// " & \" \" & "
0xe2e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe33  pop
0xe34  ldloc.2
0xe35  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0xe3a  ldloc.2
0xe3b  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0xe40  add
0xe41  stloc.s  4
0xe43  ldloc.2
0xe44  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Match::NextMatch()
0xe49  stloc.2
0xe4a  ldloc.2
0xe4b  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0xe50  brtrue   loc_C4D
0xe55  ldloc.s  4
0xe57  brfalse.s loc_E83
0xe59  ldloc.3
0xe5a  ldloc.1
0xe5b  ldloc.s  4
0xe5d  ldloc.1
0xe5e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe63  ldloc.s  4
0xe65  sub
0xe66  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe6b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmVBScriptEncode(string)
0xe70  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe75  pop
0xe76  ldloc.0
0xe77  ldloc.3
0xe78  callvirt instance string [mscorlib]System.Object::ToString()
0xe7d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xe82  ret
0xe83  ldloc.0
0xe84  ldloc.1
0xe85  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xe8a  ret
```
