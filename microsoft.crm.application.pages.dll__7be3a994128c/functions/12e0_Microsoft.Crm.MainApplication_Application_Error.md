# Microsoft.Crm.MainApplication::Application_Error

- ea: `0x12e0`
- end: `0x1c3d`
- name: `Microsoft.Crm.MainApplication::Application_Error`
- size: `2397`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1260`
- `0x12e0`
- `0x1cb0`
- `0x1d20`
- `0x1d30`
- `0x20e0`
- `0x22dc0`

## string_xrefs

- `0x13c9`: `ASHX_XML`
- `0x1419`: `ASHX_XML`
- `0x13e0`: `text/xml`
- `0x13f3`: `text/xml`
- `0x146b`: `text/xml`
- `0x14a7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x14b7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x14c7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x16ef`: `/_common/error/uploadFailure.aspx?hr=0x80043e08`
- `0x1758`: `/_common/error/popuperror.aspx?hr=`
- `0x1810`: `/tools/processcontrol/bpfconfigurator.aspx`
- `0x18c0`: `/_common/error/errorhandler.aspx`
- `0x18f6`: `/_forms/read/layout.aspx`
- `0x1953`: `/_forms/read/layout.aspx`
- `0x1926`: `application/json`
- `0x1b36`: `application/json`
- `0x1a7a`: `Microsoft.Crm.Application.Components.Strings`
- `0x1a7f`: `Microsoft.Crm.Application.Components.crm.application`
- `0x1aa6`: `CRM_Dynamics_Community`

## pseudocode

```c

