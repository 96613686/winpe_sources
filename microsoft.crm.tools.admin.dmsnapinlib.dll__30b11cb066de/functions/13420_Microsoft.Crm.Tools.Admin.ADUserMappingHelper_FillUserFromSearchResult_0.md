# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FillUserFromSearchResult_0

- ea: `0x13420`
- end: `0x135bc`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FillUserFromSearchResult_0`
- size: `412`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x133b0`
- `0x133c0`

## callees

- `0x13420`
- `0x138b0`

## string_xrefs

- `0x13563`: `objectSid`

## pseudocode

```c

```

## disassembly

```asm
0x13420  ldarg.1
0x13421  ldarg.0
0x13422  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13427  ldstr    aDistinguishedn// "distinguishedName"
0x1342c  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x13431  ldc.i4.0
0x13432  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13437  castclass [mscorlib]System.String
0x1343c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADDistinguishedName(string)
0x13441  ldarg.1
0x13442  ldarg.0
0x13443  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13448  ldstr    aCn_0// "cn"
0x1344d  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x13452  ldc.i4.0
0x13453  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13458  castclass [mscorlib]System.String
0x1345d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADCommonName(string)
0x13462  ldarg.1
0x13463  ldc.i4.1
0x13464  ldarg.0
0x13465  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x1346a  ldstr    aDisplayname// "displayName"
0x1346f  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x13474  callvirt instance int32 [mscorlib]System.Collections.ReadOnlyCollectionBase::get_Count()
0x13479  ble.s    loc_1347E
0x1347b  ldnull
0x1347c  br.s     loc_13499
0x1347e  ldarg.0
0x1347f  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13484  ldstr    aDisplayname// "displayName"
0x13489  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x1348e  ldc.i4.0
0x1348f  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13494  castclass [mscorlib]System.String
0x13499  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADDisplayName(string)
0x1349e  ldarg.1
0x1349f  ldarg.0
0x134a0  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x134a5  ldstr    aObjectguid// "objectGuid"
0x134aa  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x134af  ldc.i4.0
0x134b0  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x134b5  castclass unsigned int8[]
0x134ba  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int8[])
0x134bf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADObjectGuid(valuetype [mscorlib]System.Guid)
0x134c4  ldarg.1
0x134c5  ldarg.0
0x134c6  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x134cb  ldstr    aSamaccountname_2// "samAccountName"
0x134d0  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x134d5  ldc.i4.0
0x134d6  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x134db  castclass [mscorlib]System.String
0x134e0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADSamAccountName(string)
0x134e5  ldarg.1
0x134e6  ldc.i4.1
0x134e7  ldarg.0
0x134e8  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x134ed  ldstr    aGivenname// "givenName"
0x134f2  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x134f7  callvirt instance int32 [mscorlib]System.Collections.ReadOnlyCollectionBase::get_Count()
0x134fc  ble.s    loc_13501
0x134fe  ldnull
0x134ff  br.s     loc_1351C
0x13501  ldarg.0
0x13502  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13507  ldstr    aGivenname// "givenName"
0x1350c  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x13511  ldc.i4.0
0x13512  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13517  castclass [mscorlib]System.String
0x1351c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADGivenName(string)
0x13521  ldarg.1
0x13522  ldc.i4.1
0x13523  ldarg.0
0x13524  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13529  ldstr    aSn// "sn"
0x1352e  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x13533  callvirt instance int32 [mscorlib]System.Collections.ReadOnlyCollectionBase::get_Count()
0x13538  ble.s    loc_1353D
0x1353a  ldnull
0x1353b  br.s     loc_13558
0x1353d  ldarg.0
0x1353e  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13543  ldstr    aSn// "sn"
0x13548  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x1354d  ldc.i4.0
0x1354e  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13553  castclass [mscorlib]System.String
0x13558  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADSurname(string)
0x1355d  ldarg.0
0x1355e  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x13563  ldstr    aObjectsid// "objectSid"
0x13568  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x1356d  ldc.i4.0
0x1356e  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x13573  castclass unsigned int8[]
0x13578  stloc.0
0x13579  ldarg.1
0x1357a  ldarg.1
0x1357b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBDomainName()
0x13580  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x13585  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.FederatedUserInformation::ValidateUserPrincipalName(string)
0x1358a  brtrue.s loc_13594
0x1358c  ldloc.0
0x1358d  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetDomainAccountFromObjectSid(unsigned int8[] objectSid)
0x13592  br.s     loc_1359A
0x13594  ldarg.1
0x13595  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBDomainName()
0x1359a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADDomainAccount(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount)
0x1359f  ldarg.1
0x135a0  ldarg.1
0x135a1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_ADDomainAccount()
0x135a6  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x135ab  call     unsigned int8[] [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetSidFromAccount(string)
0x135b0  ldc.i4.0
0x135b1  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x135b6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_UserSid(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x135bb  ret
```
