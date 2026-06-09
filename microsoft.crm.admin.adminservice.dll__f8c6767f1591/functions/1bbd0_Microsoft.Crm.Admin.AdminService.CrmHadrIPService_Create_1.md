# Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Create_1

- ea: `0x1bbd0`
- end: `0x1bc29`
- name: `Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Create_1`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b310`
- `0x1b3e0`

## callees

- `0x18790`
- `0x1b160`
- `0x1bbd0`

## string_xrefs

- `0x1bbe7`: `Create`
- `0x1bbec`: `D:\a\1\s\src\CrmLive\Admin\HadrIPs\HadrIPService.cs`
- `0x1bbfe`: `Created HadrIP, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1bbd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1bbd5  stloc.0
0x1bbd6  ldloc.0
0x1bbd7  ldstr    aHadrips// "HadrIPs"
0x1bbdc  ldarg.0
0x1bbdd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1bbe2  ldc.i4   0x18F
0x1bbe7  ldstr    aCreate// "Create"
0x1bbec  ldstr    aDA1SSrcCrmlive_37// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\HadrI"...
0x1bbf1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1bbf6  pop
0x1bbf7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1bbfc  ldc.i4.s 9
0x1bbfe  ldstr    aCreatedHadripI// "Created HadrIP, Id=({0})"
0x1bc03  ldc.i4.1
0x1bc04  newarr   [mscorlib]System.Object
0x1bc09  dup
0x1bc0a  ldc.i4.0
0x1bc0b  ldarg.0
0x1bc0c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_Id()
0x1bc11  box      [mscorlib]System.Guid
0x1bc16  stelem.ref
0x1bc17  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1bc1c  leave.s  loc_1BC28
0x1bc1e  ldloc.0
0x1bc1f  brfalse.s loc_1BC27
0x1bc21  ldloc.0
0x1bc22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bc27  endfinally
0x1bc28  ret
```
