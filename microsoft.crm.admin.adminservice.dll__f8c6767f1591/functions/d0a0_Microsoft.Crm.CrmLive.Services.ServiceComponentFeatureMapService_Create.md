# Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMapService::Create

- ea: `0xd0a0`
- end: `0xd0dc`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMapService::Create`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xcef0`
- `0xd0a0`

## string_xrefs

- `0xd0bf`: `Create`
- `0xd0a1`: `serviceComponentFeatureMap`
- `0xd0b2`: `ServiceComponentFeatureMap`
- `0xd0c4`: `D:\a\1\s\src\CrmLive\Admin\Feature\ServiceComponentFeatureMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xd0a0  ldarg.1
0xd0a1  ldstr    aServicecompone_0// "serviceComponentFeatureMap"
0xd0a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd0ab  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xd0b0  stloc.0
0xd0b1  ldloc.0
0xd0b2  ldstr    aServicecompone_1// "ServiceComponentFeatureMap"
0xd0b7  ldarg.1
0xd0b8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::ToPropertyBag()
0xd0bd  ldc.i4.s 0x33
0xd0bf  ldstr    aCreate// "Create"
0xd0c4  ldstr    aDA1SSrcCrmlive_17// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xd0c9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xd0ce  pop
0xd0cf  leave.s  loc_D0DB
0xd0d1  ldloc.0
0xd0d2  brfalse.s loc_D0DA
0xd0d4  ldloc.0
0xd0d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd0da  endfinally
0xd0db  ret
```
