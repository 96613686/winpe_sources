# Microsoft.Crm.Application.WebServices.WorkflowWebService::CreateVariable

- ea: `0x2d30`
- end: `0x2fc4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CreateVariable`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x2d30`
- `0x2fd0`
- `0x8b90`
- `0x8f00`
- `0x9230`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldarg.0
0x2d31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2d36  ldarg.1
0x2d37  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2d3c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2d41  stloc.0
0x2d42  ldarg.0
0x2d43  ldloc.0
0x2d44  ldarg.3
0x2d45  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x2d4a  ldarg.2
0x2d4b  ldc.i4.1
0x2d4c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string, bool)
0x2d51  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x2d56  ldstr    aVariable// "//Variable"
0x2d5b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x2d60  stloc.1
0x2d61  ldloc.1
0x2d62  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x2d67  brfalse  loc_2FAB
0x2d6c  ldloc.1
0x2d6d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x2d72  stloc.2
0x2d73  ldloc.2
0x2d74  ldstr    aVariabletype// "VariableType"
0x2d79  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2d7e  stloc.3
0x2d7f  ldloc.2
0x2d80  ldstr    aVariablename// "VariableName"
0x2d85  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2d8a  stloc.s  4
0x2d8c  ldloc.2
0x2d8d  ldstr    aVariabledataty// "VariableDataType"
0x2d92  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2d97  stloc.s  5
0x2d99  ldloc.2
0x2d9a  ldstr    aDefaultvalue// "DefaultValue"
0x2d9f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2da4  stloc.s  6
0x2da6  ldloc.2
0x2da7  ldstr    aMetadatabound// "MetadataBound"
0x2dac  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2db1  stloc.s  7
0x2db3  ldloc.3
0x2db4  brfalse.s loc_2DC5
0x2db6  ldloc.s  4
0x2db8  brfalse.s loc_2DC5
0x2dba  ldloc.s  5
0x2dbc  brfalse.s loc_2DC5
0x2dbe  ldloc.s  7
0x2dc0  ldnull
0x2dc1  cgt.un
0x2dc3  br.s     loc_2DC6
0x2dc5  ldc.i4.0
0x2dc6  ldstr    aInvalidInput// "Invalid input"
0x2dcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2dd0  ldloc.s  5
0x2dd2  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2dd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ddc  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x2de1  stloc.s  8
0x2de3  ldloc.3
0x2de4  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2de9  ldc.i4.1
0x2dea  stloc.s  0xA
0x2dec  ldloca.s 0xA
0x2dee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2df3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2df8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dfd  stloc.s  9
0x2dff  ldloc.s  7
0x2e01  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x2e06  brfalse  loc_2ED2
0x2e0b  ldloc.s  8
0x2e0d  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::IsSupportedType(int32)
0x2e12  brtrue.s loc_2E24
0x2e14  ldstr    aUnsupportedVar// "Unsupported variable type"
0x2e19  ldstr    aType// "type"
0x2e1e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x2e23  throw
0x2e24  ldloc.2
0x2e25  ldstr    aMetadatabindin// "MetadataBinding"
0x2e2a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2e2f  dup
0x2e30  ldstr    aEntity_0// "Entity"
0x2e35  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2e3a  stloc.s  0xB
0x2e3c  dup
0x2e3d  ldstr    aAttribute// "Attribute"
0x2e42  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x2e47  stloc.s  0xC
0x2e49  brfalse.s loc_2E56
0x2e4b  ldloc.s  0xB
0x2e4d  brfalse.s loc_2E56
0x2e4f  ldloc.s  0xC
0x2e51  ldnull
0x2e52  cgt.un
0x2e54  br.s     loc_2E57
0x2e56  ldc.i4.0
0x2e57  ldstr    aInvalidInput_0// "Invalid Input"
0x2e5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2e61  ldloca.s 0xE
0x2e63  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x2e69  ldloca.s 0xE
0x2e6b  ldloc.s  8
0x2e6d  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x2e72  ldloca.s 0xE
0x2e74  ldloc.s  4
0x2e76  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2e7b  ldarg.0
0x2e7c  ldloc.s  8
0x2e7e  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAttributeType(int32 dataType)
0x2e83  ldloc.s  9
0x2e85  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x2e8a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x2e8f  ldloca.s 0xE
0x2e91  ldloc.s  7
0x2e93  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x2e98  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x2e9d  ldloca.s 0xE
0x2e9f  ldloc.s  0xB
0x2ea1  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2ea6  ldloc.s  0xC
0x2ea8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2ead  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::.ctor(string, string)
0x2eb2  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x2eb7  ldloca.s 0xE
0x2eb9  ldc.i4.0
0x2eba  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x2ebf  ldloc.s  0xE
0x2ec1  stloc.s  0xD
0x2ec3  ldloc.0
0x2ec4  ldloc.s  0xD
0x2ec6  ldloc.s  9
0x2ec8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x2ecd  br       loc_2FAB
0x2ed2  ldloc.s  6
0x2ed4  ldnull
0x2ed5  cgt.un
0x2ed7  ldstr    aInvalidInput// "Invalid input"
0x2edc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2ee1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x2ee6  ldloc.s  8
0x2ee8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::ContainsKey(var<u1>)
0x2eed  brtrue.s loc_2EFF
0x2eef  ldstr    aUnsupportedVar// "Unsupported variable type"
0x2ef4  ldstr    aType// "type"
0x2ef9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x2efe  throw
0x2eff  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x2f04  ldloc.s  8
0x2f06  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::get_Item(void)
0x2f0b  stloc.s  0xF
0x2f0d  ldloc.s  4
0x2f0f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2f14  ldloc.s  0xF
0x2f16  ldloc.s  9
0x2f18  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x2f1d  stloc.s  0x10
0x2f1f  ldloc.s  0xF
0x2f21  ldtoken  [mscorlib]System.DateTime
0x2f26  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f2b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f30  brfalse.s loc_2F96
0x2f32  ldarg.0
0x2f33  ldloc.s  6
0x2f35  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x2f3a  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.WebServices.WorkflowWebService::ConvertToUTC(string timeString)
0x2f3f  stloc.s  0x11
0x2f41  ldloca.s 0xE
0x2f43  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x2f49  ldloca.s 0xE
0x2f4b  ldloc.s  0x10
0x2f4d  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x2f52  ldloca.s 0xE
0x2f54  ldloc.s  8
0x2f56  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x2f5b  ldloca.s 0xE
0x2f5d  ldc.i4.1
0x2f5e  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x2f63  ldloca.s 0xE
0x2f65  ldc.i4.0
0x2f66  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x2f6b  ldloca.s 0xE
0x2f6d  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x2f72  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x2f77  ldloca.s 0xE
0x2f79  ldloc.s  0x11
0x2f7b  ldc.i4.1
0x2f7c  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime, valuetype [System.Xml]System.Xml.XmlDateTimeSerializationMode)
0x2f81  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsString(string)
0x2f86  ldloc.s  0xE
0x2f88  stloc.s  0x12
0x2f8a  ldloc.0
0x2f8b  ldloc.s  0x12
0x2f8d  ldloc.s  9
0x2f8f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x2f94  br.s     loc_2FAB
0x2f96  ldloc.0
0x2f97  ldloc.s  0x10
0x2f99  ldloc.s  0xF
0x2f9b  ldloc.s  6
0x2f9d  ldloc.s  0xF
0x2f9f  callvirt instance object [System.Xml]System.Xml.XPath.XPathItem::ValueAs(class [mscorlib]System.Type)
0x2fa4  ldloc.s  9
0x2fa6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x2fab  ldarg.0
0x2fac  ldloc.0
0x2fad  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2fb2  stloc.s  0x13
0x2fb4  leave.s  loc_2FC1
0x2fb6  stloc.s  0x14
0x2fb8  ldarg.0
0x2fb9  ldloc.s  0x14
0x2fbb  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2fc0  throw
0x2fc1  ldloc.s  0x13
0x2fc3  ret
```
