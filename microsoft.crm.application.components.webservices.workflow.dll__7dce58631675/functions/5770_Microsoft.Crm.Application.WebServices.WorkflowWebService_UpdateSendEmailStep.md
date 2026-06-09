# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateSendEmailStep

- ea: `0x5770`
- end: `0x5a45`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateSendEmailStep`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x5770`
- `0x8ba0`
- `0x8f00`

## string_xrefs

- `0x57e6`: `column[@id="colConfiguration"]`
- `0x57d9`: `column[@id="colTemplate"]`

## pseudocode

```c

```

## disassembly

```asm
0x5770  ldarg.0
0x5771  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5776  ldarg.2
0x5777  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x577c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5781  stloc.0
0x5782  ldloc.0
0x5783  ldarg.1
0x5784  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5789  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x578e  stloc.1
0x578f  ldarg.0
0x5790  ldloc.0
0x5791  ldarg.s  4
0x5793  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5798  ldarg.3
0x5799  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x579e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x57a3  ldstr    aCondition_0// "//condition"
0x57a8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x57ad  stloc.2
0x57ae  ldloc.2
0x57af  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x57b4  brfalse  loc_5A16
0x57b9  ldloc.2
0x57ba  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x57bf  dup
0x57c0  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x57c5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x57ca  stloc.3
0x57cb  dup
0x57cc  ldstr    aColumnIdColtyp// "column[@id=\"colType\"]"
0x57d1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x57d6  stloc.s  4
0x57d8  dup
0x57d9  ldstr    aColumnIdColtem// "column[@id=\"colTemplate\"]"
0x57de  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x57e3  stloc.s  5
0x57e5  dup
0x57e6  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x57eb  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x57f0  stloc.s  6
0x57f2  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x57f7  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x57fc  stloc.s  7
0x57fe  ldloc.3
0x57ff  brfalse  loc_5A16
0x5804  ldloc.s  6
0x5806  brfalse  loc_5A16
0x580b  ldloc.s  7
0x580d  brfalse  loc_5A16
0x5812  ldloc.s  7
0x5814  ldstr    aValue// "value"
0x5819  ldsfld   string [mscorlib]System.String::Empty
0x581e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5823  stloc.s  8
0x5825  ldloc.3
0x5826  ldstr    aValue// "value"
0x582b  ldsfld   string [mscorlib]System.String::Empty
0x5830  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5835  ldloc.s  4
0x5837  ldstr    aValue// "value"
0x583c  ldsfld   string [mscorlib]System.String::Empty
0x5841  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5846  stloc.s  9
0x5848  ldloc.s  6
0x584a  ldstr    aValue// "value"
0x584f  ldsfld   string [mscorlib]System.String::Empty
0x5854  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5859  stloc.s  0xA
0x585b  ldstr    aSendemail// "sendemail"
0x5860  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5865  brfalse  loc_5A16
0x586a  ldloc.s  0xA
0x586c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5871  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5876  stloc.s  0xB
0x5878  ldloc.s  9
0x587a  ldc.i4.1
0x587b  stloc.s  0xC
0x587d  ldloca.s 0xC
0x587f  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType
0x5885  callvirt instance string [mscorlib]System.Object::ToString()
0x588a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x588f  brfalse  loc_596F
0x5894  ldloc.1
0x5895  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x589a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_EmailTemplateId(valuetype [mscorlib]System.Guid)
0x589f  ldloc.1
0x58a0  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::get_SendEmailStepType()
0x58a5  stloc.s  0xC
0x58a7  ldloca.s 0xC
0x58a9  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType
0x58af  callvirt instance string [mscorlib]System.Object::ToString()
0x58b4  ldloc.s  9
0x58b6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x58bb  brfalse.s loc_58DA
0x58bd  ldloc.1
0x58be  ldc.i4.1
0x58bf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_SendEmailStepType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType)
0x58c4  ldloc.1
0x58c5  ldloc.1
0x58c6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x58cb  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x58d0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_RegardingEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x58d5  br       loc_5976
0x58da  ldloc.s  8
0x58dc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x58e1  stloc.s  0xD
0x58e3  ldloc.s  5
0x58e5  brfalse.s loc_5910
0x58e7  ldloc.s  5
0x58e9  ldstr    aValue// "value"
0x58ee  ldsfld   string [mscorlib]System.String::Empty
0x58f3  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x58f8  stloc.s  0xE
0x58fa  ldloc.s  0xE
0x58fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5901  brtrue.s loc_5910
0x5903  ldloc.1
0x5904  ldloc.s  0xE
0x5906  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x590b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_EmailTemplateId(valuetype [mscorlib]System.Guid)
0x5910  ldloc.1
0x5911  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x5916  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x591b  ldloc.s  8
0x591d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5922  brfalse.s loc_5932
0x5924  ldloc.1
0x5925  ldloc.0
0x5926  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x592b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_RegardingEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5930  br.s     loc_5976
0x5932  ldloc.s  8
0x5934  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x5939  stloc.s  0xF
0x593b  ldloc.s  0xF
0x593d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5942  brtrue.s loc_5956
0x5944  ldloc.1
0x5945  ldloc.0
0x5946  ldloc.s  0xF
0x5948  ldloc.s  0xD
0x594a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x594f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_RegardingEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5954  br.s     loc_5976
0x5956  ldloc.s  8
0x5958  ldloc.1
0x5959  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x595e  stloc.s  0x10
0x5960  ldloc.1
0x5961  ldloc.s  0x10
0x5963  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x5968  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_RegardingEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x596d  br.s     loc_5976
0x596f  ldloc.1
0x5970  ldc.i4.0
0x5971  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_SendEmailStepType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType)
0x5976  ldstr    aEmail// "email"
0x597b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5980  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5985  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x598a  stloc.s  8
0x598c  ldloc.1
0x598d  ldloc.s  8
0x598f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x5994  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x5999  ldloc.s  0xB
0x599b  brfalse.s loc_5A16
0x599d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x59a2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59a7  stloc.s  0x11
0x59a9  ldloc.s  0xB
0x59ab  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x59b0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x59b5  stloc.s  0x12
0x59b7  br.s     loc_59F6
0x59b9  ldloc.s  0x12
0x59bb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x59c0  castclass [System.Xml]System.Xml.XmlNode
0x59c5  stloc.s  0x13
0x59c7  ldloc.s  0x13
0x59c9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x59ce  stloc.s  0x14
0x59d0  ldloc.s  0x11
0x59d2  ldloc.0
0x59d3  ldloc.s  8
0x59d5  ldloc.s  0x13
0x59d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x59dc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x59e1  stloc.s  0x15
0x59e3  ldloc.s  0x15
0x59e5  brfalse.s loc_59F6
0x59e7  ldloc.1
0x59e8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::get_Entity()
0x59ed  ldloc.s  0x14
0x59ef  ldloc.s  0x15
0x59f1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x59f6  ldloc.s  0x12
0x59f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59fd  brtrue.s loc_59B9
0x59ff  leave.s  loc_5A16
0x5a01  ldloc.s  0x12
0x5a03  isinst   [mscorlib]System.IDisposable
0x5a08  stloc.s  0x16
0x5a0a  ldloc.s  0x16
0x5a0c  brfalse.s loc_5A15
0x5a0e  ldloc.s  0x16
0x5a10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a15  endfinally
0x5a16  ldarg.0
0x5a17  ldloc.0
0x5a18  ldarg.s  5
0x5a1a  dup
0x5a1b  brtrue.s loc_5A23
0x5a1d  pop
0x5a1e  ldstr    asc_A26A// ""
0x5a23  ldarg.s  6
0x5a25  dup
0x5a26  brtrue.s loc_5A2E
0x5a28  pop
0x5a29  ldstr    asc_A26A// ""
0x5a2e  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x5a33  stloc.s  0x17
0x5a35  leave.s  loc_5A42
0x5a37  stloc.s  0x18
0x5a39  ldarg.0
0x5a3a  ldloc.s  0x18
0x5a3c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5a41  throw
0x5a42  ldloc.s  0x17
0x5a44  ret
```
