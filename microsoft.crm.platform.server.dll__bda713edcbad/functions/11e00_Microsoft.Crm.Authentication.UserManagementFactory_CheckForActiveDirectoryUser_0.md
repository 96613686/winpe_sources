# Microsoft.Crm.Authentication.UserManagementFactory::CheckForActiveDirectoryUser_0

- ea: `0x11e00`
- end: `0x11f55`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::CheckForActiveDirectoryUser_0`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x11cb0`
- `0x11df0`

## callees

- `0x11c00`
- `0x11e00`
- `0x12600`
- `0x63400`

## string_xrefs

- `0x11ee3`: `	SetExternalActiveDirectoryInformation : AddPrincipalToGroupByName Starting`
- `0x11f0d`: `	SetExternalActiveDirectoryInformation : AddPrincipalToGroupByName Completed`

## pseudocode

```c

```

## disassembly

```asm
0x11e00  ldarg.1
0x11e01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11e06  brfalse.s loc_11E0A
0x11e08  ldnull
0x11e09  ret
0x11e0a  ldarg.1
0x11e0b  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::ValidateActiveDirectoryNameFormat(string)
0x11e10  ldarg.1
0x11e11  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.FederatedUserInformation::ValidateUserPrincipalName(string)
0x11e16  stloc.0
0x11e17  ldnull
0x11e18  stloc.1
0x11e19  dup
0x11e1a  ldloc.0
0x11e1b  or
0x11e1c  brfalse.s loc_11E28
0x11e1e  ldarg.0
0x11e1f  ldarg.1
0x11e20  ldarg.s  4
0x11e22  call     instance class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation Microsoft.Crm.Authentication.UserManagementFactory::GetActiveDirectoryInformation(string domainName, bool limitGlobalCatalogSearches)
0x11e27  stloc.1
0x11e28  brfalse  loc_11F53
0x11e2d  ldloc.1
0x11e2e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_ActiveDirectoryId()
0x11e33  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11e38  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11e3d  brtrue.s loc_11E50
0x11e3f  ldloc.1
0x11e40  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_Identifier()
0x11e45  ldnull
0x11e46  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Equality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x11e4b  brfalse  loc_11F53
0x11e50  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_ManageExternalGroups()
0x11e55  brfalse  loc_11F1D
0x11e5a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11e5f  stloc.3
0x11e60  ldarg.2
0x11e61  isinst   Microsoft.Crm.Authentication.ActiveDirectoryUserValidationParameters
0x11e66  stloc.s  4
0x11e68  ldloc.s  4
0x11e6a  brfalse.s loc_11E8F
0x11e6c  ldloc.s  4
0x11e6e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Authentication.ActiveDirectoryUserValidationParameters::get_ReportingGroupId()
0x11e73  stloc.s  5
0x11e75  ldloca.s 5
0x11e77  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x11e7c  brfalse.s loc_11E8F
0x11e7e  ldloc.s  4
0x11e80  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Authentication.ActiveDirectoryUserValidationParameters::get_ReportingGroupId()
0x11e85  stloc.s  5
0x11e87  ldloca.s 5
0x11e89  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x11e8e  stloc.3
0x11e8f  ldloc.3
0x11e90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11e95  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11e9a  brfalse.s loc_11ECE
0x11e9c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x11ea1  ldarg.3
0x11ea2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11ea7  ldarg.3
0x11ea8  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x11ead  stloc.s  6
0x11eaf  ldloc.s  6
0x11eb1  brfalse.s loc_11ECE
0x11eb3  ldloc.s  6
0x11eb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ReportingGroupId()
0x11eba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11ebf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11ec4  brfalse.s loc_11ECE
0x11ec6  ldloc.s  6
0x11ec8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ReportingGroupId()
0x11ecd  stloc.3
0x11ece  ldloc.3
0x11ecf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11ed4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11ed9  brfalse.s loc_11F1D
0x11edb  ldarg.3
0x11edc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11ee1  ldc.i4.s 0x14
0x11ee3  ldstr    aSetexternalact// "\tSetExternalActiveDirectoryInformation"...
0x11ee8  ldc.i4.0
0x11ee9  newarr   [mscorlib]System.Object
0x11eee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11ef3  ldloc.1
0x11ef4  ldloc.1
0x11ef5  callvirt instance string [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_UniqueName()
0x11efa  ldloc.3
0x11efb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityLibrary::AddPrincipalToGroupByName(string NTName, valuetype [mscorlib]System.Guid groupId)
0x11f00  callvirt instance void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::set_ActiveDirectoryId(valuetype [mscorlib]System.Guid)
0x11f05  ldarg.3
0x11f06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11f0b  ldc.i4.s 0x14
0x11f0d  ldstr    aSetexternalact_0// "\tSetExternalActiveDirectoryInformation"...
0x11f12  ldc.i4.0
0x11f13  newarr   [mscorlib]System.Object
0x11f18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11f1d  ldloc.1
0x11f1e  callvirt instance string [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_UniqueName()
0x11f23  call     unsigned int8[] [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetSidFromAccount(string)
0x11f28  stloc.2
0x11f29  ldloc.1
0x11f2a  ldloc.2
0x11f2b  ldc.i4.0
0x11f2c  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x11f31  callvirt instance void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::set_Identifier(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x11f36  ldloc.1
0x11f37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_ActiveDirectoryId()
0x11f3c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11f41  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11f46  brfalse.s loc_11F53
0x11f48  ldloc.1
0x11f49  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x11f4e  callvirt instance void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::set_ActiveDirectoryId(valuetype [mscorlib]System.Guid)
0x11f53  ldloc.1
0x11f54  ret
```
