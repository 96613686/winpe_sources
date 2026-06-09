# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateSupportCrmUser

- ea: `0x1dec0`
- end: `0x1dfba`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateSupportCrmUser`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1de30`
- `0x1dec0`
- `0x20f10`
- `0x21010`

## string_xrefs

- `0x1df69`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1df64`: `CreateSupportCrmUser`

## pseudocode

```c

```

## disassembly

```asm
0x1dec0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1dec5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1deca  ldc.i4.2
0x1decb  beq.s    loc_1DED3
0x1decd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ded2  ret
0x1ded3  ldarg.0
0x1ded4  ldarg.1
0x1ded5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveSupportUserId(valuetype [mscorlib]System.Guid organizationId)
0x1deda  stloc.0
0x1dedb  ldloc.0
0x1dedc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dee1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1dee6  brfalse.s loc_1DEEA
0x1dee8  ldloc.0
0x1dee9  ret
0x1deea  ldarg.1
0x1deeb  ldarg.2
0x1deec  ldstr    aNeworgutilityS// "NewOrgUtility.SupportUser.FirstName"
0x1def1  ldc.i4.0
0x1def2  newarr   [mscorlib]System.Object
0x1def7  call     string [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::GetString(string, object[])
0x1defc  ldstr    aNeworgutilityS_0// "NewOrgUtility.SupportUser.LastName"
0x1df01  ldc.i4.0
0x1df02  newarr   [mscorlib]System.Object
0x1df07  call     string [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::GetString(string, object[])
0x1df0c  ldc.i4.3
0x1df0d  ldstr    aNeworgutilityS_1// "NewOrgUtility.SupportUser.InternalEmail"...
0x1df12  ldc.i4.0
0x1df13  newarr   [mscorlib]System.Object
0x1df18  call     string [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ServerUtilityResource::GetString(string, object[])
0x1df1d  ldstr    a2d101bb35ced41// "{2D101BB3-5CED-4122-83F1-94D5EFDE4E3B}"
0x1df22  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateCrmUserEntity(valuetype [mscorlib]System.Guid organizationId, int32 languageCode, string firstName, string lastName, int32 systemUserAccessMode, string internalEmailAddress, string roleToAssign)
0x1df27  stloc.1
0x1df28  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::get_CreateCrmUserTestMode()
0x1df2d  brfalse.s loc_1DF35
0x1df2f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1df34  ret
0x1df35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1df3a  stloc.2
0x1df3b  ldloc.2
0x1df3c  ldstr    aSupportusercrm// "SupportUserCrmUserId"
0x1df41  ldloc.1
0x1df42  box      [mscorlib]System.Guid
0x1df47  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1df4c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x1df51  stloc.3
0x1df52  ldloc.3
0x1df53  ldstr    aOrganization// "Organization"
0x1df58  ldarg.1
0x1df59  box      [mscorlib]System.Guid
0x1df5e  ldloc.2
0x1df5f  ldc.i4   0x620
0x1df64  ldstr    aCreatesupportc// "CreateSupportCrmUser"
0x1df69  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1df6e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1df73  pop
0x1df74  leave.s  loc_1DF80
0x1df76  ldloc.3
0x1df77  brfalse.s loc_1DF7F
0x1df79  ldloc.3
0x1df7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1df7f  endfinally
0x1df80  ldloc.1
0x1df81  ldstr    aSupportusercrm// "SupportUserCrmUserId"
0x1df86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1df8b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1df90  dup
0x1df91  ldstr    aOrganizationid_1// "organizationid"
0x1df96  ldarg.1
0x1df97  box      [mscorlib]System.Guid
0x1df9c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1dfa1  dup
0x1dfa2  ldstr    aSupportuserid// "supportuserid"
0x1dfa7  ldloc.1
0x1dfa8  box      [mscorlib]System.Guid
0x1dfad  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1dfb2  ldarg.1
0x1dfb3  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.NewOrgUtility::OrganizationUpdateProperties(class [mscorlib]System.Collections.Hashtable, valuetype [mscorlib]System.Guid)
0x1dfb8  ldloc.1
0x1dfb9  ret
```
