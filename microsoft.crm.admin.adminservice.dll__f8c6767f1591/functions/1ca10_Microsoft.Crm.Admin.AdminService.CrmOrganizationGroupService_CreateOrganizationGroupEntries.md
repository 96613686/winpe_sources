# Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::CreateOrganizationGroupEntries

- ea: `0x1ca10`
- end: `0x1cacf`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::CreateOrganizationGroupEntries`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c8d0`

## callees

- `0x18790`
- `0x1ca10`
- `0x1cd40`
- `0x1cd60`
- `0x1cd80`
- `0x1cdc0`
- `0x1ce00`

## string_xrefs

- `0x1ca93`: `Guid {0} received from IDatabaseService.Create did not equal requested Guid {1}`
- `0x1ca71`: `D:\a\1\s\src\CrmLive\Admin\OrganizationGroup\CrmOrganizationGroupService.cs`
- `0x1ca6c`: `CreateOrganizationGroupEntries`

## pseudocode

```c

```

## disassembly

```asm
0x1ca10  ldarg.2
0x1ca11  ldlen
0x1ca12  conv.i4
0x1ca13  newarr   Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData
0x1ca18  stloc.0
0x1ca19  ldc.i4.0
0x1ca1a  stloc.1
0x1ca1b  br.s     loc_1CA4A
0x1ca1d  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::.ctor()
0x1ca22  stloc.2
0x1ca23  ldloc.2
0x1ca24  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1ca29  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::set_Id(valuetype [mscorlib]System.Guid value)
0x1ca2e  ldloc.2
0x1ca2f  ldarg.1
0x1ca30  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::set_OrganizationGroupId(valuetype [mscorlib]System.Guid value)
0x1ca35  ldloc.2
0x1ca36  ldarg.2
0x1ca37  ldloc.1
0x1ca38  ldelem   [mscorlib]System.Guid
0x1ca3d  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x1ca42  ldloc.0
0x1ca43  ldloc.1
0x1ca44  ldloc.2
0x1ca45  stelem.ref
0x1ca46  ldloc.1
0x1ca47  ldc.i4.1
0x1ca48  add
0x1ca49  stloc.1
0x1ca4a  ldloc.1
0x1ca4b  ldarg.2
0x1ca4c  ldlen
0x1ca4d  conv.i4
0x1ca4e  blt.s    loc_1CA1D
0x1ca50  ldloc.0
0x1ca51  stloc.3
0x1ca52  ldc.i4.0
0x1ca53  stloc.s  4
0x1ca55  br.s     loc_1CAC7
0x1ca57  ldloc.3
0x1ca58  ldloc.s  4
0x1ca5a  ldelem.ref
0x1ca5b  stloc.s  5
0x1ca5d  ldarg.3
0x1ca5e  ldstr    aOrganizationgr_0// "OrganizationGroupOrganizations"
0x1ca63  ldloc.s  5
0x1ca65  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1ca6a  ldc.i4.s 0x5D
0x1ca6c  ldstr    aCreateorganiza_0// "CreateOrganizationGroupEntries"
0x1ca71  ldstr    aDA1SSrcCrmlive_39// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1ca76  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1ca7b  unbox.any [mscorlib]System.Guid
0x1ca80  ldloc.s  5
0x1ca82  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::get_Id()
0x1ca87  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ca8c  brfalse.s loc_1CAC1
0x1ca8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ca93  ldstr    aGuid0ReceivedF// "Guid {0} received from IDatabaseService"...
0x1ca98  ldc.i4.2
0x1ca99  newarr   [mscorlib]System.Object
0x1ca9e  dup
0x1ca9f  ldc.i4.0
0x1caa0  ldarg.1
0x1caa1  box      [mscorlib]System.Guid
0x1caa6  stelem.ref
0x1caa7  dup
0x1caa8  ldc.i4.1
0x1caa9  ldloc.s  5
0x1caab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::get_Id()
0x1cab0  box      [mscorlib]System.Guid
0x1cab5  stelem.ref
0x1cab6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1cabb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1cac0  throw
0x1cac1  ldloc.s  4
0x1cac3  ldc.i4.1
0x1cac4  add
0x1cac5  stloc.s  4
0x1cac7  ldloc.s  4
0x1cac9  ldloc.3
0x1caca  ldlen
0x1cacb  conv.i4
0x1cacc  blt.s    loc_1CA57
0x1cace  ret
```
