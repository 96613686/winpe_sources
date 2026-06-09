# Microsoft.Crm.Reporting.ReportServer::SetDataSourceDefinition

- ea: `0x4d00`
- end: `0x4db5`
- name: `Microsoft.Crm.Reporting.ReportServer::SetDataSourceDefinition`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4900`

## callees

- `0x210`
- `0x4860`
- `0x4970`
- `0x4d00`

## string_xrefs

- `0x4d74`: `Calling ReportingService.SetDataSourceContents on: `

## pseudocode

```c

```

## disassembly

```asm
0x4d00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x4d05  stloc.0
0x4d06  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::.ctor()
0x4d0b  stloc.1
0x4d0c  ldloc.1
0x4d0d  ldstr    aMscrmDataConne// "MSCRM Data Connector Connection String"
0x4d12  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_ConnectString(string)
0x4d17  ldloc.1
0x4d18  ldarg.2
0x4d19  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_Extension(string)
0x4d1e  ldloc.1
0x4d1f  ldc.i4.1
0x4d20  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_Enabled(bool)
0x4d25  ldloc.1
0x4d26  ldc.i4.1
0x4d27  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_EnabledSpecified(bool)
0x4d2c  ldloc.1
0x4d2d  ldc.i4.0
0x4d2e  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_ImpersonateUser(bool)
0x4d33  ldloc.1
0x4d34  ldc.i4.1
0x4d35  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_ImpersonateUserSpecified(bool)
0x4d3a  ldloc.1
0x4d3b  ldnull
0x4d3c  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_Prompt(string)
0x4d41  ldloc.1
0x4d42  ldc.i4.0
0x4d43  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_WindowsCredentials(bool)
0x4d48  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x4d4d  stloc.2
0x4d4e  ldloc.2
0x4d4f  ldstr    aHidden// "Hidden"
0x4d54  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x4d59  ldloc.2
0x4d5a  ldsfld   string [mscorlib]System.Boolean::TrueString
0x4d5f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Value(string)
0x4d64  ldc.i4.1
0x4d65  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x4d6a  ldc.i4.0
0x4d6b  ldloc.2
0x4d6c  stelem.ref
0x4d6d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4d72  ldc.i4.s 0x20
0x4d74  ldstr    aCallingReporti_1// "Calling ReportingService.SetDataSourceC"...
0x4d79  ldc.i4.1
0x4d7a  newarr   [mscorlib]System.Object
0x4d7f  dup
0x4d80  ldc.i4.0
0x4d81  ldarg.1
0x4d82  stelem.ref
0x4d83  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4d88  ldarg.0
0x4d89  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4d8e  ldarg.1
0x4d8f  ldloc.1
0x4d90  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetDataSourceContents(string DataSource, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Definition)
0x4d95  leave.s  loc_4DB4
0x4d97  stloc.3
0x4d98  ldarg.0
0x4d99  ldloc.3
0x4d9a  ldstr    aSetdatasourcec// "SetDataSourceContents"
0x4d9f  ldc.i4   0x80048319
0x4da4  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4da9  throw
0x4daa  ldloc.0
0x4dab  brfalse.s loc_4DB3
0x4dad  ldloc.0
0x4dae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4db3  endfinally
0x4db4  ret
```
