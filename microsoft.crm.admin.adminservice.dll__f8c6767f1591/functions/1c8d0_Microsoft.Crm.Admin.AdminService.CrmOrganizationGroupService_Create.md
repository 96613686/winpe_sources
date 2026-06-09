# Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Create

- ea: `0x1c8d0`
- end: `0x1ca0d`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Create`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x22620`

## callees

- `0x18790`
- `0x1c8d0`
- `0x1ca10`
- `0x1cc50`
- `0x1cc70`
- `0x1cc90`
- `0x1ccd0`
- `0x1cd10`

## string_xrefs

- `0x1c924`: `Create`
- `0x1c98b`: `Create`
- `0x1c9b4`: `Guid {0} received from IDatabaseService.Create did not equal requested Guid {1}`
- `0x1c929`: `D:\a\1\s\src\CrmLive\Admin\OrganizationGroup\CrmOrganizationGroupService.cs`
- `0x1c990`: `D:\a\1\s\src\CrmLive\Admin\OrganizationGroup\CrmOrganizationGroupService.cs`
- `0x1c93f`: `An organization group with the name {0} already exists`

## pseudocode

```c

```

## disassembly

```asm
0x1c8d0  ldarg.1
0x1c8d1  ldstr    aName_0// "name"
0x1c8d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1c8db  ldarg.3
0x1c8dc  ldstr    aOrganizationid_2// "organizationIds"
0x1c8e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1c8e6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c8eb  stloc.0
0x1c8ec  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1c8f1  stloc.1
0x1c8f2  ldloc.1
0x1c8f3  ldc.i4.2
0x1c8f4  ldc.i4   0x1000
0x1c8f9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x1c8fe  stloc.2
0x1c8ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1c904  stloc.3
0x1c905  ldloc.3
0x1c906  ldstr    aName// "Name"
0x1c90b  ldarg.1
0x1c90c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c911  ldloc.1
0x1c912  ldstr    aOrganizationgr// "OrganizationGroup"
0x1c917  ldnull
0x1c918  ldc.i4.1
0x1c919  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1c91e  dup
0x1c91f  ldc.i4.0
0x1c920  ldloc.3
0x1c921  stelem.ref
0x1c922  ldc.i4.s 0x2B
0x1c924  ldstr    aCreate// "Create"
0x1c929  ldstr    aDA1SSrcCrmlive_39// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1c92e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1c933  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x1c938  brtrue.s loc_1C959
0x1c93a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c93f  ldstr    aAnOrganization// "An organization group with the name {0}"...
0x1c944  ldc.i4.1
0x1c945  newarr   [mscorlib]System.Object
0x1c94a  dup
0x1c94b  ldc.i4.0
0x1c94c  ldarg.1
0x1c94d  stelem.ref
0x1c94e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c953  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1c958  throw
0x1c959  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupData::.ctor()
0x1c95e  stloc.s  4
0x1c960  ldloc.s  4
0x1c962  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1c967  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupData::set_Id(valuetype [mscorlib]System.Guid value)
0x1c96c  ldloc.s  4
0x1c96e  ldarg.1
0x1c96f  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupData::set_Name(string value)
0x1c974  ldloc.s  4
0x1c976  ldarg.2
0x1c977  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupData::set_Description(string value)
0x1c97c  ldloc.1
0x1c97d  ldstr    aOrganizationgr// "OrganizationGroup"
0x1c982  ldloc.s  4
0x1c984  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1c989  ldc.i4.s 0x37
0x1c98b  ldstr    aCreate// "Create"
0x1c990  ldstr    aDA1SSrcCrmlive_39// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1c995  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1c99a  unbox.any [mscorlib]System.Guid
0x1c99f  stloc.0
0x1c9a0  ldloc.0
0x1c9a1  ldloc.s  4
0x1c9a3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationGroupData::get_Id()
0x1c9a8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c9ad  brfalse.s loc_1C9E2
0x1c9af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c9b4  ldstr    aGuid0ReceivedF// "Guid {0} received from IDatabaseService"...
0x1c9b9  ldc.i4.2
0x1c9ba  newarr   [mscorlib]System.Object
0x1c9bf  dup
0x1c9c0  ldc.i4.0
0x1c9c1  ldloc.0
0x1c9c2  box      [mscorlib]System.Guid
0x1c9c7  stelem.ref
0x1c9c8  dup
0x1c9c9  ldc.i4.1
0x1c9ca  ldloc.s  4
0x1c9cc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationGroupData::get_Id()
0x1c9d1  box      [mscorlib]System.Guid
0x1c9d6  stelem.ref
0x1c9d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c9dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1c9e1  throw
0x1c9e2  ldarg.0
0x1c9e3  ldloc.0
0x1c9e4  ldarg.3
0x1c9e5  ldloc.1
0x1c9e6  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::CreateOrganizationGroupEntries(valuetype [mscorlib]System.Guid organizationGroupId, valuetype [mscorlib]System.Guid[] organizationIds, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService cfg)
0x1c9eb  leave.s  loc_1CA0B
0x1c9ed  pop
0x1c9ee  ldloc.2
0x1c9ef  ldc.i4.0
0x1c9f0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x1c9f5  rethrow
0x1c9f7  ldloc.2
0x1c9f8  brfalse.s loc_1CA00
0x1c9fa  ldloc.2
0x1c9fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ca00  endfinally
0x1ca01  ldloc.1
0x1ca02  brfalse.s loc_1CA0A
0x1ca04  ldloc.1
0x1ca05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ca0a  endfinally
0x1ca0b  ldloc.0
0x1ca0c  ret
```
