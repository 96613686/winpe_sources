# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetBooleanInfo

- ea: `0x1000`
- end: `0x137d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetBooleanInfo`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x1000`
- `0x1380`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1000  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1005  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x100a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x100f  stloc.0
0x1010  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1015  stloc.1
0x1016  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x101b  stloc.2
0x101c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1021  stloc.3
0x1022  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1027  stloc.s  4
0x1029  ldc.i4.0
0x102a  stloc.s  6
0x102c  ldnull
0x102d  stloc.s  7
0x102f  ldnull
0x1030  stloc.s  8
0x1032  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1037  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x103c  stloc.s  9
0x103e  ldarg.1
0x103f  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata
0x1044  stloc.s  0xA
0x1046  ldloc.s  0xA
0x1048  brfalse  loc_1118
0x104d  ldloc.s  0xA
0x104f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Locked()
0x1054  brtrue.s loc_1066
0x1056  ldarg.0
0x1057  ldstr    aValues// "values"
0x105c  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1061  brtrue   loc_1118
0x1066  ldloc.s  0xA
0x1068  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IBooleanOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata::get_BooleanOptions()
0x106d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanOption>::GetEnumerator()
0x1072  stloc.s  0xE
0x1074  br.s     loc_10C8
0x1076  ldloc.s  0xE
0x1078  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanOption>::get_Current()
0x107d  dup
0x107e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1083  stloc.s  0xF
0x1085  dup
0x1086  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x108b  ldloc.s  9
0x108d  ldloc.0
0x108e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1093  stloc.s  0x10
0x1095  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Descriptions()
0x109a  ldloc.s  9
0x109c  ldloc.0
0x109d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10a2  stloc.s  0x11
0x10a4  ldloc.s  0xF
0x10a6  ldc.i4.1
0x10a7  bne.un.s loc_10BA
0x10a9  ldloc.2
0x10aa  ldloc.s  4
0x10ac  ldloc.s  0x10
0x10ae  ldloc.s  0x11
0x10b0  ldloc.s  9
0x10b2  ldloc.0
0x10b3  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddLabelAndDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection descriptionCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label label, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label description, int32 languageCode, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext orgContext)
0x10b8  br.s     loc_10C8
0x10ba  ldloc.1
0x10bb  ldloc.3
0x10bc  ldloc.s  0x10
0x10be  ldloc.s  0x11
0x10c0  ldloc.s  9
0x10c2  ldloc.0
0x10c3  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddLabelAndDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection descriptionCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label label, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label description, int32 languageCode, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext orgContext)
0x10c8  ldloc.s  0xE
0x10ca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10cf  brtrue.s loc_1076
0x10d1  leave.s  loc_10DF
0x10d3  ldloc.s  0xE
0x10d5  brfalse.s loc_10DE
0x10d7  ldloc.s  0xE
0x10d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10de  endfinally
0x10df  ldloc.s  0xA
0x10e1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata::get_DefaultValue()
0x10e6  brtrue.s loc_10EB
0x10e8  ldc.i4.0
0x10e9  br.s     loc_10EC
0x10eb  ldc.i4.1
0x10ec  stloc.s  5
0x10ee  ldstr    a0000ff// "#0000ff"
0x10f3  stloc.s  8
0x10f5  ldstr    a0000ff// "#0000ff"
0x10fa  stloc.s  7
0x10fc  ldloc.s  0xA
0x10fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IBooleanOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata::get_BooleanOptions()
0x1103  ldc.i4.0
0x1104  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanOption>::get_Item(!!T0)
0x1109  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x110e  ldc.i4.1
0x110f  ceq
0x1111  stloc.s  6
0x1113  br       loc_1285
0x1118  ldarg.0
0x1119  ldstr    aValues// "values"
0x111e  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x1123  dup
0x1124  ldstr    aValue// "value"
0x1129  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x112e  stloc.s  0x12
0x1130  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1135  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x113a  stloc.s  0x13
0x113c  ldloc.s  0x12
0x113e  ldlen
0x113f  conv.i4
0x1140  ldc.i4.2
0x1141  beq.s    loc_114E
0x1143  ldstr    aInvalidNumberO// "Invalid number of options"
0x1148  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x114d  throw
0x114e  ldloc.s  0x12
0x1150  ldc.i4.0
0x1151  ldelem.ref
0x1152  ldstr    aValue// "value"
0x1157  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x115c  brtrue.s loc_11D6
0x115e  ldloc.s  0x12
0x1160  ldc.i4.1
0x1161  ldelem.ref
0x1162  ldstr    aValue// "value"
0x1167  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x116c  ldc.i4.1
0x116d  bne.un.s loc_11D6
0x116f  ldloc.1
0x1170  ldloc.s  0x13
0x1172  ldloc.s  0x12
0x1174  ldc.i4.0
0x1175  ldelem.ref
0x1176  ldstr    aLabel// "label"
0x117b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1180  ldloc.0
0x1181  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1186  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x118b  ldloc.2
0x118c  ldloc.s  0x13
0x118e  ldloc.s  0x12
0x1190  ldc.i4.1
0x1191  ldelem.ref
0x1192  ldstr    aLabel// "label"
0x1197  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x119c  ldloc.0
0x119d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11a2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x11a7  ldloc.s  0x12
0x11a9  ldc.i4.0
0x11aa  ldelem.ref
0x11ab  ldstr    aColor// "color"
0x11b0  ldstr    a0000ff// "#0000ff"
0x11b5  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x11ba  stloc.s  7
0x11bc  ldloc.s  0x12
0x11be  ldc.i4.1
0x11bf  ldelem.ref
0x11c0  ldstr    aColor// "color"
0x11c5  ldstr    a0000ff// "#0000ff"
0x11ca  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x11cf  stloc.s  8
0x11d1  br       loc_1266
0x11d6  ldloc.s  0x12
0x11d8  ldc.i4.1
0x11d9  ldelem.ref
0x11da  ldstr    aValue// "value"
0x11df  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x11e4  brtrue.s loc_125B
0x11e6  ldloc.s  0x12
0x11e8  ldc.i4.0
0x11e9  ldelem.ref
0x11ea  ldstr    aValue// "value"
0x11ef  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x11f4  ldc.i4.1
0x11f5  bne.un.s loc_125B
0x11f7  ldloc.1
0x11f8  ldloc.s  0x13
0x11fa  ldloc.s  0x12
0x11fc  ldc.i4.1
0x11fd  ldelem.ref
0x11fe  ldstr    aLabel// "label"
0x1203  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1208  ldloc.0
0x1209  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x120e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x1213  ldloc.2
0x1214  ldloc.s  0x13
0x1216  ldloc.s  0x12
0x1218  ldc.i4.0
0x1219  ldelem.ref
0x121a  ldstr    aLabel// "label"
0x121f  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1224  ldloc.0
0x1225  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x122a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x122f  ldloc.s  0x12
0x1231  ldc.i4.0
0x1232  ldelem.ref
0x1233  ldstr    aColor// "color"
0x1238  ldstr    a0000ff// "#0000ff"
0x123d  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x1242  stloc.s  8
0x1244  ldloc.s  0x12
0x1246  ldc.i4.1
0x1247  ldelem.ref
0x1248  ldstr    aColor// "color"
0x124d  ldstr    a0000ff// "#0000ff"
0x1252  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x1257  stloc.s  7
0x1259  br.s     loc_1266
0x125b  ldstr    aInvalidOptionV// "Invalid option values"
0x1260  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1265  throw
0x1266  ldloc.s  0x12
0x1268  ldc.i4.0
0x1269  ldelem.ref
0x126a  ldstr    aValue// "value"
0x126f  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1274  ldc.i4.1
0x1275  ceq
0x1277  stloc.s  6
0x1279  ldstr    aDefault// "default"
0x127e  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1283  stloc.s  5
0x1285  ldc.i4.0
0x1286  stloc.s  0xB
0x1288  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x128d  stloc.s  0xC
0x128f  ldloc.s  0xA
0x1291  brfalse.s loc_12B1
0x1293  ldloc.s  0xA
0x1295  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0x129a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_IsGlobal()
0x129f  stloc.s  0xB
0x12a1  ldloc.s  0xA
0x12a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0x12a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Id()
0x12ad  stloc.s  0xC
0x12af  br.s     loc_12EA
0x12b1  ldarg.0
0x12b2  ldstr    aOptionsetid// "optionsetid"
0x12b7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x12bc  brfalse.s loc_12E7
0x12be  ldarg.0
0x12bf  ldstr    aOptionsetid// "optionsetid"
0x12c4  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x12c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12ce  brtrue.s loc_12E7
0x12d0  ldc.i4.1
0x12d1  stloc.s  0xB
0x12d3  ldloca.s 0xC
0x12d5  ldarg.0
0x12d6  ldstr    aOptionsetid// "optionsetid"
0x12db  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x12e0  call     instance void [mscorlib]System.Guid::.ctor(string)
0x12e5  br.s     loc_12EA
0x12e7  ldc.i4.0
0x12e8  stloc.s  0xB
0x12ea  ldloc.2
0x12eb  ldloc.1
0x12ec  ldloc.s  4
0x12ee  ldloc.3
0x12ef  ldloc.s  8
0x12f1  ldloc.s  7
0x12f3  ldloc.s  6
0x12f5  ldloc.0
0x12f6  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.BooleanAttributeInfo::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, string, string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12fb  stloc.s  0xD
0x12fd  ldloc.s  0xB
0x12ff  brfalse.s loc_1338
0x1301  ldloc.s  0xD
0x1303  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1308  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x130d  ldc.i4.1
0x130e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_IsGlobal(bool)
0x1313  ldloc.s  0xD
0x1315  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x131a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x131f  ldloc.s  0xC
0x1321  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0x1326  ldloc.s  0xD
0x1328  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x132d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1332  ldc.i4.3
0x1333  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetType(int32)
0x1338  ldloc.s  0xD
0x133a  ldloc.s  5
0x133c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo::set_DefaultValue(int32)
0x1341  ldarg.0
0x1342  ldstr    aSourcetype// "sourcetype"
0x1347  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x134c  brfalse.s loc_135B
0x134e  ldloc.s  0xD
0x1350  ldarg.0
0x1351  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
  ... truncated ...
```
