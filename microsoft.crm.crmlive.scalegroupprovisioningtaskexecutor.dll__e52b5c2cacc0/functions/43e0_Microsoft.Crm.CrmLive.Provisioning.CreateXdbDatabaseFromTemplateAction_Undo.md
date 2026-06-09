# Microsoft.Crm.CrmLive.Provisioning.CreateXdbDatabaseFromTemplateAction::Undo

- ea: `0x43e0`
- end: `0x4554`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateXdbDatabaseFromTemplateAction::Undo`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x43e0`
- `0x64b0`
- `0x6580`
- `0x65b0`
- `0x91b0`

## string_xrefs

- `0x4521`: `OrganizationDatabaseLocationService.DeleteAllOrgDatabases() error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x43e0  ldarg.0
0x43e1  ldarg.0
0x43e2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x43e7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x43ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x43f1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceUndoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x43f6  ldarg.0
0x43f7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x43fc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4401  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x4406  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x440b  brtrue.s loc_4424
0x440d  ldarg.0
0x440e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4413  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4418  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x441d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4422  brfalse.s loc_4467
0x4424  ldarg.0
0x4425  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x442a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x442f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4434  ldc.i4.s 0x4A
0x4436  ldstr    aSkipDropdataba// "skip DropDatabase as the database / log"...
0x443b  ldc.i4.0
0x443c  newarr   [mscorlib]System.Object
0x4441  call     string [mscorlib]System.String::Format(string, object[])
0x4446  ldc.i4.0
0x4447  newarr   [mscorlib]System.Object
0x444c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4451  ldarg.0
0x4452  ldarg.0
0x4453  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4458  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x445d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4462  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceUndoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x4467  call     T0x2B000019
0x446c  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzureRegion()
0x4471  stloc.0
0x4472  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4477  stloc.1
0x4478  ldloca.s 1
0x447a  constrained. [mscorlib]System.Guid
0x4480  callvirt instance string [mscorlib]System.Object::ToString()
0x4485  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x448a  dup
0x448b  ldloc.0
0x448c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string)
0x4491  dup
0x4492  ldarg.0
0x4493  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4498  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x449d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x44a2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_ConnectionString(string)
0x44a7  dup
0x44a8  ldarg.0
0x44a9  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x44ae  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x44b3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x44b8  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string)
0x44bd  dup
0x44be  ldarg.0
0x44bf  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x44c4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x44c9  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x44ce  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_LogicalServer(string)
0x44d3  ldarg.0
0x44d4  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x44d9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x44de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x44e3  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x44e8  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::DropDatabaseAsync(string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Threading.CancellationToken)
0x44ed  ldc.i4.0
0x44ee  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x44f3  stloc.2
0x44f4  ldloca.s 2
0x44f6  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x44fb  stloc.3
0x44fc  ldloca.s 3
0x44fe  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x4503  call     T0x2B00001A
0x4508  ldarg.0
0x4509  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x450e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4513  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4518  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::DeleteAllOrgDatabases(valuetype [mscorlib]System.Guid)
0x451d  leave.s  loc_453D
0x451f  stloc.s  4
0x4521  ldstr    aOrganizationda_0// "OrganizationDatabaseLocationService.Del"...
0x4526  ldc.i4.1
0x4527  newarr   [mscorlib]System.Object
0x452c  dup
0x452d  ldc.i4.0
0x452e  ldloc.s  4
0x4530  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4535  stelem.ref
0x4536  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x453b  leave.s  loc_453D
0x453d  ldarg.0
0x453e  ldarg.0
0x453f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4544  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4549  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x454e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceUndoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x4553  ret
```
