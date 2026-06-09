# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInteraction

- ea: `0x3f00`
- end: `0x3fcf`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInteraction`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x3f00`
- `0x3fd0`
- `0x40b0`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x3fa6`: `Invalid XML`

## pseudocode

```c

```

## disassembly

```asm
0x3f00  ldarg.0
0x3f01  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3f06  ldarg.3
0x3f07  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3f0c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3f11  stloc.0
0x3f12  ldloc.0
0x3f13  ldarg.1
0x3f14  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3f19  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep
0x3f1e  stloc.1
0x3f1f  ldarg.0
0x3f20  ldloc.0
0x3f21  ldarg.s  4
0x3f23  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3f28  ldarg.2
0x3f29  ldc.i4.1
0x3f2a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string, bool)
0x3f2f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x3f34  ldstr    aInteractionact// "//interactionactivity"
0x3f39  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x3f3e  stloc.2
0x3f3f  ldloc.2
0x3f40  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x3f45  brfalse.s loc_3FB6
0x3f47  ldloc.2
0x3f48  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x3f4d  dup
0x3f4e  ldstr    aSteplabel// "steplabel"
0x3f53  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3f58  stloc.3
0x3f59  dup
0x3f5a  ldstr    aPrompt// "prompt"
0x3f5f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3f64  stloc.s  4
0x3f66  ldstr    aResponse// "response"
0x3f6b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3f70  stloc.s  5
0x3f72  ldloc.3
0x3f73  brfalse.s loc_3FA6
0x3f75  ldloc.s  4
0x3f77  brfalse.s loc_3FA6
0x3f79  ldloc.s  5
0x3f7b  brfalse.s loc_3FA6
0x3f7d  ldloc.1
0x3f7e  ldloc.3
0x3f7f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3f84  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x3f89  ldarg.0
0x3f8a  ldloc.1
0x3f8b  ldloc.s  4
0x3f8d  ldloc.0
0x3f8e  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdatePromptSection(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator promptNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3f93  ldarg.0
0x3f94  ldloc.1
0x3f95  ldloc.s  5
0x3f97  ldloc.0
0x3f98  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseSection(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep interactionStep, class [System.Xml]System.Xml.XPath.XPathNavigator responseNode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3f9d  ldloc.1
0x3f9e  ldc.i4.1
0x3f9f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_IsDataSourceDirty(bool)
0x3fa4  br.s     loc_3FB6
0x3fa6  ldstr    aInvalidXml// "Invalid XML"
0x3fab  ldc.i4   0x80004005
0x3fb0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3fb5  throw
0x3fb6  ldarg.0
0x3fb7  ldloc.0
0x3fb8  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3fbd  stloc.s  6
0x3fbf  leave.s  loc_3FCC
0x3fc1  stloc.s  7
0x3fc3  ldarg.0
0x3fc4  ldloc.s  7
0x3fc6  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x3fcb  throw
0x3fcc  ldloc.s  6
0x3fce  ret
```
