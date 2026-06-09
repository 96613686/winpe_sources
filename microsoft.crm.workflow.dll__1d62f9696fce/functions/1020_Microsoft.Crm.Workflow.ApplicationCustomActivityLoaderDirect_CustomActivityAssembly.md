# Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::CustomActivityAssembly

- ea: `0x1020`
- end: `0x11d7`
- name: `Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::CustomActivityAssembly`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xf40`

## callees

- `0x1020`
- `0x11e0`
- `0x1250`

## string_xrefs

- `0x1060`: `pluginassemblyid`
- `0x1048`: `publickeytoken`
- `0x10da`: `publickeytoken`
- `0x10a2`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`

## pseudocode

```c

```

## disassembly

```asm
0x1020  ldc.i4.7
0x1021  newarr   [mscorlib]System.String
0x1026  dup
0x1027  ldc.i4.0
0x1028  ldstr    aContent// "content"
0x102d  stelem.ref
0x102e  dup
0x102f  ldc.i4.1
0x1030  ldstr    aName// "name"
0x1035  stelem.ref
0x1036  dup
0x1037  ldc.i4.2
0x1038  ldstr    aVersion// "version"
0x103d  stelem.ref
0x103e  dup
0x103f  ldc.i4.3
0x1040  ldstr    aCulture// "culture"
0x1045  stelem.ref
0x1046  dup
0x1047  ldc.i4.4
0x1048  ldstr    aPublickeytoken// "publickeytoken"
0x104d  stelem.ref
0x104e  dup
0x104f  ldc.i4.5
0x1050  ldstr    aSourcetype// "sourcetype"
0x1055  stelem.ref
0x1056  dup
0x1057  ldc.i4.6
0x1058  ldstr    aPath// "path"
0x105d  stelem.ref
0x105e  stloc.0
0x105f  ldarg.1
0x1060  ldstr    aPluginassembly// "pluginassemblyid"
0x1065  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x106a  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x106f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1074  stloc.1
0x1075  ldarg.0
0x1076  ldfld    class Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::_sdkCommand
0x107b  ldc.i4   0xDE
0x1080  stloc.s  5
0x1082  ldloca.s 5
0x1084  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0x108a  callvirt instance string [mscorlib]System.Object::ToString()
0x108f  ldloc.1
0x1090  ldloc.0
0x1091  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1096  ldc.i4.0
0x1097  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet, bool useSystemUserContext)
0x109c  stloc.2
0x109d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10a2  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x10a7  ldc.i4.4
0x10a8  newarr   [mscorlib]System.Object
0x10ad  dup
0x10ae  ldc.i4.0
0x10af  ldloc.2
0x10b0  ldstr    aName// "name"
0x10b5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10ba  stelem.ref
0x10bb  dup
0x10bc  ldc.i4.1
0x10bd  ldloc.2
0x10be  ldstr    aVersion// "version"
0x10c3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10c8  stelem.ref
0x10c9  dup
0x10ca  ldc.i4.2
0x10cb  ldloc.2
0x10cc  ldstr    aCulture// "culture"
0x10d1  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10d6  stelem.ref
0x10d7  dup
0x10d8  ldc.i4.3
0x10d9  ldloc.2
0x10da  ldstr    aPublickeytoken// "publickeytoken"
0x10df  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10e4  stelem.ref
0x10e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10ea  stloc.3
0x10eb  ldnull
0x10ec  stloc.s  4
0x10ee  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x10f3  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x10f8  stloc.s  6
0x10fa  ldc.i4.0
0x10fb  stloc.s  7
0x10fd  br.s     loc_1122
0x10ff  ldloc.s  6
0x1101  ldloc.s  7
0x1103  ldelem.ref
0x1104  stloc.s  8
0x1106  ldloc.s  8
0x1108  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x110d  ldloc.3
0x110e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1113  brfalse.s loc_111C
0x1115  ldloc.s  8
0x1117  stloc.s  4
0x1119  ldloc.s  4
0x111b  ret
0x111c  ldloc.s  7
0x111e  ldc.i4.1
0x111f  add
0x1120  stloc.s  7
0x1122  ldloc.s  7
0x1124  ldloc.s  6
0x1126  ldlen
0x1127  conv.i4
0x1128  blt.s    loc_10FF
0x112a  nop
0x112b  ldloc.2
0x112c  ldstr    aSourcetype// "sourcetype"
0x1131  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1136  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x113b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1140  stloc.s  7
0x1142  ldloc.s  7
0x1144  switch   loc_1157, loc_1175, loc_118E
0x1155  br.s     loc_1196
0x1157  ldloc.2
0x1158  ldstr    aContent// "content"
0x115d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1162  castclass [mscorlib]System.String
0x1167  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x116c  call     class [mscorlib]System.Reflection.Assembly [Microsoft.Crm]Microsoft.Crm.Extensibility.PluginAssemblyFactory::LoadAssembly(unsigned int8[])
0x1171  stloc.s  4
0x1173  br.s     loc_1196
0x1175  ldloc.2
0x1176  ldstr    aPath// "path"
0x117b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1180  castclass [mscorlib]System.String
0x1185  call     class [mscorlib]System.Reflection.Assembly [Microsoft.Crm]Microsoft.Crm.Extensibility.PluginAssemblyFactory::LoadAssembly(string)
0x118a  stloc.s  4
0x118c  br.s     loc_1196
0x118e  ldloc.3
0x118f  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x1194  stloc.s  4
0x1196  leave.s  loc_11D4
0x1198  stloc.s  9
0x119a  ldarg.0
0x119b  ldloc.s  9
0x119d  call     instance void Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::LogException(class [mscorlib]System.Exception exception)
0x11a2  ldnull
0x11a3  stloc.s  4
0x11a5  leave.s  loc_11D4
0x11a7  stloc.s  0xA
0x11a9  ldarg.0
0x11aa  ldloc.s  0xA
0x11ac  call     instance void Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::LogException(class [mscorlib]System.Exception exception)
0x11b1  ldnull
0x11b2  stloc.s  4
0x11b4  leave.s  loc_11D4
0x11b6  stloc.s  0xB
0x11b8  ldarg.0
0x11b9  ldloc.s  0xB
0x11bb  call     instance void Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::LogException(class [mscorlib]System.Exception exception)
0x11c0  ldnull
0x11c1  stloc.s  4
0x11c3  leave.s  loc_11D4
0x11c5  stloc.s  0xC
0x11c7  ldarg.0
0x11c8  ldloc.s  0xC
0x11ca  call     instance void Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::LogException(class [mscorlib]System.Exception exception)
0x11cf  ldnull
0x11d0  stloc.s  4
0x11d2  leave.s  loc_11D4
0x11d4  ldloc.s  4
0x11d6  ret
```