```

## disassembly

```asm
0x12e0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x12e5  brfalse.s loc_12F3
0x12e7  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x12ec  ldc.i4.0
0x12ed  ldc.i4.m1
0x12ee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool, int32)
0x12f3  ldc.i4.1
0x12f4  stloc.0
0x12f5  ldarg.0
0x12f6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x12fb  brfalse.s loc_1305
0x12fd  ldarg.0
0x12fe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x1303  brtrue.s loc_1307
0x1305  ldc.i4.0
0x1306  stloc.0
0x1307  leave.s  loc_130E
0x1309  pop
0x130a  ldc.i4.0
0x130b  stloc.0
0x130c  leave.s  loc_130E
0x130e  ldloc.0
0x130f  brtrue.s loc_131C
0x1311  ldstr    aApplicationErr// "Application_Error: Unable to report err"...
0x1316  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x131b  throw
0x131c  ldarg.0
0x131d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1322  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1327  ldarg.0
0x1328  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x132d  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1332  ldc.i4.1
0x1333  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1338  ldarg.0
0x1339  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpApplication::get_Server()
0x133e  callvirt instance class [mscorlib]System.Exception [System.Web]System.Web.HttpServerUtility::GetLastError()
0x1343  stloc.1
0x1344  ldarg.0
0x1345  ldloc.1
0x1346  call     instance void Microsoft.Crm.MainApplication::RedirectIfAppPortalNotificationError(class [mscorlib]System.Exception exception)
0x134b  ldnull
0x134c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1351  ldc.i4.0
0x1352  ldstr    aRequest0Failed// "Request {0} failed with exception {1}"
0x1357  ldc.i4.2
0x1358  newarr   [mscorlib]System.Object
0x135d  dup
0x135e  ldc.i4.0
0x135f  ldarg.0
0x1360  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x1365  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x136a  stelem.ref
0x136b  dup
0x136c  ldc.i4.1
0x136d  ldloc.1
0x136e  callvirt instance string [mscorlib]System.Object::ToString()
0x1373  stelem.ref
0x1374  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1379  ldloc.1
0x137a  ldarg.0
0x137b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x1380  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1385  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x138a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [System]System.Uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x138f  stloc.2
0x1390  ldarg.0
0x1391  ldloc.2
0x1392  call     instance void Microsoft.Crm.MainApplication::WriteEventLogEntryForUnhandledSqlException(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation errorInformation)
0x1397  ldc.i4.1
0x1398  ldloc.1
0x1399  call     string [Microsoft.Crm.Core]Microsoft.Crm.MiniDump::CreateDump(valuetype [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpReasons, class [mscorlib]System.Exception)
0x139e  pop
0x139f  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::get_ShowDevErrors()
0x13a4  brtrue.s loc_13B1
0x13a6  ldloc.2
0x13a7  ldsfld   string [mscorlib]System.String::Empty
0x13ac  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::set_StackTrace(string)
0x13b1  ldloc.2
0x13b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Source()
0x13b7  ldstr    aXml// "XML"
0x13bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c1  brtrue.s loc_13D5
0x13c3  ldloc.2
0x13c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Source()
0x13c9  ldstr    aAshxXml// "ASHX_XML"
0x13ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13d3  brfalse.s loc_1445
0x13d5  ldarg.0
0x13d6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x13db  callvirt instance string [System.Web]System.Web.HttpResponse::get_ContentType()
0x13e0  ldstr    aTextXml// "text/xml"
0x13e5  ldc.i4.5
0x13e6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x13eb  brfalse.s loc_13FD
0x13ed  ldarg.0
0x13ee  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x13f3  ldstr    aTextXml// "text/xml"
0x13f8  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x13fd  call     class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_XmlSerializer()
0x1402  ldarg.0
0x1403  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1408  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0x140d  ldloc.2
0x140e  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.Stream, object)
0x1413  ldloc.2
0x1414  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Source()
0x1419  ldstr    aAshxXml// "ASHX_XML"
0x141e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1423  brfalse.s loc_1435
0x1425  ldarg.0
0x1426  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x142b  ldc.i4   0x1F4
0x1430  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x1435  ldarg.0
0x1436  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x143b  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1440  br       loc_1A20
0x1445  ldloc.2
0x1446  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Source()
0x144b  ldstr    aSoap// "SOAP"
0x1450  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1455  brfalse  loc_151E
0x145a  ldarg.0
0x145b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1460  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1465  ldarg.0
0x1466  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x146b  ldstr    aTextXml// "text/xml"
0x1470  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1475  ldarg.0
0x1476  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x147b  ldc.i4   0x1F4
0x1480  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x1485  ldarg.0
0x1486  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x148b  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.HttpResponse::get_Output()
0x1490  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter)
0x1495  stloc.3
0x1496  ldloc.3
0x1497  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument()
0x149c  ldloc.3
0x149d  ldstr    aSoap_0// "soap"
0x14a2  ldstr    aEnvelope// "Envelope"
0x14a7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x14ac  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x14b1  ldloc.3
0x14b2  ldstr    aBody// "Body"
0x14b7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x14bc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x14c1  ldloc.3
0x14c2  ldstr    aFault// "Fault"
0x14c7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x14cc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x14d1  ldloc.3
0x14d2  ldstr    aFaultcode// "faultcode"
0x14d7  ldstr    aServer// "Server"
0x14dc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14e1  ldloc.3
0x14e2  ldstr    aFaultstring// "faultstring"
0x14e7  ldsfld   string [mscorlib]System.String::Empty
0x14ec  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14f1  ldloc.3
0x14f2  ldstr    aDetail// "detail"
0x14f7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x14fc  ldloc.3
0x14fd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndDocument()
0x1502  leave.s  loc_150E
0x1504  ldloc.3
0x1505  brfalse.s loc_150D
0x1507  ldloc.3
0x1508  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x150d  endfinally
0x150e  ldarg.0
0x150f  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1514  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1519  br       loc_1A20
0x151e  ldloc.1
0x151f  isinst   [System.Web]System.Web.HttpException
0x1524  stloc.s  4
0x1526  ldstr    aMaximumRequest// "Maximum request length exceeded."
0x152b  stloc.s  5
0x152d  ldarg.0
0x152e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x1533  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x1538  stloc.s  6
0x153a  ldloc.s  6
0x153c  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1541  stloc.s  7
0x1543  ldarg.0
0x1544  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x1549  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x154e  ldstr    aIsturboform// "isTurboForm"
0x1553  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1558  stloc.s  8
0x155a  ldloc.s  8
0x155c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1561  brtrue.s loc_1587
0x1563  ldloc.s  8
0x1565  ldstr    a1// "1"
0x156a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x156f  brtrue.s loc_1584
0x1571  ldloc.s  8
0x1573  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1578  ldstr    aTrue// "TRUE"
0x157d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1582  br.s     loc_1588
0x1584  ldc.i4.1
0x1585  br.s     loc_1588
0x1587  ldc.i4.0
0x1588  stloc.s  9
0x158a  ldloc.s  7
0x158c  ldstr    aImportfileuplo// "ImportFileUpload.aspx"
0x1591  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1596  brfalse  loc_1640
0x159b  ldloc.s  4
0x159d  brfalse  loc_1640
0x15a2  ldloc.s  4
0x15a4  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x15a9  ldc.i4   0x80004005
0x15ae  bne.un   loc_1640
0x15b3  ldloc.1
0x15b4  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x15b9  brtrue.s loc_15BE
0x15bb  ldc.i4.1
0x15bc  br.s     loc_15D0
0x15be  ldloc.s  5
0x15c0  ldloc.1
0x15c1  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x15c6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15d0  brfalse.s loc_1640
0x15d2  ldarg.0
0x15d3  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpApplication::get_Server()
0x15d8  callvirt instance void [System.Web]System.Web.HttpServerUtility::ClearError()
0x15dd  ldarg.0
0x15de  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x15e3  ldstr    aHtmlHeadScript// "<html><head><script>"
0x15e8  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x15ed  ldarg.0
0x15ee  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x15f3  ldstr    aThisLocationHr// "this.location.href = "
0x15f8  ldstr    aToolsImportwiz// "/Tools/ImportWizard/ImportFileUpload.as"...
0x15fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1602  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1607  callvirt instance string [mscorlib]System.Object::ToString()
0x160c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1611  ldstr    asc_113A60// ";"
0x1616  call     string [mscorlib]System.String::Concat(string, string, string)
0x161b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1620  ldarg.0
0x1621  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1626  ldstr    aScriptHeadBody// "</script></head><body></body></html>"
0x162b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1630  ldarg.0
0x1631  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1636  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x163b  br       loc_1A20
0x1640  ldloc.s  7
0x1642  ldstr    aSolutionimport// "SolutionImportProcess.aspx"
0x1647  callvirt instance bool [mscorlib]System.String::Equals(string)
0x164c  brfalse.s loc_16C3
0x164e  ldloc.s  4
0x1650  brfalse.s loc_16C3
0x1652  ldloc.s  4
0x1654  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x1659  ldc.i4   0x80004005
0x165e  bne.un.s loc_16C3
0x1660  ldarg.0
0x1661  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpApplication::get_Server()
0x1666  callvirt instance void [System.Web]System.Web.HttpServerUtility::ClearError()
0x166b  ldarg.0
0x166c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1671  ldstr    aHtmlHeadScript// "<html><head><script>"
0x1676  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x167b  ldarg.0
0x167c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x1681  ldstr    aThisLocationHr// "this.location.href = "
0x1686  ldstr    aToolsSolutionI// "/Tools/Solution/import/SolutionImportPr"...
0x168b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1690  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1695  callvirt instance string [mscorlib]System.Object::ToString()
0x169a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x169f  ldstr    asc_113A60// ";"
0x16a4  call     string [mscorlib]System.String::Concat(string, string, string)
0x16a9  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x16ae  ldarg.0
0x16af  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x16b4  ldstr    aScriptHeadBody// "</script></head><body></body></html>"
0x16b9  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x16be  br       loc_1A20
0x16c3  ldloc.s  7
0x16c5  ldstr    aUploadAspx// "upload.aspx"
0x16ca  callvirt instance bool [mscorlib]System.String::Equals(string)
0x16cf  brfalse.s loc_1708
0x16d1  ldloc.s  4
0x16d3  brfalse.s loc_1708
0x16d5  ldloc.s  4
0x16d7  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x16dc  ldc.i4   0x80004005
  ... truncated ...
```
