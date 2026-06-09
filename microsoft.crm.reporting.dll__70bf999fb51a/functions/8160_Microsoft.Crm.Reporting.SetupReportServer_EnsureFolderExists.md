# Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists

- ea: `0x8160`
- end: `0x8211`
- name: `Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x75e0`
- `0x7f60`

## callees

- `0x220`
- `0x4860`
- `0x4960`
- `0x7a30`
- `0x8160`
- `0x8220`

## string_xrefs

- `0x81f1`: `rsItemAlreadyExists`
- `0x8173`: `Folder {0}/{1} already exists`
- `0x81a8`: `Calling ReportingService.CreateFolder: New folder {0} under {1}`
- `0x81ff`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x8160  ldarg.0
0x8161  ldarg.1
0x8162  ldarg.2
0x8163  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::FolderExists(string parent, string folderName)
0x8168  stloc.0
0x8169  ldloc.0
0x816a  brfalse.s loc_818D
0x816c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8171  ldc.i4.s 0x20
0x8173  ldstr    aFolder01Alread// "Folder {0}/{1} already exists"
0x8178  ldc.i4.2
0x8179  newarr   [mscorlib]System.Object
0x817e  dup
0x817f  ldc.i4.0
0x8180  ldarg.1
0x8181  stelem.ref
0x8182  dup
0x8183  ldc.i4.1
0x8184  ldarg.2
0x8185  stelem.ref
0x8186  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x818b  br.s     loc_820C
0x818d  ldnull
0x818e  stloc.1
0x818f  ldarg.3
0x8190  brfalse.s loc_81A1
0x8192  ldc.i4.1
0x8193  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x8198  dup
0x8199  ldc.i4.0
0x819a  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property Microsoft.Crm.Reporting.SetupReportServer::CreateHiddenProperty()
0x819f  stelem.ref
0x81a0  stloc.1
0x81a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x81a6  ldc.i4.s 0x20
0x81a8  ldstr    aCallingReporti_26// "Calling ReportingService.CreateFolder: "...
0x81ad  ldc.i4.2
0x81ae  newarr   [mscorlib]System.Object
0x81b3  dup
0x81b4  ldc.i4.0
0x81b5  ldarg.2
0x81b6  stelem.ref
0x81b7  dup
0x81b8  ldc.i4.1
0x81b9  ldarg.1
0x81ba  stelem.ref
0x81bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x81c0  ldarg.0
0x81c1  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x81c6  ldarg.2
0x81c7  ldarg.1
0x81c8  ldloc.1
0x81c9  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.IReportingService::CreateFolder(string Folder, string Parent, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Properties)
0x81ce  pop
0x81cf  leave.s  loc_820C
0x81d1  stloc.2
0x81d2  ldloc.2
0x81d3  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x81d8  stloc.3
0x81d9  ldloc.3
0x81da  brfalse.s loc_81FD
0x81dc  ldloc.3
0x81dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x81e2  ldstr    aErrorcode// "ErrorCode"
0x81e7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x81ec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x81f1  ldstr    aRsitemalreadye// "rsItemAlreadyExists"
0x81f6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x81fb  brfalse.s loc_820A
0x81fd  ldarg.0
0x81fe  ldloc.2
0x81ff  ldstr    aCreatefolder// "CreateFolder"
0x8204  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x8209  throw
0x820a  leave.s  loc_820C
0x820c  ldloc.0
0x820d  ldc.i4.0
0x820e  ceq
0x8210  ret
```
