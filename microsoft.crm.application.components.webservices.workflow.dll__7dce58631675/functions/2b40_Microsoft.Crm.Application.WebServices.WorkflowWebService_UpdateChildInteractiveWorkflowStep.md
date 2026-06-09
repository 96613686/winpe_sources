# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildInteractiveWorkflowStep

- ea: `0x2b40`
- end: `0x2d0a`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildInteractiveWorkflowStep`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x2b40`
- `0x2d10`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x2b9c`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x2b40  ldarg.0
0x2b41  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2b46  ldarg.2
0x2b47  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b4c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2b51  stloc.0
0x2b52  ldloc.0
0x2b53  ldarg.1
0x2b54  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x2b59  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep
0x2b5e  stloc.1
0x2b5f  ldarg.0
0x2b60  ldloc.0
0x2b61  ldarg.s  4
0x2b63  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x2b68  ldarg.3
0x2b69  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2b6e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x2b73  ldstr    aCondition_0// "//condition"
0x2b78  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x2b7d  stloc.2
0x2b7e  ldloc.2
0x2b7f  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x2b84  brfalse  loc_2CF1
0x2b89  ldloc.2
0x2b8a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x2b8f  dup
0x2b90  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x2b95  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2b9a  stloc.3
0x2b9b  dup
0x2b9c  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x2ba1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2ba6  stloc.s  4
0x2ba8  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x2bad  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2bb2  stloc.s  5
0x2bb4  ldloc.3
0x2bb5  brfalse  loc_2CF1
0x2bba  ldloc.s  4
0x2bbc  brfalse  loc_2CF1
0x2bc1  ldloc.s  5
0x2bc3  brfalse  loc_2CF1
0x2bc8  ldloc.s  5
0x2bca  ldstr    aValue// "value"
0x2bcf  ldsfld   string [mscorlib]System.String::Empty
0x2bd4  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x2bd9  stloc.s  6
0x2bdb  ldloc.3
0x2bdc  ldstr    aValue// "value"
0x2be1  ldsfld   string [mscorlib]System.String::Empty
0x2be6  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x2beb  ldloc.s  4
0x2bed  ldstr    aValue// "value"
0x2bf2  ldsfld   string [mscorlib]System.String::Empty
0x2bf7  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x2bfc  stloc.s  7
0x2bfe  ldstr    aChildworkflow// "childworkflow"
0x2c03  ldc.i4.5
0x2c04  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2c09  brfalse  loc_2CF1
0x2c0e  ldloc.s  7
0x2c10  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2c15  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2c1a  stloc.s  8
0x2c1c  ldloc.s  6
0x2c1e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x2c23  stloc.s  9
0x2c25  ldloc.1
0x2c26  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x2c2b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x2c30  ldloc.s  6
0x2c32  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c37  brfalse.s loc_2C47
0x2c39  ldloc.1
0x2c3a  ldloc.0
0x2c3b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2c40  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x2c45  br.s     loc_2C82
0x2c47  ldloc.s  6
0x2c49  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x2c4e  stloc.s  0xA
0x2c50  ldloc.s  0xA
0x2c52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c57  brtrue.s loc_2C6B
0x2c59  ldloc.1
0x2c5a  ldloc.0
0x2c5b  ldloc.s  0xA
0x2c5d  ldloc.s  9
0x2c5f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x2c64  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x2c69  br.s     loc_2C82
0x2c6b  ldloc.s  6
0x2c6d  ldloc.1
0x2c6e  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2c73  stloc.s  0xB
0x2c75  ldloc.1
0x2c76  ldloc.s  0xB
0x2c78  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x2c7d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x2c82  nop
0x2c83  ldloca.s 0xC
0x2c85  ldloc.s  8
0x2c87  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c8c  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2c91  ldloc.s  8
0x2c93  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2c98  ldstr    aName// "name"
0x2c9d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2ca2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2ca7  stloc.s  0xD
0x2ca9  ldloc.1
0x2caa  ldloc.0
0x2cab  ldloc.0
0x2cac  ldloc.s  0xC
0x2cae  box      [mscorlib]System.Guid
0x2cb3  ldc.i4.s 0xF
0x2cb5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x2cba  ldc.i4.6
0x2cbb  ldc.i4   0x125F
0x2cc0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x2cc5  ldloc.s  0xD
0x2cc7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x2ccc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2cd1  leave.s  loc_2CF1
0x2cd3  pop
0x2cd4  ldarg.0
0x2cd5  ldloc.1
0x2cd6  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::ClearChildWorkflowLinkage(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep linkedChildDialogStep)
0x2cdb  leave.s  loc_2CF1
0x2cdd  pop
0x2cde  ldarg.0
0x2cdf  ldloc.1
0x2ce0  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::ClearChildWorkflowLinkage(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep linkedChildDialogStep)
0x2ce5  leave.s  loc_2CF1
0x2ce7  pop
0x2ce8  ldarg.0
0x2ce9  ldloc.1
0x2cea  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::ClearChildWorkflowLinkage(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep linkedChildDialogStep)
0x2cef  leave.s  loc_2CF1
0x2cf1  ldarg.0
0x2cf2  ldloc.0
0x2cf3  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2cf8  stloc.s  0xE
0x2cfa  leave.s  loc_2D07
0x2cfc  stloc.s  0xF
0x2cfe  ldarg.0
0x2cff  ldloc.s  0xF
0x2d01  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2d06  throw
0x2d07  ldloc.s  0xE
0x2d09  ret
```
