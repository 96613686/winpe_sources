# Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::UpdateUserName

- ea: `0x22970`
- end: `0x22a2d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::UpdateUserName`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x22740`

## callees

- `0x1bf30`
- `0x1c3b0`
- `0x22970`

## string_xrefs

- `0x22a1c`: `UpdateUserName`
- `0x22a21`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationConfigureExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x22970  ldarg.1
0x22971  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserFirstName()
0x22976  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2297b  brtrue   loc_22A2C
0x22980  ldarg.1
0x22981  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserLastName()
0x22986  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2298b  brtrue   loc_22A2C
0x22990  ldarg.1
0x22991  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserEmail()
0x22996  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2299b  brtrue   loc_22A2C
0x229a0  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x229a5  ldarg.1
0x229a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_OrgId()
0x229ab  ldarg.1
0x229ac  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserFirstName()
0x229b1  ldarg.1
0x229b2  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserLastName()
0x229b7  ldarg.1
0x229b8  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserEmail()
0x229bd  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateInitialUser(valuetype [mscorlib]System.Guid orgId, string firstName, string lastName, string userEmail)
0x229c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x229c7  stloc.0
0x229c8  ldloc.0
0x229c9  ldstr    aInitialuserfir// "InitialUserFirstName"
0x229ce  ldarg.1
0x229cf  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserFirstName()
0x229d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x229d9  ldloc.0
0x229da  ldstr    aInitialuserlas// "InitialUserLastName"
0x229df  ldarg.1
0x229e0  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_UserLastName()
0x229e5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x229ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x229ef  stloc.1
0x229f0  ldloc.1
0x229f1  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x229f6  ldarg.1
0x229f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationConfigurationData::get_OrgId()
0x229fc  box      [mscorlib]System.Guid
0x22a01  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22a06  ldarg.0
0x22a07  ldstr    aOrganizationli// "OrganizationLifecycle"
0x22a0c  ldloc.0
0x22a0d  ldc.i4.1
0x22a0e  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x22a13  dup
0x22a14  ldc.i4.0
0x22a15  ldloc.1
0x22a16  stelem.ref
0x22a17  ldc.i4   0xB1
0x22a1c  ldstr    aUpdateusername// "UpdateUserName"
0x22a21  ldstr    aDDbsShDccm2110_35// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x22a26  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x22a2b  pop
0x22a2c  ret
```
