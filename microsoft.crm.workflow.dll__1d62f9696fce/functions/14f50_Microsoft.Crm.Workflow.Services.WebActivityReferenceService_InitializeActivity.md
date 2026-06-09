# Microsoft.Crm.Workflow.Services.WebActivityReferenceService::InitializeActivity

- ea: `0x14f50`
- end: `0x14fb4`
- name: `Microsoft.Crm.Workflow.Services.WebActivityReferenceService::InitializeActivity`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14fc0`
- `0x15620`

## string_xrefs

- `0x14f73`: `webActivityReference.pluginTypeId`

## pseudocode

```c

```

## disassembly

```asm
0x14f50  ldarg.1
0x14f51  ldstr    aActivityrefere// "activityReferencebase"
0x14f56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x14f5b  ldarg.1
0x14f5c  castclass [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference
0x14f61  stloc.0
0x14f62  ldloc.0
0x14f63  ldstr    aWebactivityref// "webActivityReference"
0x14f68  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x14f6d  ldloc.0
0x14f6e  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference::get_PluginTypeId()
0x14f73  ldstr    aWebactivityref_0// "webActivityReference.pluginTypeId"
0x14f78  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14f7d  ldarg.0
0x14f7e  ldloc.0
0x14f7f  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference::get_PluginTypeId()
0x14f84  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x14f89  call     instance class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32> Microsoft.Crm.Workflow.Services.WebActivityReferenceService::ResolveType(valuetype [mscorlib]System.Guid pluginTypeId)
0x14f8e  stloc.1
0x14f8f  ldarg.0
0x14f90  ldloc.1
0x14f91  ldloc.0
0x14f92  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x14f97  ldloc.0
0x14f98  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x14f9d  ldloc.0
0x14f9e  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x14fa3  ldloc.1
0x14fa4  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item4()
0x14fa9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeName()
0x14fae  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Services.ActivityReferenceService::InitializeActivityInternal(class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32> activityTypeData, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> activityArguments, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> activityProperties, string activityDisplayName, string assemblyQualifiedName)
0x14fb3  ret
```
