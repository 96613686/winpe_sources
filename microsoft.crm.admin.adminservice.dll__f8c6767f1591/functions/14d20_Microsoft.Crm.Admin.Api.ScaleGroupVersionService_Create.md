# Microsoft.Crm.Admin.Api.ScaleGroupVersionService::Create

- ea: `0x14d20`
- end: `0x14da7`
- name: `Microsoft.Crm.Admin.Api.ScaleGroupVersionService::Create`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14d20`
- `0x15030`

## string_xrefs

- `0x14d84`: `Create`
- `0x14d49`: `Scale Group Version already exists.`
- `0x14d89`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroupVersion\ScaleGroupVersionService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x14d20  ldarg.1
0x14d21  ldstr    aName_0// "name"
0x14d26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14d2b  ldarg.2
0x14d2c  ldstr    aProperties// "properties"
0x14d31  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x14d36  ldarg.0
0x14d37  ldarg.1
0x14d38  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.Api.ScaleGroupVersionService::GetVersionIdFromName(string scaleGroupVersionName)
0x14d3d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14d42  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14d47  brfalse.s loc_14D54
0x14d49  ldstr    aScaleGroupVers// "Scale Group Version already exists."
0x14d4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x14d53  throw
0x14d54  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x14d59  stloc.0
0x14d5a  ldarg.2
0x14d5b  ldstr    aName// "Name"
0x14d60  ldarg.1
0x14d61  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14d66  ldarg.2
0x14d67  ldstr    aId// "Id"
0x14d6c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x14d71  box      [mscorlib]System.Guid
0x14d76  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14d7b  ldloc.0
0x14d7c  ldstr    aScalegroupvers// "ScaleGroupVersion"
0x14d81  ldarg.2
0x14d82  ldc.i4.s 0x2A
0x14d84  ldstr    aCreate// "Create"
0x14d89  ldstr    aDA1SSrcCrmlive_29// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x14d8e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x14d93  unbox.any [mscorlib]System.Guid
0x14d98  stloc.1
0x14d99  leave.s  loc_14DA5
0x14d9b  ldloc.0
0x14d9c  brfalse.s loc_14DA4
0x14d9e  ldloc.0
0x14d9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14da4  endfinally
0x14da5  ldloc.1
0x14da6  ret
```
