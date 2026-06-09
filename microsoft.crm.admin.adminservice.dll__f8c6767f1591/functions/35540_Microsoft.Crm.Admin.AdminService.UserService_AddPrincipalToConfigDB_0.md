# Microsoft.Crm.Admin.AdminService.UserService::AddPrincipalToConfigDB_0

- ea: `0x35540`
- end: `0x35a1e`
- name: `Microsoft.Crm.Admin.AdminService.UserService::AddPrincipalToConfigDB_0`
- size: `1246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x35520`

## callees

- `0x35540`
- `0x35a20`
- `0x35f10`

## string_xrefs

- `0x35604`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35656`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x356a0`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35716`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x3579c`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x357de`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x3586e`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x358cc`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x359a7`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x359d7`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35969`: `DirectoryObjectId`
- `0x359b4`: `DirectoryObjectId`
- `0x355ff`: `AddPrincipalToConfigDB`
- `0x35651`: `AddPrincipalToConfigDB`
- `0x3569b`: `AddPrincipalToConfigDB`
- `0x35711`: `AddPrincipalToConfigDB`
- `0x35797`: `AddPrincipalToConfigDB`
- `0x357d9`: `AddPrincipalToConfigDB`
- `0x35869`: `AddPrincipalToConfigDB`
- `0x358c7`: `AddPrincipalToConfigDB`
- `0x359a2`: `AddPrincipalToConfigDB`
- `0x359d2`: `AddPrincipalToConfigDB`

## pseudocode

```c

```

## disassembly

