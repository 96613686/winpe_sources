# Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueJson

- ea: `0x11420`
- end: `0x11c7a`
- name: `Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueJson`
- size: `2138`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10da0`

## callees

- `0x11400`
- `0x11420`
- `0x11c80`
- `0x11d20`
- `0x11d50`
- `0x11dc0`
- `0x11de0`
- `0x11e60`
- `0x11f10`
- `0x11f60`
- `0x11fb0`
- `0x12040`
- `0x121a0`
- `0x12240`
- `0x14420`
- `0x14440`
- `0x14470`

## string_xrefs

- `0x11442`: `securedcreate`
- `0x11462`: `securedupdate`
- `0x114a3`: `securedread`
- `0x11573`: `"_noread":"none",`
- `0x11b99`: `SecuritySettingForEmail`
- `0x11bb1`: `SecuritySettingForEmail`

## pseudocode

```c

```

## disassembly

```asm
0x11420  ldarg.0
0x11421  ldstr    asc_F6722// "{"
0x11426  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1142b  pop
0x1142c  ldarg.2
0x1142d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x11432  ldarg.1
0x11433  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x11438  stloc.0
0x11439  ldloc.0
0x1143a  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata)
0x1143f  brfalse.s loc_11458
0x11441  ldarg.0
0x11442  ldstr    aSecuredcreate// "securedcreate"
0x11447  ldstr    a1_0// "1"
0x1144c  ldc.i4.1
0x1144d  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11452  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11457  pop
0x11458  ldloc.0
0x11459  ldarg.2
0x1145a  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x1145f  brfalse.s loc_11478
0x11461  ldarg.0
0x11462  ldstr    aSecuredupdate// "securedupdate"
0x11467  ldstr    a1_0// "1"
0x1146c  ldc.i4.1
0x1146d  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11472  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11477  pop
0x11478  ldloc.0
0x11479  call     bool Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::IsLocalizedAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x1147e  brfalse.s loc_11497
0x11480  ldarg.0
0x11481  ldstr    aSecuredlocaliz// "securedLocalize"
0x11486  ldstr    a1_0// "1"
0x1148b  ldc.i4.1
0x1148c  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11491  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11496  pop
0x11497  ldloc.0
0x11498  ldarg.2
0x11499  call     bool Microsoft.Crm.Application.InlineEdit.PrivilegeHelper::IsAttributeSecuredRead(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x1149e  stloc.1
0x1149f  ldloc.1
0x114a0  brfalse.s loc_114B9
0x114a2  ldarg.0
0x114a3  ldstr    aSecuredread// "securedread"
0x114a8  ldstr    a1_0// "1"
0x114ad  ldc.i4.1
0x114ae  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x114b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x114b8  pop
0x114b9  ldarg.1
0x114ba  ldarg.2
0x114bb  ldloc.0
0x114bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x114c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.PropertyFactory::GetProperty(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x114c6  stloc.2
0x114c7  ldsfld   string [mscorlib]System.String::Empty
0x114cc  stloc.3
0x114cd  ldarg.3
0x114ce  brfalse.s loc_114D8
0x114d0  ldarg.3
0x114d1  ldarg.1
0x114d2  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetAttributeClassId(class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator formMediator, string attributeName)
0x114d7  stloc.3
0x114d8  ldnull
0x114d9  stloc.s  4
0x114db  ldloc.0
0x114dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x114e1  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x114e6  stloc.s  5
0x114e8  ldloc.s  5
0x114ea  switch   loc_11969, loc_11554, loc_11A0B, loc_11725, loc_1176B, loc_116DA, loc_11C57, loc_11554, loc_11B5D, loc_11A56, loc_11554, loc_116A4, loc_117B1, loc_11C57, loc_117B1, loc_117B1, loc_11C40, loc_11C57, loc_11C57, loc_11C57, loc_11C57, loc_11C57, loc_11C57, loc_118D7
0x1154f  br       loc_11C57
0x11554  ldloc.2
0x11555  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x1155a  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.LookupInformation
0x1155f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.LookupInformation::get_Data()
0x11564  stloc.s  6
0x11566  ldarg.0
0x11567  ldstr    aVisibleInlineB// "\"_visible\":\"inline-block\","
0x1156c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11571  pop
0x11572  ldarg.0
0x11573  ldstr    aNoreadNone// "\"_noread\":\"none\","
0x11578  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1157d  pop
0x1157e  ldarg.0
0x1157f  ldloc.1
0x11580  ldarg.s  4
0x11582  brtrue.s loc_1158C
0x11584  ldloc.2
0x11585  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_FormattedValue()
0x1158a  br.s     loc_1159C
0x1158c  ldloc.2
0x1158d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_FormattedValue()
0x11592  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x11597  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1159c  ldc.i4.1
0x1159d  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueForAttribute(class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, string dataValue, bool appendComma)
0x115a2  ldarg.0
0x115a3  ldstr    aOid// "oid"
0x115a8  ldloc.s  6
0x115aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x115af  ldc.i4.1
0x115b0  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x115b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x115ba  pop
0x115bb  ldarg.0
0x115bc  ldstr    aOtype// "otype"
0x115c1  ldloc.s  6
0x115c3  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x115c8  stloc.s  8
0x115ca  ldloca.s 8
0x115cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x115d1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x115d6  ldc.i4.1
0x115d7  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x115dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x115e1  pop
0x115e2  ldarg.0
0x115e3  ldstr    aImg_0// "img"
0x115e8  ldloc.s  6
0x115ea  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x115ef  ldc.i4.0
0x115f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x115f5  callvirt instance string [mscorlib]System.Object::ToString()
0x115fa  ldc.i4.1
0x115fb  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11600  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11605  pop
0x11606  ldarg.0
0x11607  ldstr    aOtypename// "otypename"
0x1160c  ldloc.s  6
0x1160e  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x11613  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11618  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1161d  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x11622  ldc.i4.1
0x11623  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11628  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1162d  pop
0x1162e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11633  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x11638  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1163d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11642  ldloc.s  6
0x11644  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x11649  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1164e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11653  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x11658  ldc.i4.1
0x11659  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1165e  stloc.s  7
0x11660  ldloc.s  7
0x11662  brfalse.s loc_11686
0x11664  ldarg.0
0x11665  ldstr    aIsprocessenabl// "isprocessenabled"
0x1166a  ldloc.s  7
0x1166c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBusinessProcessEnabled()
0x11671  stloc.s  9
0x11673  ldloca.s 9
0x11675  call     instance string [mscorlib]System.Boolean::ToString()
0x1167a  ldc.i4.1
0x1167b  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11680  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11685  pop
0x11686  ldarg.0
0x11687  ldstr    aProperties// "\"properties\":"
0x1168c  ldloc.0
0x1168d  ldarg.s  5
0x1168f  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::LookupSpecificProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x11694  call     string [mscorlib]System.String::Concat(string, string)
0x11699  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1169e  pop
0x1169f  br       loc_11C6D
0x116a4  ldarg.2
0x116a5  ldloc.0
0x116a6  ldloc.2
0x116a7  ldarg.0
0x116a8  ldloc.1
0x116a9  ldarg.s  4
0x116ab  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendPartyListItems(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty gridProperty, class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, bool encodeValues)
0x116b0  ldarg.0
0x116b1  ldstr    asc_11387C// ","
0x116b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x116bb  pop
0x116bc  ldarg.0
0x116bd  ldstr    aProperties// "\"properties\":"
0x116c2  ldloc.0
0x116c3  ldarg.s  5
0x116c5  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::LookupSpecificProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata metadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x116ca  call     string [mscorlib]System.String::Concat(string, string)
0x116cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x116d4  pop
0x116d5  br       loc_11C6D
0x116da  ldloc.0
0x116db  ldloc.2
0x116dc  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetIntegerFormattedValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty gridProperty)
0x116e1  stloc.s  0xA
0x116e3  ldarg.0
0x116e4  ldstr    aRaw// "raw"
0x116e9  ldloc.2
0x116ea  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x116ef  unbox.any [mscorlib]System.Int32
0x116f4  stloc.s  8
0x116f6  ldloca.s 8
0x116f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x116fd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11702  ldc.i4.1
0x11703  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11708  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1170d  pop
0x1170e  ldarg.0
0x1170f  ldloc.1
0x11710  ldloc.3
0x11711  ldloc.s  0xA
0x11713  ldarg.s  4
0x11715  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetDefaultFormattedValue(string attributeClassId, string formattedValue, bool encodeValues)
0x1171a  ldc.i4.0
0x1171b  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueForAttribute(class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, string dataValue, bool appendComma)
0x11720  br       loc_11C6D
0x11725  ldarg.0
0x11726  ldstr    aRaw// "raw"
0x1172b  ldloc.2
0x1172c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x11731  unbox.any [mscorlib]System.Decimal
0x11736  stloc.s  0xB
0x11738  ldloca.s 0xB
0x1173a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1173f  call     instance string [mscorlib]System.Decimal::ToString(class [mscorlib]System.IFormatProvider)
0x11744  ldc.i4.1
0x11745  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x1174a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1174f  pop
0x11750  ldarg.0
0x11751  ldloc.1
0x11752  ldloc.3
0x11753  ldloc.2
0x11754  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_FormattedValue()
0x11759  ldarg.s  4
0x1175b  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetDefaultFormattedValue(string attributeClassId, string formattedValue, bool encodeValues)
0x11760  ldc.i4.0
0x11761  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueForAttribute(class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, string dataValue, bool appendComma)
0x11766  br       loc_11C6D
0x1176b  ldarg.0
0x1176c  ldstr    aRaw// "raw"
0x11771  ldloc.2
0x11772  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x11777  unbox.any [mscorlib]System.Double
0x1177c  stloc.s  0xC
0x1177e  ldloca.s 0xC
0x11780  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11785  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x1178a  ldc.i4.1
0x1178b  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string key, string value, bool appendComma)
0x11790  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11795  pop
0x11796  ldarg.0
0x11797  ldloc.1
0x11798  ldloc.3
0x11799  ldloc.2
0x1179a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_FormattedValue()
0x1179f  ldarg.s  4
0x117a1  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetDefaultFormattedValue(string attributeClassId, string formattedValue, bool encodeValues)
0x117a6  ldc.i4.0
0x117a7  call     void Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::AppendDataValueForAttribute(class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, string dataValue, bool appendComma)
0x117ac  br       loc_11C6D
0x117b1  ldc.i4.m1
0x117b2  stloc.s  0xD
0x117b4  ldloc.0
0x117b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x117ba  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x117bf  ldc.i4.s 0xE
0x117c1  bne.un.s loc_117E2
0x117c3  ldloc.0
0x117c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x117c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x117ce  ldloc.2
0x117cf  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x117d4  castclass [mscorlib]System.String
0x117d9  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x117de  stloc.s  0xD
0x117e0  br.s     loc_117EF
0x117e2  ldloc.2
0x117e3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x117e8  unbox.any [mscorlib]System.Int32
0x117ed  stloc.s  0xD
0x117ef  ldloc.2
0x117f0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x117f5  brfalse.s loc_1180E
0x117f7  ldloc.2
0x117f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_FormattedValue()
0x117fd  brtrue.s loc_1180E
0x117ff  ldloc.0
0x11800  ldloc.s  0xD
0x11802  box      [mscorlib]System.Int32
0x11807  call     string Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::RetrieveFormattedValueFromRawValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, object rawValue)
  ... truncated ...
```
