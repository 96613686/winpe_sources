# SolutionComponentViewDecoratorCommand::DecorateQuery

- ea: `0xa1170`
- end: `0xa14a2`
- name: `SolutionComponentViewDecoratorCommand::DecorateQuery`
- size: `818`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x11fa0`
- `0x12030`
- `0x12070`
- `0x2fb90`
- `0x42e20`
- `0x9cb20`
- `0x9cbb0`
- `0xa1170`

## string_xrefs

- `0xa11aa`: `SolutionComponent`
- `0xa122e`: `componentSubFilter`
- `0xa1245`: `componentSubFilter`
- `0xa1362`: `componentSubFilter`
- `0xa1379`: `componentSubFilter`
- `0xa1468`: `componentSubFilter`
- `0xa147f`: `componentSubFilter`

## pseudocode

```c

```

## disassembly

```asm
0xa1170  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xa1175  stloc.0
0xa1176  ldarg.0
0xa1177  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa117c  ldstr    aSolutionid_0// "solutionid"
0xa1181  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa1186  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa118b  brtrue.s loc_A11A4
0xa118d  ldloca.s 0
0xa118f  ldarg.0
0xa1190  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1195  ldstr    aSolutionid_0// "solutionid"
0xa119a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa119f  call     instance void [mscorlib]System.Guid::.ctor(string)
0xa11a4  ldarg.0
0xa11a5  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa11aa  ldstr    aSolutioncompon_1// "SolutionComponent"
0xa11af  ldstr    aObjectid_0// "objectid"
0xa11b4  ldarg.0
0xa11b5  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa11ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0xa11bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xa11c4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xa11c9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xa11ce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0xa11d3  ldc.i4.0
0xa11d4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xa11d9  ldstr    aSolutionid_0// "solutionid"
0xa11de  ldc.i4.0
0xa11df  ldloc.0
0xa11e0  box      [mscorlib]System.Guid
0xa11e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa11ea  pop
0xa11eb  ldarg.0
0xa11ec  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa11f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0xa11f6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa11fb  stloc.1
0xa11fc  ldloc.1
0xa11fd  ldstr    aWebresource_0// "webresource"
0xa1202  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1207  brtrue.s loc_A121E
0xa1209  ldloc.1
0xa120a  ldstr    aWorkflow// "workflow"
0xa120f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1214  brtrue   loc_A1305
0xa1219  br       loc_A1430
0xa121e  ldc.i4.0
0xa121f  stloc.2
0xa1220  ldarg.0
0xa1221  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1226  brfalse.s loc_A125A
0xa1228  ldarg.0
0xa1229  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa122e  ldstr    aComponentsubfi// "componentSubFilter"
0xa1233  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa1238  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa123d  brtrue.s loc_A125A
0xa123f  ldarg.0
0xa1240  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1245  ldstr    aComponentsubfi// "componentSubFilter"
0xa124a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa124f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa1254  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xa1259  stloc.2
0xa125a  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa125f  call     bool Microsoft.Crm.Application.Utility.Util::IsWebresourceLocalizationAndDependencyFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xa1264  brtrue.s loc_A1284
0xa1266  ldarg.0
0xa1267  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa126c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa1271  ldstr    aWebresourcetyp// "webresourcetype"
0xa1276  ldc.i4.1
0xa1277  ldc.i4.s 0xC
0xa1279  box      [mscorlib]System.Int32
0xa127e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1283  pop
0xa1284  ldloc.2
0xa1285  stloc.s  4
0xa1287  ldloc.s  4
0xa1289  ldc.i4.1
0xa128a  sub
0xa128b  switch   loc_A12A1, loc_A12AD, loc_A12CA, loc_A12E7
0xa12a0  ret
0xa12a1  ldarg.0
0xa12a2  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa12a7  call     void Microsoft.Crm.Utility.SolutionFilter::AddCustomizableFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityQuery)
0xa12ac  ret
0xa12ad  ldarg.0
0xa12ae  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa12b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa12b8  ldstr    aWebresourcetyp// "webresourcetype"
0xa12bd  ldc.i4.8
0xa12be  call     int32[] Microsoft.Crm.Utility.SolutionFilter::GetWebResourceImageTypes()
0xa12c3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xa12c8  pop
0xa12c9  ret
0xa12ca  ldarg.0
0xa12cb  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa12d0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa12d5  ldstr    aWebresourcetyp// "webresourcetype"
0xa12da  ldc.i4.8
0xa12db  call     int32[] Microsoft.Crm.Utility.SolutionFilter::GetWebResourceWebpageTypes()
0xa12e0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xa12e5  pop
0xa12e6  ret
0xa12e7  ldarg.0
0xa12e8  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa12ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa12f2  ldstr    aWebresourcetyp// "webresourcetype"
0xa12f7  ldc.i4.0
0xa12f8  ldc.i4.8
0xa12f9  box      [mscorlib]System.Int32
0xa12fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1303  pop
0xa1304  ret
0xa1305  ldarg.0
0xa1306  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa130b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa1310  ldstr    aCategory// "category"
0xa1315  ldc.i4.1
0xa1316  ldc.i4.2
0xa1317  box      [mscorlib]System.Int32
0xa131c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1321  pop
0xa1322  ldarg.0
0xa1323  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa1328  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0xa132d  ldstr    aRendererobject// "rendererobjecttypecode"
0xa1332  ldc.i4.1
0xa1333  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa1338  brfalse.s loc_A1352
0xa133a  ldarg.0
0xa133b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa1340  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa1345  ldstr    aRendererobject// "rendererobjecttypecode"
0xa134a  ldc.i4.s 0xC
0xa134c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xa1351  pop
0xa1352  ldc.i4.0
0xa1353  stloc.3
0xa1354  ldarg.0
0xa1355  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa135a  brfalse.s loc_A138E
0xa135c  ldarg.0
0xa135d  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1362  ldstr    aComponentsubfi// "componentSubFilter"
0xa1367  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa136c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa1371  brtrue.s loc_A138E
0xa1373  ldarg.0
0xa1374  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1379  ldstr    aComponentsubfi// "componentSubFilter"
0xa137e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa1383  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa1388  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xa138d  stloc.3
0xa138e  ldloc.3
0xa138f  stloc.s  4
0xa1391  ldloc.s  4
0xa1393  ldc.i4.1
0xa1394  sub
0xa1395  switch   loc_A13AC, loc_A13B8, loc_A13D6, loc_A13F4
0xa13aa  br.s     loc_A1412
0xa13ac  ldarg.0
0xa13ad  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa13b2  call     void Microsoft.Crm.Utility.SolutionFilter::AddCustomizableFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityQuery)
0xa13b7  ret
0xa13b8  ldarg.0
0xa13b9  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa13be  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa13c3  ldstr    aType// "type"
0xa13c8  ldc.i4.0
0xa13c9  ldc.i4.1
0xa13ca  box      [mscorlib]System.Int32
0xa13cf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa13d4  pop
0xa13d5  ret
0xa13d6  ldarg.0
0xa13d7  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa13dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa13e1  ldstr    aType// "type"
0xa13e6  ldc.i4.0
0xa13e7  ldc.i4.3
0xa13e8  box      [mscorlib]System.Int32
0xa13ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa13f2  pop
0xa13f3  ret
0xa13f4  ldarg.0
0xa13f5  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa13fa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa13ff  ldstr    aCategory// "category"
0xa1404  ldc.i4.0
0xa1405  ldc.i4.4
0xa1406  box      [mscorlib]System.Int32
0xa140b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1410  pop
0xa1411  ret
0xa1412  ldarg.0
0xa1413  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa1418  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa141d  ldstr    aType// "type"
0xa1422  ldc.i4.1
0xa1423  ldc.i4.2
0xa1424  box      [mscorlib]System.Int32
0xa1429  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa142e  pop
0xa142f  ret
0xa1430  ldarg.0
0xa1431  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa1436  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0xa143b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0xa1440  brfalse.s loc_A14A1
0xa1442  ldarg.0
0xa1443  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa1448  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0xa144d  ldstr    aIscustomizable// "iscustomizable"
0xa1452  ldc.i4.1
0xa1453  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa1458  brfalse.s loc_A14A1
0xa145a  ldarg.0
0xa145b  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1460  brfalse.s loc_A14A1
0xa1462  ldarg.0
0xa1463  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa1468  ldstr    aComponentsubfi// "componentSubFilter"
0xa146d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa1472  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa1477  brtrue.s loc_A14A1
0xa1479  ldarg.0
0xa147a  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa147f  ldstr    aComponentsubfi// "componentSubFilter"
0xa1484  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa1489  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa148e  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xa1493  ldc.i4.1
0xa1494  bne.un.s loc_A14A1
0xa1496  ldarg.0
0xa1497  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0xa149c  call     void Microsoft.Crm.Utility.SolutionFilter::AddCustomizableFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityQuery)
0xa14a1  ret
```