```asm
0x35540  ldarg.0
0x35541  ldstr    aOrganizationid// "organizationId"
0x35546  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3554b  ldarg.1
0x3554c  ldstr    aCrmid// "crmId"
0x35551  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x35556  ldarg.2
0x35557  ldstr    aAuthinfo_0// "authInfo"
0x3555c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x35561  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x35566  ldarg.0
0x35567  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x3556c  brfalse.s loc_3557D
0x3556e  ldarg.0
0x3556f  ldarg.1
0x35570  ldarg.2
0x35571  ldarg.s  5
0x35573  ldarg.s  6
0x35575  ldarg.s  7
0x35577  call     void Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserRecordsInConfigDb(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmUserId, string authInfo, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext, valuetype [mscorlib]System.Guid directoryObjectId, valuetype Microsoft.Crm.Admin.AdminService.UserServiceIsToBeAppliedUpdateMode isToBeAppliedUpdateMode)
0x3557c  ret
0x3557d  ldarg.3
0x3557e  brfalse.s loc_3558C
0x35580  ldarg.s  4
0x35582  ldstr    aOriginalauthin// "originalAuthInfo"
0x35587  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3558c  ldarg.s  5
0x3558e  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x35593  stloc.0
0x35594  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35599  stloc.1
0x3559a  ldloc.0
0x3559b  ldc.i4.2
0x3559c  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x355a1  stloc.2
0x355a2  ldloc.2
0x355a3  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x355a8  ldloc.2
0x355a9  callvirt instance class [System.Data]System.Data.IDbTransaction [System.Data]System.Data.IDbConnection::BeginTransaction()
0x355ae  stloc.3
0x355af  ldarg.2
0x355b0  call     string Microsoft.Crm.Admin.AdminService.UserService::AuthInfoToLockName(string authInfo)
0x355b5  ldc.i4.2
0x355b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLockWithClientSideWait(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x355bb  stloc.s  4
0x355bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x355c2  stloc.s  5
0x355c4  ldloc.s  5
0x355c6  ldstr    aCrmuserid// "CrmUserId"
0x355cb  ldarg.1
0x355cc  box      [mscorlib]System.Guid
0x355d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x355d6  ldloc.s  5
0x355d8  ldstr    aOrganizationid_0// "OrganizationId"
0x355dd  ldarg.0
0x355de  box      [mscorlib]System.Guid
0x355e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x355e8  ldloc.0
0x355e9  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x355ee  ldnull
0x355ef  ldc.i4.1
0x355f0  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x355f5  dup
0x355f6  ldc.i4.0
0x355f7  ldloc.s  5
0x355f9  stelem.ref
0x355fa  ldc.i4   0x161
0x355ff  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x35604  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35609  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3560e  stloc.s  6
0x35610  ldarg.3
0x35611  brtrue.s loc_3561C
0x35613  ldloc.s  6
0x35615  brfalse.s loc_3561C
0x35617  leave    loc_35A1D
0x3561c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35621  stloc.s  5
0x35623  ldarg.3
0x35624  brfalse.s loc_35677
0x35626  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3562b  stloc.s  8
0x3562d  ldloc.s  8
0x3562f  ldstr    aAuthinfo// "AuthInfo"
0x35634  ldarg.2
0x35635  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3563a  ldloc.0
0x3563b  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x35640  ldnull
0x35641  ldc.i4.1
0x35642  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35647  dup
0x35648  ldc.i4.0
0x35649  ldloc.s  8
0x3564b  stelem.ref
0x3564c  ldc.i4   0x173
0x35651  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x35656  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3565b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35660  brfalse.s loc_35667
0x35662  leave    loc_35A1D
0x35667  ldloc.s  5
0x35669  ldstr    aAuthinfo// "AuthInfo"
0x3566e  ldarg.s  4
0x35670  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35675  br.s     loc_35684
0x35677  ldloc.s  5
0x35679  ldstr    aAuthinfo// "AuthInfo"
0x3567e  ldarg.2
0x3567f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35684  ldloc.0
0x35685  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x3568a  ldnull
0x3568b  ldc.i4.1
0x3568c  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35691  dup
0x35692  ldc.i4.0
0x35693  ldloc.s  5
0x35695  stelem.ref
0x35696  ldc.i4   0x182
0x3569b  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x356a0  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x356a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x356aa  stloc.s  6
0x356ac  ldloc.s  6
0x356ae  brfalse  loc_35807
0x356b3  ldloc.s  6
0x356b5  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x356ba  stloc.s  9
0x356bc  br       loc_357EB
0x356c1  ldloca.s 9
0x356c3  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x356c8  stloc.s  0xC
0x356ca  ldloca.s 0xC
0x356cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x356d1  ldstr    aUserid// "UserId"
0x356d6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x356db  unbox.any [mscorlib]System.Guid
0x356e0  stloc.1
0x356e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x356e6  stloc.s  0xA
0x356e8  ldloc.s  0xA
0x356ea  ldstr    aId// "Id"
0x356ef  ldloc.1
0x356f0  box      [mscorlib]System.Guid
0x356f5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x356fa  ldloc.0
0x356fb  ldstr    aSystemuser// "SystemUser"
0x35700  ldnull
0x35701  ldc.i4.1
0x35702  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35707  dup
0x35708  ldc.i4.0
0x35709  ldloc.s  0xA
0x3570b  stelem.ref
0x3570c  ldc.i4   0x18F
0x35711  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x35716  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3571b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35720  stloc.s  0xB
0x35722  ldloc.s  0xB
0x35724  brfalse  loc_357F7
0x35729  ldloc.s  0xB
0x3572b  ldc.i4.0
0x3572c  call     T0x2B0000B1
0x35731  stloc.s  0xC
0x35733  ldloca.s 0xC
0x35735  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x3573a  ldstr    aDefaultorganiz_1// "defaultOrganizationId"
0x3573f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x35744  unbox.any [mscorlib]System.Guid
0x35749  stloc.s  0xD
0x3574b  ldloc.s  0xD
0x3574d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35752  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35757  brtrue.s loc_35766
0x35759  ldloc.s  0xD
0x3575b  ldarg.0
0x3575c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35761  brfalse  loc_357F7
0x35766  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3576b  stloc.s  0xE
0x3576d  ldloc.s  0xE
0x3576f  ldstr    aId// "Id"
0x35774  ldloc.s  0xD
0x35776  box      [mscorlib]System.Guid
0x3577b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35780  ldloc.0
0x35781  ldstr    aOrganization// "Organization"
0x35786  ldnull
0x35787  ldc.i4.1
0x35788  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3578d  dup
0x3578e  ldc.i4.0
0x3578f  ldloc.s  0xE
0x35791  stelem.ref
0x35792  ldc.i4   0x19A
0x35797  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x3579c  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x357a1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x357a6  brtrue.s loc_357F7
0x357a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x357ad  stloc.s  0xF
0x357af  ldloc.s  0xF
0x357b1  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x357b6  ldarg.0
0x357b7  box      [mscorlib]System.Guid
0x357bc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x357c1  ldloc.0
0x357c2  ldstr    aSystemuser// "SystemUser"
0x357c7  ldloc.s  0xF
0x357c9  ldc.i4.1
0x357ca  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x357cf  dup
0x357d0  ldc.i4.0
0x357d1  ldloc.s  0xA
0x357d3  stelem.ref
0x357d4  ldc.i4   0x19F
0x357d9  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x357de  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x357e3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x357e8  pop
0x357e9  leave.s  loc_35807
0x357eb  ldloca.s 9
0x357ed  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x357f2  brtrue   loc_356C1
0x357f7  leave.s  loc_35807
0x357f9  ldloca.s 9
0x357fb  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x35801  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35806  endfinally
0x35807  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3580c  stloc.s  7
0x3580e  ldloc.1
0x3580f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35814  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35819  brtrue.s loc_35831
0x3581b  ldarg.3
0x3581c  brfalse  loc_358D7
0x35821  ldloc.1
0x35822  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35827  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3582c  brfalse  loc_358D7
0x35831  ldloc.s  7
0x35833  ldstr    aId// "Id"
0x35838  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3583d  box      [mscorlib]System.Guid
0x35842  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35847  ldloc.s  7
0x35849  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x3584e  ldarg.0
0x3584f  box      [mscorlib]System.Guid
0x35854  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35859  ldarg.3
0x3585a  brtrue.s loc_3587E
0x3585c  ldloc.0
0x3585d  ldstr    aSystemuser// "SystemUser"
0x35862  ldloc.s  7
0x35864  ldc.i4   0x1B0
0x35869  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x3586e  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35873  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x35878  unbox.any [mscorlib]System.Guid
0x3587d  stloc.1
0x3587e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35883  stloc.s  7
0x35885  ldloc.s  7
0x35887  ldstr    aId// "Id"
0x3588c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x35891  box      [mscorlib]System.Guid
0x35896  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3589b  ldloc.s  7
0x3589d  ldstr    aUserid// "UserId"
0x358a2  ldloc.1
0x358a3  box      [mscorlib]System.Guid
0x358a8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x358ad  ldloc.s  7
0x358af  ldstr    aAuthinfo// "AuthInfo"
0x358b4  ldarg.2
0x358b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x358ba  ldloc.0
0x358bb  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x358c0  ldloc.s  7
0x358c2  ldc.i4   0x1B7
0x358c7  ldstr    aAddprincipalto// "AddPrincipalToConfigDB"
0x358cc  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x358d1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x358d6  pop
0x358d7  ldarg.3
0x358d8  brtrue   loc_359E2
0x358dd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x358e2  stloc.s  7
0x358e4  ldloc.s  7
0x358e6  ldstr    aId// "Id"
0x358eb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x358f0  box      [mscorlib]System.Guid
0x358f5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x358fa  ldloc.s  7
0x358fc  ldstr    aUserid// "UserId"
0x35901  ldloc.1
  ... truncated ...
```
