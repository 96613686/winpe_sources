# Microsoft.Crm.Reporting.SetupReportServer::OrganizationDeleteCleanUp

- ea: `0x7760`
- end: `0x77d3`
- name: `Microsoft.Crm.Reporting.SetupReportServer::OrganizationDeleteCleanUp`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x4aa0`
- `0x7760`
- `0x7fc0`

## string_xrefs

- `0x7767`: `OrganizationDeleteCleanUp : Instantiating clean up`
- `0x77a3`: `OrganizationDeleteCleanUp : No folder found to delete.`
- `0x77bb`: `OrganizationDeleteCleanUp : Deleting Organization Folder`

## pseudocode

```c

```

## disassembly

```asm
0x7760  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7765  ldc.i4.s 0x20
0x7767  ldstr    aOrganizationde// "OrganizationDeleteCleanUp : Instantiati"...
0x776c  ldc.i4.0
0x776d  newarr   [mscorlib]System.Object
0x7772  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7777  ldarg.1
0x7778  ldstr    aOrganizationna// "organizationName"
0x777d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7782  ldarg.1
0x7783  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x7788  stloc.0
0x7789  ldarg.0
0x778a  ldstr    asc_C3C6// "/"
0x778f  ldloc.0
0x7790  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderName()
0x7795  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.ReportServer::FindFolder(string parent, string folderName)
0x779a  brtrue.s loc_77B4
0x779c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x77a1  ldc.i4.s 0x20
0x77a3  ldstr    aOrganizationde_0// "OrganizationDeleteCleanUp : No folder f"...
0x77a8  ldc.i4.0
0x77a9  newarr   [mscorlib]System.Object
0x77ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77b3  ret
0x77b4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x77b9  ldc.i4.s 0x20
0x77bb  ldstr    aOrganizationde_1// "OrganizationDeleteCleanUp : Deleting Or"...
0x77c0  ldc.i4.0
0x77c1  newarr   [mscorlib]System.Object
0x77c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77cb  ldarg.0
0x77cc  ldloc.0
0x77cd  call     instance void Microsoft.Crm.Reporting.SetupReportServer::DeleteOrganizationFolder(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext)
0x77d2  ret
```
