# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetActivityInfo

- ea: `0x1b990`
- end: `0x1b9c7`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetActivityInfo`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1c6d0`
- `0x1c6e0`
- `0x1c6f0`
- `0x1c740`

## string_xrefs

- `0x1b99a`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x1b990  ldarg.0
0x1b991  ldarg.1
0x1b992  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetPluginTypeEntity(valuetype [mscorlib]System.Guid pluginTypeId)
0x1b997  stloc.0
0x1b998  ldarg.0
0x1b999  ldloc.0
0x1b99a  ldstr    aPluginassembly// "pluginassemblyid"
0x1b99f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b9a4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1b9a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1b9ae  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetPluginAssembly(valuetype [mscorlib]System.Guid assemblyId)
0x1b9b3  stloc.1
0x1b9b4  ldarg.0
0x1b9b5  ldarg.1
0x1b9b6  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetPluginType(valuetype [mscorlib]System.Guid pluginTypeId)
0x1b9bb  stloc.2
0x1b9bc  ldarg.0
0x1b9bd  ldloc.1
0x1b9be  ldloc.0
0x1b9bf  ldloc.2
0x1b9c0  ldarg.1
0x1b9c1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetActivityInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activityAssembly, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity, class [mscorlib]System.Type activityType, valuetype [mscorlib]System.Guid pluginTypeId)
0x1b9c6  ret
```
