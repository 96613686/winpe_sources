# Microsoft.Crm.Tools.ImportExportPublish.Helper::ContainsId

- ea: `0x12fb0`
- end: `0x13087`
- name: `Microsoft.Crm.Tools.ImportExportPublish.Helper::ContainsId`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x12ec0`

## callees

- `0x12fb0`

## string_xrefs

- `0x12fe9`: `RootComponent[@type='{0}']`
- `0x13012`: `RootComponent[@type='{0}'][@parentId='{1}']`
- `0x1303f`: `RootComponent[@type='{0}'][@id='{1}']`
- `0x1305f`: `RootComponent[@type='{0}'][@id='{1}'][@parentId='{1}']`

## pseudocode

```c

```

## disassembly

```asm
0x12fb0  ldarga.s 2
0x12fb2  ldstr    aB// "B"
0x12fb7  call     instance string [mscorlib]System.Guid::ToString(string)
0x12fbc  stloc.1
0x12fbd  ldarga.s 3
0x12fbf  ldstr    aB// "B"
0x12fc4  call     instance string [mscorlib]System.Guid::ToString(string)
0x12fc9  stloc.2
0x12fca  ldarg.2
0x12fcb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12fd0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12fd5  brfalse.s loc_13000
0x12fd7  ldarg.3
0x12fd8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12fdd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12fe2  brfalse.s loc_13000
0x12fe4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12fe9  ldstr    aRootcomponentT_0// "RootComponent[@type='{0}']"
0x12fee  ldc.i4.1
0x12fef  newarr   [mscorlib]System.Object
0x12ff4  dup
0x12ff5  ldc.i4.0
0x12ff6  ldarg.1
0x12ff7  stelem.ref
0x12ff8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12ffd  stloc.0
0x12ffe  br.s     loc_1307C
0x13000  ldarg.2
0x13001  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13006  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1300b  brfalse.s loc_1302D
0x1300d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13012  ldstr    aRootcomponentT_1// "RootComponent[@type='{0}'][@parentId='{"...
0x13017  ldc.i4.2
0x13018  newarr   [mscorlib]System.Object
0x1301d  dup
0x1301e  ldc.i4.0
0x1301f  ldarg.1
0x13020  stelem.ref
0x13021  dup
0x13022  ldc.i4.1
0x13023  ldloc.2
0x13024  stelem.ref
0x13025  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1302a  stloc.0
0x1302b  br.s     loc_1307C
0x1302d  ldarg.3
0x1302e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13033  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13038  brfalse.s loc_1305A
0x1303a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1303f  ldstr    aRootcomponentT_2// "RootComponent[@type='{0}'][@id='{1}']"
0x13044  ldc.i4.2
0x13045  newarr   [mscorlib]System.Object
0x1304a  dup
0x1304b  ldc.i4.0
0x1304c  ldarg.1
0x1304d  stelem.ref
0x1304e  dup
0x1304f  ldc.i4.1
0x13050  ldloc.1
0x13051  stelem.ref
0x13052  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13057  stloc.0
0x13058  br.s     loc_1307C
0x1305a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1305f  ldstr    aRootcomponentT_3// "RootComponent[@type='{0}'][@id='{1}'][@"...
0x13064  ldc.i4.3
0x13065  newarr   [mscorlib]System.Object
0x1306a  dup
0x1306b  ldc.i4.0
0x1306c  ldarg.1
0x1306d  stelem.ref
0x1306e  dup
0x1306f  ldc.i4.1
0x13070  ldloc.1
0x13071  stelem.ref
0x13072  dup
0x13073  ldc.i4.2
0x13074  ldloc.2
0x13075  stelem.ref
0x13076  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1307b  stloc.0
0x1307c  ldarg.0
0x1307d  ldloc.0
0x1307e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x13083  ldnull
0x13084  cgt.un
0x13086  ret
```
