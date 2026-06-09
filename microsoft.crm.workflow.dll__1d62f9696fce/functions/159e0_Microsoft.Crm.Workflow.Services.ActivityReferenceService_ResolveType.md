# Microsoft.Crm.Workflow.Services.ActivityReferenceService::ResolveType

- ea: `0x159e0`
- end: `0x15adc`
- name: `Microsoft.Crm.Workflow.Services.ActivityReferenceService::ResolveType`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x155d0`

## callees

- `0x8f50`
- `0x159e0`
- `0x1b280`
- `0x1b520`
- `0x1b540`
- `0x1b950`

## pseudocode

```c

```

## disassembly

```asm
0x159e0  ldarg.1
0x159e1  ldloca.s 0
0x159e3  ldloca.s 1
0x159e5  ldloca.s 2
0x159e7  ldloca.s 3
0x159e9  ldloca.s 4
0x159eb  call     void Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::GetTypeDetails(string assemblyQualifiedName, [out] string& typeName, [out] string& assemblyName, [out] string& version, [out] string& culture, [out] string& publicKeyToken)
0x159f0  ldtoken  Microsoft.Crm.Workflow.Activities.Composite
0x159f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159fa  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x159ff  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x15a04  ldloca.s 5
0x15a06  ldloca.s 6
0x15a08  ldloca.s 7
0x15a0a  ldloca.s 8
0x15a0c  call     void Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::GetAssemblyDetails(string assemblyStrongName, [out] string& assemblyName, [out] string& version, [out] string& culture, [out] string& publicKeyToken)
0x15a11  ldloc.1
0x15a12  ldloc.s  5
0x15a14  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15a19  brfalse.s loc_15A4A
0x15a1b  ldloc.s  4
0x15a1d  ldloc.s  8
0x15a1f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15a24  brfalse.s loc_15A4A
0x15a26  ldtoken  Microsoft.Crm.Workflow.Activities.Composite
0x15a2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a30  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x15a35  ldloc.0
0x15a36  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x15a3b  ldc.i4.1
0x15a3c  ldnull
0x15a3d  ldnull
0x15a3e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15a43  ldc.i4.1
0x15a44  newobj   instance void class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x15a49  ret
0x15a4a  ldarg.0
0x15a4b  ldfld    class Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper Microsoft.Crm.Workflow.Services.ActivityReferenceService::_resolverHelper
0x15a50  ldarg.1
0x15a51  ldc.i4.1
0x15a52  ldc.i4.1
0x15a53  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreatePluginQueryFromTypeName(string assemblyQualifiedTypeName, bool includeNonDesignerActivities, bool ignoreWeb)
0x15a58  stloc.s  9
0x15a5a  ldarg.0
0x15a5b  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader Microsoft.Crm.Workflow.Services.ActivityReferenceService::_activityLoader
0x15a60  ldloc.s  9
0x15a62  ldloc.2
0x15a63  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader::RetrievePluginId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, string version)
0x15a68  stloc.s  0xA
0x15a6a  ldarg.0
0x15a6b  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader Microsoft.Crm.Workflow.Services.ActivityReferenceService::_activityLoader
0x15a70  castclass Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect
0x15a75  ldloc.s  0xA
0x15a77  callvirt instance class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData> Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::CustomActivityTypeAndAssemblyData(valuetype [mscorlib]System.Guid pluginTypeId)
0x15a7c  stloc.s  0xB
0x15a7e  ldloc.s  0xB
0x15a80  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item2()
0x15a85  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_IsolationMode()
0x15a8a  stloc.s  0xC
0x15a8c  ldloc.s  0xB
0x15a8e  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item1()
0x15a93  ldc.i4.0
0x15a94  ldloc.s  0xB
0x15a96  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item2()
0x15a9b  ldloc.s  0xB
0x15a9d  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [mscorlib]System.Type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::get_Item3()
0x15aa2  ldloc.s  0xA
0x15aa4  ldloc.s  0xC
0x15aa6  newobj   instance void class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x15aab  stloc.s  0xD
0x15aad  leave.s  loc_15AD9
0x15aaf  stloc.s  0xE
0x15ab1  ldloc.s  0xE
0x15ab3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x15ab8  ldc.i4   0x80040217
0x15abd  bne.un.s loc_15AD7
0x15abf  ldstr    aCannotLoadWork_0// "Cannot load workflow activity: "
0x15ac4  ldarg.1
0x15ac5  call     string [mscorlib]System.String::Concat(string, string)
0x15aca  ldloc.s  0xE
0x15acc  ldc.i4   0x80040217
0x15ad1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x15ad6  throw
0x15ad7  rethrow
0x15ad9  ldloc.s  0xD
0x15adb  ret
```
