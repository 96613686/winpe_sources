# Microsoft.Crm.Reporting.RuntimeReportServer::CreateReportDataSource

- ea: `0x6810`
- end: `0x687b`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::CreateReportDataSource`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7130`

## callees

- `0x560`
- `0x580`
- `0x6810`

## pseudocode

```c

```

## disassembly

```asm
0x6810  ldc.i4.1
0x6811  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource
0x6816  dup
0x6817  ldc.i4.0
0x6818  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::.ctor()
0x681d  stelem.ref
0x681e  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference::.ctor()
0x6823  stloc.0
0x6824  ldarg.1
0x6825  callvirt instance valuetype Microsoft.Crm.Reporting.DataProviderType Microsoft.Crm.Reporting.SRSReport::get_MSCRMDataSourceType()
0x682a  ldc.i4.1
0x682b  bne.un.s loc_6845
0x682d  ldloc.0
0x682e  ldarg.2
0x682f  ldstr    asc_C3C6// "/"
0x6834  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedFetchDataSourceName
0x6839  call     string [mscorlib]System.String::Concat(string, string, string)
0x683e  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference::set_Reference(string)
0x6843  br.s     loc_6863
0x6845  ldarg.1
0x6846  callvirt instance valuetype Microsoft.Crm.Reporting.DataProviderType Microsoft.Crm.Reporting.SRSReport::get_MSCRMDataSourceType()
0x684b  brtrue.s loc_6863
0x684d  ldloc.0
0x684e  ldarg.2
0x684f  ldstr    asc_C3C6// "/"
0x6854  ldsfld   string Microsoft.Crm.Reporting.ReportServer::SharedSqlDataSourceName
0x6859  call     string [mscorlib]System.String::Concat(string, string, string)
0x685e  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference::set_Reference(string)
0x6863  dup
0x6864  ldc.i4.0
0x6865  ldelem.ref
0x6866  ldloc.0
0x6867  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference)
0x686c  dup
0x686d  ldc.i4.0
0x686e  ldelem.ref
0x686f  ldarg.1
0x6870  callvirt instance string Microsoft.Crm.Reporting.SRSReport::get_MSCRMDataSourceName()
0x6875  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::set_Name(string)
0x687a  ret
```
