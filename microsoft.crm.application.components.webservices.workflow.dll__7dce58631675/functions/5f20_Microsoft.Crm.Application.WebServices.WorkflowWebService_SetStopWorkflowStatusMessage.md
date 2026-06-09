# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatusMessage

- ea: `0x5f20`
- end: `0x5fb3`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatusMessage`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e20`

## callees

- `0x5f20`

## pseudocode

```c

```

## disassembly

```asm
0x5f20  ldarg.2
0x5f21  brfalse  loc_5FB2
0x5f26  ldarg.2
0x5f27  ldstr    aValue// "value"
0x5f2c  ldsfld   string [mscorlib]System.String::Empty
0x5f31  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5f36  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5f3b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x5f40  stloc.0
0x5f41  ldloc.0
0x5f42  ldstr    aParametersPara_0// "//parameters/parameter/slugbody"
0x5f47  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5f4c  stloc.1
0x5f4d  ldloc.1
0x5f4e  brfalse.s loc_5F81
0x5f50  ldloc.1
0x5f51  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x5f56  ldc.i4.0
0x5f57  ble.s    loc_5F81
0x5f59  ldloc.1
0x5f5a  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5f5f  pop
0x5f60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5f65  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5f6a  ldarg.0
0x5f6b  ldc.i4.s 0xE
0x5f6d  ldloc.1
0x5f6e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5f73  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x5f78  ldc.i4.0
0x5f79  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x5f7e  stloc.2
0x5f7f  br.s     loc_5FA8
0x5f81  ldloc.0
0x5f82  ldstr    aParametersPara// "//parameters/parameter"
0x5f87  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5f8c  stloc.3
0x5f8d  ldloc.3
0x5f8e  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5f93  pop
0x5f94  ldarg.0
0x5f95  ldloc.3
0x5f96  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5f9b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x5fa0  ldc.i4.s 0xE
0x5fa2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x5fa7  stloc.2
0x5fa8  ldloc.2
0x5fa9  brfalse.s loc_5FB2
0x5fab  ldarg.1
0x5fac  ldloc.2
0x5fad  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::set_StatusMessage(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5fb2  ret
```
