# Microsoft.Crm.Tools.Admin.RSPublishAction::Do

- ea: `0x11770`
- end: `0x11871`
- name: `Microsoft.Crm.Tools.Admin.RSPublishAction::Do`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x22e0`
- `0x71d0`
- `0x8630`
- `0x8670`
- `0x11770`
- `0x11880`

## string_xrefs

- `0x11811`: `Reporting Services Web site metabase property UploadReadAheadSize must be set to {0} or higher.`

## pseudocode

```c

```

## disassembly

```asm
0x11770  ldarg.0
0x11771  ldarg.0
0x11772  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x11777  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x1177c  call     instance void Microsoft.Crm.Tools.Admin.RSPublishAction::PublishReports(string organizationUniqueName)
0x11781  leave.s  loc_117A5
0x11783  pop
0x11784  ldc.i4.0
0x11785  ldc.i4.0
0x11786  ldc.i4.s 0x1E
0x11788  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x1178d  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x11792  ldarg.0
0x11793  ldarg.0
0x11794  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x11799  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x1179e  call     instance void Microsoft.Crm.Tools.Admin.RSPublishAction::PublishReports(string organizationUniqueName)
0x117a3  leave.s  loc_117A5
0x117a5  leave    loc_11860
0x117aa  stloc.0
0x117ab  ldarg.0
0x117ac  ldc.i4.1
0x117ad  stfld    bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::CriticalFailure
0x117b2  ldarg.0
0x117b3  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x117b8  ldstr    aRspublishactio// "RSPublishAction.Failure"
0x117bd  ldc.i4.0
0x117be  newarr   [mscorlib]System.Object
0x117c3  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x117c8  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::set_FailureMessage(string)
0x117cd  ldloc.0
0x117ce  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x117d3  isinst   [System]System.Net.HttpWebResponse
0x117d8  brfalse.s loc_11839
0x117da  ldc.i4   0x19D
0x117df  ldloc.0
0x117e0  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x117e5  castclass [System]System.Net.HttpWebResponse
0x117ea  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x117ef  bne.un.s loc_11839
0x117f1  ldarg.0
0x117f2  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x117f7  ldstr    aRspublishactio_0// "RSPublishAction.Failure.UploadSize"
0x117fc  ldc.i4.0
0x117fd  newarr   [mscorlib]System.Object
0x11802  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x11807  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::set_FailureMessage(string)
0x1180c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x11811  ldstr    aReportingServi// "Reporting Services Web site metabase pr"...
0x11816  ldc.i4.1
0x11817  newarr   [mscorlib]System.Object
0x1181c  dup
0x1181d  ldc.i4.0
0x1181e  ldc.i4   0x927C0
0x11823  box      [mscorlib]System.Int32
0x11828  stelem.ref
0x11829  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1182e  ldc.i4.0
0x1182f  newarr   [mscorlib]System.Object
0x11834  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x11839  rethrow
0x1183b  pop
0x1183c  ldarg.0
0x1183d  ldc.i4.1
0x1183e  stfld    bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::CriticalFailure
0x11843  ldarg.0
0x11844  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x11849  ldstr    aRspublishactio// "RSPublishAction.Failure"
0x1184e  ldc.i4.0
0x1184f  newarr   [mscorlib]System.Object
0x11854  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x11859  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::set_FailureMessage(string)
0x1185e  rethrow
0x11860  ldarg.0
0x11861  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x11866  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1186b  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ReportsUtility::MarkReportsPublishedForOrganization(valuetype [mscorlib]System.Guid)
0x11870  ret
```
