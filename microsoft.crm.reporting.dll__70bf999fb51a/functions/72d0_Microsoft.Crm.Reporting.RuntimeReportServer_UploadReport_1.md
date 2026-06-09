# Microsoft.Crm.Reporting.RuntimeReportServer::UploadReport_1

- ea: `0x72d0`
- end: `0x74bf`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::UploadReport_1`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d40`
- `0x7290`

## callees

- `0x1c0`
- `0x250`
- `0x340`
- `0x4860`
- `0x4970`
- `0x72d0`
- `0x74c0`

## string_xrefs

- `0x72fd`: `Calling ReportingService.CreateReport to create: {0} in path {1}.`
- `0x7359`: `ReportingService.GetItemType failed for path {0}.`
- `0x73b8`: `ReportingService.CreateCatalogItem failed to create: {0} in path {1} in attempt {2}.`
- `0x744c`: `CreateCatalogItem`
- `0x7470`: `CreateCatalogItem`
- `0x7494`: `CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x72d0  ldc.i4.1
0x72d1  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x72d6  stloc.0
0x72d7  ldloc.0
0x72d8  ldc.i4.0
0x72d9  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x72de  stelem.ref
0x72df  ldloc.0
0x72e0  ldc.i4.0
0x72e1  ldelem.ref
0x72e2  ldstr    aDescription_0// "Description"
0x72e7  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x72ec  ldloc.0
0x72ed  ldc.i4.0
0x72ee  ldelem.ref
0x72ef  ldarg.s  4
0x72f1  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Value(string)
0x72f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x72fb  ldc.i4.s 0x20
0x72fd  ldstr    aCallingReporti_19// "Calling ReportingService.CreateReport t"...
0x7302  ldc.i4.2
0x7303  newarr   [mscorlib]System.Object
0x7308  dup
0x7309  ldc.i4.0
0x730a  ldarg.3
0x730b  stelem.ref
0x730c  dup
0x730d  ldc.i4.1
0x730e  ldarg.1
0x730f  stelem.ref
0x7310  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7315  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x731a  stloc.1
0x731b  ldarg.0
0x731c  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x7321  ldarg.1
0x7322  ldarg.3
0x7323  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, string)
0x7328  stloc.2
0x7329  ldarg.s  5
0x732b  brtrue.s loc_7383
0x732d  ldarg.0
0x732e  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7333  ldloc.2
0x7334  callvirt instance string Microsoft.Crm.Reporting.IReportingService::GetItemType(string ItemPath)
0x7339  ldstr    aReport_0// "Report"
0x733e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7343  brfalse.s loc_734A
0x7345  leave    loc_74BE
0x734a  leave.s  loc_7383
0x734c  stloc.3
0x734d  ldarg.s  6
0x734f  brfalse.s loc_736F
0x7351  ldloc.3
0x7352  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7357  ldc.i4.s 0x20
0x7359  ldstr    aReportingservi_27// "ReportingService.GetItemType failed for"...
0x735e  ldc.i4.1
0x735f  newarr   [mscorlib]System.Object
0x7364  dup
0x7365  ldc.i4.0
0x7366  ldloc.2
0x7367  stelem.ref
0x7368  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x736d  br.s     loc_7381
0x736f  ldarg.0
0x7370  ldloc.3
0x7371  ldstr    aGetitemtype// "GetItemType"
0x7376  ldc.i4   0x8004832B
0x737b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7380  throw
0x7381  leave.s  loc_7383
0x7383  ldc.i4.1
0x7384  stloc.s  4
0x7386  br       loc_74AA
0x738b  nop
0x738c  ldnull
0x738d  stloc.s  5
0x738f  ldarg.0
0x7390  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7395  ldstr    aReport_0// "Report"
0x739a  ldarg.3
0x739b  ldarg.1
0x739c  ldarg.s  5
0x739e  ldarg.2
0x739f  ldloc.0
0x73a0  ldloca.s 5
0x73a2  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.IReportingService::CreateCatalogItem(string ItemType, string Name, string Parent, bool Overwrite, unsigned int8[] Definition, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Properties, [out] class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Warning[]& Warnings)
0x73a7  pop
0x73a8  leave    loc_74BE
0x73ad  stloc.s  6
0x73af  ldloc.s  6
0x73b1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x73b6  ldc.i4.s 0x20
0x73b8  ldstr    aReportingservi_28// "ReportingService.CreateCatalogItem fail"...
0x73bd  ldc.i4.3
0x73be  newarr   [mscorlib]System.Object
0x73c3  dup
0x73c4  ldc.i4.0
0x73c5  ldarg.3
0x73c6  stelem.ref
0x73c7  dup
0x73c8  ldc.i4.1
0x73c9  ldarg.1
0x73ca  stelem.ref
0x73cb  dup
0x73cc  ldc.i4.2
0x73cd  ldloc.s  4
0x73cf  box      [mscorlib]System.Int32
0x73d4  stelem.ref
0x73d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x73da  ldarg.0
0x73db  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x73e0  brfalse.s loc_73EF
0x73e2  ldarg.0
0x73e3  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x73e8  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x73ed  brtrue.s loc_73F6
0x73ef  ldstr    aNotfound// "[NotFound]"
0x73f4  br.s     loc_7401
0x73f6  ldarg.0
0x73f7  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x73fc  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x7401  stloc.s  7
0x7403  ldloc.s  6
0x7405  brfalse.s loc_741A
0x7407  ldloc.s  6
0x7409  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x740e  ldstr    aMessage// "Message"
0x7413  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7418  brtrue.s loc_7421
0x741a  ldstr    aNotfound// "[NotFound]"
0x741f  br.s     loc_7437
0x7421  ldloc.s  6
0x7423  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x7428  ldstr    aMessage// "Message"
0x742d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7432  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7437  stloc.s  8
0x7439  ldstr    aMscrmreporting// "MSCRMReporting"
0x743e  ldc.i4   0xC0004E01
0x7443  conv.u8
0x7444  ldc.i4.3
0x7445  newarr   [mscorlib]System.String
0x744a  dup
0x744b  ldc.i4.0
0x744c  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x7451  stelem.ref
0x7452  dup
0x7453  ldc.i4.1
0x7454  ldloc.s  7
0x7456  stelem.ref
0x7457  dup
0x7458  ldc.i4.2
0x7459  ldloc.s  8
0x745b  stelem.ref
0x745c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x7461  ldloc.s  4
0x7463  ldc.i4.3
0x7464  clt
0x7466  ldarg.s  6
0x7468  or
0x7469  brfalse.s loc_746D
0x746b  leave.s  loc_74A4
0x746d  ldarg.0
0x746e  ldloc.s  6
0x7470  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x7475  ldarg.0
0x7476  ldloc.s  6
0x7478  call     instance int32 Microsoft.Crm.Reporting.RuntimeReportServer::GetExceptionErrorCode(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception)
0x747d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7482  throw
0x7483  stloc.s  9
0x7485  ldloc.s  4
0x7487  ldc.i4.3
0x7488  clt
0x748a  ldarg.s  6
0x748c  or
0x748d  brfalse.s loc_7491
0x748f  leave.s  loc_74A4
0x7491  ldarg.0
0x7492  ldloc.s  9
0x7494  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x7499  ldc.i4   0x80048298
0x749e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x74a3  throw
0x74a4  ldloc.s  4
0x74a6  ldc.i4.1
0x74a7  add
0x74a8  stloc.s  4
0x74aa  ldloc.s  4
0x74ac  ldc.i4.3
0x74ad  ble      loc_738B
0x74b2  leave.s  loc_74BE
0x74b4  ldloc.1
0x74b5  brfalse.s loc_74BD
0x74b7  ldloc.1
0x74b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74bd  endfinally
0x74be  ret
```
