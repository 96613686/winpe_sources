# Microsoft.Crm.Workflow.LegacyWorkflowContext::GetOnlyItem

- ea: `0x1200`
- end: `0x1239`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::GetOnlyItem`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xed0`
- `0xf00`

## callees

- `0xeb0`
- `0x1200`

## pseudocode

```c

```

## disassembly

```asm
0x1200  ldarg.1
0x1201  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1206  ldc.i4.1
0x1207  bne.un.s loc_1237
0x1209  ldarg.1
0x120a  ldarg.0
0x120b  call     instance string Microsoft.Crm.Workflow.LegacyWorkflowContext::get_PrimaryEntityName()
0x1210  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x1215  stloc.0
0x1216  ldarg.0
0x1217  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x121c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_ConversionContext()
0x1221  ldloc.0
0x1222  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x1227  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122c  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x1231  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x1236  ret
0x1237  ldnull
0x1238  ret
```
