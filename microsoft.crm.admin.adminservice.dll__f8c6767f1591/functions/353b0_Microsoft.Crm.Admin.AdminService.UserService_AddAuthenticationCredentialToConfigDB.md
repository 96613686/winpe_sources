# Microsoft.Crm.Admin.AdminService.UserService::AddAuthenticationCredentialToConfigDB

- ea: `0x353b0`
- end: `0x3551e`
- name: `Microsoft.Crm.Admin.AdminService.UserService::AddAuthenticationCredentialToConfigDB`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x353b0`
- `0x35f10`

## string_xrefs

- `0x35407`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35445`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x354f5`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35402`: `AddAuthenticationCredentialToConfigDB`
- `0x35440`: `AddAuthenticationCredentialToConfigDB`
- `0x354f0`: `AddAuthenticationCredentialToConfigDB`

## pseudocode

```c

```

## disassembly

```asm
0x353b0  ldarg.0
0x353b1  ldstr    aAuthinfo_0// "authInfo"
0x353b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x353bb  ldarg.1
0x353bc  ldstr    aOriginalauthin// "originalAuthInfo"
0x353c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x353c6  ldarg.2
0x353c7  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x353cc  stloc.0
0x353cd  ldarg.0
0x353ce  call     string Microsoft.Crm.Admin.AdminService.UserService::AuthInfoToLockName(string authInfo)
0x353d3  ldc.i4.2
0x353d4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLockWithClientSideWait(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x353d9  stloc.1
0x353da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x353df  stloc.2
0x353e0  ldloc.2
0x353e1  ldstr    aAuthinfo// "AuthInfo"
0x353e6  ldarg.0
0x353e7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x353ec  ldloc.0
0x353ed  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x353f2  ldnull
0x353f3  ldc.i4.1
0x353f4  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x353f9  dup
0x353fa  ldc.i4.0
0x353fb  ldloc.2
0x353fc  stelem.ref
0x353fd  ldc.i4   0x10D
0x35402  ldstr    aAddauthenticat// "AddAuthenticationCredentialToConfigDB"
0x35407  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3540c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35411  brfalse.s loc_35418
0x35413  leave    loc_3551D
0x35418  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3541d  stloc.3
0x3541e  ldloc.3
0x3541f  ldstr    aAuthinfo// "AuthInfo"
0x35424  ldarg.1
0x35425  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3542a  ldloc.0
0x3542b  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x35430  ldnull
0x35431  ldc.i4.1
0x35432  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35437  dup
0x35438  ldc.i4.0
0x35439  ldloc.3
0x3543a  stelem.ref
0x3543b  ldc.i4   0x118
0x35440  ldstr    aAddauthenticat// "AddAuthenticationCredentialToConfigDB"
0x35445  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3544a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3544f  stloc.s  4
0x35451  ldloc.s  4
0x35453  brfalse  loc_35500
0x35458  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3545d  stloc.s  5
0x3545f  ldloc.s  4
0x35461  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x35466  stloc.s  7
0x35468  br.s     loc_3548D
0x3546a  ldloca.s 7
0x3546c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x35471  stloc.s  8
0x35473  ldloca.s 8
0x35475  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x3547a  ldstr    aUserid// "UserId"
0x3547f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x35484  unbox.any [mscorlib]System.Guid
0x35489  stloc.s  5
0x3548b  leave.s  loc_354A6
0x3548d  ldloca.s 7
0x3548f  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x35494  brtrue.s loc_3546A
0x35496  leave.s  loc_354A6
0x35498  ldloca.s 7
0x3549a  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x354a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x354a5  endfinally
0x354a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x354ab  stloc.s  6
0x354ad  ldloc.s  6
0x354af  ldstr    aId// "Id"
0x354b4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x354b9  box      [mscorlib]System.Guid
0x354be  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x354c3  ldloc.s  6
0x354c5  ldstr    aUserid// "UserId"
0x354ca  ldloc.s  5
0x354cc  box      [mscorlib]System.Guid
0x354d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x354d6  ldloc.s  6
0x354d8  ldstr    aAuthinfo// "AuthInfo"
0x354dd  ldarg.0
0x354de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x354e3  ldloc.0
0x354e4  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x354e9  ldloc.s  6
0x354eb  ldc.i4   0x12A
0x354f0  ldstr    aAddauthenticat// "AddAuthenticationCredentialToConfigDB"
0x354f5  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x354fa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x354ff  pop
0x35500  leave.s  loc_35516
0x35502  ldloc.1
0x35503  brfalse.s loc_3550B
0x35505  ldloc.1
0x35506  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3550b  endfinally
0x3550c  ldloc.0
0x3550d  brfalse.s loc_35515
0x3550f  ldloc.0
0x35510  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35515  endfinally
0x35516  ldarg.0
0x35517  ldarg.2
0x35518  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::FlushLocatorCacheForUserMembershipChange(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x3551d  ret
```
