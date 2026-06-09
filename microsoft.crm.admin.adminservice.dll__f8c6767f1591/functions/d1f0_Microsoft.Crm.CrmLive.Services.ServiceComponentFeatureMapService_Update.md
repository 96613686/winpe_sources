# Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMapService::Update

- ea: `0xd1f0`
- end: `0xd244`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMapService::Update`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xce50`
- `0xcef0`
- `0xd1f0`

## string_xrefs

- `0xd227`: `Update`
- `0xd1f1`: `serviceComponentFeatureMap`
- `0xd214`: `ServiceComponentFeatureMap`
- `0xd22c`: `D:\a\1\s\src\CrmLive\Admin\Feature\ServiceComponentFeatureMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xd1f0  ldarg.1
0xd1f1  ldstr    aServicecompone_0// "serviceComponentFeatureMap"
0xd1f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd1fb  ldarg.1
0xd1fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::ToPropertyBag()
0xd201  stloc.0
0xd202  ldloc.0
0xd203  ldstr    aId// "Id"
0xd208  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0xd20d  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xd212  stloc.1
0xd213  ldloc.1
0xd214  ldstr    aServicecompone_1// "ServiceComponentFeatureMap"
0xd219  ldarg.1
0xd21a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::get_Id()
0xd21f  box      [mscorlib]System.Guid
0xd224  ldloc.0
0xd225  ldc.i4.s 0x6E
0xd227  ldstr    aUpdate// "Update"
0xd22c  ldstr    aDA1SSrcCrmlive_17// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xd231  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xd236  pop
0xd237  leave.s  loc_D243
0xd239  ldloc.1
0xd23a  brfalse.s loc_D242
0xd23c  ldloc.1
0xd23d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd242  endfinally
0xd243  ret
```
