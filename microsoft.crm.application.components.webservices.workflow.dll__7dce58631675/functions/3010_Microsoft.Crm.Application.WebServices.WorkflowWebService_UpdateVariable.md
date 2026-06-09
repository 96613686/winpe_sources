# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateVariable

- ea: `0x3010`
- end: `0x33b2`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateVariable`
- size: `930`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x2fd0`
- `0x3010`
- `0x8b90`
- `0x8f00`
- `0x9230`

## pseudocode

```c

```

## disassembly

```asm
0x3010  ldarg.3
0x3011  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3016  ldc.i4.0
0x3017  ceq
0x3019  ldstr    aVariableIdIsRe// "variable id is required"
0x301e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3023  ldarg.0
0x3024  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3029  ldarg.1
0x302a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x302f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3034  stloc.0
0x3035  ldarg.0
0x3036  ldloc.0
0x3037  ldarg.s  4
0x3039  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x303e  ldarg.2
0x303f  ldc.i4.1
0x3040  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string, bool)
0x3045  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x304a  ldstr    aVariable// "//Variable"
0x304f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x3054  stloc.1
0x3055  ldloc.1
0x3056  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x305b  brfalse  loc_3399
0x3060  ldloc.1
0x3061  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x3066  stloc.2
0x3067  ldloc.2
0x3068  ldstr    aVariabletype// "VariableType"
0x306d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3072  stloc.3
0x3073  ldloc.2
0x3074  ldstr    aVariablename// "VariableName"
0x3079  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x307e  stloc.s  4
0x3080  ldloc.2
0x3081  ldstr    aVariabledataty// "VariableDataType"
0x3086  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x308b  stloc.s  5
0x308d  ldloc.2
0x308e  ldstr    aDefaultvalue// "DefaultValue"
0x3093  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3098  stloc.s  6
0x309a  ldloc.2
0x309b  ldstr    aMetadatabound// "MetadataBound"
0x30a0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x30a5  stloc.s  7
0x30a7  ldloc.3
0x30a8  brfalse.s loc_30B9
0x30aa  ldloc.s  4
0x30ac  brfalse.s loc_30B9
0x30ae  ldloc.s  5
0x30b0  brfalse.s loc_30B9
0x30b2  ldloc.s  7
0x30b4  ldnull
0x30b5  cgt.un
0x30b7  br.s     loc_30BA
0x30b9  ldc.i4.0
0x30ba  ldstr    aInvalidInput// "Invalid input"
0x30bf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x30c4  ldloc.s  5
0x30c6  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30d0  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x30d5  stloc.s  8
0x30d7  ldloc.3
0x30d8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30dd  ldc.i4.1
0x30de  stloc.s  0xB
0x30e0  ldloca.s 0xB
0x30e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30e7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x30ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x30f1  stloc.s  9
0x30f3  ldarg.3
0x30f4  ldstr    aUiscriptInput// "UIScript_Input_"
0x30f9  ldc.i4.4
0x30fa  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x30ff  stloc.s  0xA
0x3101  ldloc.s  7
0x3103  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x3108  brfalse  loc_3226
0x310d  ldloc.s  8
0x310f  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::IsSupportedType(int32)
0x3114  brtrue.s loc_3126
0x3116  ldstr    aUnsupportedVar// "Unsupported variable type"
0x311b  ldstr    aType// "type"
0x3120  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x3125  throw
0x3126  ldloc.s  4
0x3128  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x312d  ldarg.0
0x312e  ldloc.s  8
0x3130  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAttributeType(int32 dataType)
0x3135  ldloc.s  9
0x3137  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x313c  stloc.s  0xC
0x313e  ldloc.2
0x313f  ldstr    aMetadatabindin// "MetadataBinding"
0x3144  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3149  dup
0x314a  ldstr    aEntity_0// "Entity"
0x314f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3154  stloc.s  0xD
0x3156  dup
0x3157  ldstr    aAttribute// "Attribute"
0x315c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3161  stloc.s  0xE
0x3163  brfalse.s loc_3170
0x3165  ldloc.s  0xD
0x3167  brfalse.s loc_3170
0x3169  ldloc.s  0xE
0x316b  ldnull
0x316c  cgt.un
0x316e  br.s     loc_3171
0x3170  ldc.i4.0
0x3171  ldstr    aInvalidInput_0// "Invalid Input"
0x3176  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x317b  ldloca.s 0x10
0x317d  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x3183  ldloca.s 0x10
0x3185  ldloc.s  8
0x3187  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x318c  ldloca.s 0x10
0x318e  ldloc.s  4
0x3190  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3195  ldarg.0
0x3196  ldloc.s  8
0x3198  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAttributeType(int32 dataType)
0x319d  ldloc.s  9
0x319f  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x31a4  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x31a9  ldloca.s 0x10
0x31ab  ldloc.s  7
0x31ad  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x31b2  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x31b7  ldloca.s 0x10
0x31b9  ldloc.s  0xD
0x31bb  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x31c0  ldloc.s  0xE
0x31c2  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x31c7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::.ctor(string, string)
0x31cc  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x31d1  ldloca.s 0x10
0x31d3  ldc.i4.0
0x31d4  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x31d9  ldloc.s  0x10
0x31db  stloc.s  0xF
0x31dd  ldloc.s  9
0x31df  ldloc.s  0xA
0x31e1  bne.un.s loc_31FC
0x31e3  ldarg.3
0x31e4  ldloc.s  0xC
0x31e6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x31eb  brfalse.s loc_31FC
0x31ed  ldloc.0
0x31ee  ldloc.s  0xF
0x31f0  ldloc.s  0xA
0x31f2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x31f7  br       loc_3399
0x31fc  ldloc.0
0x31fd  ldarg.3
0x31fe  ldloc.s  0xA
0x3200  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::RemoveVariable(string, bool)
0x3205  ldloc.0
0x3206  ldloc.s  0xF
0x3208  ldloc.s  9
0x320a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x320f  ldarg.3
0x3210  ldloc.s  0xC
0x3212  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::.ctor(string, string)
0x3217  stloc.s  0x11
0x3219  ldloc.0
0x321a  ldloc.s  0x11
0x321c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::Apply(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase)
0x3221  br       loc_3399
0x3226  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x322b  ldloc.s  8
0x322d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::get_Item(void)
0x3232  stloc.s  0x12
0x3234  ldloc.s  4
0x3236  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x323b  ldloc.s  0x12
0x323d  ldloc.s  9
0x323f  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x3244  stloc.s  0x13
0x3246  ldloc.s  9
0x3248  ldloc.s  0xA
0x324a  bne.un   loc_32EF
0x324f  ldarg.3
0x3250  ldloc.s  0x13
0x3252  callvirt instance bool [mscorlib]System.String::Equals(string)
0x3257  brfalse  loc_32EF
0x325c  ldloc.s  0x12
0x325e  ldtoken  [mscorlib]System.DateTime
0x3263  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3268  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x326d  brfalse.s loc_32D6
0x326f  ldarg.0
0x3270  ldloc.s  6
0x3272  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x3277  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.WebServices.WorkflowWebService::ConvertToUTC(string timeString)
0x327c  stloc.s  0x14
0x327e  ldloca.s 0x10
0x3280  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x3286  ldloca.s 0x10
0x3288  ldloc.s  0x13
0x328a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x328f  ldloca.s 0x10
0x3291  ldloc.s  8
0x3293  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x3298  ldloca.s 0x10
0x329a  ldc.i4.1
0x329b  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x32a0  ldloca.s 0x10
0x32a2  ldc.i4.0
0x32a3  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x32a8  ldloca.s 0x10
0x32aa  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x32af  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x32b4  ldloca.s 0x10
0x32b6  ldloc.s  0x14
0x32b8  ldc.i4.1
0x32b9  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime, valuetype [System.Xml]System.Xml.XmlDateTimeSerializationMode)
0x32be  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsString(string)
0x32c3  ldloc.s  0x10
0x32c5  stloc.s  0x15
0x32c7  ldloc.0
0x32c8  ldloc.s  0x15
0x32ca  ldloc.s  0xA
0x32cc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x32d1  br       loc_3399
0x32d6  ldloc.0
0x32d7  ldarg.3
0x32d8  ldloc.s  0x12
0x32da  ldloc.s  6
0x32dc  ldloc.s  0x12
0x32de  callvirt instance object [System.Xml]System.Xml.XPath.XPathItem::ValueAs(class [mscorlib]System.Type)
0x32e3  ldloc.s  0xA
0x32e5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateVariable(string, class [mscorlib]System.Type, object, bool)
0x32ea  br       loc_3399
0x32ef  ldloc.0
0x32f0  ldarg.3
0x32f1  ldloc.s  0xA
0x32f3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::RemoveVariable(string, bool)
0x32f8  ldloc.s  0x12
0x32fa  ldtoken  [mscorlib]System.DateTime
0x32ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3304  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3309  brfalse.s loc_3372
0x330b  ldloca.s 0x10
0x330d  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x3313  ldloca.s 0x10
0x3315  ldloc.s  0x13
0x3317  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x331c  ldloca.s 0x10
0x331e  ldloc.s  8
0x3320  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x3325  ldloca.s 0x10
0x3327  ldc.i4.1
0x3328  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x332d  ldloca.s 0x10
0x332f  ldc.i4.0
0x3330  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x3335  ldloca.s 0x10
0x3337  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x333c  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x3341  ldloca.s 0x10
0x3343  ldloc.s  6
0x3345  callvirt instance valuetype [mscorlib]System.DateTime [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsDateTime()
0x334a  box      [mscorlib]System.DateTime
0x334f  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Value(object)
0x3354  ldloca.s 0x10
0x3356  ldloc.s  6
0x3358  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x335d  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsString(string)
0x3362  ldloc.s  0x10
0x3364  stloc.s  0x17
0x3366  ldloc.0
0x3367  ldloc.s  0x17
0x3369  ldloc.s  9
0x336b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x3370  br.s     loc_3387
0x3372  ldloc.0
0x3373  ldloc.s  0x13
0x3375  ldloc.s  0x12
0x3377  ldloc.s  6
0x3379  ldloc.s  0x12
0x337b  callvirt instance object [System.Xml]System.Xml.XPath.XPathItem::ValueAs(class [mscorlib]System.Type)
0x3380  ldloc.s  9
0x3382  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x3387  ldarg.3
0x3388  ldloc.s  0x13
0x338a  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::.ctor(string, string)
0x338f  stloc.s  0x16
0x3391  ldloc.0
0x3392  ldloc.s  0x16
0x3394  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::Apply(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase)
  ... truncated ...
```
