# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssign

- ea: `0x34c0`
- end: `0x3562`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssign`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3590`
- `0x3950`

## callees

- `0x34c0`
- `0x35d0`
- `0x3990`
- `0x8b90`

## string_xrefs

- `0x3539`: `Invalid XML`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.2
0x34c1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x34c6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x34cb  ldstr    aAssignstep// "//AssignStep"
0x34d0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x34d5  stloc.0
0x34d6  ldloc.0
0x34d7  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x34dc  brfalse.s loc_3549
0x34de  ldloc.0
0x34df  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x34e4  dup
0x34e5  ldstr    aSteplabel// "steplabel"
0x34ea  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x34ef  stloc.1
0x34f0  dup
0x34f1  ldstr    aVariable_0// "Variable"
0x34f6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x34fb  stloc.2
0x34fc  ldstr    aArgument// "Argument"
0x3501  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3506  stloc.3
0x3507  ldloc.1
0x3508  brfalse.s loc_3539
0x350a  ldarg.1
0x350b  ldloc.1
0x350c  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3511  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x3516  ldloc.2
0x3517  brfalse.s loc_3529
0x3519  ldarg.0
0x351a  ldarg.1
0x351b  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x3520  ldloc.2
0x3521  ldarg.3
0x3522  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateFormulaDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep assignStep, class [System.Xml]System.Xml.XPath.XPathNavigator variableNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3527  br.s     loc_3549
0x3529  ldarg.0
0x352a  ldarg.1
0x352b  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep
0x3530  ldloc.3
0x3531  ldarg.3
0x3532  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateArgumentDetails(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep assignStep, class [System.Xml]System.Xml.XPath.XPathNavigator variableNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3537  br.s     loc_3549
0x3539  ldstr    aInvalidXml// "Invalid XML"
0x353e  ldc.i4   0x80004005
0x3543  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3548  throw
0x3549  ldarg.0
0x354a  ldarg.3
0x354b  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3550  stloc.s  4
0x3552  leave.s  loc_355F
0x3554  stloc.s  5
0x3556  ldarg.0
0x3557  ldloc.s  5
0x3559  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x355e  throw
0x355f  ldloc.s  4
0x3561  ret
```
