# Microsoft.Crm.Workflow.Services.WebActivityReferenceService::ResolveType

- ea: `0x14fc0`
- end: `0x15068`
- name: `Microsoft.Crm.Workflow.Services.WebActivityReferenceService::ResolveType`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14f50`

## callees

- `0x8f50`
- `0x14fc0`
- `0x15b50`
- `0x1b850`

## string_xrefs

- `0x14ff2`: `Unexpected SourceType:{0} detected for web plugin with PluginTypeId:{1} `
- `0x15047`: `Cannot load workflow activity, pluginTypeId: `

## pseudocode

```c

```

## disassembly

```asm
0x14fc0  ldarg.0
0x14fc1  call     instance class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader Microsoft.Crm.Workflow.Services.ActivityReferenceService::get_ActivityLoader()
0x14fc6  castclass Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect
0x14fcb  ldarg.1
0x14fcc  callvirt instance class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData> Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::CustomActivityTypeAndAssemblyData(valuetype [mscorlib]System.Guid pluginTypeId)
0x14fd1  stloc.0
0x14fd2  ldloc.0
0x14fd3  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item2()
0x14fd8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_IsolationMode()
0x14fdd  stloc.1
0x14fde  ldloc.0
0x14fdf  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item2()
0x14fe4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_SourceType()
0x14fe9  stloc.2
0x14fea  ldloc.2
0x14feb  call     bool Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::IsAssemblySourceWebType(int32 sourceType)
0x14ff0  brtrue.s loc_1501A
0x14ff2  ldstr    aUnexpectedSour// "Unexpected SourceType:{0} detected for "...
0x14ff7  ldloc.2
0x14ff8  box      [mscorlib]System.Int32
0x14ffd  ldarga.s 1
0x14fff  constrained. [mscorlib]System.Guid
0x15005  callvirt instance string [mscorlib]System.Object::ToString()
0x1500a  call     string [mscorlib]System.String::Format(string, object, object)
0x1500f  ldc.i4   0x80040216
0x15014  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x15019  throw
0x1501a  ldloc.0
0x1501b  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item1()
0x15020  ldc.i4.0
0x15021  ldloc.0
0x15022  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item2()
0x15027  ldloc.0
0x15028  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item3()
0x1502d  ldarg.1
0x1502e  ldloc.1
0x1502f  newobj   instance void class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x15034  stloc.3
0x15035  leave.s  loc_15066
0x15037  stloc.s  4
0x15039  ldloc.s  4
0x1503b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x15040  ldc.i4   0x80040217
0x15045  bne.un.s loc_15064
0x15047  ldstr    aCannotLoadWork// "Cannot load workflow activity, pluginTy"...
0x1504c  ldarg.1
0x1504d  box      [mscorlib]System.Guid
0x15052  call     string [mscorlib]System.String::Concat(object, object)
0x15057  ldloc.s  4
0x15059  ldc.i4   0x80040217
0x1505e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x15063  throw
0x15064  rethrow
0x15066  ldloc.3
0x15067  ret
```
