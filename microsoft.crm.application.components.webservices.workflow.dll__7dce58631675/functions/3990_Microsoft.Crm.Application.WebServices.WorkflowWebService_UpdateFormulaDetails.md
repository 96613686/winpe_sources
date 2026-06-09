# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateFormulaDetails

- ea: `0x3990`
- end: `0x3c85`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateFormulaDetails`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x34c0`

## callees

- `0x3990`
- `0x3c90`
- `0x3cb0`

## pseudocode

```c

```

## disassembly

```asm
0x3990  ldarg.2
0x3991  ldstr    aVariabletype// "VariableType"
0x3996  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x399b  stloc.0
0x399c  ldarg.2
0x399d  ldstr    aVariabledataty// "VariableDataType"
0x39a2  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x39a7  stloc.1
0x39a8  ldarg.2
0x39a9  ldstr    aVariablename// "VariableName"
0x39ae  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x39b3  stloc.2
0x39b4  ldarg.2
0x39b5  ldstr    aVariablevalue// "VariableValue"
0x39ba  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x39bf  stloc.3
0x39c0  ldarg.0
0x39c1  ldarg.1
0x39c2  ldloc.0
0x39c3  ldloc.2
0x39c4  ldloc.1
0x39c5  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetVariableProperties(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep assignStep, class [System.Xml]System.Xml.XPath.XPathNavigator typeNode, class [System.Xml]System.Xml.XPath.XPathNavigator nameNode, class [System.Xml]System.Xml.XPath.XPathNavigator dataTypeNode)
0x39ca  ldloc.3
0x39cb  ldstr    aSlugbody_2// "//slugbody"
0x39d0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x39d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39da  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x39df  stloc.s  4
0x39e1  ldnull
0x39e2  cgt.un
0x39e4  stloc.s  5
0x39e6  ldloc.s  5
0x39e8  brtrue.s loc_39FA
0x39ea  ldloc.3
0x39eb  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x39f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x39f5  brtrue   loc_3C84
0x39fa  ldarg.1
0x39fb  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_DataType()
0x3a00  ldtoken  [mscorlib]System.Int32
0x3a05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a0a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3a0f  brfalse.s loc_3A41
0x3a11  ldloc.3
0x3a12  ldstr    aVariablevaluei// "variableValueInteger"
0x3a17  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3a1c  stloc.s  6
0x3a1e  ldarg.1
0x3a1f  ldloc.s  4
0x3a21  ldarg.3
0x3a22  ldc.i4.5
0x3a23  ldloc.s  5
0x3a25  brtrue.s loc_3A2F
0x3a27  ldloc.3
0x3a28  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3a2d  br.s     loc_3A36
0x3a2f  ldloc.s  6
0x3a31  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3a36  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3a3b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3a40  ret
0x3a41  ldarg.1
0x3a42  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_DataType()
0x3a47  ldtoken  [mscorlib]System.String
0x3a4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a51  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3a56  brfalse.s loc_3AA3
0x3a58  ldloc.3
0x3a59  ldstr    aVariablevaluet// "variableValueText"
0x3a5e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3a63  stloc.s  7
0x3a65  ldarg.1
0x3a66  ldloc.s  4
0x3a68  ldarg.3
0x3a69  ldc.i4.s 0xE
0x3a6b  ldloc.s  5
0x3a6d  brtrue.s loc_3A77
0x3a6f  ldloc.3
0x3a70  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3a75  br.s     loc_3A7E
0x3a77  ldloc.s  7
0x3a79  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3a7e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3a83  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3a88  ldarg.1
0x3a89  ldarg.0
0x3a8a  ldarg.3
0x3a8b  ldarg.1
0x3a8c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_ValueExpression()
0x3a91  ldsfld   string [mscorlib]System.String::Empty
0x3a96  ldc.i4.s 0xE
0x3a98  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatPrimitiveExpressionForClearOperator(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase valueExpression, object value, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType type)
0x3a9d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3aa2  ret
0x3aa3  ldarg.1
0x3aa4  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_DataType()
0x3aa9  ldtoken  [mscorlib]System.Double
0x3aae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ab3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3ab8  brfalse.s loc_3AEA
0x3aba  ldloc.3
0x3abb  ldstr    aVariablevaluef// "variableValueFloat"
0x3ac0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3ac5  stloc.s  8
0x3ac7  ldarg.1
0x3ac8  ldloc.s  4
0x3aca  ldarg.3
0x3acb  ldc.i4.4
0x3acc  ldloc.s  5
0x3ace  brtrue.s loc_3AD8
0x3ad0  ldloc.3
0x3ad1  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3ad6  br.s     loc_3ADF
0x3ad8  ldloc.s  8
0x3ada  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3adf  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3ae4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3ae9  ret
0x3aea  ldarg.1
0x3aeb  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_DataType()
0x3af0  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x3af5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3afa  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3aff  brfalse  loc_3BF2
0x3b04  ldloc.3
0x3b05  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3b0a  ldstr    aSlugbody_0// "<slugbody>"
0x3b0f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x3b14  ldloc.3
0x3b15  ldstr    aVariablevaluel// "variableValueLookup"
0x3b1a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3b1f  stloc.s  9
0x3b21  brfalse.s loc_3B3A
0x3b23  ldarg.1
0x3b24  ldloc.s  4
0x3b26  ldarg.3
0x3b27  ldc.i4.6
0x3b28  ldloc.s  9
0x3b2a  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3b2f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3b34  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3b39  ret
0x3b3a  ldloc.3
0x3b3b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3b40  ldc.i4.1
0x3b41  newarr   [mscorlib]System.Char
0x3b46  dup
0x3b47  ldc.i4.0
0x3b48  ldc.i4.s 0x3B
0x3b4a  stelem.i2
0x3b4b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3b50  stloc.s  0xA
0x3b52  ldloca.s 0xB
0x3b54  ldloc.s  0xA
0x3b56  ldc.i4.0
0x3b57  ldelem.ref
0x3b58  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3b5d  ldloc.s  0xA
0x3b5f  ldc.i4.1
0x3b60  ldelem.ref
0x3b61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b66  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3b6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3b70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3b75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3b7a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b7f  stloc.s  0xC
0x3b81  ldloc.s  0xC
0x3b83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x3b88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x3b8d  stloc.s  0xD
0x3b8f  ldloc.s  0xC
0x3b91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x3b96  ldloc.s  0xB
0x3b98  ldc.i4.1
0x3b99  newarr   [mscorlib]System.String
0x3b9e  dup
0x3b9f  ldc.i4.0
0x3ba0  ldloc.s  0xD
0x3ba2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x3ba7  stelem.ref
0x3ba8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bb2  ldsfld   string [mscorlib]System.String::Empty
0x3bb7  stloc.s  0xE
0x3bb9  ldloc.s  0xD
0x3bbb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x3bc0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3bc5  castclass [mscorlib]System.String
0x3bca  stloc.s  0xE
0x3bcc  ldarg.1
0x3bcd  ldarg.3
0x3bce  ldarg.3
0x3bcf  ldloc.s  0xB
0x3bd1  box      [mscorlib]System.Guid
0x3bd6  ldc.i4.s 0xF
0x3bd8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x3bdd  ldc.i4.6
0x3bde  ldloc.s  0xC
0x3be0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x3be5  ldloc.s  0xE
0x3be7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x3bec  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3bf1  ret
0x3bf2  ldarg.1
0x3bf3  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_DataType()
0x3bf8  ldtoken  [mscorlib]System.DateTime
0x3bfd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c02  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c07  brfalse.s loc_3C84
0x3c09  ldloc.1
0x3c0a  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x3c0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c14  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3c19  stloc.s  0xF
0x3c1b  ldloc.s  0xF
0x3c1d  ldc.i4.4
0x3c1e  bne.un.s loc_3C50
0x3c20  ldloc.3
0x3c21  ldstr    aVariablevalued// "variableValueDateOnly"
0x3c26  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3c2b  stloc.s  0x10
0x3c2d  ldarg.1
0x3c2e  ldloc.s  4
0x3c30  ldarg.3
0x3c31  ldc.i4.2
0x3c32  ldloc.s  5
0x3c34  brtrue.s loc_3C3E
0x3c36  ldloc.3
0x3c37  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3c3c  br.s     loc_3C45
0x3c3e  ldloc.s  0x10
0x3c40  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3c45  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3c4a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3c4f  ret
0x3c50  ldloc.s  0xF
0x3c52  ldc.i4.3
0x3c53  bne.un.s loc_3C84
0x3c55  ldloc.3
0x3c56  ldstr    aVariablevalued_0// "variableValueDateTime"
0x3c5b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3c60  stloc.s  0x11
0x3c62  ldarg.1
0x3c63  ldloc.s  4
0x3c65  ldarg.3
0x3c66  ldc.i4.2
0x3c67  ldloc.s  5
0x3c69  brtrue.s loc_3C73
0x3c6b  ldloc.3
0x3c6c  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3c71  br.s     loc_3C7A
0x3c73  ldloc.s  0x11
0x3c75  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3c7a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3c7f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3c84  ret
```
