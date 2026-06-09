# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateUpdateEntityStep

- ea: `0x4dd0`
- end: `0x4fc3`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateUpdateEntityStep`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4dd0`
- `0x8ba0`
- `0x8f00`

## string_xrefs

- `0x4e8e`: `update`
- `0x4e2c`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x4dd0  ldarg.0
0x4dd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4dd6  ldarg.2
0x4dd7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4ddc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4de1  stloc.0
0x4de2  ldloc.0
0x4de3  ldarg.1
0x4de4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4de9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep
0x4dee  stloc.1
0x4def  ldarg.0
0x4df0  ldloc.0
0x4df1  ldarg.s  4
0x4df3  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4df8  ldarg.3
0x4df9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4dfe  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x4e03  ldstr    aCondition_0// "//condition"
0x4e08  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x4e0d  stloc.2
0x4e0e  ldloc.2
0x4e0f  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x4e14  brfalse  loc_4F94
0x4e19  ldloc.2
0x4e1a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x4e1f  dup
0x4e20  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x4e25  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4e2a  stloc.3
0x4e2b  dup
0x4e2c  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x4e31  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4e36  stloc.s  4
0x4e38  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x4e3d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4e42  stloc.s  5
0x4e44  ldloc.3
0x4e45  brfalse  loc_4F94
0x4e4a  ldloc.s  4
0x4e4c  brfalse  loc_4F94
0x4e51  ldloc.s  5
0x4e53  brfalse  loc_4F94
0x4e58  ldloc.s  5
0x4e5a  ldstr    aValue// "value"
0x4e5f  ldsfld   string [mscorlib]System.String::Empty
0x4e64  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4e69  stloc.s  6
0x4e6b  ldloc.3
0x4e6c  ldstr    aValue// "value"
0x4e71  ldsfld   string [mscorlib]System.String::Empty
0x4e76  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4e7b  ldloc.s  4
0x4e7d  ldstr    aValue// "value"
0x4e82  ldsfld   string [mscorlib]System.String::Empty
0x4e87  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4e8c  stloc.s  7
0x4e8e  ldstr    aUpdate// "update"
0x4e93  ldc.i4.5
0x4e94  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4e99  brfalse  loc_4F94
0x4e9e  ldloc.s  7
0x4ea0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4ea5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4eaa  ldloc.s  6
0x4eac  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x4eb1  stloc.s  8
0x4eb3  ldloc.1
0x4eb4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x4eb9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x4ebe  ldloc.s  6
0x4ec0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec5  brfalse.s loc_4ED5
0x4ec7  ldloc.1
0x4ec8  ldloc.0
0x4ec9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4ece  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x4ed3  br.s     loc_4F10
0x4ed5  ldloc.s  6
0x4ed7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x4edc  stloc.s  0xA
0x4ede  ldloc.s  0xA
0x4ee0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ee5  brtrue.s loc_4EF9
0x4ee7  ldloc.1
0x4ee8  ldloc.0
0x4ee9  ldloc.s  0xA
0x4eeb  ldloc.s  8
0x4eed  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x4ef2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x4ef7  br.s     loc_4F10
0x4ef9  ldloc.s  6
0x4efb  ldloc.1
0x4efc  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4f01  stloc.s  0xB
0x4f03  ldloc.1
0x4f04  ldloc.s  0xB
0x4f06  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x4f0b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x4f10  ldloc.1
0x4f11  ldloc.s  8
0x4f13  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x4f18  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x4f1d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4f22  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f27  stloc.s  9
0x4f29  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4f2e  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x4f33  stloc.s  0xC
0x4f35  br.s     loc_4F74
0x4f37  ldloc.s  0xC
0x4f39  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4f3e  castclass [System.Xml]System.Xml.XmlNode
0x4f43  stloc.s  0xD
0x4f45  ldloc.s  0xD
0x4f47  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x4f4c  stloc.s  0xE
0x4f4e  ldloc.s  9
0x4f50  ldloc.0
0x4f51  ldloc.s  8
0x4f53  ldloc.s  0xD
0x4f55  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4f5a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x4f5f  stloc.s  0xF
0x4f61  ldloc.s  0xF
0x4f63  brfalse.s loc_4F74
0x4f65  ldloc.1
0x4f66  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x4f6b  ldloc.s  0xE
0x4f6d  ldloc.s  0xF
0x4f6f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4f74  ldloc.s  0xC
0x4f76  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4f7b  brtrue.s loc_4F37
0x4f7d  leave.s  loc_4F94
0x4f7f  ldloc.s  0xC
0x4f81  isinst   [mscorlib]System.IDisposable
0x4f86  stloc.s  0x10
0x4f88  ldloc.s  0x10
0x4f8a  brfalse.s loc_4F93
0x4f8c  ldloc.s  0x10
0x4f8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f93  endfinally
0x4f94  ldarg.0
0x4f95  ldloc.0
0x4f96  ldarg.s  5
0x4f98  dup
0x4f99  brtrue.s loc_4FA1
0x4f9b  pop
0x4f9c  ldstr    asc_A26A// ""
0x4fa1  ldarg.s  6
0x4fa3  dup
0x4fa4  brtrue.s loc_4FAC
0x4fa6  pop
0x4fa7  ldstr    asc_A26A// ""
0x4fac  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4fb1  stloc.s  0x11
0x4fb3  leave.s  loc_4FC0
0x4fb5  stloc.s  0x12
0x4fb7  ldarg.0
0x4fb8  ldloc.s  0x12
0x4fba  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4fbf  throw
0x4fc0  ldloc.s  0x11
0x4fc2  ret
```
