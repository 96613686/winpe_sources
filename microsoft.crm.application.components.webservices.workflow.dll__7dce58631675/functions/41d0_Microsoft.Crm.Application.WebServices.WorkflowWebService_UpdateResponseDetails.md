# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails

- ea: `0x41d0`
- end: `0x4413`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateResponseDetails`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x40b0`

## callees

- `0x4040`
- `0x41d0`
- `0x44e0`
- `0x9230`

## string_xrefs

- `0x4292`: `Invalid XML`
- `0x4402`: `Invalid XML`
- `0x43bf`: `<IdentifierXml>`
- `0x43cb`: `</IdentifierXml>`

## pseudocode

```c

```

## disassembly

```asm
0x41d0  ldarg.2
0x41d1  ldstr    aResponseloggin// "responselogging"
0x41d6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x41db  stloc.0
0x41dc  ldarg.1
0x41dd  ldloc.0
0x41de  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x41e3  ldstr    a1// "1"
0x41e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41ed  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_LogResponse(bool)
0x41f2  ldarg.2
0x41f3  ldstr    aResponsetype// "responsetype"
0x41f8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x41fd  stloc.1
0x41fe  ldarg.1
0x41ff  ldloc.1
0x4200  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x4205  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x420a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x420f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseMetadataType(int32)
0x4214  ldarg.3
0x4215  brfalse  loc_4412
0x421a  ldarg.2
0x421b  ldstr    aDefaultvalue_0// "defaultValue"
0x4220  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4225  stloc.2
0x4226  ldloc.2
0x4227  brtrue.s loc_42A2
0x4229  ldarg.1
0x422a  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x422f  stloc.3
0x4230  ldloc.3
0x4231  switch   loc_425A, loc_4268, loc_424C, loc_4284, loc_4276
0x424a  br.s     loc_4292
0x424c  ldarg.2
0x424d  ldstr    aResponsetextde// "responseTextDefault2"
0x4252  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4257  stloc.2
0x4258  br.s     loc_42A2
0x425a  ldarg.2
0x425b  ldstr    aResponsetextde_0// "responseTextDefault0"
0x4260  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4265  stloc.2
0x4266  br.s     loc_42A2
0x4268  ldarg.2
0x4269  ldstr    aResponsetextde_1// "responseTextDefault1"
0x426e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4273  stloc.2
0x4274  br.s     loc_42A2
0x4276  ldarg.2
0x4277  ldstr    aResponsetextde_2// "responseTextDefault4"
0x427c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x4281  stloc.2
0x4282  br.s     loc_42A2
0x4284  ldarg.2
0x4285  ldstr    aResponsetextde_3// "responseTextDefault3"
0x428a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x428f  stloc.2
0x4290  br.s     loc_42A2
0x4292  ldstr    aInvalidXml// "Invalid XML"
0x4297  ldc.i4   0x80004005
0x429c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42a1  throw
0x42a2  ldloc.2
0x42a3  brfalse  loc_4402
0x42a8  ldloc.2
0x42a9  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x42ae  stloc.s  4
0x42b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x42b5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42ba  stloc.s  5
0x42bc  ldarg.1
0x42bd  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x42c2  ldc.i4.4
0x42c3  beq.s    loc_42D1
0x42c5  ldarg.1
0x42c6  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x42cb  ldc.i4.3
0x42cc  bne.un   loc_43E8
0x42d1  ldloc.2
0x42d2  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x42d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42dc  brtrue   loc_43E0
0x42e1  ldarg.0
0x42e2  ldloc.2
0x42e3  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::IsDateTimeSlug(class [System.Xml]System.Xml.XPath.XPathNavigator defaultValueNode)
0x42e8  brfalse.s loc_4328
0x42ea  ldloc.s  5
0x42ec  ldarg.s  4
0x42ee  ldc.i4.2
0x42ef  ldloc.s  4
0x42f1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x42f6  stloc.s  6
0x42f8  ldarg.1
0x42f9  ldarg.s  4
0x42fb  ldc.i4.s 0x10
0x42fd  ldc.i4.2
0x42fe  newarr   [mscorlib]System.Object
0x4303  dup
0x4304  ldc.i4.0
0x4305  ldarg.1
0x4306  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x430b  ldc.i4.4
0x430c  beq.s    loc_4311
0x430e  ldc.i4.0
0x430f  br.s     loc_4312
0x4311  ldc.i4.1
0x4312  box      [mscorlib]System.Boolean
0x4317  stelem.ref
0x4318  dup
0x4319  ldc.i4.1
0x431a  ldloc.s  6
0x431c  stelem.ref
0x431d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x4322  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_DefaultResponseValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4327  ret
0x4328  ldloc.2
0x4329  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x432e  call     bool [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsValidIsoDateTime(string)
0x4333  brfalse  loc_4412
0x4338  ldarg.0
0x4339  ldloc.2
0x433a  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x433f  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.WebServices.WorkflowWebService::ConvertToUTC(string timeString)
0x4344  stloc.s  7
0x4346  ldloca.s 0xA
0x4348  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x434e  ldloca.s 0xA
0x4350  ldarg.1
0x4351  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x4356  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x435b  ldloca.s 0xA
0x435d  ldarg.1
0x435e  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x4363  ldc.i4.3
0x4364  beq.s    loc_4369
0x4366  ldc.i4.4
0x4367  br.s     loc_436A
0x4369  ldc.i4.3
0x436a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x436f  ldloca.s 0xA
0x4371  ldc.i4.1
0x4372  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x4377  ldloca.s 0xA
0x4379  ldc.i4.0
0x437a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x437f  ldloca.s 0xA
0x4381  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x4386  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x438b  ldloca.s 0xA
0x438d  ldloc.s  7
0x438f  ldc.i4.1
0x4390  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime, valuetype [System.Xml]System.Xml.XmlDateTimeSerializationMode)
0x4395  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsString(string)
0x439a  ldloc.s  0xA
0x439c  stloc.s  8
0x439e  ldloc.s  8
0x43a0  box      [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x43a5  call     class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.TypeDescriptor::GetConverter(object)
0x43aa  ldloc.s  8
0x43ac  box      [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x43b1  callvirt instance string [System]System.ComponentModel.TypeConverter::ConvertToString(object)
0x43b6  stloc.s  9
0x43b8  ldarg.1
0x43b9  ldloc.s  5
0x43bb  ldarg.s  4
0x43bd  ldc.i4.s 0xE
0x43bf  ldstr    aIdentifierxml// "<IdentifierXml>"
0x43c4  ldloc.s  9
0x43c6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x43cb  ldstr    aIdentifierxml_0// "</IdentifierXml>"
0x43d0  call     string [mscorlib]System.String::Concat(string, string, string)
0x43d5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x43da  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_DefaultResponseValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x43df  ret
0x43e0  ldarg.1
0x43e1  ldnull
0x43e2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_DefaultResponseValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x43e7  ret
0x43e8  ldarg.1
0x43e9  ldloc.s  5
0x43eb  ldarg.s  4
0x43ed  ldc.i4.s 0xE
0x43ef  ldarg.0
0x43f0  ldloc.s  4
0x43f2  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::GetModifiedTextXmlWithEmptyPrimitive(string textXml)
0x43f7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x43fc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_DefaultResponseValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4401  ret
0x4402  ldstr    aInvalidXml// "Invalid XML"
0x4407  ldc.i4   0x80004005
0x440c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4411  throw
0x4412  ret
```
