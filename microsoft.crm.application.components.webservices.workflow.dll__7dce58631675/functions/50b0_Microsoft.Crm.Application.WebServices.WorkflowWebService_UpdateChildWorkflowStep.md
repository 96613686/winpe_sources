# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildWorkflowStep

- ea: `0x50b0`
- end: `0x5290`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildWorkflowStep`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x50b0`
- `0x8ba0`
- `0x8f00`

## string_xrefs

- `0x510c`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x50b0  ldarg.0
0x50b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x50b6  ldarg.2
0x50b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x50bc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x50c1  stloc.0
0x50c2  ldloc.0
0x50c3  ldarg.1
0x50c4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x50c9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep
0x50ce  stloc.1
0x50cf  ldarg.0
0x50d0  ldloc.0
0x50d1  ldarg.s  4
0x50d3  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x50d8  ldarg.3
0x50d9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x50de  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x50e3  ldstr    aCondition_0// "//condition"
0x50e8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x50ed  stloc.2
0x50ee  ldloc.2
0x50ef  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x50f4  brfalse  loc_5261
0x50f9  ldloc.2
0x50fa  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x50ff  dup
0x5100  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x5105  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x510a  stloc.3
0x510b  dup
0x510c  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x5111  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5116  stloc.s  4
0x5118  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x511d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x5122  stloc.s  5
0x5124  ldloc.3
0x5125  brfalse  loc_5261
0x512a  ldloc.s  4
0x512c  brfalse  loc_5261
0x5131  ldloc.s  5
0x5133  brfalse  loc_5261
0x5138  ldloc.s  5
0x513a  ldstr    aValue// "value"
0x513f  ldsfld   string [mscorlib]System.String::Empty
0x5144  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5149  stloc.s  6
0x514b  ldloc.3
0x514c  ldstr    aValue// "value"
0x5151  ldsfld   string [mscorlib]System.String::Empty
0x5156  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x515b  ldloc.s  4
0x515d  ldstr    aValue// "value"
0x5162  ldsfld   string [mscorlib]System.String::Empty
0x5167  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x516c  stloc.s  7
0x516e  ldstr    aChildworkflow// "childworkflow"
0x5173  ldc.i4.5
0x5174  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5179  brfalse  loc_5261
0x517e  ldloc.s  7
0x5180  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5185  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x518a  stloc.s  8
0x518c  ldloc.s  6
0x518e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x5193  stloc.s  9
0x5195  ldloc.1
0x5196  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x519b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x51a0  ldloc.s  6
0x51a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a7  brfalse.s loc_51B7
0x51a9  ldloc.1
0x51aa  ldloc.0
0x51ab  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x51b0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x51b5  br.s     loc_51F2
0x51b7  ldloc.s  6
0x51b9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x51be  stloc.s  0xA
0x51c0  ldloc.s  0xA
0x51c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51c7  brtrue.s loc_51DB
0x51c9  ldloc.1
0x51ca  ldloc.0
0x51cb  ldloc.s  0xA
0x51cd  ldloc.s  9
0x51cf  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x51d4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x51d9  br.s     loc_51F2
0x51db  ldloc.s  6
0x51dd  ldloc.1
0x51de  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x51e3  stloc.s  0xB
0x51e5  ldloc.1
0x51e6  ldloc.s  0xB
0x51e8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x51ed  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x51f2  nop
0x51f3  ldloca.s 0xC
0x51f5  ldloc.s  8
0x51f7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x51fc  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5201  ldloc.s  8
0x5203  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5208  ldstr    aName// "name"
0x520d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5212  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5217  stloc.s  0xD
0x5219  ldloc.1
0x521a  ldloc.0
0x521b  ldloc.0
0x521c  ldloc.s  0xC
0x521e  box      [mscorlib]System.Guid
0x5223  ldc.i4.s 0xF
0x5225  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x522a  ldc.i4.6
0x522b  ldc.i4   0x125F
0x5230  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x5235  ldloc.s  0xD
0x5237  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x523c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5241  leave.s  loc_5261
0x5243  pop
0x5244  ldloc.1
0x5245  ldnull
0x5246  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x524b  leave.s  loc_5261
0x524d  pop
0x524e  ldloc.1
0x524f  ldnull
0x5250  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5255  leave.s  loc_5261
0x5257  pop
0x5258  ldloc.1
0x5259  ldnull
0x525a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x525f  leave.s  loc_5261
0x5261  ldarg.0
0x5262  ldloc.0
0x5263  ldarg.s  5
0x5265  dup
0x5266  brtrue.s loc_526E
0x5268  pop
0x5269  ldstr    asc_A26A// ""
0x526e  ldarg.s  6
0x5270  dup
0x5271  brtrue.s loc_5279
0x5273  pop
0x5274  ldstr    asc_A26A// ""
0x5279  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x527e  stloc.s  0xE
0x5280  leave.s  loc_528D
0x5282  stloc.s  0xF
0x5284  ldarg.0
0x5285  ldloc.s  0xF
0x5287  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x528c  throw
0x528d  ldloc.s  0xE
0x528f  ret
```
