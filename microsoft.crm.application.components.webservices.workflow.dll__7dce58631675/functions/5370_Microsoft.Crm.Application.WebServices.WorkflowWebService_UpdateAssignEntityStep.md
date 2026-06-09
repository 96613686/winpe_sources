# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignEntityStep

- ea: `0x5370`
- end: `0x568d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignEntityStep`
- size: `797`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x5370`
- `0x8ba0`
- `0x8f00`

## string_xrefs

- `0x53cc`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x5370  ldarg.0
0x5371  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5376  ldarg.2
0x5377  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x537c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5381  stloc.0
0x5382  ldloc.0
0x5383  ldarg.1
0x5384  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5389  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep
0x538e  stloc.1
0x538f  ldarg.0
0x5390  ldloc.0
0x5391  ldarg.s  4
0x5393  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5398  ldarg.3
0x5399  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x539e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x53a3  ldstr    aCondition_0// "//condition"
0x53a8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x53ad  stloc.2
0x53ae  ldloc.2
0x53af  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x53b4  brfalse  loc_565E
0x53b9  ldloc.2
0x53ba  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x53bf  dup
0x53c0  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x53c5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x53ca  stloc.3
0x53cb  dup
0x53cc  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x53d1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x53d6  stloc.s  4
0x53d8  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x53dd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x53e2  stloc.s  5
0x53e4  ldloc.3
0x53e5  brfalse  loc_565E
0x53ea  ldloc.s  4
0x53ec  brfalse  loc_565E
0x53f1  ldloc.s  5
0x53f3  brfalse  loc_565E
0x53f8  ldloc.s  5
0x53fa  ldstr    aValue// "value"
0x53ff  ldsfld   string [mscorlib]System.String::Empty
0x5404  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x5409  stloc.s  6
0x540b  ldloc.3
0x540c  ldstr    aValue// "value"
0x5411  ldsfld   string [mscorlib]System.String::Empty
0x5416  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x541b  ldloc.s  4
0x541d  ldstr    aValue// "value"
0x5422  ldsfld   string [mscorlib]System.String::Empty
0x5427  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x542c  stloc.s  7
0x542e  ldstr    aAssign// "assign"
0x5433  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5438  brfalse  loc_565E
0x543d  ldloc.s  7
0x543f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5444  stloc.s  8
0x5446  ldloc.s  8
0x5448  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x544d  stloc.s  9
0x544f  ldloc.s  6
0x5451  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityFromCompositeString(string)
0x5456  stloc.s  0xA
0x5458  ldloc.1
0x5459  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x545e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x5463  ldloc.s  6
0x5465  call     bool [mscorlib]System.String::op_Equality(string, string)
0x546a  brfalse.s loc_547A
0x546c  ldloc.1
0x546d  ldloc.0
0x546e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5473  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5478  br.s     loc_54B5
0x547a  ldloc.s  6
0x547c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetRelatedAttributeFromCompositeString(string)
0x5481  stloc.s  0xB
0x5483  ldloc.s  0xB
0x5485  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x548a  brtrue.s loc_549E
0x548c  ldloc.1
0x548d  ldloc.0
0x548e  ldloc.s  0xB
0x5490  ldloc.s  0xA
0x5492  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x5497  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x549c  br.s     loc_54B5
0x549e  ldloc.s  6
0x54a0  ldloc.1
0x54a1  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.UIWorkflowLibrary.EntityNameUtility::GetEntityCreatedByStepName(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x54a6  stloc.s  0xC
0x54a8  ldloc.1
0x54a9  ldloc.s  0xC
0x54ab  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x54b0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x54b5  nop
0x54b6  ldloc.s  8
0x54b8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x54bd  dup
0x54be  ldstr    aParametersPara_0// "//parameters/parameter/slugbody"
0x54c3  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x54c8  stloc.s  0xD
0x54ca  ldstr    aParametersPara_1// "//parameters/parameter/*"
0x54cf  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x54d4  stloc.s  0xE
0x54d6  ldloc.s  0xD
0x54d8  brfalse.s loc_5520
0x54da  ldloc.s  0xD
0x54dc  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x54e1  ldc.i4.0
0x54e2  ble.s    loc_5520
0x54e4  ldloc.s  0xD
0x54e6  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x54eb  pop
0x54ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54f1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54f6  ldloc.0
0x54f7  ldc.i4.8
0x54f8  ldloc.s  0xD
0x54fa  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x54ff  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x5504  ldc.i4.0
0x5505  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x550a  stloc.s  0xF
0x550c  ldloc.s  0xF
0x550e  brfalse  loc_563E
0x5513  ldloc.1
0x5514  ldloc.s  0xF
0x5516  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x551b  br       loc_563E
0x5520  ldloc.s  0xE
0x5522  brfalse  loc_55BE
0x5527  ldloc.s  0xE
0x5529  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x552e  ldc.i4.0
0x552f  ble      loc_55BE
0x5534  ldloc.s  0xE
0x5536  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x553b  pop
0x553c  ldloca.s 0x10
0x553e  ldloc.s  0xE
0x5540  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5545  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x554a  call     instance void [mscorlib]System.Guid::.ctor(string)
0x554f  ldloc.s  0xE
0x5551  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5556  pop
0x5557  ldloc.s  0xE
0x5559  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x555e  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x5563  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5568  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x556d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5572  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5577  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x557c  stloc.s  0x11
0x557e  ldloc.s  0xE
0x5580  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5585  pop
0x5586  ldloc.s  0xE
0x5588  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x558d  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x5592  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlDecode(string)
0x5597  stloc.s  0x12
0x5599  ldloc.1
0x559a  ldloc.0
0x559b  ldloc.0
0x559c  ldloc.s  0x10
0x559e  box      [mscorlib]System.Guid
0x55a3  ldc.i4.s 0xF
0x55a5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x55aa  ldc.i4.6
0x55ab  ldloc.s  0x11
0x55ad  ldloc.s  0x12
0x55af  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x55b4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x55b9  br       loc_563E
0x55be  ldloc.s  9
0x55c0  brfalse.s loc_5637
0x55c2  ldloc.s  9
0x55c4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x55c9  ldstr    aType// "type"
0x55ce  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x55d3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x55d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55dd  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x55e2  ldloc.s  9
0x55e4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x55e9  ldstr    aName// "name"
0x55ee  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x55f3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x55f8  stloc.s  0x13
0x55fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x55ff  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5604  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5609  stloc.s  0x14
0x560b  ldloc.1
0x560c  ldloc.0
0x560d  ldloc.0
0x560e  ldloc.s  9
0x5610  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5615  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x561a  box      [mscorlib]System.Guid
0x561f  ldc.i4.s 0xF
0x5621  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x5626  ldc.i4.6
0x5627  ldloc.s  0x14
0x5629  ldloc.s  0x13
0x562b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x5630  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5635  br.s     loc_563E
0x5637  ldloc.1
0x5638  ldnull
0x5639  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x563e  leave.s  loc_565E
0x5640  pop
0x5641  ldloc.1
0x5642  ldnull
0x5643  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5648  leave.s  loc_565E
0x564a  pop
0x564b  ldloc.1
0x564c  ldnull
0x564d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5652  leave.s  loc_565E
0x5654  pop
0x5655  ldloc.1
0x5656  ldnull
0x5657  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_AssignTo(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x565c  leave.s  loc_565E
0x565e  ldarg.0
0x565f  ldloc.0
0x5660  ldarg.s  5
0x5662  dup
0x5663  brtrue.s loc_566B
0x5665  pop
0x5666  ldstr    asc_A26A// ""
0x566b  ldarg.s  6
0x566d  dup
0x566e  brtrue.s loc_5676
0x5670  pop
0x5671  ldstr    asc_A26A// ""
0x5676  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x567b  stloc.s  0x15
0x567d  leave.s  loc_568A
0x567f  stloc.s  0x16
0x5681  ldarg.0
0x5682  ldloc.s  0x16
0x5684  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5689  throw
0x568a  ldloc.s  0x15
0x568c  ret
```
