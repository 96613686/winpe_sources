# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::Create_2

- ea: `0x374c0`
- end: `0x37753`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::Create_2`
- size: `659`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x37430`
- `0x37440`
- `0x37480`

## callees

- `0x17830`
- `0x18790`
- `0x371d0`
- `0x37200`
- `0x37220`
- `0x37240`
- `0x37260`
- `0x37280`
- `0x372a0`
- `0x374c0`
- `0x37760`

## string_xrefs

- `0x37500`: `Create`
- `0x37569`: `Create`
- `0x375a4`: `Create`
- `0x375e4`: `Create`
- `0x3763e`: `Create`
- `0x3765b`: `Create`
- `0x3772b`: `Create`
- `0x37505`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x3756e`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x375a9`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x375e9`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x37643`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x37660`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x37730`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x374c0  ldarg.1
0x374c1  ldstr    aName_0// "name"
0x374c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x374cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x374d0  stloc.0
0x374d1  ldarg.0
0x374d2  ldarg.1
0x374d3  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName(string name)
0x374d8  stloc.1
0x374d9  ldloc.0
0x374da  ldstr    aName// "Name"
0x374df  ldloc.1
0x374e0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x374e5  ldc.i4.1
0x374e6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x374eb  dup
0x374ec  ldc.i4.0
0x374ed  ldloc.0
0x374ee  stelem.ref
0x374ef  stloc.2
0x374f0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x374f5  stloc.3
0x374f6  ldloc.3
0x374f7  ldstr    aSystemuser// "SystemUser"
0x374fc  ldnull
0x374fd  ldloc.2
0x374fe  ldc.i4.s 0x61
0x37500  ldstr    aCreate// "Create"
0x37505  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x3750a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3750f  stloc.s  4
0x37511  ldloc.s  4
0x37513  brfalse.s loc_37521
0x37515  ldstr    aSystemuser// "SystemUser"
0x3751a  ldloc.1
0x3751b  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBDuplicateRecord(string objectType, object value)
0x37520  throw
0x37521  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::.ctor()
0x37526  stloc.s  5
0x37528  ldloc.s  5
0x3752a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3752f  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::set_Id(valuetype [mscorlib]System.Guid value)
0x37534  ldloc.s  5
0x37536  ldloc.1
0x37537  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::set_Name(string value)
0x3753c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x37541  stloc.s  6
0x37543  ldloc.s  6
0x37545  ldstr    aId// "Id"
0x3754a  ldarg.2
0x3754b  box      [mscorlib]System.Guid
0x37550  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x37555  ldloc.3
0x37556  ldstr    aOrganization// "Organization"
0x3755b  ldnull
0x3755c  ldc.i4.1
0x3755d  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x37562  dup
0x37563  ldc.i4.0
0x37564  ldloc.s  6
0x37566  stelem.ref
0x37567  ldc.i4.s 0x6F
0x37569  ldstr    aCreate// "Create"
0x3756e  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37573  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x37578  stloc.s  7
0x3757a  ldloc.s  5
0x3757c  ldloc.s  7
0x3757e  brfalse.s loc_37583
0x37580  ldarg.2
0x37581  br.s     loc_37588
0x37583  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x37588  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::set_DefaultOrganizationId(valuetype [mscorlib]System.Guid value)
0x3758d  ldarg.3
0x3758e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37593  brfalse.s loc_375B9
0x37595  ldloc.3
0x37596  ldstr    aSystemuser// "SystemUser"
0x3759b  ldloc.s  5
0x3759d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x375a2  ldc.i4.s 0x75
0x375a4  ldstr    aCreate// "Create"
0x375a9  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x375ae  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x375b3  pop
0x375b4  br       loc_3773B
0x375b9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x375be  stloc.s  8
0x375c0  ldloc.s  8
0x375c2  ldstr    aAuthinfo// "AuthInfo"
0x375c7  ldarg.3
0x375c8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x375cd  ldloc.3
0x375ce  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x375d3  ldnull
0x375d4  ldc.i4.1
0x375d5  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x375da  dup
0x375db  ldc.i4.0
0x375dc  ldloc.s  8
0x375de  stelem.ref
0x375df  ldc.i4   0x80
0x375e4  ldstr    aCreate// "Create"
0x375e9  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x375ee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x375f3  stloc.s  9
0x375f5  ldloc.s  9
0x375f7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x375fc  brfalse.s loc_37670
0x375fe  ldloc.s  8
0x37600  ldstr    aId// "Id"
0x37605  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3760a  box      [mscorlib]System.Guid
0x3760f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x37614  ldloc.s  8
0x37616  ldstr    aUserid// "UserId"
0x3761b  ldloc.s  5
0x3761d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Id()
0x37622  box      [mscorlib]System.Guid
0x37627  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3762c  ldloc.3
0x3762d  ldstr    aSystemuser// "SystemUser"
0x37632  ldloc.s  5
0x37634  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x37639  ldc.i4   0x86
0x3763e  ldstr    aCreate// "Create"
0x37643  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37648  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3764d  pop
0x3764e  ldloc.3
0x3764f  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x37654  ldloc.s  8
0x37656  ldc.i4   0x87
0x3765b  ldstr    aCreate// "Create"
0x37660  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37665  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3766a  pop
0x3766b  br       loc_3773B
0x37670  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x37675  stloc.s  0xA
0x37677  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3767c  stloc.s  0xB
0x3767e  ldloc.s  0xB
0x37680  ldstr    aId// "Id"
0x37685  ldloc.s  9
0x37687  ldc.i4.0
0x37688  call     T0x2B0000B1
0x3768d  stloc.s  0xC
0x3768f  ldloca.s 0xC
0x37691  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x37696  ldstr    aUserid// "UserId"
0x3769b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x376a0  unbox.any [mscorlib]System.Guid
0x376a5  box      [mscorlib]System.Guid
0x376aa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x376af  ldloc.s  5
0x376b1  ldloc.s  0xB
0x376b3  ldstr    aId// "Id"
0x376b8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x376bd  unbox.any [mscorlib]System.Guid
0x376c2  callvirt instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::set_Id(valuetype [mscorlib]System.Guid value)
0x376c7  ldloc.s  5
0x376c9  callvirt instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Name()
0x376ce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x376d3  brtrue.s loc_376E8
0x376d5  ldloc.s  0xA
0x376d7  ldstr    aName// "Name"
0x376dc  ldloc.s  5
0x376de  callvirt instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Name()
0x376e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x376e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x376ed  ldloc.s  5
0x376ef  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_DefaultOrganizationId()
0x376f4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x376f9  brfalse.s loc_37713
0x376fb  ldloc.s  0xA
0x376fd  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x37702  ldloc.s  5
0x37704  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_DefaultOrganizationId()
0x37709  box      [mscorlib]System.Guid
0x3770e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x37713  ldloc.3
0x37714  ldstr    aSystemuser// "SystemUser"
0x37719  ldloc.s  0xA
0x3771b  ldc.i4.1
0x3771c  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x37721  dup
0x37722  ldc.i4.0
0x37723  ldloc.s  0xB
0x37725  stelem.ref
0x37726  ldc.i4   0x99
0x3772b  ldstr    aCreate// "Create"
0x37730  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x37735  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3773a  pop
0x3773b  ldloc.s  5
0x3773d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_Id()
0x37742  stloc.s  0xD
0x37744  leave.s  loc_37750
0x37746  ldloc.3
0x37747  brfalse.s loc_3774F
0x37749  ldloc.3
0x3774a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3774f  endfinally
0x37750  ldloc.s  0xD
0x37752  ret
```
