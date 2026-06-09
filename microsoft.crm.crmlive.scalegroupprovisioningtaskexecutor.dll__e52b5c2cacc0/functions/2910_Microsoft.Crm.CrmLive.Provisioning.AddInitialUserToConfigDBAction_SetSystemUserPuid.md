# Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::SetSystemUserPuid

- ea: `0x2910`
- end: `0x29be`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::SetSystemUserPuid`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2580`

## callees

- `0x26e0`
- `0x2910`
- `0x2a30`
- `0x64b0`
- `0x91b0`
- `0x9270`

## string_xrefs

- `0x2955`: `Calling AddPrincipalToConfigDB for CrmUserId [`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.0
0x2911  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2916  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsInitialUserLicensed()
0x291b  brtrue.s loc_2920
0x291d  ldc.i4.2
0x291e  br.s     loc_2921
0x2920  ldc.i4.1
0x2921  stloc.0
0x2922  ldarg.2
0x2923  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::FormatPuid(string)
0x2928  stloc.1
0x2929  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x292e  ldarg.0
0x292f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2934  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2939  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x293e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x2943  brfalse.s loc_29A3
0x2945  ldarg.0
0x2946  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::GetDirectoryObjectId()
0x294b  stloc.2
0x294c  ldarg.0
0x294d  ldc.i4.5
0x294e  newarr   [mscorlib]System.Object
0x2953  dup
0x2954  ldc.i4.0
0x2955  ldstr    aCallingAddprin// "Calling AddPrincipalToConfigDB for CrmU"...
0x295a  stelem.ref
0x295b  dup
0x295c  ldc.i4.1
0x295d  ldarg.0
0x295e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x2963  box      [mscorlib]System.Guid
0x2968  stelem.ref
0x2969  dup
0x296a  ldc.i4.2
0x296b  ldstr    aObjectid_0// "] ObjectId ["
0x2970  stelem.ref
0x2971  dup
0x2972  ldc.i4.3
0x2973  ldloc.2
0x2974  box      [mscorlib]System.Guid
0x2979  stelem.ref
0x297a  dup
0x297b  ldc.i4.4
0x297c  ldstr    asc_36586// "]"
0x2981  stelem.ref
0x2982  call     string [mscorlib]System.String::Concat(object[])
0x2987  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x298c  ldarg.1
0x298d  ldarg.0
0x298e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x2993  ldloc.1
0x2994  ldc.i4.0
0x2995  ldsfld   string [mscorlib]System.String::Empty
0x299a  ldc.i4.0
0x299b  ldloc.2
0x299c  ldloc.0
0x299d  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserService::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserServiceIsToBeAppliedUpdateMode)
0x29a2  ret
0x29a3  ldarg.1
0x29a4  ldarg.0
0x29a5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x29aa  ldloc.1
0x29ab  ldc.i4.0
0x29ac  ldsfld   string [mscorlib]System.String::Empty
0x29b1  ldc.i4.0
0x29b2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29b7  ldloc.0
0x29b8  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserService::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserServiceIsToBeAppliedUpdateMode)
0x29bd  ret
```
