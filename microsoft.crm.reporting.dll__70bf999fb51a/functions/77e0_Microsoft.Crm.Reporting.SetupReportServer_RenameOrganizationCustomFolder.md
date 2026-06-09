# Microsoft.Crm.Reporting.SetupReportServer::RenameOrganizationCustomFolder

- ea: `0x77e0`
- end: `0x7906`
- name: `Microsoft.Crm.Reporting.SetupReportServer::RenameOrganizationCustomFolder`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x350`
- `0x4860`
- `0x4970`
- `0x77e0`
- `0x8220`

## string_xrefs

- `0x7899`: `Calling ReportingService.MoveItem: Renaming folder {0} to {1}`
- `0x78f5`: `MoveFolder`

## pseudocode

```c

```

## disassembly

```asm
0x77e0  ldarg.1
0x77e1  ldstr    aOrganizationna// "organizationName"
0x77e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x77eb  ldarg.1
0x77ec  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x77f1  stloc.0
0x77f2  ldarg.0
0x77f3  ldstr    asc_C3C6// "/"
0x77f8  ldloc.0
0x77f9  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderName()
0x77fe  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::FolderExists(string parent, string folderName)
0x7803  brfalse.s loc_7818
0x7805  ldarg.0
0x7806  ldloc.0
0x7807  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x780c  ldstr    a40// "4.0"
0x7811  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::FolderExists(string parent, string folderName)
0x7816  brtrue.s loc_7819
0x7818  ret
0x7819  ldarg.0
0x781a  ldloc.0
0x781b  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7820  ldstr    aCustomreports// "CustomReports"
0x7825  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::FolderExists(string parent, string folderName)
0x782a  brfalse.s loc_7892
0x782c  ldloc.0
0x782d  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x7832  ldstr    asc_C3F4// "_"
0x7837  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x783c  stloc.2
0x783d  ldloca.s 2
0x783f  ldstr    aYyyymmddhhmmss// "yyyyMMddhhmmss"
0x7844  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7849  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x784e  call     string [mscorlib]System.String::Concat(string, string, string)
0x7853  stloc.1
0x7854  ldnull
0x7855  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x785a  ldc.i4.s 0x20
0x785c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7861  ldstr    aCustomReportFo// "Custom Report folder exist at SRS along"...
0x7866  ldc.i4.1
0x7867  newarr   [mscorlib]System.Object
0x786c  dup
0x786d  ldc.i4.0
0x786e  ldloc.1
0x786f  stelem.ref
0x7870  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7875  ldc.i4.0
0x7876  newarr   [mscorlib]System.Object
0x787b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7880  ldarg.0
0x7881  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7886  ldloc.0
0x7887  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x788c  ldloc.1
0x788d  callvirt instance void Microsoft.Crm.Reporting.IReportingService::MoveItem(string ItemPath, string Target)
0x7892  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7897  ldc.i4.s 0x20
0x7899  ldstr    aCallingReporti_20// "Calling ReportingService.MoveItem: Rena"...
0x789e  ldc.i4.2
0x789f  newarr   [mscorlib]System.Object
0x78a4  dup
0x78a5  ldc.i4.0
0x78a6  ldstr    a40// "4.0"
0x78ab  stelem.ref
0x78ac  dup
0x78ad  ldc.i4.1
0x78ae  ldstr    aCustomreports// "CustomReports"
0x78b3  stelem.ref
0x78b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78b9  ldarg.0
0x78ba  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x78bf  ldloc.0
0x78c0  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_V4InternalFolderPath()
0x78c5  ldloc.0
0x78c6  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x78cb  callvirt instance void Microsoft.Crm.Reporting.IReportingService::MoveItem(string ItemPath, string Target)
0x78d0  leave.s  loc_7905
0x78d2  stloc.3
0x78d3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x78d8  ldc.i4.s 0x20
0x78da  ldstr    aExceptionOccur// "Exception occurs while moving V4 custom"...
0x78df  ldc.i4.1
0x78e0  newarr   [mscorlib]System.Object
0x78e5  dup
0x78e6  ldc.i4.0
0x78e7  ldloc.3
0x78e8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x78ed  stelem.ref
0x78ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78f3  ldarg.0
0x78f4  ldloc.3
0x78f5  ldstr    aMovefolder// "MoveFolder"
0x78fa  ldc.i4   0x80048330
0x78ff  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x7904  throw
0x7905  ret
```
