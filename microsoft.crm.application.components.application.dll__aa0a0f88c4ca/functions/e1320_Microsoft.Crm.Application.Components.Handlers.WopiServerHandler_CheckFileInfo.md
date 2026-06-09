# Microsoft.Crm.Application.Components.Handlers.WopiServerHandler::CheckFileInfo

- ea: `0xe1320`
- end: `0xe14e8`
- name: `Microsoft.Crm.Application.Components.Handlers.WopiServerHandler::CheckFileInfo`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xe1180`

## callees

- `0xe1140`
- `0xe1160`
- `0xe1320`
- `0xe1840`
- `0xe1910`
- `0xe1930`
- `0xe1950`
- `0xe1970`
- `0xe1990`
- `0xe19b0`
- `0xe19d0`
- `0xe19f0`
- `0xe1a10`
- `0xe1a30`
- `0xe1a40`

## string_xrefs

- `0xe13f7`: `access_token`
- `0xe1412`: `access_token_ttl`
- `0xe1449`: `{0}/wopi/files/{1}/contents?access_token={2}&access_token_ttl={3}`

## pseudocode

```c

```

## disassembly

```asm
0xe1320  ldc.i4.5
0xe1321  newarr   [mscorlib]System.String
0xe1326  dup
0xe1327  ldc.i4.0
0xe1328  ldstr    aName// "name"
0xe132d  stelem.ref
0xe132e  dup
0xe132f  ldc.i4.1
0xe1330  ldstr    aOwnerid// "ownerid"
0xe1335  stelem.ref
0xe1336  dup
0xe1337  ldc.i4.2
0xe1338  ldstr    aFilesize// "filesize"
0xe133d  stelem.ref
0xe133e  dup
0xe133f  ldc.i4.3
0xe1340  ldstr    aSha256// "sha256"
0xe1345  stelem.ref
0xe1346  dup
0xe1347  ldc.i4.4
0xe1348  ldstr    aVersionnumber// "versionnumber"
0xe134d  stelem.ref
0xe134e  stloc.0
0xe134f  ldarg.0
0xe1350  ldloc.0
0xe1351  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Application.Components.Handlers.WopiServerHandler::RetrieveOfficeDocument(string[] columns)
0xe1356  dup
0xe1357  ldstr    aName// "name"
0xe135c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe1361  castclass [mscorlib]System.String
0xe1366  stloc.1
0xe1367  dup
0xe1368  ldstr    aOwnerid// "ownerid"
0xe136d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe1372  callvirt instance string [mscorlib]System.Object::ToString()
0xe1377  stloc.2
0xe1378  dup
0xe1379  ldstr    aFilesize// "filesize"
0xe137e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe1383  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe1388  call     int64 [mscorlib]System.Convert::ToInt64(object, class [mscorlib]System.IFormatProvider)
0xe138d  stloc.3
0xe138e  dup
0xe138f  ldstr    aSha256// "sha256"
0xe1394  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe1399  castclass [mscorlib]System.String
0xe139e  stloc.s  4
0xe13a0  ldstr    aVersionnumber// "versionnumber"
0xe13a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe13aa  unbox.any [mscorlib]System.Int64
0xe13af  stloc.s  0xC
0xe13b1  ldloca.s 0xC
0xe13b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe13b8  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0xe13bd  stloc.s  5
0xe13bf  ldloc.1
0xe13c0  brfalse.s loc_E13D0
0xe13c2  ldloc.2
0xe13c3  brfalse.s loc_E13D0
0xe13c5  ldloc.3
0xe13c6  brfalse.s loc_E13D0
0xe13c8  ldloc.s  4
0xe13ca  brfalse.s loc_E13D0
0xe13cc  ldloc.s  5
0xe13ce  brtrue.s loc_E13E1
0xe13d0  ldc.i4   0x80060805
0xe13d5  ldc.i4.0
0xe13d6  newarr   [mscorlib]System.Object
0xe13db  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe13e0  throw
0xe13e1  ldsfld   string [mscorlib]System.String::Empty
0xe13e6  stloc.s  6
0xe13e8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe13ed  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe13f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe13f7  ldstr    aAccessToken// "access_token"
0xe13fc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe1401  stloc.s  7
0xe1403  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe1408  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe140d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe1412  ldstr    aAccessTokenTtl// "access_token_ttl"
0xe1417  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe141c  stloc.s  8
0xe141e  ldarg.0
0xe141f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Handlers.WopiServerHandler::get_OrganizationId()
0xe1424  ldc.i4.0
0xe1425  ldc.i4.0
0xe1426  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe142b  stloc.s  0xD
0xe142d  ldloc.s  0xD
0xe142f  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WopiAppHelper::GetOrgUrl(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe1434  stloc.s  6
0xe1436  leave.s  loc_E1444
0xe1438  ldloc.s  0xD
0xe143a  brfalse.s loc_E1443
0xe143c  ldloc.s  0xD
0xe143e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe1443  endfinally
0xe1444  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe1449  ldstr    a0WopiFiles1Con// "{0}/wopi/files/{1}/contents?access_toke"...
0xe144e  ldc.i4.4
0xe144f  newarr   [mscorlib]System.Object
0xe1454  dup
0xe1455  ldc.i4.0
0xe1456  ldloc.s  6
0xe1458  stelem.ref
0xe1459  dup
0xe145a  ldc.i4.1
0xe145b  ldarg.0
0xe145c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Handlers.WopiServerHandler::get_FileId()
0xe1461  box      [mscorlib]System.Guid
0xe1466  stelem.ref
0xe1467  dup
0xe1468  ldc.i4.2
0xe1469  ldloc.s  7
0xe146b  stelem.ref
0xe146c  dup
0xe146d  ldc.i4.3
0xe146e  ldloc.s  8
0xe1470  stelem.ref
0xe1471  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe1476  stloc.s  9
0xe1478  newobj   instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::.ctor()
0xe147d  dup
0xe147e  ldloc.1
0xe147f  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_BaseFileName(string value)
0xe1484  dup
0xe1485  ldloc.2
0xe1486  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_OwnerId(string value)
0xe148b  dup
0xe148c  ldloc.3
0xe148d  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_Size(int64 value)
0xe1492  dup
0xe1493  ldloc.s  4
0xe1495  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_SHA256(string value)
0xe149a  dup
0xe149b  ldloc.s  5
0xe149d  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_Version(string value)
0xe14a2  dup
0xe14a3  ldloc.s  9
0xe14a5  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_DownloadUrl(string value)
0xe14aa  dup
0xe14ab  ldc.i4.0
0xe14ac  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_RestrictedWebViewOnly(bool value)
0xe14b1  dup
0xe14b2  ldc.i4.1
0xe14b3  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_SupportsUpdate(bool value)
0xe14b8  dup
0xe14b9  ldc.i4.1
0xe14ba  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_UserCanWrite(bool value)
0xe14bf  dup
0xe14c0  ldc.i4.1
0xe14c1  callvirt instance void Microsoft.Crm.Application.Components.Handlers.WopiFileInfo::set_SupportsLocks(bool value)
0xe14c6  stloc.s  0xA
0xe14c8  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0xe14cd  ldloc.s  0xA
0xe14cf  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0xe14d4  stloc.s  0xB
0xe14d6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe14db  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xe14e0  ldloc.s  0xB
0xe14e2  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xe14e7  ret
```
