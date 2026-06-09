# Microsoft.Crm.Reporting.ReportServer::IsDataExtensionInstalled

- ea: `0x4f30`
- end: `0x4f9d`
- name: `Microsoft.Crm.Reporting.ReportServer::IsDataExtensionInstalled`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x47f0`

## callees

- `0x310`
- `0x4860`
- `0x4970`
- `0x4f30`

## string_xrefs

- `0x4f37`: `Calling ReportingService.ListExtensions to get {0} extensions`
- `0x4f65`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x4f30  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4f35  ldc.i4.s 0x20
0x4f37  ldstr    aCallingReporti_4// "Calling ReportingService.ListExtensions"...
0x4f3c  ldc.i4.1
0x4f3d  newarr   [mscorlib]System.Object
0x4f42  dup
0x4f43  ldc.i4.0
0x4f44  ldstr    aData// "Data"
0x4f49  stelem.ref
0x4f4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4f4f  ldarg.0
0x4f50  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4f55  ldstr    aData// "Data"
0x4f5a  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Extension[] Microsoft.Crm.Reporting.IReportingService::ListExtensions(string ExtensionType)
0x4f5f  stloc.0
0x4f60  leave.s  loc_4F75
0x4f62  stloc.2
0x4f63  ldarg.0
0x4f64  ldloc.2
0x4f65  ldstr    aListextensions// "ListExtensions"
0x4f6a  ldc.i4   0x8004831B
0x4f6f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4f74  throw
0x4f75  ldc.i4.0
0x4f76  stloc.1
0x4f77  ldc.i4.0
0x4f78  stloc.3
0x4f79  br.s     loc_4F92
0x4f7b  ldloc.0
0x4f7c  ldloc.3
0x4f7d  ldelem.ref
0x4f7e  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Extension::get_Name()
0x4f83  ldarg.1
0x4f84  ldc.i4.5
0x4f85  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4f8a  brfalse.s loc_4F8E
0x4f8c  ldc.i4.1
0x4f8d  stloc.1
0x4f8e  ldloc.3
0x4f8f  ldc.i4.1
0x4f90  add
0x4f91  stloc.3
0x4f92  ldloc.3
0x4f93  ldloc.0
0x4f94  ldlen
0x4f95  conv.i4
0x4f96  bge.s    loc_4F9B
0x4f98  ldloc.1
0x4f99  brfalse.s loc_4F7B
0x4f9b  ldloc.1
0x4f9c  ret
```
