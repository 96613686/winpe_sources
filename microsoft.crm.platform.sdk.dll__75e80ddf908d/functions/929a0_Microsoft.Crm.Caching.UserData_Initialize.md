# Microsoft.Crm.Caching.UserData::Initialize

- ea: `0x929a0`
- end: `0x92bc2`
- name: `Microsoft.Crm.Caching.UserData::Initialize`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x81f50`
- `0x81f60`
- `0x85a60`
- `0x85df0`
- `0x90a20`
- `0x91320`
- `0x91990`
- `0x91a70`
- `0x91ab0`
- `0x91d30`
- `0x91d50`
- `0x91d90`
- `0x91dd0`
- `0x91e30`
- `0x91e50`
- `0x91e70`
- `0x91e90`
- `0x91ed0`
- `0x91f10`
- `0x91f90`
- `0x91fb0`
- `0x92380`
- `0x929a0`
- `0x92bd0`
- `0x92c00`
- `0x92f80`
- `0x93840`
- `0x96cd0`

## string_xrefs

- `0x92b80`: `azureactivedirectoryobjectid`
- `0x92b8e`: `azureactivedirectoryobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x929a0  ldarg.1
0x929a1  ldstr    aOrganizationid_1// "organizationid"
0x929a6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x929ab  brtrue.s loc_929C3
0x929ad  ldarg.0
0x929ae  ldarg.1
0x929af  ldstr    aOrganizationid_1// "organizationid"
0x929b4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x929b9  unbox.any [mscorlib]System.Guid
0x929be  call     instance void Microsoft.Crm.Caching.UserData::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x929c3  ldarg.0
0x929c4  ldarg.s  0xE
0x929c6  stfld    bool Microsoft.Crm.Caching.UserData::_isSystemUser
0x929cb  ldarg.0
0x929cc  ldarg.1
0x929cd  call     instance void Microsoft.Crm.Caching.UserData::InitUserProperties(class Microsoft.Crm.Caching.ICacheEntityWrapper user)
0x929d2  ldarg.2
0x929d3  brfalse.s loc_92A53
0x929d5  ldarg.0
0x929d6  ldarg.2
0x929d7  ldarg.s  0xF
0x929d9  call     instance void Microsoft.Crm.Caching.UserData::InitUserSettings(class Microsoft.Crm.Caching.ICacheEntityWrapper userSettings, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x929de  ldarg.0
0x929df  ldarg.2
0x929e0  ldarg.s  0xF
0x929e2  call     instance void Microsoft.Crm.Caching.UserData::InitUserCultureInfo(class Microsoft.Crm.Caching.ICacheEntityWrapper usersettings, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x929e7  ldarg.s  0xD
0x929e9  brtrue.s loc_929F8
0x929eb  ldarg.0
0x929ec  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.DynamicTimeZone [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.DynamicTimeZone::get_GreenwichStandardTimeZone()
0x929f1  call     instance void Microsoft.Crm.Caching.UserData::set_TimeZone(class [mscorlib]System.TimeZone value)
0x929f6  br.s     loc_92A00
0x929f8  ldarg.0
0x929f9  ldarg.s  0xD
0x929fb  call     instance void Microsoft.Crm.Caching.UserData::set_TimeZone(class [mscorlib]System.TimeZone value)
0x92a00  ldarg.2
0x92a01  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x92a06  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92a0b  brtrue.s loc_92A2C
0x92a0d  ldarg.0
0x92a0e  ldarg.2
0x92a0f  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x92a14  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92a19  unbox.any [mscorlib]System.Guid
0x92a1e  call     instance void Microsoft.Crm.Caching.UserData::set_TransactionCurrencyId(valuetype [mscorlib]System.Guid value)
0x92a23  ldarg.0
0x92a24  ldc.i4.0
0x92a25  stfld    bool Microsoft.Crm.Caching.UserData::_isDefaultCurrencyForUserNull
0x92a2a  br.s     loc_92A96
0x92a2c  ldarg.0
0x92a2d  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x92a32  ldarg.s  0xF
0x92a34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x92a39  ldarg.s  0xF
0x92a3b  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x92a40  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.IOrganizationSettings::get_BaseCurrencyId()
0x92a45  call     instance void Microsoft.Crm.Caching.UserData::set_TransactionCurrencyId(valuetype [mscorlib]System.Guid value)
0x92a4a  ldarg.0
0x92a4b  ldc.i4.1
0x92a4c  stfld    bool Microsoft.Crm.Caching.UserData::_isDefaultCurrencyForUserNull
0x92a51  br.s     loc_92A96
0x92a53  ldarg.0
0x92a54  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x92a59  ldarg.s  0xF
0x92a5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x92a60  ldarg.s  0xF
0x92a62  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x92a67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.IOrganizationSettings::get_BaseCurrencyId()
0x92a6c  call     instance void Microsoft.Crm.Caching.UserData::set_TransactionCurrencyId(valuetype [mscorlib]System.Guid value)
0x92a71  ldarg.0
0x92a72  ldc.i4.1
0x92a73  stfld    bool Microsoft.Crm.Caching.UserData::_isDefaultCurrencyForUserNull
0x92a78  ldarg.0
0x92a79  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x92a7e  ldarg.s  0xF
0x92a80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x92a85  ldarg.s  0xF
0x92a87  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x92a8c  callvirt instance int32 Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x92a91  call     instance void Microsoft.Crm.Caching.UserData::set_LanguageId(int32 value)
0x92a96  ldarg.3
0x92a97  ldnull
0x92a98  ldftn    int32 Microsoft.Crm.Caching.UserData::CompareRolePrivileges(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege rp1, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege rp2)
0x92a9e  newobj   instance void class [mscorlib]System.Comparison`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::.ctor(object, native int)
0x92aa3  call     T0x2B0000D7
0x92aa8  ldarg.0
0x92aa9  ldarg.3
0x92aaa  call     instance void Microsoft.Crm.Caching.UserData::set_Privileges(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] value)
0x92aaf  ldarg.0
0x92ab0  ldarg.s  5
0x92ab2  call     instance void Microsoft.Crm.Caching.UserData::set_MaxPrivilegeDepth(class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>> value)
0x92ab7  ldarg.s  6
0x92ab9  brfalse.s loc_92ACE
0x92abb  ldarg.s  4
0x92abd  ldnull
0x92abe  ldftn    int32 Microsoft.Crm.Caching.UserData::CompareRolePrivileges(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege rp1, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege rp2)
0x92ac4  newobj   instance void class [mscorlib]System.Comparison`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::.ctor(object, native int)
0x92ac9  call     T0x2B0000D7
0x92ace  ldarg.0
0x92acf  ldarg.s  4
0x92ad1  call     instance void Microsoft.Crm.Caching.UserData::set_MaxDepthTeamPrivileges(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] value)
0x92ad6  ldarg.0
0x92ad7  ldarg.s  6
0x92ad9  call     instance void Microsoft.Crm.Caching.UserData::set_IsMaxDepthTeamPrivilegesDataExist(bool value)
0x92ade  ldarg.0
0x92adf  ldarg.s  7
0x92ae1  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilegeCollection Microsoft.Crm.Caching.UserData::_attributePrivileges
0x92ae6  ldarg.s  7
0x92ae8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege>::GetEnumerator()
0x92aed  stloc.0
0x92aee  br.s     loc_92B20
0x92af0  ldloc.0
0x92af1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege>::get_Current()
0x92af6  stloc.1
0x92af7  ldarg.0
0x92af8  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.AttributePermissions> Microsoft.Crm.Caching.UserData::_dictionaryAttributePrivileges
0x92afd  ldloc.1
0x92afe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_AttributeId()
0x92b03  ldloc.1
0x92b04  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_CanCreate()
0x92b09  ldloc.1
0x92b0a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_CanRead()
0x92b0f  ldloc.1
0x92b10  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_CanUpdate()
0x92b15  newobj   instance void Microsoft.Crm.Caching.AttributePermissions::.ctor(int32 canCreate, int32 canRead, int32 canUpdate)
0x92b1a  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.AttributePermissions>::TryAdd(var<u1>, !!T0)
0x92b1f  pop
0x92b20  ldloc.0
0x92b21  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x92b26  brtrue.s loc_92AF0
0x92b28  leave.s  loc_92B34
0x92b2a  ldloc.0
0x92b2b  brfalse.s loc_92B33
0x92b2d  ldloc.0
0x92b2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92b33  endfinally
0x92b34  ldarg.0
0x92b35  ldarg.s  8
0x92b37  call     instance void Microsoft.Crm.Caching.UserData::set_Teams(valuetype [mscorlib]System.Guid[] value)
0x92b3c  ldarg.0
0x92b3d  ldarg.s  9
0x92b3f  call     instance void Microsoft.Crm.Caching.UserData::set_Roles(valuetype [mscorlib]System.Guid[] value)
0x92b44  ldarg.0
0x92b45  ldarg.s  0xA
0x92b47  call     instance void Microsoft.Crm.Caching.UserData::set_ParentRootRoles(valuetype [mscorlib]System.Guid[] value)
0x92b4c  ldarg.0
0x92b4d  ldarg.s  0xB
0x92b4f  call     instance void Microsoft.Crm.Caching.UserData::set_BusinessUnitReadPrivilegeDictionary(class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]> value)
0x92b54  ldarg.0
0x92b55  ldarg.s  0xC
0x92b57  call     instance void Microsoft.Crm.Caching.UserData::set_IsSupportUser(bool value)
0x92b5c  ldarg.1
0x92b5d  ldstr    aApplicationid// "applicationid"
0x92b62  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92b67  brtrue.s loc_92B7F
0x92b69  ldarg.0
0x92b6a  ldarg.1
0x92b6b  ldstr    aApplicationid_0// "applicationId"
0x92b70  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92b75  unbox.any [mscorlib]System.Guid
0x92b7a  call     instance void Microsoft.Crm.Caching.UserData::set_ApplicationId(valuetype [mscorlib]System.Guid value)
0x92b7f  ldarg.1
0x92b80  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x92b85  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92b8a  brtrue.s loc_92BA2
0x92b8c  ldarg.0
0x92b8d  ldarg.1
0x92b8e  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x92b93  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92b98  unbox.any [mscorlib]System.Guid
0x92b9d  call     instance void Microsoft.Crm.Caching.UserData::set_AzureActiveDirectoryObjectId(valuetype [mscorlib]System.Guid value)
0x92ba2  ldarg.s  0xE
0x92ba4  brfalse.s loc_92BAD
0x92ba6  ldarg.0
0x92ba7  ldc.i4.0
0x92ba8  call     instance void Microsoft.Crm.Caching.UserData::set_IsDisabled(bool value)
0x92bad  ldarg.0
0x92bae  ldarg.0
0x92baf  ldarg.s  0xF
0x92bb1  newobj   instance void Microsoft.Crm.Caching.UserAuthenticationTracking::.ctor(class Microsoft.Crm.Caching.UserData user, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x92bb6  stfld    class Microsoft.Crm.Caching.UserAuthenticationTracking Microsoft.Crm.Caching.UserData::_userAuthenticationTracking
0x92bbb  ldarg.0
0x92bbc  call     instance void Microsoft.Crm.Caching.UserData::UpdateTimestamp()
0x92bc1  ret
```
