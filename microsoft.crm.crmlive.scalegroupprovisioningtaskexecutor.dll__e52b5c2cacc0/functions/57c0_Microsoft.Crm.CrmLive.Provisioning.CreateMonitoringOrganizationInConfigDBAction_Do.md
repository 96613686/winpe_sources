# Microsoft.Crm.CrmLive.Provisioning.CreateMonitoringOrganizationInConfigDBAction::Do

- ea: `0x57c0`
- end: `0x5960`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateMonitoringOrganizationInConfigDBAction::Do`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x57c0`
- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x9250`
- `0x1bec0`
- `0x1c3b0`

## string_xrefs

- `0x583d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateMonitoringOrganizationInConfigDbAction.cs`
- `0x590d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateMonitoringOrganizationInConfigDbAction.cs`
- `0x5932`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateMonitoringOrganizationInConfigDbAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldarg.0
0x57c1  ldarg.0
0x57c2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x57c7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x57cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x57d1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x57d6  ldarg.0
0x57d7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x57dc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x57e1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x57e6  ldc.i4.1
0x57e7  bne.un   loc_5949
0x57ec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x57f1  stloc.0
0x57f2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x57f7  stloc.1
0x57f8  ldloc.1
0x57f9  ldstr    aOrganizationid_0// "OrganizationId"
0x57fe  ldarg.0
0x57ff  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5804  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5809  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x580e  box      [mscorlib]System.Guid
0x5813  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5818  ldloc.0
0x5819  ldstr    aOrganizationmo// "OrganizationMonitoringSettings"
0x581e  ldc.i4.1
0x581f  newarr   [mscorlib]System.String
0x5824  dup
0x5825  ldc.i4.0
0x5826  ldstr    aId// "Id"
0x582b  stelem.ref
0x582c  ldc.i4.1
0x582d  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x5832  dup
0x5833  ldc.i4.0
0x5834  ldloc.1
0x5835  stelem.ref
0x5836  ldc.i4.s 0x22
0x5838  ldstr    aDo// "Do"
0x583d  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x5842  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x5847  stloc.2
0x5848  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x584d  stloc.3
0x584e  ldloc.3
0x584f  ldstr    aOrganizationid_0// "OrganizationId"
0x5854  ldarg.0
0x5855  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x585a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x585f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5864  box      [mscorlib]System.Guid
0x5869  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x586e  ldloc.3
0x586f  ldstr    aUsername// "UserName"
0x5874  ldarg.0
0x5875  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x587a  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x587f  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_Email()
0x5884  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5889  ldloc.3
0x588a  ldstr    aUserpassword// "UserPassword"
0x588f  ldarg.0
0x5890  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5895  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x589a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_Password()
0x589f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x58a4  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x58a9  stloc.s  4
0x58ab  ldloc.3
0x58ac  ldstr    aUserid// "UserId"
0x58b1  ldloc.s  4
0x58b3  ldarg.0
0x58b4  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x58b9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x58be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x58c3  callvirt instance class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetInitialCrmSystemUserIdAndFullName(valuetype [mscorlib]System.Guid orgId)
0x58c8  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item1()
0x58cd  box      [mscorlib]System.Guid
0x58d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x58d7  ldloc.2
0x58d8  brfalse.s loc_58EA
0x58da  ldloc.2
0x58db  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x58e0  brfalse.s loc_58EA
0x58e2  ldloc.2
0x58e3  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x58e8  brtrue.s loc_591A
0x58ea  ldloc.3
0x58eb  ldstr    aId// "Id"
0x58f0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x58f5  box      [mscorlib]System.Guid
0x58fa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x58ff  ldloc.0
0x5900  ldstr    aOrganizationmo// "OrganizationMonitoringSettings"
0x5905  ldloc.3
0x5906  ldc.i4.s 0x2F
0x5908  ldstr    aDo// "Do"
0x590d  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x5912  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x5917  pop
0x5918  leave.s  loc_5949
0x591a  ldloc.0
0x591b  ldstr    aOrganizationmo// "OrganizationMonitoringSettings"
0x5920  ldloc.3
0x5921  ldc.i4.1
0x5922  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x5927  dup
0x5928  ldc.i4.0
0x5929  ldloc.1
0x592a  stelem.ref
0x592b  ldc.i4.s 0x33
0x592d  ldstr    aDo// "Do"
0x5932  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x5937  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x593c  pop
0x593d  leave.s  loc_5949
0x593f  ldloc.0
0x5940  brfalse.s loc_5948
0x5942  ldloc.0
0x5943  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5948  endfinally
0x5949  ldarg.0
0x594a  ldarg.0
0x594b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5950  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5955  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x595a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x595f  ret
```
