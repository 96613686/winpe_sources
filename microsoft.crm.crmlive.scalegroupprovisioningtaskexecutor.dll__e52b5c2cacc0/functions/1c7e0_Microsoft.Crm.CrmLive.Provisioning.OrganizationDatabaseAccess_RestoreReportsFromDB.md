# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RestoreReportsFromDB

- ea: `0x1c7e0`
- end: `0x1ca5d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RestoreReportsFromDB`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1c7e0`
- `0x32280`
- `0x322f0`
- `0x32310`
- `0x32330`

## string_xrefs

- `0x1c941`: `Configuring report server for the remote data center id: {0}, report server: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1c7e0  newobj   instance void <>c__DisplayClass14_1::.ctor()
0x1c7e5  stloc.0
0x1c7e6  ldloc.0
0x1c7e7  ldarg.3
0x1c7e8  stfld    string <>c__DisplayClass14_1::uniqueName
0x1c7ed  ldarg.2
0x1c7ee  ldc.i4.s 9
0x1c7f0  ldstr    aCreatingReport// "Creating reports for organization {0} o"...
0x1c7f5  ldc.i4.2
0x1c7f6  newarr   [mscorlib]System.Object
0x1c7fb  dup
0x1c7fc  ldc.i4.0
0x1c7fd  ldloc.0
0x1c7fe  ldfld    string <>c__DisplayClass14_1::uniqueName
0x1c803  stelem.ref
0x1c804  dup
0x1c805  ldc.i4.1
0x1c806  ldarg.1
0x1c807  stelem.ref
0x1c808  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c80d  newobj   instance void <>c__DisplayClass14_2::.ctor()
0x1c812  stloc.1
0x1c813  ldloc.1
0x1c814  ldloc.0
0x1c815  stfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals1
0x1c81a  ldloc.1
0x1c81b  ldarg.2
0x1c81c  ldc.i4.0
0x1c81d  ldc.i4.0
0x1c81e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1c823  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <>c__DisplayClass14_2::connection
0x1c828  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x1c82d  stloc.2
0x1c82e  ldloc.2
0x1c82f  ldloc.1
0x1c830  stfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_0::CS$<>8__locals2
0x1c835  ldloc.2
0x1c836  ldarg.1
0x1c837  newobj   instance void [System]System.Uri::.ctor(string)
0x1c83c  stfld    class [System]System.Uri <>c__DisplayClass14_0::srsUri
0x1c841  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1c846  ldstr    aIgnorecustomre// "IgnoreCustomReportUploadFailures"
0x1c84b  callvirt T0x2B000098
0x1c850  stloc.3
0x1c851  ldloc.2
0x1c852  ldloca.s 3
0x1c854  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1c859  brfalse.s loc_1C864
0x1c85b  ldloca.s 3
0x1c85d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1c862  br.s     loc_1C865
0x1c864  ldc.i4.0
0x1c865  stfld    bool <>c__DisplayClass14_0::ignoreCustomReportUploadFailures
0x1c86a  ldarg.2
0x1c86b  ldstr    aOrganization// "Organization"
0x1c870  ldstr    aRestorereport// "RestoreReport"
0x1c875  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x1c87a  ldarg.2
0x1c87b  ldstr    aOrganization// "Organization"
0x1c880  ldstr    aRestorereportl// "RestoreReportLocal"
0x1c885  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x1c88a  ldarg.2
0x1c88b  ldloc.2
0x1c88c  ldfld    class [System]System.Uri <>c__DisplayClass14_0::srsUri
0x1c891  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c896  ldloc.2
0x1c897  ldftn    instance void <>c__DisplayClass14_0::<RestoreReportsFromDB>b__0()
0x1c89d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c8a2  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c8a7  ldarg.2
0x1c8a8  ldloc.2
0x1c8a9  ldfld    class [System]System.Uri <>c__DisplayClass14_0::srsUri
0x1c8ae  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c8b3  ldloc.2
0x1c8b4  ldftn    instance void <>c__DisplayClass14_0::<RestoreReportsFromDB>b__1()
0x1c8ba  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c8bf  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c8c4  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1c8c9  stloc.s  5
0x1c8cb  ldloc.s  5
0x1c8cd  ldarg.2
0x1c8ce  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1c8d3  ldloc.s  5
0x1c8d5  ldc.i4.1
0x1c8d6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_AreReportsPublished(bool)
0x1c8db  ldloc.s  5
0x1c8dd  ldarg.1
0x1c8de  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string)
0x1c8e3  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1c8e8  ldloc.s  5
0x1c8ea  call     instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x1c8ef  leave.s  loc_1C902
0x1c8f1  ldarg.2
0x1c8f2  ldstr    aOrganization// "Organization"
0x1c8f7  ldstr    aRestorereportl// "RestoreReportLocal"
0x1c8fc  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x1c901  endfinally
0x1c902  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x1c907  ldarg.2
0x1c908  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetOrganizationRemoteDatacenterId(valuetype [mscorlib]System.Guid)
0x1c90d  stloc.s  4
0x1c90f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c914  ldloc.s  4
0x1c916  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c91b  brfalse  loc_1C9E9
0x1c920  newobj   instance void <>c__DisplayClass14_3::.ctor()
0x1c925  stloc.s  6
0x1c927  ldloc.s  6
0x1c929  ldloc.2
0x1c92a  stfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_3::CS$<>8__locals3
0x1c92f  ldloc.s  6
0x1c931  ldloc.s  4
0x1c933  ldarg.2
0x1c934  call     class [System]System.Uri [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::GetReportServerUrl(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c939  stfld    class [System]System.Uri <>c__DisplayClass14_3::remoteSrsUrl
0x1c93e  ldarg.2
0x1c93f  ldc.i4.s 0xA
0x1c941  ldstr    aConfiguringRep// "Configuring report server for the remot"...
0x1c946  ldc.i4.2
0x1c947  newarr   [mscorlib]System.Object
0x1c94c  dup
0x1c94d  ldc.i4.0
0x1c94e  ldloc.s  4
0x1c950  box      [mscorlib]System.Guid
0x1c955  stelem.ref
0x1c956  dup
0x1c957  ldc.i4.1
0x1c958  ldloc.s  6
0x1c95a  ldfld    class [System]System.Uri <>c__DisplayClass14_3::remoteSrsUrl
0x1c95f  stelem.ref
0x1c960  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c965  ldarg.2
0x1c966  ldstr    aOrganization// "Organization"
0x1c96b  ldstr    aRestorereportr// "RestoreReportRemote"
0x1c970  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x1c975  ldarg.2
0x1c976  ldloc.s  6
0x1c978  ldfld    class [System]System.Uri <>c__DisplayClass14_3::remoteSrsUrl
0x1c97d  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c982  ldloc.s  6
0x1c984  ldftn    instance void <>c__DisplayClass14_3::<RestoreReportsFromDB>b__2()
0x1c98a  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c98f  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c994  ldarg.2
0x1c995  ldloc.s  6
0x1c997  ldfld    class [System]System.Uri <>c__DisplayClass14_3::remoteSrsUrl
0x1c99c  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c9a1  ldloc.s  6
0x1c9a3  ldftn    instance void <>c__DisplayClass14_3::<RestoreReportsFromDB>b__3()
0x1c9a9  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c9ae  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c9b3  leave.s  loc_1C9C6
0x1c9b5  ldarg.2
0x1c9b6  ldstr    aOrganization// "Organization"
0x1c9bb  ldstr    aRestorereportr// "RestoreReportRemote"
0x1c9c0  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x1c9c5  endfinally
0x1c9c6  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1c9cb  stloc.s  7
0x1c9cd  ldloc.s  7
0x1c9cf  ldarg.2
0x1c9d0  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1c9d5  ldloc.s  7
0x1c9d7  ldc.i4.1
0x1c9d8  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsRemoteReportServerConfigured(bool)
0x1c9dd  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1c9e2  ldloc.s  7
0x1c9e4  call     instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x1c9e9  leave.s  loc_1CA5C
0x1c9eb  stloc.s  8
0x1c9ed  ldloc.s  8
0x1c9ef  ldarg.2
0x1c9f0  ldc.i4.s 0xA
0x1c9f2  ldstr    aRestoreFailedT// "Restore failed to restore reports for o"...
0x1c9f7  ldc.i4.3
0x1c9f8  newarr   [mscorlib]System.Object
0x1c9fd  dup
0x1c9fe  ldc.i4.0
0x1c9ff  ldloc.2
0x1ca00  ldfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_0::CS$<>8__locals2
0x1ca05  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals1
0x1ca0a  ldfld    string <>c__DisplayClass14_1::uniqueName
0x1ca0f  stelem.ref
0x1ca10  dup
0x1ca11  ldc.i4.1
0x1ca12  ldarg.1
0x1ca13  stelem.ref
0x1ca14  dup
0x1ca15  ldc.i4.2
0x1ca16  ldloc.s  8
0x1ca18  callvirt instance string [mscorlib]System.Object::ToString()
0x1ca1d  ldloc.s  8
0x1ca1f  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1ca24  call     string [mscorlib]System.String::Concat(string, string)
0x1ca29  stelem.ref
0x1ca2a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ca2f  ldarg.s  4
0x1ca31  brfalse.s loc_1CA35
0x1ca33  rethrow
0x1ca35  leave.s  loc_1CA5C
0x1ca37  ldarg.2
0x1ca38  ldstr    aOrganization// "Organization"
0x1ca3d  ldstr    aRestorereport// "RestoreReport"
0x1ca42  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x1ca47  endfinally
0x1ca48  ldloc.1
0x1ca49  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <>c__DisplayClass14_2::connection
0x1ca4e  brfalse.s loc_1CA5B
0x1ca50  ldloc.1
0x1ca51  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <>c__DisplayClass14_2::connection
0x1ca56  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ca5b  endfinally
0x1ca5c  ret
```
