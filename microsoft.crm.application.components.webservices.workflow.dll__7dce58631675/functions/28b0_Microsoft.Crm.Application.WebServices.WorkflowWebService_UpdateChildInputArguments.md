# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildInputArguments

- ea: `0x28b0`
- end: `0x2b3f`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateChildInputArguments`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x28b0`
- `0x76c0`
- `0x8090`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x2b0a`: `Invalid XML`
- `0x2a11`: `The argumentsXml contains an unexpected parameter`

## pseudocode

```c

```

## disassembly

```asm
0x28b0  ldarg.0
0x28b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x28b6  ldarg.3
0x28b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x28bc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x28c1  stloc.0
0x28c2  ldarg.0
0x28c3  ldloc.0
0x28c4  ldarg.s  4
0x28c6  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x28cb  ldloc.0
0x28cc  ldarg.1
0x28cd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x28d2  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep
0x28d7  stloc.1
0x28d8  ldloc.1
0x28d9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_ChildWorkflow()
0x28de  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression
0x28e3  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::get_Value()
0x28e8  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x28ed  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x28f2  unbox.any [mscorlib]System.Guid
0x28f7  stloc.2
0x28f8  ldarg.0
0x28f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x28fe  ldloc.2
0x28ff  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2904  stloc.3
0x2905  ldarg.2
0x2906  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x290b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x2910  ldstr    aParametersPara// "//parameters/parameter"
0x2915  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x291a  stloc.s  4
0x291c  ldloc.1
0x291d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Inputs()
0x2922  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Clear()
0x2927  ldloc.1
0x2928  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEffectiveChildInteractiveWorkflowInputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep childInteractiveWorkflowStep)
0x292d  stloc.s  5
0x292f  br       loc_2B1A
0x2934  ldloc.s  4
0x2936  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x293b  stloc.s  6
0x293d  ldloc.s  6
0x293f  ldstr    aName// "name"
0x2944  ldsfld   string [mscorlib]System.String::Empty
0x2949  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x294e  stloc.s  7
0x2950  ldloc.s  6
0x2952  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2957  stloc.s  8
0x2959  ldloc.s  7
0x295b  brfalse  loc_2B0A
0x2960  ldloc.s  8
0x2962  brfalse  loc_2B0A
0x2967  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x296c  stloc.s  9
0x296e  ldloc.s  9
0x2970  ldloc.s  7
0x2972  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x2977  ldloc.3
0x2978  ldloc.s  7
0x297a  ldc.i4.1
0x297b  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetVariableValue(string, bool)
0x2980  stloc.s  0xA
0x2982  ldloc.s  0xA
0x2984  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x2989  brfalse.s loc_29CA
0x298b  ldloc.s  0xA
0x298d  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x2992  stloc.s  0xF
0x2994  ldloc.s  9
0x2996  ldloc.s  0xF
0x2998  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x299d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>)
0x29a2  ldloc.s  9
0x29a4  ldloca.s 0xF
0x29a6  call     instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x29ab  callvirt instance string [mscorlib]System.Type::get_FullName()
0x29b0  call     class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetCrmTypeFromDotNetType(string)
0x29b5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x29ba  ldloc.s  9
0x29bc  ldloca.s 0xF
0x29be  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x29c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x29c8  br.s     loc_29F5
0x29ca  ldloc.s  9
0x29cc  ldloc.s  0xA
0x29ce  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x29d3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x29d8  call     class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetCrmTypeFromDotNetType(string)
0x29dd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x29e2  ldloc.s  9
0x29e4  ldloc.s  9
0x29e6  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x29eb  call     valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetWorkflowType(class [mscorlib]System.Type)
0x29f0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x29f5  ldloc.s  9
0x29f7  ldloc.s  7
0x29f9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x29fe  ldloc.s  9
0x2a00  ldc.i4.1
0x2a01  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x2a06  ldloc.s  5
0x2a08  ldloc.s  9
0x2a0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ContainsKey(var<u1>)
0x2a0f  brtrue.s loc_2A1C
0x2a11  ldstr    aTheArgumentsxm// "The argumentsXml contains an unexpected"...
0x2a16  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x2a1b  throw
0x2a1c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a21  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a26  stloc.s  0xB
0x2a28  ldnull
0x2a29  stloc.s  0xC
0x2a2b  ldloc.s  6
0x2a2d  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x2a32  ldstr    aSlugbody_0// "<slugbody>"
0x2a37  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2a3c  brfalse.s loc_2A59
0x2a3e  ldloc.s  0xB
0x2a40  ldloc.0
0x2a41  ldloc.s  9
0x2a43  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x2a48  ldloc.s  6
0x2a4a  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x2a4f  ldc.i4.0
0x2a50  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x2a55  stloc.s  0xC
0x2a57  br.s     loc_2ABD
0x2a59  ldloc.s  9
0x2a5b  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x2a60  ldc.i4.6
0x2a61  bne.un.s loc_2AA5
0x2a63  ldarg.0
0x2a64  ldloc.s  9
0x2a66  ldloc.s  6
0x2a68  call     instance object Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomParameterValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo input, class [System.Xml]System.Xml.XPath.XPathNavigator parameter)
0x2a6d  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x2a72  stloc.s  0x10
0x2a74  ldloc.s  0x10
0x2a76  brfalse.s loc_2ABD
0x2a78  ldloc.0
0x2a79  ldloc.0
0x2a7a  ldloc.s  0x10
0x2a7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x2a81  box      [mscorlib]System.Guid
0x2a86  ldc.i4.s 0xF
0x2a88  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x2a8d  ldc.i4.6
0x2a8e  ldloc.s  0x10
0x2a90  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x2a95  ldloc.s  0x10
0x2a97  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_name()
0x2a9c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x2aa1  stloc.s  0xC
0x2aa3  br.s     loc_2ABD
0x2aa5  ldloc.s  0xB
0x2aa7  ldloc.0
0x2aa8  ldloc.s  9
0x2aaa  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x2aaf  ldloc.s  6
0x2ab1  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x2ab6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x2abb  stloc.s  0xC
0x2abd  ldc.i4.0
0x2abe  stloc.s  0xD
0x2ac0  ldloc.s  0xC
0x2ac2  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x2ac7  stloc.s  0xE
0x2ac9  ldloc.s  0xE
0x2acb  brfalse.s loc_2AF1
0x2acd  ldloc.s  0xE
0x2acf  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x2ad4  ldloc.s  5
0x2ad6  ldloc.s  9
0x2ad8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x2add  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x2ae2  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x2ae7  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x2aec  brfalse.s loc_2AF1
0x2aee  ldc.i4.1
0x2aef  stloc.s  0xD
0x2af1  ldloc.s  0xD
0x2af3  brtrue.s loc_2B1A
0x2af5  ldloc.s  0xC
0x2af7  brfalse.s loc_2B1A
0x2af9  ldloc.1
0x2afa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Inputs()
0x2aff  ldloc.s  9
0x2b01  ldloc.s  0xC
0x2b03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x2b08  br.s     loc_2B1A
0x2b0a  ldstr    aInvalidXml// "Invalid XML"
0x2b0f  ldc.i4   0x80004005
0x2b14  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2b19  throw
0x2b1a  ldloc.s  4
0x2b1c  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x2b21  brtrue   loc_2934
0x2b26  ldarg.0
0x2b27  ldloc.0
0x2b28  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2b2d  stloc.s  0x11
0x2b2f  leave.s  loc_2B3C
0x2b31  stloc.s  0x12
0x2b33  ldarg.0
0x2b34  ldloc.s  0x12
0x2b36  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2b3b  throw
0x2b3c  ldloc.s  0x11
0x2b3e  ret
```
