# Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::IsPluginWebType

- ea: `0xfd0`
- end: `0x1012`
- name: `Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::IsPluginWebType`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1260`
- `0x1b7a0`
- `0x1b850`

## string_xrefs

- `0xfee`: `pluginassembly.sourcetype`

## pseudocode

```c

```

## disassembly

```asm
0xfd0  ldarg.1
0xfd1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreateQueryFromPluginTypeIdWithAssemblyLinkEntity(valuetype [mscorlib]System.Guid pluginTypeId)
0xfd6  stloc.0
0xfd7  ldarg.0
0xfd8  ldfld    class Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::_sdkCommand
0xfdd  ldloc.0
0xfde  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query)
0xfe3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xfe8  ldc.i4.0
0xfe9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xfee  ldstr    aPluginassembly_0// "pluginassembly.sourcetype"
0xff3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xff8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0xffd  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x1002  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1007  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x100c  call     bool Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::IsAssemblySourceWebType(int32 sourceType)
0x1011  ret
```
