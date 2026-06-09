# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageOperationStep

- ea: `0x6360`
- end: `0x65fe`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageOperationStep`
- size: `670`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x6230`
- `0x6360`
- `0x6600`
- `0x6680`
- `0x6ac0`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x63f0`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x6360  ldarg.0
0x6361  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6366  ldarg.2
0x6367  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x636c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6371  stloc.0
0x6372  ldloc.0
0x6373  ldarg.1
0x6374  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6379  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep
0x637e  stloc.1
0x637f  ldarg.0
0x6380  ldloc.0
0x6381  ldarg.s  4
0x6383  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6388  ldarg.0
0x6389  ldloc.1
0x638a  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep invokeSdkMessageStep)
0x638f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6394  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6399  stloc.2
0x639a  ldloc.1
0x639b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x63a0  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo
0x63a5  stloc.3
0x63a6  ldarg.0
0x63a7  ldloc.3
0x63a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageId()
0x63ad  ldloc.3
0x63ae  ldstr    asc_A26A// ""
0x63b3  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSdkMessageDetails(valuetype [mscorlib]System.Guid sdkMessageId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo objActivityInfo, [opt] string sdkMessageFilterId)
0x63b8  ldarg.3
0x63b9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x63be  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x63c3  ldstr    aCondition_0// "//condition"
0x63c8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x63cd  stloc.s  4
0x63cf  ldloc.s  4
0x63d1  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x63d6  brfalse  loc_65DE
0x63db  ldloc.s  4
0x63dd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x63e2  dup
0x63e3  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x63e8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x63ed  stloc.s  5
0x63ef  dup
0x63f0  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x63f5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x63fa  stloc.s  6
0x63fc  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x6401  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x6406  stloc.s  7
0x6408  ldloc.s  5
0x640a  brfalse  loc_65DE
0x640f  ldloc.s  6
0x6411  brfalse  loc_65DE
0x6416  ldloc.s  7
0x6418  brfalse  loc_65DE
0x641d  ldloc.s  6
0x641f  ldstr    aValue// "value"
0x6424  ldsfld   string [mscorlib]System.String::Empty
0x6429  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x642e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6433  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x6438  stloc.s  8
0x643a  ldloc.1
0x643b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6440  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Keys()
0x6445  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Count()
0x644a  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo
0x644f  stloc.s  9
0x6451  ldloc.1
0x6452  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6457  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Keys()
0x645c  ldloc.s  9
0x645e  ldc.i4.0
0x645f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::CopyTo(var<u1>[], !!T0)
0x6464  ldloc.1
0x6465  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x646a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::get_Keys()
0x646f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::get_Count()
0x6474  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo
0x6479  stloc.s  0xA
0x647b  ldloc.1
0x647c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x6481  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::get_Values()
0x6486  ldloc.s  0xA
0x6488  ldc.i4.0
0x6489  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::CopyTo(var<u1>[], void)
0x648e  ldloc.s  9
0x6490  stloc.s  0xB
0x6492  ldc.i4.0
0x6493  stloc.s  0xC
0x6495  br       loc_65D3
0x649a  ldloc.s  0xB
0x649c  ldloc.s  0xC
0x649e  ldelem.ref
0x649f  stloc.s  0xD
0x64a1  ldnull
0x64a2  stloc.s  0xE
0x64a4  ldloc.s  8
0x64a6  ldstr    aParameter// "//parameter"
0x64ab  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x64b0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XPath.XPathNodeIterator::GetEnumerator()
0x64b5  stloc.s  0xF
0x64b7  br.s     loc_64EC
0x64b9  ldloc.s  0xF
0x64bb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x64c0  castclass [System.Xml]System.Xml.XPath.XPathNavigator
0x64c5  stloc.s  0x10
0x64c7  ldloc.s  0x10
0x64c9  ldstr    aName// "name"
0x64ce  ldsfld   string [mscorlib]System.String::Empty
0x64d3  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x64d8  ldloc.s  0xD
0x64da  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x64df  callvirt instance bool [mscorlib]System.String::Equals(string)
0x64e4  brfalse.s loc_64EC
0x64e6  ldloc.s  0x10
0x64e8  stloc.s  0xE
0x64ea  br.s     loc_64F5
0x64ec  ldloc.s  0xF
0x64ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64f3  brtrue.s loc_64B9
0x64f5  leave.s  loc_650C
0x64f7  ldloc.s  0xF
0x64f9  isinst   [mscorlib]System.IDisposable
0x64fe  stloc.s  0x11
0x6500  ldloc.s  0x11
0x6502  brfalse.s loc_650B
0x6504  ldloc.s  0x11
0x6506  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x650b  endfinally
0x650c  ldloc.s  0xE
0x650e  brfalse.s loc_6583
0x6510  ldloc.s  0xE
0x6512  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x6517  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x651c  brtrue.s loc_6583
0x651e  ldloc.s  0xE
0x6520  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x6525  ldstr    aSlugbody_0// "<slugbody>"
0x652a  ldc.i4.5
0x652b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6530  brfalse.s loc_6583
0x6532  ldloc.2
0x6533  ldloc.0
0x6534  ldloc.1
0x6535  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x653a  ldloc.s  0xD
0x653c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x6541  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::get_Type()
0x6546  ldloc.s  0xE
0x6548  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x654d  ldc.i4.0
0x654e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x6553  stloc.s  0x12
0x6555  ldloc.s  0x12
0x6557  brfalse.s loc_65CD
0x6559  ldloc.s  0x12
0x655b  ldloc.1
0x655c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6561  ldloc.s  0xD
0x6563  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x6568  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::get_Type()
0x656d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::set_Type(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x6572  ldloc.1
0x6573  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6578  ldloc.s  0xD
0x657a  ldloc.s  0x12
0x657c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x6581  br.s     loc_65CD
0x6583  ldloc.s  0xE
0x6585  brfalse.s loc_65B7
0x6587  ldloc.s  0xE
0x6589  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x658e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6593  ldc.i4.0
0x6594  ble.s    loc_65B7
0x6596  ldloc.1
0x6597  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x659c  ldloc.s  0xD
0x659e  ldloc.1
0x659f  ldloc.s  0xD
0x65a1  ldarg.0
0x65a2  ldloc.s  0xD
0x65a4  ldloc.s  0xE
0x65a6  call     instance object Microsoft.Crm.Application.WebServices.WorkflowWebService::GetInvokeSdkMessageParameterValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo input, class [System.Xml]System.Xml.XPath.XPathNavigator parameter)
0x65ab  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetPrimitiveExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, object)
0x65b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x65b5  br.s     loc_65CD
0x65b7  ldloc.1
0x65b8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x65bd  ldloc.s  0xD
0x65bf  ldloc.1
0x65c0  ldloc.s  0xD
0x65c2  ldnull
0x65c3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetPrimitiveExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, object)
0x65c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x65cd  ldloc.s  0xC
0x65cf  ldc.i4.1
0x65d0  add
0x65d1  stloc.s  0xC
0x65d3  ldloc.s  0xC
0x65d5  ldloc.s  0xB
0x65d7  ldlen
0x65d8  conv.i4
0x65d9  blt      loc_649A
0x65de  ldarg.0
0x65df  ldloc.0
0x65e0  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::ValidateInvokeSdkMessageStepOutputParameters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x65e5  ldarg.0
0x65e6  ldloc.0
0x65e7  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x65ec  stloc.s  0x13
0x65ee  leave.s  loc_65FB
0x65f0  stloc.s  0x14
0x65f2  ldarg.0
0x65f3  ldloc.s  0x14
0x65f5  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x65fa  throw
0x65fb  ldloc.s  0x13
0x65fd  ret
```
