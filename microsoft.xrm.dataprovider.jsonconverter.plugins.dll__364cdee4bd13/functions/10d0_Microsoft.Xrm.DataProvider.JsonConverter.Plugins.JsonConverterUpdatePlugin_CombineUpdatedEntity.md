# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::CombineUpdatedEntity

- ea: `0x10d0`
- end: `0x11af`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::CombineUpdatedEntity`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10d0`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  nop
0x10d1  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo> class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.TypeReflector`1<mvar<u1>>::TypeProperties
0x10d6  stloc.0
0x10d7  ldarg.2
0x10d8  stloc.1
0x10d9  nop
0x10da  ldarg.3
0x10db  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap> [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap::get_AttributeMap()
0x10e0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap>::GetEnumerator()
0x10e5  stloc.2
0x10e6  br       loc_118F
0x10eb  ldloc.2
0x10ec  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap>::get_Current()
0x10f1  stloc.3
0x10f2  nop
0x10f3  ldloc.0
0x10f4  ldloc.3
0x10f5  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap::get_NameMap()
0x10fa  callvirt instance string [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap::get_ExternalName()
0x10ff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo>::get_Item(void)
0x1104  ldarg.1
0x1105  box      mvar<u1>
0x110a  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x110f  stloc.s  4
0x1111  ldloc.s  4
0x1113  ldnull
0x1114  cgt.un
0x1116  stloc.s  5
0x1118  ldloc.s  5
0x111a  brfalse.s loc_118E
0x111c  nop
0x111d  ldloc.s  4
0x111f  isinst   [mscorlib]System.Guid
0x1124  brfalse.s loc_113C
0x1126  ldloc.s  4
0x1128  unbox.any [mscorlib]System.Guid
0x112d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1132  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1137  ldc.i4.0
0x1138  ceq
0x113a  br.s     loc_113D
0x113c  ldc.i4.1
0x113d  stloc.s  6
0x113f  ldloc.s  6
0x1141  brfalse.s loc_118D
0x1143  nop
0x1144  ldarg.0
0x1145  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::attributesToBeUpdated
0x114a  brfalse.s loc_1164
0x114c  ldarg.0
0x114d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::attributesToBeUpdated
0x1152  ldloc.3
0x1153  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap::get_NameMap()
0x1158  callvirt instance string [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap::get_XrmName()
0x115d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1162  br.s     loc_1165
0x1164  ldc.i4.0
0x1165  stloc.s  7
0x1167  ldloc.s  7
0x1169  brfalse.s loc_118C
0x116b  nop
0x116c  ldloc.0
0x116d  ldloc.3
0x116e  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap::get_NameMap()
0x1173  callvirt instance string [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap::get_ExternalName()
0x1178  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo>::get_Item(void)
0x117d  ldloc.1
0x117e  box      mvar<u1>
0x1183  ldloc.s  4
0x1185  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0x118a  nop
0x118b  nop
0x118c  nop
0x118d  nop
0x118e  nop
0x118f  ldloc.2
0x1190  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1195  brtrue   loc_10EB
0x119a  leave.s  loc_11A7
0x119c  ldloc.2
0x119d  brfalse.s loc_11A6
0x119f  ldloc.2
0x11a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11a5  nop
0x11a6  endfinally
0x11a7  ldloc.1
0x11a8  stloc.s  8
0x11aa  br.s     loc_11AC
0x11ac  ldloc.s  8
0x11ae  ret
```
