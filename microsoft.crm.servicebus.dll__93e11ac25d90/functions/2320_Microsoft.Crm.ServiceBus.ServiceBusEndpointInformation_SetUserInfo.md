# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetUserInfo

- ea: `0x2320`
- end: `0x258b`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetUserInfo`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d0`

## callees

- `0x1a70`
- `0x1b70`
- `0x1b80`
- `0x1b90`
- `0x1ba0`
- `0x2320`

## pseudocode

```c

```

## disassembly

```asm
0x2320  ldarg.0
0x2321  call     instance valuetype UserClaimType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserClaim()
0x2326  ldc.i4.2
0x2327  bne.un.s loc_234E
0x2329  ldarg.0
0x232a  ldarga.s 1
0x232c  ldstr    aB// "B"
0x2331  call     instance string [mscorlib]System.Guid::ToString(string)
0x2336  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_UserInfo(string value)
0x233b  ldarg.0
0x233c  ldarga.s 2
0x233e  ldstr    aB// "B"
0x2343  call     instance string [mscorlib]System.Guid::ToString(string)
0x2348  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_InitiatingUserInfo(string value)
0x234d  ret
0x234e  ldarg.0
0x234f  call     instance valuetype UserClaimType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserClaim()
0x2354  ldc.i4.3
0x2355  bne.un   loc_258A
0x235a  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x235f  ldstr    aDisableuserinf// "DisableUserInfoClaim"
0x2364  ldc.i4.0
0x2365  callvirt T0x2B000003
0x236a  brtrue   loc_258A
0x236f  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x2374  brfalse.s loc_23CA
0x2376  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x237b  ldarg.1
0x237c  ldarg.3
0x237d  ldc.i4.2
0x237e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetAuthInfo(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType)
0x2383  stloc.0
0x2384  ldloc.0
0x2385  brfalse.s loc_23A0
0x2387  ldloc.0
0x2388  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x238d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2392  brtrue.s loc_23A0
0x2394  ldarg.0
0x2395  ldloc.0
0x2396  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x239b  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_UserInfo(string value)
0x23a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x23a5  ldarg.2
0x23a6  ldarg.3
0x23a7  ldc.i4.2
0x23a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetAuthInfo(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType)
0x23ad  stloc.0
0x23ae  ldloc.0
0x23af  brfalse.s loc_23CA
0x23b1  ldloc.0
0x23b2  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x23b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23bc  brtrue.s loc_23CA
0x23be  ldarg.0
0x23bf  ldloc.0
0x23c0  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x23c5  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_InitiatingUserInfo(string value)
0x23ca  ldarg.0
0x23cb  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserInfo()
0x23d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23d5  brtrue.s loc_23E7
0x23d7  ldarg.0
0x23d8  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_InitiatingUserInfo()
0x23dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23e2  brfalse  loc_258A
0x23e7  ldstr    aSystemuser// "systemuser"
0x23ec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x23f1  stloc.1
0x23f2  ldloc.1
0x23f3  ldc.i4.3
0x23f4  newarr   [mscorlib]System.String
0x23f9  dup
0x23fa  ldc.i4.0
0x23fb  ldstr    aDomainname// "domainname"
0x2400  stelem.ref
0x2401  dup
0x2402  ldc.i4.1
0x2403  ldstr    aWindowsliveid// "windowsliveid"
0x2408  stelem.ref
0x2409  dup
0x240a  ldc.i4.2
0x240b  ldstr    aFullname// "fullname"
0x2410  stelem.ref
0x2411  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x2416  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x241b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2420  stloc.2
0x2421  ldloc.2
0x2422  ldarg.1
0x2423  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2428  ldloc.2
0x2429  ldarg.2
0x242a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x242f  ldstr    aSystemuserid// "systemuserid"
0x2434  ldc.i4.8
0x2435  ldloc.2
0x2436  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Collections.ICollection)
0x243b  stloc.3
0x243c  ldloc.1
0x243d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x2442  ldloc.3
0x2443  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x2448  ldarg.s  4
0x244a  ldloc.1
0x244b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x2450  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x2455  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x245a  stloc.s  4
0x245c  br       loc_2570
0x2461  ldloc.s  4
0x2463  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x2468  stloc.s  5
0x246a  ldloc.s  5
0x246c  ldstr    aSystemuserid// "systemuserid"
0x2471  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2476  unbox.any [mscorlib]System.Guid
0x247b  stloc.s  6
0x247d  ldsfld   string [mscorlib]System.String::Empty
0x2482  stloc.s  7
0x2484  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2489  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x248e  ldc.i4.2
0x248f  bne.un.s loc_24CA
0x2491  ldloc.s  5
0x2493  ldstr    aWindowsliveid// "windowsliveid"
0x2498  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x249d  brfalse.s loc_24CA
0x249f  ldloc.s  5
0x24a1  ldstr    aWindowsliveid// "windowsliveid"
0x24a6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x24ab  castclass [mscorlib]System.String
0x24b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24b5  brtrue.s loc_24CA
0x24b7  ldloc.s  5
0x24b9  ldstr    aWindowsliveid// "windowsliveid"
0x24be  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x24c3  castclass [mscorlib]System.String
0x24c8  stloc.s  7
0x24ca  ldloc.s  5
0x24cc  ldstr    aDomainname// "domainname"
0x24d1  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x24d6  brfalse.s loc_2505
0x24d8  ldloc.s  5
0x24da  ldstr    aDomainname// "domainname"
0x24df  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x24e4  castclass [mscorlib]System.String
0x24e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24ee  brtrue.s loc_2505
0x24f0  ldloc.s  5
0x24f2  ldstr    aDomainname// "domainname"
0x24f7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x24fc  castclass [mscorlib]System.String
0x2501  stloc.s  7
0x2503  br.s     loc_2526
0x2505  ldloc.s  5
0x2507  ldstr    aFullname// "fullname"
0x250c  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x2511  brfalse.s loc_2526
0x2513  ldloc.s  5
0x2515  ldstr    aFullname// "fullname"
0x251a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x251f  castclass [mscorlib]System.String
0x2524  stloc.s  7
0x2526  ldloc.s  7
0x2528  ldstr    aSystemusername// "systemUserName"
0x252d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2532  ldarg.0
0x2533  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserInfo()
0x2538  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x253d  brfalse.s loc_2551
0x253f  ldloc.s  6
0x2541  ldarg.1
0x2542  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2547  brfalse.s loc_2551
0x2549  ldarg.0
0x254a  ldloc.s  7
0x254c  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_UserInfo(string value)
0x2551  ldarg.0
0x2552  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_InitiatingUserInfo()
0x2557  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x255c  brfalse.s loc_2570
0x255e  ldloc.s  6
0x2560  ldarg.2
0x2561  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2566  brfalse.s loc_2570
0x2568  ldarg.0
0x2569  ldloc.s  7
0x256b  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_InitiatingUserInfo(string value)
0x2570  ldloc.s  4
0x2572  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2577  brtrue   loc_2461
0x257c  leave.s  loc_258A
0x257e  ldloc.s  4
0x2580  brfalse.s loc_2589
0x2582  ldloc.s  4
0x2584  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2589  endfinally
0x258a  ret
```
