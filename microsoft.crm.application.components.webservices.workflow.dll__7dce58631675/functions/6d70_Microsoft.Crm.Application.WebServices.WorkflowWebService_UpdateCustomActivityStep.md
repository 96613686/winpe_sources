# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStep

- ea: `0x6d70`
- end: `0x7032`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStep`
- size: `706`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x49c0`
- `0x6d70`
- `0x76c0`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x6dd8`: `column[@id="colConfiguration"]`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  ldarg.0
0x6d71  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6d76  ldarg.2
0x6d77  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6d7c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6d81  stloc.0
0x6d82  ldloc.0
0x6d83  ldarg.1
0x6d84  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6d89  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep
0x6d8e  stloc.1
0x6d8f  ldarg.0
0x6d90  ldloc.0
0x6d91  ldarg.s  4
0x6d93  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6d98  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6d9d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6da2  stloc.2
0x6da3  ldarg.3
0x6da4  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6da9  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x6dae  ldstr    aCondition_0// "//condition"
0x6db3  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x6db8  stloc.3
0x6db9  ldloc.3
0x6dba  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x6dbf  brfalse  loc_7019
0x6dc4  ldloc.3
0x6dc5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x6dca  dup
0x6dcb  ldstr    aColumnIdColact// "column[@id=\"colAction\"]"
0x6dd0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x6dd5  stloc.s  4
0x6dd7  dup
0x6dd8  ldstr    aColumnIdColcon// "column[@id=\"colConfiguration\"]"
0x6ddd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x6de2  stloc.s  5
0x6de4  ldstr    aColumnIdColpar// "column[@id=\"colParameter\"]"
0x6de9  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x6dee  stloc.s  6
0x6df0  ldloc.s  4
0x6df2  brfalse  loc_7019
0x6df7  ldloc.s  5
0x6df9  brfalse  loc_7019
0x6dfe  ldloc.s  6
0x6e00  brfalse  loc_7019
0x6e05  ldloc.s  6
0x6e07  ldstr    aValue// "value"
0x6e0c  ldsfld   string [mscorlib]System.String::Empty
0x6e11  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x6e16  stloc.s  7
0x6e18  ldloc.s  4
0x6e1a  ldstr    aValue// "value"
0x6e1f  ldsfld   string [mscorlib]System.String::Empty
0x6e24  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x6e29  stloc.s  8
0x6e2b  ldloc.s  5
0x6e2d  ldstr    aValue// "value"
0x6e32  ldsfld   string [mscorlib]System.String::Empty
0x6e37  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x6e3c  stloc.s  9
0x6e3e  ldloc.s  8
0x6e40  ldstr    aVersion// "version"
0x6e45  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6e4a  brfalse.s loc_6E79
0x6e4c  ldloc.s  7
0x6e4e  stloc.s  0xA
0x6e50  ldloc.1
0x6e51  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x6e56  ldloc.s  0xA
0x6e58  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_AssemblyVersion(string)
0x6e5d  ldloc.1
0x6e5e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x6e63  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e68  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_PluginTypeId(valuetype [mscorlib]System.Guid)
0x6e6d  ldarg.0
0x6e6e  ldloc.1
0x6e6f  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStepPrameters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep customActivityStep)
0x6e74  br       loc_7019
0x6e79  ldloc.s  8
0x6e7b  ldstr    aCustomactivity// "customActivity"
0x6e80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6e85  brfalse  loc_7019
0x6e8a  ldarg.0
0x6e8b  ldloc.1
0x6e8c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStepPrameters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep customActivityStep)
0x6e91  ldloc.s  9
0x6e93  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6e98  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x6e9d  stloc.s  0xB
0x6e9f  ldloc.1
0x6ea0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6ea5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Keys()
0x6eaa  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Count()
0x6eaf  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo
0x6eb4  stloc.s  0xC
0x6eb6  ldloc.1
0x6eb7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6ebc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Keys()
0x6ec1  ldloc.s  0xC
0x6ec3  ldc.i4.0
0x6ec4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::CopyTo(var<u1>[], !!T0)
0x6ec9  ldloc.s  0xC
0x6ecb  stloc.s  0xD
0x6ecd  ldc.i4.0
0x6ece  stloc.s  0xE
0x6ed0  br       loc_700E
0x6ed5  ldloc.s  0xD
0x6ed7  ldloc.s  0xE
0x6ed9  ldelem.ref
0x6eda  stloc.s  0xF
0x6edc  ldnull
0x6edd  stloc.s  0x10
0x6edf  ldloc.s  0xB
0x6ee1  ldstr    aParameter// "//parameter"
0x6ee6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x6eeb  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XPath.XPathNodeIterator::GetEnumerator()
0x6ef0  stloc.s  0x11
0x6ef2  br.s     loc_6F27
0x6ef4  ldloc.s  0x11
0x6ef6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6efb  castclass [System.Xml]System.Xml.XPath.XPathNavigator
0x6f00  stloc.s  0x12
0x6f02  ldloc.s  0x12
0x6f04  ldstr    aName// "name"
0x6f09  ldsfld   string [mscorlib]System.String::Empty
0x6f0e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x6f13  ldloc.s  0xF
0x6f15  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x6f1a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x6f1f  brfalse.s loc_6F27
0x6f21  ldloc.s  0x12
0x6f23  stloc.s  0x10
0x6f25  br.s     loc_6F30
0x6f27  ldloc.s  0x11
0x6f29  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6f2e  brtrue.s loc_6EF4
0x6f30  leave.s  loc_6F47
0x6f32  ldloc.s  0x11
0x6f34  isinst   [mscorlib]System.IDisposable
0x6f39  stloc.s  0x13
0x6f3b  ldloc.s  0x13
0x6f3d  brfalse.s loc_6F46
0x6f3f  ldloc.s  0x13
0x6f41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f46  endfinally
0x6f47  ldloc.s  0x10
0x6f49  brfalse.s loc_6FBE
0x6f4b  ldloc.s  0x10
0x6f4d  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x6f52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f57  brtrue.s loc_6FBE
0x6f59  ldloc.s  0x10
0x6f5b  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x6f60  ldstr    aSlugbody_0// "<slugbody>"
0x6f65  ldc.i4.5
0x6f66  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6f6b  brfalse.s loc_6FBE
0x6f6d  ldloc.2
0x6f6e  ldloc.0
0x6f6f  ldloc.1
0x6f70  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6f75  ldloc.s  0xF
0x6f77  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x6f7c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::get_Type()
0x6f81  ldloc.s  0x10
0x6f83  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x6f88  ldc.i4.0
0x6f89  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x6f8e  stloc.s  0x14
0x6f90  ldloc.s  0x14
0x6f92  brfalse.s loc_7008
0x6f94  ldloc.s  0x14
0x6f96  ldloc.1
0x6f97  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6f9c  ldloc.s  0xF
0x6f9e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x6fa3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::get_Type()
0x6fa8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::set_Type(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x6fad  ldloc.1
0x6fae  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6fb3  ldloc.s  0xF
0x6fb5  ldloc.s  0x14
0x6fb7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x6fbc  br.s     loc_7008
0x6fbe  ldloc.s  0x10
0x6fc0  brfalse.s loc_6FF2
0x6fc2  ldloc.s  0x10
0x6fc4  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6fc9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6fce  ldc.i4.0
0x6fcf  ble.s    loc_6FF2
0x6fd1  ldloc.1
0x6fd2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6fd7  ldloc.s  0xF
0x6fd9  ldloc.1
0x6fda  ldloc.s  0xF
0x6fdc  ldarg.0
0x6fdd  ldloc.s  0xF
0x6fdf  ldloc.s  0x10
0x6fe1  call     instance object Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomParameterValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo input, class [System.Xml]System.Xml.XPath.XPathNavigator parameter)
0x6fe6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetPrimitiveExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, object)
0x6feb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x6ff0  br.s     loc_7008
0x6ff2  ldloc.1
0x6ff3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x6ff8  ldloc.s  0xF
0x6ffa  ldloc.1
0x6ffb  ldloc.s  0xF
0x6ffd  ldnull
0x6ffe  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetPrimitiveExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, object)
0x7003  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x7008  ldloc.s  0xE
0x700a  ldc.i4.1
0x700b  add
0x700c  stloc.s  0xE
0x700e  ldloc.s  0xE
0x7010  ldloc.s  0xD
0x7012  ldlen
0x7013  conv.i4
0x7014  blt      loc_6ED5
0x7019  ldarg.0
0x701a  ldloc.0
0x701b  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x7020  stloc.s  0x15
0x7022  leave.s  loc_702F
0x7024  stloc.s  0x16
0x7026  ldarg.0
0x7027  ldloc.s  0x16
0x7029  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x702e  throw
0x702f  ldloc.s  0x15
0x7031  ret
```
