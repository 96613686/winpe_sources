# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::DeleteSystemUser

- ea: `0x38930`
- end: `0x38a23`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::DeleteSystemUser`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x38330`
- `0x38930`

## string_xrefs

- `0x38970`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x38a0c`: `D:\a\1\s\src\CrmLive\Admin\Security\SystemUserService.cs`
- `0x3896b`: `DeleteSystemUser`
- `0x38a07`: `DeleteSystemUser`
- `0x389d2`: `User with id {0} has an associated OrganizationId. User cannot be deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x38930  ldarg.1
0x38931  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RevokeAllRolesForUser(valuetype [mscorlib]System.Guid systemUserId)
0x38936  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3893b  stloc.0
0x3893c  ldloc.0
0x3893d  ldstr    aId// "Id"
0x38942  ldarg.1
0x38943  box      [mscorlib]System.Guid
0x38948  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3894d  ldc.i4.1
0x3894e  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x38953  dup
0x38954  ldc.i4.0
0x38955  ldloc.0
0x38956  stelem.ref
0x38957  stloc.1
0x38958  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x3895d  stloc.2
0x3895e  ldloc.2
0x3895f  ldstr    aSystemuser// "SystemUser"
0x38964  ldnull
0x38965  ldloc.1
0x38966  ldc.i4   0x3AE
0x3896b  ldstr    aDeletesystemus// "DeleteSystemUser"
0x38970  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x38975  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3897a  stloc.3
0x3897b  ldloc.3
0x3897c  brtrue.s loc_389A7
0x3897e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38983  ldstr    aUserWithId0Doe// "User with id {0} does not exist."
0x38988  ldc.i4.1
0x38989  newarr   [mscorlib]System.Object
0x3898e  dup
0x3898f  ldc.i4.0
0x38990  ldarg.1
0x38991  box      [mscorlib]System.Guid
0x38996  stelem.ref
0x38997  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3899c  ldc.i4   0x80040217
0x389a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x389a6  throw
0x389a7  ldloc.3
0x389a8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x389ad  call     T0x2B00005D
0x389b2  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x389b7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x389bc  unbox.any [mscorlib]System.Guid
0x389c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x389c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x389cb  brfalse.s loc_389F6
0x389cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x389d2  ldstr    aUserWithId0Has// "User with id {0} has an associated Orga"...
0x389d7  ldc.i4.1
0x389d8  newarr   [mscorlib]System.Object
0x389dd  dup
0x389de  ldc.i4.0
0x389df  ldarg.1
0x389e0  box      [mscorlib]System.Guid
0x389e5  stelem.ref
0x389e6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x389eb  ldc.i4   0x80040203
0x389f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x389f5  throw
0x389f6  ldloc.2
0x389f7  ldstr    aSystemuser// "SystemUser"
0x389fc  ldarg.1
0x389fd  box      [mscorlib]System.Guid
0x38a02  ldc.i4   0x3B9
0x38a07  ldstr    aDeletesystemus// "DeleteSystemUser"
0x38a0c  ldstr    aDA1SSrcCrmlive_64// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x38a11  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x38a16  leave.s  loc_38A22
0x38a18  ldloc.2
0x38a19  brfalse.s loc_38A21
0x38a1b  ldloc.2
0x38a1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38a21  endfinally
0x38a22  ret
```
