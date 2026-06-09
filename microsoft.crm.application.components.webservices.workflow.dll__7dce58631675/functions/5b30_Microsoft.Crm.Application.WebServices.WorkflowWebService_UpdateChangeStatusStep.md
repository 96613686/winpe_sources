# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChangeStatusStep

- ea: `0x5b30`
- end: `0x5d02`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChangeStatusStep`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x5b30`
- `0x5d10`
- `0x8ba0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x5b30  ldarg.0
0x5b31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5b36  ldarg.2
0x5b37  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5b3c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5b41  stloc.0
0x5b42  ldloc.0
0x5b43  ldarg.1
0x5b44  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5b49  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep
0x5b4e  stloc.1
0x5b4f  ldarg.0
0x5b50  ldloc.0
0x5b51  ldarg.s  4
0x5b53  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5b58  ldarg.3
0x5b59  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5b5e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x5b63  ldstr    aCondition_0// "//condition"
0x5b68  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5b6d  stloc.2
0x5b6e  ldloc.2
0x5b6f  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5b74  brfalse  loc_5CD3
0x5b79  ldloc.2
0x5b7a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5b7f  dup
0x5b80  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x5b85  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5b8a  stloc.3
0x5b8b  dup
0x5b8c  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x5b91  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5b96  stloc.s  4
0x5b98  dup
0x5b99  ldstr    aColumnIdColsta// "column[@id=\"colState\"]"
0x5b9e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5ba3  stloc.s  5
0x5ba5  ldstr    aColumnIdColsta_0// "column[@id=\"colStatus\"]"
0x5baa  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5baf  stloc.s  6
0x5bb1  ldloc.3
0x5bb2  brfalse  loc_5CD3
0x5bb7  ldloc.s  5
0x5bb9  brfalse  loc_5CD3
0x5bbe  ldloc.s  6
0x5bc0  brfalse  loc_5CD3
0x5bc5  ldloc.s  4
0x5bc7  brfalse  loc_5CD3
0x5bcc  ldloc.s  4
0x5bce  ldstr    aValue// "value"
0x5bd3  ldsfld   string [mscorlib]System.String::Empty
0x5bd8  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5bdd  stloc.s  7
0x5bdf  ldloc.3
0x5be0  ldstr    aValue// "value"
0x5be5  ldsfld   string [mscorlib]System.String::Empty
0x5bea  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5bef  ldloc.s  5
0x5bf1  ldstr    aValue// "value"
0x5bf6  ldsfld   string [mscorlib]System.String::Empty
0x5bfb  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5c00  stloc.s  8
0x5c02  ldloc.s  6
0x5c04  ldstr    aValue// "value"
0x5c09  ldsfld   string [mscorlib]System.String::Empty
0x5c0e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5c13  stloc.s  9
0x5c15  ldloc.s  7
0x5c17  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x5c1c  stloc.s  0xA
0x5c1e  ldloc.1
0x5c1f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x5c24  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x5c29  ldloc.s  7
0x5c2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c30  brfalse.s loc_5C40
0x5c32  ldloc.1
0x5c33  ldloc.0
0x5c34  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5c39  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5c3e  br.s     loc_5C7B
0x5c40  ldloc.s  7
0x5c42  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x5c47  stloc.s  0xB
0x5c49  ldloc.s  0xB
0x5c4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5c50  brtrue.s loc_5C64
0x5c52  ldloc.1
0x5c53  ldloc.0
0x5c54  ldloc.s  0xB
0x5c56  ldloc.s  0xA
0x5c58  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x5c5d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5c62  br.s     loc_5C7B
0x5c64  ldloc.s  7
0x5c66  ldloc.1
0x5c67  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5c6c  stloc.s  0xC
0x5c6e  ldloc.1
0x5c6f  ldloc.s  0xC
0x5c71  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x5c76  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5c7b  ldstr    aChangestatus_0// "changeStatus"
0x5c80  ldc.i4.5
0x5c81  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5c86  brfalse.s loc_5CD3
0x5c88  ldloc.s  9
0x5c8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c8f  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5c94  stloc.s  0xD
0x5c96  ldarg.0
0x5c97  ldloc.1
0x5c98  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::get_Entity()
0x5c9d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x5ca2  ldloc.s  8
0x5ca4  call     instance int32 Microsoft.Crm.Application.WebServices.WorkflowWebService::GetStateValue(string entityName, string legacyStateValue)
0x5ca9  stloc.s  0xE
0x5cab  ldloc.1
0x5cac  ldloc.0
0x5cad  ldloc.s  0xE
0x5caf  box      [mscorlib]System.Int32
0x5cb4  ldc.i4.5
0x5cb5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x5cba  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_State(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5cbf  ldloc.1
0x5cc0  ldloc.0
0x5cc1  ldloc.s  0xD
0x5cc3  box      [mscorlib]System.Int32
0x5cc8  ldc.i4.5
0x5cc9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x5cce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Status(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5cd3  ldarg.0
0x5cd4  ldloc.0
0x5cd5  ldarg.s  5
0x5cd7  dup
0x5cd8  brtrue.s loc_5CE0
0x5cda  pop
0x5cdb  ldstr    asc_A26A// ""
0x5ce0  ldarg.s  6
0x5ce2  dup
0x5ce3  brtrue.s loc_5CEB
0x5ce5  pop
0x5ce6  ldstr    asc_A26A// ""
0x5ceb  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x5cf0  stloc.s  0xF
0x5cf2  leave.s  loc_5CFF
0x5cf4  stloc.s  0x10
0x5cf6  ldarg.0
0x5cf7  ldloc.s  0x10
0x5cf9  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5cfe  throw
0x5cff  ldloc.s  0xF
0x5d01  ret
```
