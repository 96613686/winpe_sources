# Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::UpdateCustomEntityFeatureStateIfNecessary

- ea: `0x4a720`
- end: `0x4a7aa`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::UpdateCustomEntityFeatureStateIfNecessary`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x4a720`
- `0x4a7b0`

## string_xrefs

- `0x4a739`: `UpdateCustomEntityFeatureStateIfNecessary`
- `0x4a73e`: `D:\a\1\s\src\ManagedPlatform\Server\Metadata\MetadataServices\EntityService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4a720  ldarg.2
0x4a721  ldstr    aSqlcontext// "sqlContext"
0x4a726  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4a72b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x4a730  ldarg.2
0x4a731  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4a736  ldc.i4.4
0x4a737  ldc.i4.s 0x5C
0x4a739  ldstr    aUpdatecustomen// "UpdateCustomEntityFeatureStateIfNecessa"...
0x4a73e  ldstr    aDA1SSrcManaged_9// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x4a743  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationResourceLimit(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ResourceType, int32, string, string)
0x4a748  stloc.0
0x4a749  ldloca.s 0
0x4a74b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4a750  brfalse.s loc_4A7A8
0x4a752  ldarg.0
0x4a753  ldarg.2
0x4a754  ldc.i4.1
0x4a755  call     instance int32 Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::GetCurrentCustomEntityCount(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext, bool excludeFirstParty)
0x4a75a  stloc.1
0x4a75b  ldarg.1
0x4a75c  brtrue.s loc_4A777
0x4a75e  ldloc.1
0x4a75f  ldloc.0
0x4a760  stloc.2
0x4a761  ldloca.s 2
0x4a763  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x4a768  clt
0x4a76a  ldc.i4.0
0x4a76b  ceq
0x4a76d  ldloca.s 2
0x4a76f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4a774  and
0x4a775  brtrue.s loc_4A790
0x4a777  ldarg.1
0x4a778  brfalse.s loc_4A7A8
0x4a77a  ldloc.1
0x4a77b  ldloc.0
0x4a77c  stloc.2
0x4a77d  ldloca.s 2
0x4a77f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x4a784  clt
0x4a786  ldloca.s 2
0x4a788  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4a78d  and
0x4a78e  brfalse.s loc_4A7A8
0x4a790  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControlInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.FeatureControlInfoProvider::get_Instance()
0x4a795  ldarg.2
0x4a796  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4a79b  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateCustomEntity
0x4a7a0  ldarg.1
0x4a7a1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControlInfoProvider::SetOrganizationFeatureState(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, bool)
0x4a7a6  ldc.i4.1
0x4a7a7  ret
0x4a7a8  ldc.i4.0
0x4a7a9  ret
```
