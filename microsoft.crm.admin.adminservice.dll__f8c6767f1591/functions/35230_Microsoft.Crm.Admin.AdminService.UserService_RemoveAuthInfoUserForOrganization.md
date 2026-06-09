# Microsoft.Crm.Admin.AdminService.UserService::RemoveAuthInfoUserForOrganization

- ea: `0x35230`
- end: `0x353af`
- name: `Microsoft.Crm.Admin.AdminService.UserService::RemoveAuthInfoUserForOrganization`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x35230`

## string_xrefs

- `0x35279`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x3532e`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35389`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35274`: `RemoveAuthInfoUserForOrganization`
- `0x35329`: `RemoveAuthInfoUserForOrganization`
- `0x35384`: `RemoveAuthInfoUserForOrganization`

## pseudocode

```c

```

## disassembly

```asm
0x35230  ldarg.0
0x35231  ldstr    aOrganizationid// "organizationId"
0x35236  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3523b  ldarg.1
0x3523c  ldstr    aAuthinfo_0// "authInfo"
0x35241  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x35246  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x3524b  stloc.0
0x3524c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35251  stloc.1
0x35252  ldloc.1
0x35253  ldstr    aAuthinfo// "AuthInfo"
0x35258  ldarg.1
0x35259  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3525e  ldloc.0
0x3525f  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x35264  ldnull
0x35265  ldc.i4.1
0x35266  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3526b  dup
0x3526c  ldc.i4.0
0x3526d  ldloc.1
0x3526e  stelem.ref
0x3526f  ldc.i4   0xD5
0x35274  ldstr    aRemoveauthinfo// "RemoveAuthInfoUserForOrganization"
0x35279  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3527e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35283  stloc.2
0x35284  ldloc.2
0x35285  brtrue.s loc_3528F
0x35287  ldc.i4.0
0x35288  stloc.s  5
0x3528a  leave    loc_353AC
0x3528f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35294  stloc.3
0x35295  ldloc.2
0x35296  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3529b  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x352a0  stloc.s  6
0x352a2  br.s     loc_352BD
0x352a4  ldloca.s 6
0x352a6  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x352ab  ldstr    aUserid// "UserId"
0x352b0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x352b5  unbox.any [mscorlib]System.Guid
0x352ba  stloc.3
0x352bb  leave.s  loc_352D6
0x352bd  ldloca.s 6
0x352bf  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x352c4  brtrue.s loc_352A4
0x352c6  leave.s  loc_352D6
0x352c8  ldloca.s 6
0x352ca  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x352d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x352d5  endfinally
0x352d6  ldloc.3
0x352d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x352dc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x352e1  brfalse.s loc_352EB
0x352e3  ldc.i4.0
0x352e4  stloc.s  5
0x352e6  leave    loc_353AC
0x352eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x352f0  stloc.1
0x352f1  ldloc.1
0x352f2  ldstr    aOrganizationid_0// "OrganizationId"
0x352f7  ldarg.0
0x352f8  box      [mscorlib]System.Guid
0x352fd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35302  ldloc.1
0x35303  ldstr    aUserid// "UserId"
0x35308  ldloc.3
0x35309  box      [mscorlib]System.Guid
0x3530e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35313  ldloc.0
0x35314  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x35319  ldnull
0x3531a  ldc.i4.1
0x3531b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35320  dup
0x35321  ldc.i4.0
0x35322  ldloc.1
0x35323  stelem.ref
0x35324  ldc.i4   0xEB
0x35329  ldstr    aRemoveauthinfo// "RemoveAuthInfoUserForOrganization"
0x3532e  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35333  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35338  ldc.i4.0
0x35339  stloc.s  4
0x3533b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x35340  brtrue.s loc_3539C
0x35342  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35347  stloc.s  7
0x35349  ldloc.s  7
0x3534b  ldstr    aUserid// "UserId"
0x35350  ldloc.3
0x35351  box      [mscorlib]System.Guid
0x35356  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3535b  ldloc.s  7
0x3535d  ldstr    aOrganizationid_0// "OrganizationId"
0x35362  ldarg.0
0x35363  box      [mscorlib]System.Guid
0x35368  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3536d  ldloc.0
0x3536e  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x35373  ldc.i4.1
0x35374  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35379  dup
0x3537a  ldc.i4.0
0x3537b  ldloc.s  7
0x3537d  stelem.ref
0x3537e  ldc.i4.0
0x3537f  ldc.i4   0xF3
0x35384  ldstr    aRemoveauthinfo// "RemoveAuthInfoUserForOrganization"
0x35389  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3538e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], bool, int32, string, string)
0x35393  stloc.s  4
0x35395  ldarg.1
0x35396  ldarg.0
0x35397  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::FlushLocatorCacheForUserMembershipChange(string, valuetype [mscorlib]System.Guid)
0x3539c  ldloc.s  4
0x3539e  stloc.s  5
0x353a0  leave.s  loc_353AC
0x353a2  ldloc.0
0x353a3  brfalse.s loc_353AB
0x353a5  ldloc.0
0x353a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x353ab  endfinally
0x353ac  ldloc.s  5
0x353ae  ret
```
