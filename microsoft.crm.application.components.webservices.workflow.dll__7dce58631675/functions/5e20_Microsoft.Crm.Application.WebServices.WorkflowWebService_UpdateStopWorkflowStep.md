# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStopWorkflowStep

- ea: `0x5e20`
- end: `0x5ee4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStopWorkflowStep`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x5e20`
- `0x5ef0`
- `0x5f20`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x5eb6`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x5e20  ldarg.0
0x5e21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5e26  ldarg.2
0x5e27  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5e2c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5e31  stloc.0
0x5e32  ldloc.0
0x5e33  ldarg.1
0x5e34  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5e39  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep
0x5e3e  stloc.1
0x5e3f  ldarg.0
0x5e40  ldloc.0
0x5e41  ldarg.s  4
0x5e43  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5e48  ldarg.3
0x5e49  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5e4e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x5e53  ldstr    aCondition_0// "//condition"
0x5e58  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5e5d  stloc.2
0x5e5e  ldloc.2
0x5e5f  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5e64  brfalse.s loc_5ECB
0x5e66  ldloc.2
0x5e67  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5e6c  stloc.3
0x5e6d  ldloc.3
0x5e6e  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x5e73  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5e78  stloc.s  4
0x5e7a  ldloc.3
0x5e7b  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x5e80  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5e85  stloc.s  5
0x5e87  ldloc.s  4
0x5e89  brfalse.s loc_5ECB
0x5e8b  ldloc.s  5
0x5e8d  brfalse.s loc_5ECB
0x5e8f  ldloc.s  4
0x5e91  ldstr    aValue// "value"
0x5e96  ldsfld   string [mscorlib]System.String::Empty
0x5e9b  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5ea0  ldstr    aStopworkflow// "stopWorkflow"
0x5ea5  ldc.i4.4
0x5ea6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5eab  brfalse.s loc_5ECB
0x5ead  ldloc.1
0x5eae  ldloc.s  5
0x5eb0  call     void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatus(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep stopWorkflowStep, class [System.Xml]System.Xml.XPath.XPathNavigator parameterColumn)
0x5eb5  ldloc.3
0x5eb6  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x5ebb  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5ec0  stloc.s  6
0x5ec2  ldloc.0
0x5ec3  ldloc.1
0x5ec4  ldloc.s  6
0x5ec6  call     void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStopWorkflowStatusMessage(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep stopWorkflowStep, class [System.Xml]System.Xml.XPath.XPathNavigator configColumn)
0x5ecb  ldarg.0
0x5ecc  ldloc.0
0x5ecd  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x5ed2  stloc.s  7
0x5ed4  leave.s  loc_5EE1
0x5ed6  stloc.s  8
0x5ed8  ldarg.0
0x5ed9  ldloc.s  8
0x5edb  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5ee0  throw
0x5ee1  ldloc.s  7
0x5ee3  ret
```
