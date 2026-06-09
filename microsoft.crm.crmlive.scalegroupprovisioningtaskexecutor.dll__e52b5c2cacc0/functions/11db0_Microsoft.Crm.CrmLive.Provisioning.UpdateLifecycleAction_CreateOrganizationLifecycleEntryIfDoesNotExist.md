# Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::CreateOrganizationLifecycleEntryIfDoesNotExist

- ea: `0x11db0`
- end: `0x11f52`
- name: `Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::CreateOrganizationLifecycleEntryIfDoesNotExist`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11b70`

## callees

- `0x64b0`
- `0x91b0`
- `0x11db0`

## string_xrefs

- `0x11ee2`: `CreatedOn`
- `0x11e2d`: `CreateOrganizationLifecycleEntryIfDoesNotExist`
- `0x11f2b`: `CreateOrganizationLifecycleEntryIfDoesNotExist`
- `0x11e32`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\UpdateLifeCycleAction.cs`
- `0x11f30`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\UpdateLifeCycleAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x11db0  ldstr    aOrganizationli_0// "OrganizationLifeCycle_"
0x11db5  ldarg.0
0x11db6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11dbb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11dc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11dc5  stloc.1
0x11dc6  ldloca.s 1
0x11dc8  constrained. [mscorlib]System.Guid
0x11dce  callvirt instance string [mscorlib]System.Object::ToString()
0x11dd3  call     string [mscorlib]System.String::Concat(string, string)
0x11dd8  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string)
0x11ddd  stloc.0
0x11dde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x11de3  stloc.2
0x11de4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x11de9  stloc.3
0x11dea  ldloc.3
0x11deb  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x11df0  ldarg.0
0x11df1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11df6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11dfb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11e00  box      [mscorlib]System.Guid
0x11e05  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11e0a  ldloc.2
0x11e0b  ldstr    aOrganizationli// "OrganizationLifecycle"
0x11e10  ldc.i4.1
0x11e11  newarr   [mscorlib]System.String
0x11e16  dup
0x11e17  ldc.i4.0
0x11e18  ldstr    aId// "Id"
0x11e1d  stelem.ref
0x11e1e  ldc.i4.1
0x11e1f  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x11e24  dup
0x11e25  ldc.i4.0
0x11e26  ldloc.3
0x11e27  stelem.ref
0x11e28  ldc.i4   0x9E
0x11e2d  ldstr    aCreateorganiza_0// "CreateOrganizationLifecycleEntryIfDoesN"...
0x11e32  ldstr    aDDbsShDccm2110_24// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x11e37  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x11e3c  brtrue   loc_11F3B
0x11e41  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x11e46  stloc.s  4
0x11e48  ldloc.s  4
0x11e4a  ldstr    aId// "Id"
0x11e4f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x11e54  box      [mscorlib]System.Guid
0x11e59  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11e5e  ldloc.s  4
0x11e60  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x11e65  ldarg.0
0x11e66  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11e6b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11e70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11e75  box      [mscorlib]System.Guid
0x11e7a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11e7f  ldloc.s  4
0x11e81  ldstr    aOrganizationun// "OrganizationUniqueName"
0x11e86  ldarg.0
0x11e87  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11e8c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11e91  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x11e96  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11e9b  ldloc.s  4
0x11e9d  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0x11ea2  ldarg.0
0x11ea3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11ea8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11ead  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_FriendlyName()
0x11eb2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11eb7  brtrue.s loc_11ECB
0x11eb9  ldarg.0
0x11eba  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11ebf  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11ec4  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_FriendlyName()
0x11ec9  br.s     loc_11EDB
0x11ecb  ldarg.0
0x11ecc  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11ed1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11ed6  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x11edb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11ee0  ldloc.s  4
0x11ee2  ldstr    aCreatedon// "CreatedOn"
0x11ee7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11eec  box      [mscorlib]System.DateTime
0x11ef1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11ef6  ldloc.s  4
0x11ef8  ldstr    aModifiedon// "ModifiedOn"
0x11efd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11f02  box      [mscorlib]System.DateTime
0x11f07  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11f0c  ldloc.s  4
0x11f0e  ldstr    aStatuscode_0// "StatusCode"
0x11f13  ldc.i4.7
0x11f14  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0x11f19  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11f1e  ldloc.2
0x11f1f  ldstr    aOrganizationli// "OrganizationLifecycle"
0x11f24  ldloc.s  4
0x11f26  ldc.i4   0xAB
0x11f2b  ldstr    aCreateorganiza_0// "CreateOrganizationLifecycleEntryIfDoesN"...
0x11f30  ldstr    aDDbsShDccm2110_24// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x11f35  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x11f3a  pop
0x11f3b  leave.s  loc_11F51
0x11f3d  ldloc.2
0x11f3e  brfalse.s loc_11F46
0x11f40  ldloc.2
0x11f41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11f46  endfinally
0x11f47  ldloc.0
0x11f48  brfalse.s loc_11F50
0x11f4a  ldloc.0
0x11f4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11f50  endfinally
0x11f51  ret
```
