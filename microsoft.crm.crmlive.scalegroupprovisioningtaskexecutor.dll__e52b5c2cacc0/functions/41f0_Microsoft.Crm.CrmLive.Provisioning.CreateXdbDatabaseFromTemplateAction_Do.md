# Microsoft.Crm.CrmLive.Provisioning.CreateXdbDatabaseFromTemplateAction::Do

- ea: `0x41f0`
- end: `0x43e0`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateXdbDatabaseFromTemplateAction::Do`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x41f0`
- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x93a0`
- `0x9410`
- `0x9430`

## string_xrefs

- `0x4348`: `Unexpected records found in OrganizationDatabaseLocationService table.`
- `0x438e`: `OrganizationDatabaseLocationService.CreateDatabaseEntry() error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x41f0  ldarg.0
0x41f1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x41f6  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x41fb  brtrue.s loc_41FE
0x41fd  ret
0x41fe  ldarg.0
0x41ff  ldarg.0
0x4200  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4205  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x420a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x420f  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x4214  call     T0x2B000019
0x4219  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzureRegion()
0x421e  stloc.0
0x421f  ldarg.0
0x4220  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4225  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x422a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x422f  stloc.s  7
0x4231  ldloca.s 7
0x4233  constrained. [mscorlib]System.Guid
0x4239  callvirt instance string [mscorlib]System.Object::ToString()
0x423e  ldstr    aRetry// "_Retry_"
0x4243  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4248  box      [mscorlib]System.Guid
0x424d  call     string [mscorlib]System.String::Concat(object, object, object)
0x4252  stloc.1
0x4253  ldarg.0
0x4254  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4259  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x425e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ScaleGroupId()
0x4263  stloc.2
0x4264  ldarg.0
0x4265  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x426a  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_XdbTemplateIdentifier()
0x426f  stloc.3
0x4270  ldloc.2
0x4271  call     string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::GetScaleGroupEdition(valuetype [mscorlib]System.Guid)
0x4276  stloc.s  4
0x4278  ldloc.s  4
0x427a  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanDatabaseTierGroup(string)
0x427f  stloc.s  5
0x4281  ldloc.1
0x4282  ldloc.0
0x4283  ldloc.s  5
0x4285  ldloc.3
0x4286  ldarg.0
0x4287  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x428c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4291  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4296  ldloc.2
0x4297  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x429c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::CreateDatabaseFromTemplateAsync(string, string, string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Threading.CancellationToken)
0x42a1  ldc.i4.0
0x42a2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::ConfigureAwait(!!T0)
0x42a7  stloc.s  8
0x42a9  ldloca.s 8
0x42ab  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::GetAwaiter()
0x42b0  stloc.s  9
0x42b2  ldloca.s 9
0x42b4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier>::GetResult()
0x42b9  stloc.s  6
0x42bb  ldarg.0
0x42bc  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x42c1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x42c6  ldloc.s  4
0x42c8  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Edition(string)
0x42cd  ldarg.0
0x42ce  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x42d3  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x42d8  ldloc.s  6
0x42da  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_ConnectionString()
0x42df  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ConnectionString(string)
0x42e4  ldarg.0
0x42e5  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x42ea  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x42ef  ldloc.s  6
0x42f1  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x42f6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatabaseName(string)
0x42fb  ldarg.0
0x42fc  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4301  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4306  ldloc.s  6
0x4308  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x430d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x4312  ldarg.0
0x4313  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4318  ldloc.s  6
0x431a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x431f  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_PrimarySqlServer(string value)
0x4324  call     T0x2B00001A
0x4329  ldarg.0
0x432a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x432f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4334  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4339  ldc.i4.0
0x433a  ldc.i4.0
0x433b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::RetrieveOrganizationCurrentDatabaseDetails(valuetype [mscorlib]System.Guid, bool, bool)
0x4340  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation>::get_Count()
0x4345  ldc.i4.0
0x4346  ble.s    loc_436C
0x4348  ldstr    aUnexpectedReco// "Unexpected records found in Organizatio"...
0x434d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x4352  call     T0x2B00001A
0x4357  ldarg.0
0x4358  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x435d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4362  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4367  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::DeleteAllOrgDatabases(valuetype [mscorlib]System.Guid)
0x436c  call     T0x2B00001A
0x4371  ldarg.0
0x4372  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4377  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x437c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4381  ldloc.s  6
0x4383  ldc.i4.0
0x4384  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::CreateDatabaseEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier, bool)
0x4389  pop
0x438a  leave.s  loc_43C9
0x438c  stloc.s  0xA
0x438e  ldstr    aOrganizationda// "OrganizationDatabaseLocationService.Cre"...
0x4393  ldc.i4.1
0x4394  newarr   [mscorlib]System.Object
0x4399  dup
0x439a  ldc.i4.0
0x439b  ldloc.s  0xA
0x439d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43a2  stelem.ref
0x43a3  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x43a8  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x43ad  ldstr    aSpartanenviron// "SpartanEnvironment"
0x43b2  ldc.i4.1
0x43b3  callvirt T0x2B000011
0x43b8  ldstr    aTest// "test"
0x43bd  ldc.i4.5
0x43be  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x43c3  brtrue.s loc_43C7
0x43c5  rethrow
0x43c7  leave.s  loc_43C9
0x43c9  ldarg.0
0x43ca  ldarg.0
0x43cb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x43d0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x43d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x43da  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x43df  ret
```
