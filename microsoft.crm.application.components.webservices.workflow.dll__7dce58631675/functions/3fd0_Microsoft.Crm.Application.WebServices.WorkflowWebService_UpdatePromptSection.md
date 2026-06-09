# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdatePromptSection

- ea: `0x3fd0`
- end: `0x403d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdatePromptSection`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3f00`

## callees

- `0x4040`

## pseudocode

```c

```

## disassembly

```asm
0x3fd0  ldarg.2
0x3fd1  ldstr    aPrompttext// "promptText"
0x3fd6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3fdb  stloc.0
0x3fdc  ldarg.0
0x3fdd  ldloc.0
0x3fde  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3fe3  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::GetModifiedTextXmlWithEmptyPrimitive(string textXml)
0x3fe8  stloc.1
0x3fe9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3fee  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3ff3  stloc.2
0x3ff4  ldarg.1
0x3ff5  ldloc.2
0x3ff6  ldarg.3
0x3ff7  ldc.i4.s 0xE
0x3ff9  ldloc.1
0x3ffa  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3fff  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_PromptText(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4004  ldarg.2
0x4005  ldstr    aCuetext// "cueText"
0x400a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x400f  stloc.3
0x4010  ldarg.0
0x4011  ldloc.3
0x4012  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x4017  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::GetModifiedTextXmlWithEmptyPrimitive(string textXml)
0x401c  stloc.s  4
0x401e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4023  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4028  stloc.s  5
0x402a  ldarg.1
0x402b  ldloc.s  5
0x402d  ldarg.3
0x402e  ldc.i4.s 0xE
0x4030  ldloc.s  4
0x4032  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x4037  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_HintText(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x403c  ret
```
