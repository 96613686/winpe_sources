# Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::IsPluginWebType

- ea: `0x9000`
- end: `0x9048`
- name: `Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::IsPluginWebType`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6900`
- `0x1b7a0`
- `0x1b850`

## string_xrefs

- `0x9024`: `pluginassembly.sourcetype`

## pseudocode

```c

```

## disassembly

```asm
0x9000  ldarg.1
0x9001  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreateQueryFromPluginTypeIdWithAssemblyLinkEntity(valuetype [mscorlib]System.Guid pluginTypeId)
0x9006  stloc.0
0x9007  ldarg.0
0x9008  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::_context
0x900d  ldc.i4.0
0x900e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x9013  ldloc.0
0x9014  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x9019  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x901e  ldc.i4.0
0x901f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x9024  ldstr    aPluginassembly_0// "pluginassembly.sourcetype"
0x9029  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x902e  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x9033  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x9038  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x903d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x9042  call     bool Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::IsAssemblySourceWebType(int32 sourceType)
0x9047  ret
```
