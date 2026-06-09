# Microsoft.Crm.Reporting.RuntimeReportServer::PrepareReportDataSourceCredentials

- ea: `0x6e70`
- end: `0x6f6b`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::PrepareReportDataSourceCredentials`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a00`

## callees

- `0x230`
- `0x4860`
- `0x4970`
- `0x6e70`

## string_xrefs

- `0x6e79`: `Calling ReportingService.GetItemDataSources on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6e70  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x6e75  stloc.2
0x6e76  ldarg.3
0x6e77  ldc.i4.s 0x20
0x6e79  ldstr    aCallingReporti_7// "Calling ReportingService.GetItemDataSou"...
0x6e7e  ldc.i4.1
0x6e7f  newarr   [mscorlib]System.Object
0x6e84  dup
0x6e85  ldc.i4.0
0x6e86  ldarg.1
0x6e87  stelem.ref
0x6e88  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e8d  ldarg.0
0x6e8e  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6e93  ldarg.1
0x6e94  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] Microsoft.Crm.Reporting.IReportingService::GetItemDataSources(string ItemPath)
0x6e99  stloc.0
0x6e9a  leave.s  loc_6EB9
0x6e9c  stloc.3
0x6e9d  ldarg.0
0x6e9e  ldloc.3
0x6e9f  ldstr    aGetitemdatasou// "GetItemDataSources"
0x6ea4  ldc.i4   0x80048321
0x6ea9  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6eae  throw
0x6eaf  ldloc.2
0x6eb0  brfalse.s loc_6EB8
0x6eb2  ldloc.2
0x6eb3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eb8  endfinally
0x6eb9  ldnull
0x6eba  stloc.1
0x6ebb  ldloc.0
0x6ebc  ldlen
0x6ebd  brfalse  loc_6F69
0x6ec2  ldarga.s 2
0x6ec4  ldstr    aB// "B"
0x6ec9  call     instance string [mscorlib]System.Guid::ToString(string)
0x6ece  stloc.s  4
0x6ed0  ldarga.s 3
0x6ed2  ldstr    aB// "B"
0x6ed7  call     instance string [mscorlib]System.Guid::ToString(string)
0x6edc  stloc.s  5
0x6ede  ldloc.0
0x6edf  ldlen
0x6ee0  conv.i4
0x6ee1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials>::.ctor(int32)
0x6ee6  stloc.s  6
0x6ee8  ldloc.0
0x6ee9  stloc.s  7
0x6eeb  ldc.i4.0
0x6eec  stloc.s  8
0x6eee  br.s     loc_6F4F
0x6ef0  ldloc.s  7
0x6ef2  ldloc.s  8
0x6ef4  ldelem.ref
0x6ef5  stloc.s  9
0x6ef7  ldloc.s  9
0x6ef9  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Item()
0x6efe  isinst   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition
0x6f03  brfalse.s loc_6F19
0x6f05  ldloc.s  9
0x6f07  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Item()
0x6f0c  castclass [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition
0x6f11  callvirt instance valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CredentialRetrievalEnum [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::get_CredentialRetrieval()
0x6f16  ldc.i4.1
0x6f17  beq.s    loc_6F49
0x6f19  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials::.ctor()
0x6f1e  stloc.s  0xA
0x6f20  ldloc.s  0xA
0x6f22  ldloc.s  9
0x6f24  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Name()
0x6f29  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials::set_DataSourceName(string)
0x6f2e  ldloc.s  0xA
0x6f30  ldloc.s  4
0x6f32  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials::set_UserName(string)
0x6f37  ldloc.s  0xA
0x6f39  ldloc.s  5
0x6f3b  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials::set_Password(string)
0x6f40  ldloc.s  6
0x6f42  ldloc.s  0xA
0x6f44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials>::Add(var<u1>)
0x6f49  ldloc.s  8
0x6f4b  ldc.i4.1
0x6f4c  add
0x6f4d  stloc.s  8
0x6f4f  ldloc.s  8
0x6f51  ldloc.s  7
0x6f53  ldlen
0x6f54  conv.i4
0x6f55  blt.s    loc_6EF0
0x6f57  ldloc.s  6
0x6f59  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials>::get_Count()
0x6f5e  ldc.i4.0
0x6f5f  ble.s    loc_6F69
0x6f61  ldloc.s  6
0x6f63  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials>::ToArray()
0x6f68  stloc.1
0x6f69  ldloc.1
0x6f6a  ret
```
