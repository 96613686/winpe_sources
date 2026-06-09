# Microsoft.Crm.ApplicationQuery::InitQuery

- ea: `0x1300`
- end: `0x1429`
- name: `Microsoft.Crm.ApplicationQuery::InitQuery`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1290`
- `0x12c0`

## callees

- `0xbd0`
- `0x1270`
- `0x1280`
- `0x1300`
- `0x1530`
- `0x1630`
- `0x1640`
- `0x1690`
- `0x58b0`
- `0x58d0`
- `0x58f0`
- `0x5900`
- `0x5910`
- `0x5940`
- `0x115b0`
- `0x2fb90`
- `0x2fba0`

## string_xrefs

- `0x1315`: `Attempting to create an ApplicationQuery in the client context without an OrganizationContext`
- `0x140b`: `ApplicationQuery.InitQuery: Loading new Application Query.  View Id : {0}.  QueryXml : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x1300  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x1305  brfalse.s loc_1314
0x1307  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x130c  brtrue.s loc_1314
0x130e  ldarg.3
0x130f  ldnull
0x1310  cgt.un
0x1312  br.s     loc_1315
0x1314  ldc.i4.1
0x1315  ldstr    aAttemptingToCr// "Attempting to create an ApplicationQuer"...
0x131a  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x131f  ldarg.0
0x1320  ldarg.3
0x1321  dup
0x1322  brtrue.s loc_132A
0x1324  pop
0x1325  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x132a  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::_context
0x132f  ldarg.0
0x1330  ldarg.1
0x1331  stfld    class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::_view
0x1336  ldarg.1
0x1337  callvirt instance string Microsoft.Crm.View::get_FetchXml()
0x133c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1341  brfalse.s loc_135F
0x1343  ldarg.2
0x1344  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1349  brfalse.s loc_135F
0x134b  ldarg.1
0x134c  callvirt instance string Microsoft.Crm.View::get_QueryApi()
0x1351  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1356  brtrue.s loc_135F
0x1358  ldarg.0
0x1359  ldc.i4.1
0x135a  call     instance void Microsoft.Crm.ApplicationQuery::set_IsApiQuery(bool value)
0x135f  ldarg.2
0x1360  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1365  brfalse.s loc_137F
0x1367  ldarg.0
0x1368  call     instance bool Microsoft.Crm.ApplicationQuery::get_IsApiQuery()
0x136d  brtrue.s loc_1377
0x136f  ldarg.1
0x1370  callvirt instance string Microsoft.Crm.View::get_FetchXml()
0x1375  br.s     loc_137D
0x1377  ldarg.1
0x1378  callvirt instance string Microsoft.Crm.View::get_ColumnXml()
0x137d  starg.s  2
0x137f  ldarg.0
0x1380  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::get_OrganizationContext()
0x1385  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x138a  ldarg.0
0x138b  call     instance class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::get_View()
0x1390  callvirt instance string Microsoft.Crm.View::get_ObjectType()
0x1395  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x139a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x139f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x13a4  stloc.0
0x13a5  ldarg.0
0x13a6  ldloc.0
0x13a7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x13ac  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x13b6  ldarg.0
0x13b7  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::get_OrganizationContext()
0x13bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x13c1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13c6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x13cb  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::_entityExpression
0x13d0  ldarg.0
0x13d1  call     instance class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::get_View()
0x13d6  callvirt instance int32 Microsoft.Crm.View::get_QueryType()
0x13db  stloc.1
0x13dc  ldloc.1
0x13dd  ldc.i4.4
0x13de  bne.un.s loc_13E9
0x13e0  ldarg.0
0x13e1  ldarg.2
0x13e2  call     instance void Microsoft.Crm.ApplicationQuery::set_QuickFindXml(string value)
0x13e7  br.s     loc_140B
0x13e9  ldarg.0
0x13ea  call     instance bool Microsoft.Crm.ApplicationQuery::get_IsApiQuery()
0x13ef  brfalse.s loc_13FF
0x13f1  ldarg.0
0x13f2  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x13f7  ldarg.2
0x13f8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::DeserializeFromColumnSetXml(string)
0x13fd  br.s     loc_140B
0x13ff  ldarg.0
0x1400  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1405  ldarg.2
0x1406  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::DeserializeFromFetchXml(string)
0x140b  ldstr    aApplicationque// "ApplicationQuery.InitQuery: Loading new"...
0x1410  ldc.i4.2
0x1411  newarr   [mscorlib]System.Object
0x1416  dup
0x1417  ldc.i4.0
0x1418  ldarg.1
0x1419  callvirt instance string Microsoft.Crm.View::get_ViewId()
0x141e  stelem.ref
0x141f  dup
0x1420  ldc.i4.1
0x1421  ldarg.2
0x1422  stelem.ref
0x1423  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x1428  ret
```
