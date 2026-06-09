# Microsoft.Crm.CrmTransaction::GetReferencedObjects

- ea: `0x10740`
- end: `0x10b19`
- name: `Microsoft.Crm.CrmTransaction::GetReferencedObjects`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x106a0`

## callees

- `0x10740`
- `0x10b20`

## string_xrefs

- `0x107e4`: `FindLiveReader`
- `0x107fc`: `null == findLiveReader`
- `0x10826`: `null == reader`
- `0x1083e`: `_command`
- `0x10856`: `null == commandField`
- `0x1089a`: `<Command timestampUTC="{0}">`
- `0x10abc`: `</Command>`

## pseudocode

```c

```

## disassembly

```asm
0x10740  ldarg.1
0x10741  ldnull
0x10742  stind.ref
0x10743  ldarg.0
0x10744  isinst   [System.Data]System.Data.SqlClient.SqlConnection
0x10749  stloc.0
0x1074a  ldloc.0
0x1074b  brtrue.s loc_1075E
0x1074d  ldstr    aCanTCastCrmdbc// "Can't cast crmDbconnection as SqlConnec"...
0x10752  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10757  stloc.s  8
0x10759  leave    loc_10B16
0x1075e  ldloc.0
0x1075f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10764  ldstr    aInnerconnectio// "_innerConnection"
0x10769  ldc.i4.s 0x24
0x1076b  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x10770  stloc.1
0x10771  ldnull
0x10772  ldloc.1
0x10773  call     bool [mscorlib]System.Reflection.FieldInfo::op_Equality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0x10778  brfalse.s loc_1078B
0x1077a  ldstr    aNullInnerconne// "null == innerConnectionField"
0x1077f  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10784  stloc.s  8
0x10786  leave    loc_10B16
0x1078b  ldloc.1
0x1078c  ldloc.0
0x1078d  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x10792  stloc.2
0x10793  ldloc.2
0x10794  brtrue.s loc_107A7
0x10796  ldstr    aNullInnerconne_0// "null == innerConnection"
0x1079b  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x107a0  stloc.s  8
0x107a2  leave    loc_10B16
0x107a7  ldloc.2
0x107a8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x107ad  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x107b2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x107b7  ldstr    aReferencecolle// "_referenceCollection"
0x107bc  ldc.i4.s 0x24
0x107be  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x107c3  ldloc.2
0x107c4  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x107c9  stloc.3
0x107ca  ldloc.3
0x107cb  brtrue.s loc_107DE
0x107cd  ldstr    aNullReferencec// "null == referenceCollection"
0x107d2  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x107d7  stloc.s  8
0x107d9  leave    loc_10B16
0x107de  ldloc.3
0x107df  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x107e4  ldstr    aFindlivereader// "FindLiveReader"
0x107e9  ldc.i4.s 0x24
0x107eb  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x107f0  stloc.s  4
0x107f2  ldnull
0x107f3  ldloc.s  4
0x107f5  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x107fa  brfalse.s loc_1080D
0x107fc  ldstr    aNullFindlivere// "null == findLiveReader"
0x10801  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10806  stloc.s  8
0x10808  leave    loc_10B16
0x1080d  ldarg.1
0x1080e  ldloc.s  4
0x10810  ldloc.3
0x10811  ldc.i4.1
0x10812  newarr   [mscorlib]System.Object
0x10817  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x1081c  castclass [System.Data]System.Data.SqlClient.SqlDataReader
0x10821  stind.ref
0x10822  ldarg.1
0x10823  ldind.ref
0x10824  brtrue.s loc_10837
0x10826  ldstr    aNullReader// "null == reader"
0x1082b  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10830  stloc.s  8
0x10832  leave    loc_10B16
0x10837  ldarg.1
0x10838  ldind.ref
0x10839  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1083e  ldstr    aCommand_1// "_command"
0x10843  ldc.i4.s 0x24
0x10845  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x1084a  stloc.s  5
0x1084c  ldnull
0x1084d  ldloc.s  5
0x1084f  call     bool [mscorlib]System.Reflection.FieldInfo::op_Equality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0x10854  brfalse.s loc_10867
0x10856  ldstr    aNullCommandfie// "null == commandField"
0x1085b  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10860  stloc.s  8
0x10862  leave    loc_10B16
0x10867  ldloc.s  5
0x10869  ldarg.1
0x1086a  ldind.ref
0x1086b  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x10870  isinst   [System.Data]System.Data.SqlClient.SqlCommand
0x10875  stloc.s  6
0x10877  ldloc.s  6
0x10879  brtrue.s loc_1088C
0x1087b  ldstr    aNullCmd// "null == cmd"
0x10880  call     string Microsoft.Crm.CrmTransaction::TraceErrorAndReturnEmpty(string message)
0x10885  stloc.s  8
0x10887  leave    loc_10B16
0x1088c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x10891  stloc.s  7
0x10893  ldloc.s  7
0x10895  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1089a  ldstr    aCommandTimesta// "<Command timestampUTC=\"{0}\">"
0x1089f  call     string [mscorlib]System.Environment::get_NewLine()
0x108a4  call     string [mscorlib]System.String::Concat(string, string)
0x108a9  ldc.i4.1
0x108aa  newarr   [mscorlib]System.Object
0x108af  dup
0x108b0  ldc.i4.0
0x108b1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x108b6  stloc.s  9
0x108b8  ldloca.s 9
0x108ba  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x108bf  ldstr    asc_77B3C// " "
0x108c4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x108c9  stloc.s  9
0x108cb  ldloca.s 9
0x108cd  call     instance string [mscorlib]System.DateTime::ToLongTimeString()
0x108d2  call     string [mscorlib]System.String::Concat(string, string, string)
0x108d7  stelem.ref
0x108d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x108dd  pop
0x108de  ldloc.s  6
0x108e0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x108e5  ldc.i4.s 0x14
0x108e7  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties(valuetype [mscorlib]System.Reflection.BindingFlags)
0x108ec  stloc.s  0xA
0x108ee  ldc.i4.0
0x108ef  stloc.s  0xB
0x108f1  br       loc_10AAA
0x108f6  ldloc.s  0xA
0x108f8  ldloc.s  0xB
0x108fa  ldelem.ref
0x108fb  stloc.s  0xC
0x108fd  ldloc.s  0xC
0x108ff  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x10904  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x10909  brtrue.s loc_10923
0x1090b  ldloc.s  0xC
0x1090d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x10912  ldtoken  [mscorlib]System.String
0x10917  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1091c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10921  brfalse.s loc_10961
0x10923  ldloc.s  7
0x10925  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1092a  ldstr    a010// "\t<{0}>{1}</{0}>"
0x1092f  call     string [mscorlib]System.Environment::get_NewLine()
0x10934  call     string [mscorlib]System.String::Concat(string, string)
0x10939  ldc.i4.2
0x1093a  newarr   [mscorlib]System.Object
0x1093f  dup
0x10940  ldc.i4.0
0x10941  ldloc.s  0xC
0x10943  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10948  stelem.ref
0x10949  dup
0x1094a  ldc.i4.1
0x1094b  ldloc.s  0xC
0x1094d  ldloc.s  6
0x1094f  ldnull
0x10950  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x10955  callvirt instance string [mscorlib]System.Object::ToString()
0x1095a  stelem.ref
0x1095b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x10960  pop
0x10961  ldloc.s  0xC
0x10963  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x10968  ldtoken  [System.Data]System.Data.SqlClient.SqlConnection
0x1096d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10972  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10977  brfalse  loc_10AA4
0x1097c  ldloc.s  0xC
0x1097e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10983  ldstr    aConnection// "Connection"
0x10988  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1098d  brfalse  loc_10AA4
0x10992  ldloc.s  7
0x10994  ldstr    aConnection_0// "\t<Connection>"
0x10999  call     string [mscorlib]System.Environment::get_NewLine()
0x1099e  call     string [mscorlib]System.String::Concat(string, string)
0x109a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x109a8  pop
0x109a9  ldloc.s  0xC
0x109ab  ldloc.s  6
0x109ad  ldnull
0x109ae  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x109b3  isinst   [System.Data]System.Data.SqlClient.SqlConnection
0x109b8  stloc.s  0xD
0x109ba  ldloc.s  0xD
0x109bc  brtrue.s loc_109E4
0x109be  ldloc.s  7
0x109c0  ldstr    aNullCon1// "\t\tnull == con1 "
0x109c5  call     string [mscorlib]System.Environment::get_NewLine()
0x109ca  ldstr    aConnection_1// "\t</Connection>"
0x109cf  call     string [mscorlib]System.Environment::get_NewLine()
0x109d4  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x109d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x109de  pop
0x109df  br       loc_10AA4
0x109e4  ldloc.s  7
0x109e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x109eb  ldstr    aState0State// "\t\t<State>{0}</State>"
0x109f0  call     string [mscorlib]System.Environment::get_NewLine()
0x109f5  call     string [mscorlib]System.String::Concat(string, string)
0x109fa  ldc.i4.1
0x109fb  newarr   [mscorlib]System.Object
0x10a00  dup
0x10a01  ldc.i4.0
0x10a02  ldloc.s  0xD
0x10a04  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x10a09  box      [System.Data]System.Data.ConnectionState
0x10a0e  stelem.ref
0x10a0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x10a14  pop
0x10a15  ldloc.s  0xD
0x10a17  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10a1c  ldc.i4.s 0x14
0x10a1e  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties(valuetype [mscorlib]System.Reflection.BindingFlags)
0x10a23  stloc.s  0xE
0x10a25  ldc.i4.0
0x10a26  stloc.s  0xF
0x10a28  br.s     loc_10A85
0x10a2a  ldloc.s  0xE
0x10a2c  ldloc.s  0xF
0x10a2e  ldelem.ref
0x10a2f  stloc.s  0x10
0x10a31  ldloc.s  0x10
0x10a33  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x10a38  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x10a3d  brtrue.s loc_10A57
0x10a3f  ldloc.s  0x10
0x10a41  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x10a46  ldtoken  [mscorlib]System.String
0x10a4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a50  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10a55  brfalse.s loc_10A7F
0x10a57  ldloc.s  7
0x10a59  ldstr    a010_0// "\t\t<{0}>{1}</{0}>"
0x10a5e  call     string [mscorlib]System.Environment::get_NewLine()
0x10a63  call     string [mscorlib]System.String::Concat(string, string)
0x10a68  ldloc.s  0x10
0x10a6a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10a6f  ldloc.s  0x10
0x10a71  ldloc.s  0xD
0x10a73  ldnull
0x10a74  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x10a79  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x10a7e  pop
0x10a7f  ldloc.s  0xF
0x10a81  ldc.i4.1
0x10a82  add
0x10a83  stloc.s  0xF
0x10a85  ldloc.s  0xF
0x10a87  ldloc.s  0xE
0x10a89  ldlen
0x10a8a  conv.i4
0x10a8b  blt.s    loc_10A2A
0x10a8d  ldloc.s  7
0x10a8f  ldstr    aConnection_1// "\t</Connection>"
0x10a94  call     string [mscorlib]System.Environment::get_NewLine()
0x10a99  call     string [mscorlib]System.String::Concat(string, string)
0x10a9e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10aa3  pop
0x10aa4  ldloc.s  0xB
0x10aa6  ldc.i4.1
0x10aa7  add
0x10aa8  stloc.s  0xB
0x10aaa  ldloc.s  0xB
0x10aac  ldloc.s  0xA
0x10aae  ldlen
0x10aaf  conv.i4
0x10ab0  blt      loc_108F6
0x10ab5  ldloc.s  7
0x10ab7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10abc  ldstr    aCommand_2// "</Command>"
0x10ac1  call     string [mscorlib]System.Environment::get_NewLine()
0x10ac6  call     string [mscorlib]System.String::Concat(string, string)
0x10acb  ldc.i4.0
0x10acc  newarr   [mscorlib]System.Object
0x10ad1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x10ad6  pop
0x10ad7  ldloc.s  7
0x10ad9  callvirt instance string [mscorlib]System.Object::ToString()
0x10ade  stloc.s  8
0x10ae0  leave.s  loc_10B16
0x10ae2  stloc.s  0x11
0x10ae4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10ae9  ldstr    aUnexpectedExce// "Unexpected exception: {0}\n Call stack"...
0x10aee  ldc.i4.2
  ... truncated ...
```
