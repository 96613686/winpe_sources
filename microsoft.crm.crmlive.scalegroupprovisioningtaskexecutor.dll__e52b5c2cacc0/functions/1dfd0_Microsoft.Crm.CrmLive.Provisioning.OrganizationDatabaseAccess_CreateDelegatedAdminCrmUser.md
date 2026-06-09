# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateDelegatedAdminCrmUser

- ea: `0x1dfd0`
- end: `0x1e0dd`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateDelegatedAdminCrmUser`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1dfc0`
- `0x1dfd0`
- `0x20f10`
- `0x21010`

## string_xrefs

- `0x1e08a`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1e085`: `CreateDelegatedAdminCrmUser`

## pseudocode

```c

```

## disassembly

```asm
0x1dfd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1dfd5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1dfda  ldc.i4.2
0x1dfdb  beq.s    loc_1DFE3
0x1dfdd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dfe2  ret
0x1dfe3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dfe8  stloc.0
0x1dfe9  ldarg.0
0x1dfea  ldarg.1
0x1dfeb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveDelegatedAdminUserId(valuetype [mscorlib]System.Guid organizationId)
0x1dff0  stloc.1
0x1dff1  ldloc.1
0x1dff2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dff7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1dffc  brfalse.s loc_1E002
0x1dffe  ldloc.1
0x1dfff  stloc.0
0x1e000  br.s     loc_1E047
0x1e002  ldarg.2
0x1e003  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1e008  stloc.3
0x1e009  ldarg.1
0x1e00a  ldarg.2
0x1e00b  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::get_ResourceManager()
0x1e010  ldstr    aNeworgutilityD// "NewOrgUtility.DelegatedAdmin.FirstName"
0x1e015  ldloc.3
0x1e016  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x1e01b  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::get_ResourceManager()
0x1e020  ldstr    aNeworgutilityD_0// "NewOrgUtility.DelegatedAdmin.LastName"
0x1e025  ldloc.3
0x1e026  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x1e02b  ldc.i4.5
0x1e02c  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::get_ResourceManager()
0x1e031  ldstr    aNeworgutilityD_1// "NewOrgUtility.DelegatedAdmin.InternalEm"...
0x1e036  ldloc.3
0x1e037  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x1e03c  ldstr    a627090ff40a340// "{627090FF-40A3-4053-8790-584EDC5BE201}"
0x1e041  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateCrmUserEntity(valuetype [mscorlib]System.Guid organizationId, int32 languageCode, string firstName, string lastName, int32 systemUserAccessMode, string internalEmailAddress, string roleToAssign)
0x1e046  stloc.0
0x1e047  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::get_CreateCrmUserTestMode()
0x1e04c  brfalse.s loc_1E054
0x1e04e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1e053  ret
0x1e054  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1e059  stloc.2
0x1e05a  ldloc.2
0x1e05b  ldstr    aDelegatedadmin// "DelegatedAdminCrmUserId"
0x1e060  ldloc.0
0x1e061  box      [mscorlib]System.Guid
0x1e066  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1e06b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x1e070  stloc.s  4
0x1e072  ldloc.s  4
0x1e074  ldstr    aOrganization// "Organization"
0x1e079  ldarg.1
0x1e07a  box      [mscorlib]System.Guid
0x1e07f  ldloc.2
0x1e080  ldc.i4   0x655
0x1e085  ldstr    aCreatedelegate// "CreateDelegatedAdminCrmUser"
0x1e08a  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1e08f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1e094  pop
0x1e095  leave.s  loc_1E0A3
0x1e097  ldloc.s  4
0x1e099  brfalse.s loc_1E0A2
0x1e09b  ldloc.s  4
0x1e09d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e0a2  endfinally
0x1e0a3  ldloc.0
0x1e0a4  ldstr    aDelegatedadmin_0// "delegatedAdminCrmUserId"
0x1e0a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1e0ae  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1e0b3  dup
0x1e0b4  ldstr    aOrganizationid_1// "organizationid"
0x1e0b9  ldarg.1
0x1e0ba  box      [mscorlib]System.Guid
0x1e0bf  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1e0c4  dup
0x1e0c5  ldstr    aDelegatedadmin_1// "delegatedadminuserid"
0x1e0ca  ldloc.0
0x1e0cb  box      [mscorlib]System.Guid
0x1e0d0  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1e0d5  ldarg.1
0x1e0d6  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.NewOrgUtility::OrganizationUpdateProperties(class [mscorlib]System.Collections.Hashtable, valuetype [mscorlib]System.Guid)
0x1e0db  ldloc.0
0x1e0dc  ret
```
