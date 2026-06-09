# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCreateEntityStep

- ea: `0x4b20`
- end: `0x4cec`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCreateEntityStep`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4b20`
- `0x8a30`
- `0x8ba0`
- `0x8e00`
- `0x8f00`

## string_xrefs

- `0x4b87`: `column[@id="colConfiguration"]`
- `0x4beb`: `create`

## pseudocode

```c

```

## disassembly

```asm
0x4b20  ldarg.0
0x4b21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4b26  ldarg.2
0x4b27  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4b2c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4b31  stloc.0
0x4b32  ldloc.0
0x4b33  ldarg.1
0x4b34  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4b39  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep
0x4b3e  stloc.1
0x4b3f  ldarg.0
0x4b40  ldloc.0
0x4b41  ldarg.s  4
0x4b43  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4b48  ldloc.1
0x4b49  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x4b4e  ldnull
0x4b4f  ceq
0x4b51  stloc.2
0x4b52  ldarg.3
0x4b53  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4b58  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x4b5d  ldstr    aCondition_0// "//condition"
0x4b62  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x4b67  stloc.3
0x4b68  ldloc.3
0x4b69  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x4b6e  brfalse  loc_4CB4
0x4b73  ldloc.3
0x4b74  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x4b79  dup
0x4b7a  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x4b7f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4b84  stloc.s  4
0x4b86  dup
0x4b87  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x4b8c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4b91  stloc.s  5
0x4b93  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x4b98  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4b9d  stloc.s  6
0x4b9f  ldloc.s  4
0x4ba1  brfalse  loc_4CB4
0x4ba6  ldloc.s  5
0x4ba8  brfalse  loc_4CB4
0x4bad  ldloc.s  6
0x4baf  brfalse  loc_4CB4
0x4bb4  ldloc.s  6
0x4bb6  ldstr    aValue// "value"
0x4bbb  ldsfld   string [mscorlib]System.String::Empty
0x4bc0  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4bc5  stloc.s  7
0x4bc7  ldloc.s  4
0x4bc9  ldstr    aValue// "value"
0x4bce  ldsfld   string [mscorlib]System.String::Empty
0x4bd3  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4bd8  ldloc.s  5
0x4bda  ldstr    aValue// "value"
0x4bdf  ldsfld   string [mscorlib]System.String::Empty
0x4be4  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4be9  stloc.s  8
0x4beb  ldstr    aCreate// "create"
0x4bf0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bf5  brfalse  loc_4CB4
0x4bfa  ldloc.s  8
0x4bfc  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4c01  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4c06  ldloc.1
0x4c07  ldloc.s  7
0x4c09  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x4c0e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x4c13  ldc.i4.0
0x4c14  stloc.s  9
0x4c16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c1b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c20  stloc.s  0xA
0x4c22  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4c27  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x4c2c  stloc.s  0xB
0x4c2e  br.s     loc_4C7E
0x4c30  ldloc.s  0xB
0x4c32  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4c37  castclass [System.Xml]System.Xml.XmlNode
0x4c3c  stloc.s  0xC
0x4c3e  ldloc.s  0xC
0x4c40  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x4c45  stloc.s  0xD
0x4c47  ldloc.s  0xA
0x4c49  ldloc.0
0x4c4a  ldloc.s  7
0x4c4c  ldloc.s  0xC
0x4c4e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4c53  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x4c58  stloc.s  0xE
0x4c5a  ldloc.s  0xE
0x4c5c  brfalse.s loc_4C6D
0x4c5e  ldloc.1
0x4c5f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x4c64  ldloc.s  0xD
0x4c66  ldloc.s  0xE
0x4c68  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4c6d  ldloc.s  0xD
0x4c6f  ldstr    aRegardingobjec// "regardingobjectid"
0x4c74  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c79  brfalse.s loc_4C7E
0x4c7b  ldc.i4.1
0x4c7c  stloc.s  9
0x4c7e  ldloc.s  0xB
0x4c80  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c85  brtrue.s loc_4C30
0x4c87  leave.s  loc_4C9E
0x4c89  ldloc.s  0xB
0x4c8b  isinst   [mscorlib]System.IDisposable
0x4c90  stloc.s  0xF
0x4c92  ldloc.s  0xF
0x4c94  brfalse.s loc_4C9D
0x4c96  ldloc.s  0xF
0x4c98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c9d  endfinally
0x4c9e  ldloc.s  9
0x4ca0  ldc.i4.0
0x4ca1  ceq
0x4ca3  ldloc.2
0x4ca4  and
0x4ca5  brfalse.s loc_4CB4
0x4ca7  ldarg.0
0x4ca8  ldloc.0
0x4ca9  ldloc.1
0x4caa  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x4caf  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetRegardingObjectDefault(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification entitySpecification)
0x4cb4  ldarg.s  6
0x4cb6  ldloc.1
0x4cb7  ldloc.0
0x4cb8  call     void Microsoft.Crm.Application.WebServices.WorkflowWebService::AddDefaultProperties(string rendererTypeCode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep rootWorkflowStep)
0x4cbd  ldarg.0
0x4cbe  ldloc.0
0x4cbf  ldarg.s  5
0x4cc1  dup
0x4cc2  brtrue.s loc_4CCA
0x4cc4  pop
0x4cc5  ldstr    asc_A26A// ""
0x4cca  ldarg.s  6
0x4ccc  dup
0x4ccd  brtrue.s loc_4CD5
0x4ccf  pop
0x4cd0  ldstr    asc_A26A// ""
0x4cd5  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4cda  stloc.s  0x10
0x4cdc  leave.s  loc_4CE9
0x4cde  stloc.s  0x11
0x4ce0  ldarg.0
0x4ce1  ldloc.s  0x11
0x4ce3  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4ce8  throw
0x4ce9  ldloc.s  0x10
0x4ceb  ret
```
