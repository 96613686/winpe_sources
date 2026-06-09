# Microsoft.Crm.Sdk.Messages.RecentItem::.ctor_0

- ea: `0x1040`
- end: `0x1225`
- name: `Microsoft.Crm.Sdk.Messages.RecentItem::.ctor_0`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xc40`
- `0xc60`
- `0xc80`
- `0xca0`
- `0xcc0`
- `0xce0`
- `0xd20`
- `0xd50`
- `0xd70`
- `0xd90`
- `0xda0`
- `0xdb0`
- `0xdd0`
- `0xdf0`
- `0x1040`

## string_xrefs

- `0x1121`: `IconPath`
- `0x1189`: `ProcessId`
- `0x11d4`: `LastAccessed`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldarg.0
0x1041  call     instance void [mscorlib]System.Object::.ctor()
0x1046  ldc.i4.m1
0x1047  stloc.0
0x1048  ldarg.1
0x1049  ldstr    aType// "Type"
0x104e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1053  stloc.1
0x1054  ldloc.1
0x1055  brfalse.s loc_1072
0x1057  ldloc.1
0x1058  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x105d  ldloca.s 0
0x105f  call     T0x2B000001
0x1064  brfalse.s loc_1072
0x1066  ldarg.0
0x1067  ldloc.0
0x1068  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType>::.ctor(var<u1>)
0x106d  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_RecordType(valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType> value)
0x1072  ldarg.0
0x1073  ldarg.1
0x1074  ldstr    aObjectid// "ObjectId"
0x1079  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x107e  dup
0x107f  brtrue.s loc_1085
0x1081  pop
0x1082  ldnull
0x1083  br.s     loc_108A
0x1085  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x108a  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_ObjectId(string value)
0x108f  ldarg.0
0x1090  ldarg.1
0x1091  ldstr    aTitle// "Title"
0x1096  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x109b  dup
0x109c  brtrue.s loc_10A2
0x109e  pop
0x109f  ldnull
0x10a0  br.s     loc_10A7
0x10a2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10a7  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_Title(string value)
0x10ac  ldarg.0
0x10ad  ldarg.1
0x10ae  ldstr    aDisplayname// "DisplayName"
0x10b3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x10b8  dup
0x10b9  brtrue.s loc_10BF
0x10bb  pop
0x10bc  ldnull
0x10bd  br.s     loc_10C4
0x10bf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10c4  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_DisplayName(string value)
0x10c9  ldarg.1
0x10ca  ldstr    aAction// "Action"
0x10cf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x10d4  stloc.2
0x10d5  ldloc.2
0x10d6  brfalse.s loc_111F
0x10d8  ldarg.0
0x10d9  ldloc.2
0x10da  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10df  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_Action(string value)
0x10e4  ldarg.0
0x10e5  call     instance valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType> Microsoft.Crm.Sdk.Messages.RecentItem::get_RecordType()
0x10ea  stloc.s  9
0x10ec  ldc.i4.1
0x10ed  stloc.s  0xA
0x10ef  ldloca.s 9
0x10f1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType>::GetValueOrDefault()
0x10f6  ldloc.s  0xA
0x10f8  ceq
0x10fa  ldloca.s 9
0x10fc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType>::get_HasValue()
0x1101  and
0x1102  brfalse.s loc_111F
0x1104  ldarg.0
0x1105  ldloc.2
0x1106  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x110b  ldstr    aViewtype4230// "viewtype=4230"
0x1110  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1115  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x111a  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_IsUserView(valuetype [mscorlib]System.Nullable`1<bool> value)
0x111f  ldarg.0
0x1120  ldarg.1
0x1121  ldstr    aIconpath// "IconPath"
0x1126  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x112b  dup
0x112c  brtrue.s loc_1132
0x112e  pop
0x112f  ldnull
0x1130  br.s     loc_1137
0x1132  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1137  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_IconPath(string value)
0x113c  ldarg.1
0x113d  ldstr    aPinstatus// "PinStatus"
0x1142  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1147  stloc.3
0x1148  ldc.i4.0
0x1149  stloc.s  4
0x114b  ldloc.3
0x114c  brfalse.s loc_116A
0x114e  ldloc.3
0x114f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1154  ldloca.s 4
0x1156  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x115b  brfalse.s loc_116A
0x115d  ldarg.0
0x115e  ldloc.s  4
0x1160  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1165  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_PinStatus(valuetype [mscorlib]System.Nullable`1<bool> value)
0x116a  ldarg.0
0x116b  ldarg.1
0x116c  ldstr    aProcessinstanc// "ProcessInstanceId"
0x1171  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1176  dup
0x1177  brtrue.s loc_117D
0x1179  pop
0x117a  ldnull
0x117b  br.s     loc_1182
0x117d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1182  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_ProcessInstanceId(string value)
0x1187  ldarg.0
0x1188  ldarg.1
0x1189  ldstr    aProcessid// "ProcessId"
0x118e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1193  dup
0x1194  brtrue.s loc_119A
0x1196  pop
0x1197  ldnull
0x1198  br.s     loc_119F
0x119a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x119f  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_ProcessId(string value)
0x11a4  ldarg.1
0x11a5  ldstr    aEntitytypecode// "EntityTypeCode"
0x11aa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x11af  stloc.s  5
0x11b1  ldloc.s  5
0x11b3  brfalse.s loc_11D3
0x11b5  ldloc.s  5
0x11b7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x11bc  ldc.i4.7
0x11bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c2  ldloca.s 6
0x11c4  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x11c9  brfalse.s loc_11D3
0x11cb  ldarg.0
0x11cc  ldloc.s  6
0x11ce  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_EntityTypeCode(int32 value)
0x11d3  ldarg.1
0x11d4  ldstr    aLastaccessed// "LastAccessed"
0x11d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x11de  stloc.s  7
0x11e0  ldloc.s  7
0x11e2  brfalse.s loc_1210
0x11e4  ldloc.s  7
0x11e6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x11eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11f0  brtrue.s loc_1210
0x11f2  ldloc.s  7
0x11f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x11f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11fe  ldc.i4.0
0x11ff  ldloca.s 8
0x1201  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x1206  brfalse.s loc_1210
0x1208  ldarg.0
0x1209  ldloc.s  8
0x120b  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_LastAccessed(valuetype [mscorlib]System.DateTime value)
0x1210  ldarg.0
0x1211  ldloc.s  7
0x1213  brtrue.s loc_1218
0x1215  ldnull
0x1216  br.s     loc_121F
0x1218  ldloc.s  7
0x121a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x121f  call     instance void Microsoft.Crm.Sdk.Messages.RecentItem::set_LastAccessedStr(string value)
0x1224  ret
```
