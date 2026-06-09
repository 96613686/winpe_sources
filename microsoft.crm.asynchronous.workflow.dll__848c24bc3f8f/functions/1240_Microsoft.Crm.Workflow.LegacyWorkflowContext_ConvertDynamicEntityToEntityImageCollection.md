# Microsoft.Crm.Workflow.LegacyWorkflowContext::ConvertDynamicEntityToEntityImageCollection

- ea: `0x1240`
- end: `0x1274`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::ConvertDynamicEntityToEntityImageCollection`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1280`

## callees

- `0xeb0`

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.0
0x1241  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1246  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_ConversionContext()
0x124b  ldarg.1
0x124c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x1251  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1256  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x125b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x1260  stloc.0
0x1261  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection::.ctor()
0x1266  dup
0x1267  ldarg.0
0x1268  call     instance string Microsoft.Crm.Workflow.LegacyWorkflowContext::get_PrimaryEntityName()
0x126d  ldloc.0
0x126e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Item(var<u1>, !!T0)
0x1273  ret
```
