# Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveExpressionFromConditionXml

- ea: `0x1930`
- end: `0x19a9`
- name: `Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveExpressionFromConditionXml`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x19b0`

## string_xrefs

- `0x1931`: `workflowStepAsJson`
- `0x193c`: `conditionXml`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.1
0x1931  ldstr    aWorkflowstepas// "workflowStepAsJson"
0x1936  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x193b  ldarg.2
0x193c  ldstr    aConditionxml// "conditionXml"
0x1941  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1946  ldarg.0
0x1947  ldarg.1
0x1948  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.ProcessWebService::DeserializeJsonWorkflowStep(string jsonData)
0x194d  stloc.0
0x194e  ldloc.0
0x194f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ApplicationMetadataProvider::.ctor()
0x1954  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::set_MetadataProvider(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider)
0x1959  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x195e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1963  ldloc.0
0x1964  ldarg.2
0x1965  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::CreateConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x196a  stloc.1
0x196b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1970  stloc.2
0x1971  ldloc.2
0x1972  ldstr    aExpression// "Expression"
0x1977  ldloc.1
0x1978  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x197d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1982  ldloc.2
0x1983  ldstr    aDisplaytext// "DisplayText"
0x1988  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionDisplayExpressionVisitor::.ctor()
0x198d  ldloc.1
0x198e  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionDisplayExpressionVisitor::GetDisplayText(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1993  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1998  ldstr    aFor// "for(;;);"
0x199d  ldloc.2
0x199e  call     T0x2B000008
0x19a3  call     string [mscorlib]System.String::Concat(string, string)
0x19a8  ret
```
