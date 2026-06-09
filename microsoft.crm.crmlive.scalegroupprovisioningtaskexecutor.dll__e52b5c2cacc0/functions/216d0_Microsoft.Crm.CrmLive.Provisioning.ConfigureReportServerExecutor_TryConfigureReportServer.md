# Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::TryConfigureReportServer

- ea: `0x216d0`
- end: `0x217d7`
- name: `Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::TryConfigureReportServer`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21550`

## callees

- `0x216d0`
- `0x32d60`

## string_xrefs

- `0x21793`: `CrmScaleGroupProvisioningService`
- `0x216e6`: `TryConfigureReportServer`
- `0x2170c`: `TryConfigureReportServer`
- `0x216eb`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\ConfigureReportsExecutor.cs`
- `0x21711`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\ConfigureReportsExecutor.cs`
- `0x2175f`: `ConfigureReportServerExecutor failed for organization {0} error message {1}, stack trace {2} `

## pseudocode

```c

```

## disassembly

```asm
0x216d0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x216d5  stloc.0
0x216d6  ldc.i4.0
0x216d7  stloc.1
0x216d8  ldloc.0
0x216d9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x216de  ldarg.0
0x216df  ldstr    aUniquename// "UniqueName"
0x216e4  ldc.i4.s 0x53
0x216e6  ldstr    aTryconfigurere// "TryConfigureReportServer"
0x216eb  ldstr    aDDbsShDccm2110_32// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x216f0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x216f5  castclass [mscorlib]System.String
0x216fa  stfld    string <>c__DisplayClass1_0::organizationUniqueName
0x216ff  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x21704  ldarg.0
0x21705  ldstr    aSrsurl// "SrsUrl"
0x2170a  ldc.i4.s 0x54
0x2170c  ldstr    aTryconfigurere// "TryConfigureReportServer"
0x21711  ldstr    aDDbsShDccm2110_32// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x21716  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x2171b  castclass [mscorlib]System.String
0x21720  stloc.2
0x21721  ldloc.0
0x21722  ldloc.2
0x21723  newobj   instance void [System]System.Uri::.ctor(string)
0x21728  stfld    class [System]System.Uri <>c__DisplayClass1_0::srsUri
0x2172d  ldloc.0
0x2172e  ldloc.2
0x2172f  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UriUtility::IsLocalUrl(string)
0x21734  stfld    bool <>c__DisplayClass1_0::grantNetworkServiceAccess
0x21739  ldarg.0
0x2173a  ldloc.0
0x2173b  ldfld    class [System]System.Uri <>c__DisplayClass1_0::srsUri
0x21740  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x21745  ldloc.0
0x21746  ldftn    instance void <>c__DisplayClass1_0::<TryConfigureReportServer>b__0()
0x2174c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x21751  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x21756  ldc.i4.1
0x21757  stloc.1
0x21758  leave.s  loc_217D5
0x2175a  stloc.3
0x2175b  ldloc.3
0x2175c  ldarg.0
0x2175d  ldc.i4.s 0xA
0x2175f  ldstr    aConfigurerepor// "ConfigureReportServerExecutor failed fo"...
0x21764  ldc.i4.3
0x21765  newarr   [mscorlib]System.Object
0x2176a  dup
0x2176b  ldc.i4.0
0x2176c  ldarg.0
0x2176d  box      [mscorlib]System.Guid
0x21772  stelem.ref
0x21773  dup
0x21774  ldc.i4.1
0x21775  ldloc.3
0x21776  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2177b  stelem.ref
0x2177c  dup
0x2177d  ldc.i4.2
0x2177e  ldloc.3
0x2177f  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x21784  stelem.ref
0x21785  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2178a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x2178f  stloc.s  4
0x21791  ldloc.s  4
0x21793  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x21798  ldc.i4.1
0x21799  ldc.i4   0xC0004687
0x2179e  conv.u8
0x2179f  ldc.i4.3
0x217a0  newarr   [mscorlib]System.Object
0x217a5  dup
0x217a6  ldc.i4.0
0x217a7  ldarg.0
0x217a8  box      [mscorlib]System.Guid
0x217ad  stelem.ref
0x217ae  dup
0x217af  ldc.i4.1
0x217b0  ldarg.1
0x217b1  box      [mscorlib]System.Guid
0x217b6  stelem.ref
0x217b7  dup
0x217b8  ldc.i4.2
0x217b9  ldloc.3
0x217ba  callvirt instance string [mscorlib]System.Exception::get_Message()
0x217bf  stelem.ref
0x217c0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x217c5  leave.s  loc_217D3
0x217c7  ldloc.s  4
0x217c9  brfalse.s loc_217D2
0x217cb  ldloc.s  4
0x217cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x217d2  endfinally
0x217d3  leave.s  loc_217D5
0x217d5  ldloc.1
0x217d6  ret
```
