# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateArgumentDetails

- ea: `0x35d0`
- end: `0x3905`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateArgumentDetails`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x34c0`

## callees

- `0x35d0`
- `0x3c90`
- `0x9250`

## pseudocode

```c

```

## disassembly

```asm
0x35d0  ldarg.2
0x35d1  ldstr    aArgumentname// "ArgumentName"
0x35d6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x35db  stloc.0
0x35dc  ldarg.2
0x35dd  ldstr    aArgumentvalue// "ArgumentValue"
0x35e2  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x35e7  stloc.1
0x35e8  ldloc.1
0x35e9  ldstr    aSlugbody_2// "//slugbody"
0x35ee  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x35f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x35f8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x35fd  stloc.2
0x35fe  ldnull
0x35ff  cgt.un
0x3601  stloc.3
0x3602  ldarg.1
0x3603  ldloc.0
0x3604  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3609  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ArgumentName(string)
0x360e  ldloc.3
0x360f  brtrue.s loc_3621
0x3611  ldloc.1
0x3612  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x3617  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x361c  brtrue   loc_3904
0x3621  ldnull
0x3622  stloc.s  4
0x3624  ldarg.3
0x3625  ldarg.1
0x3626  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::get_ArgumentName()
0x362b  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetArgumentWorkflowAttributeType(string)
0x3630  stloc.s  5
0x3632  ldloc.s  5
0x3634  switch   loc_3728, loc_3904, loc_37B8, loc_3758, loc_36F8, loc_36C8, loc_3904, loc_3788, loc_3904, loc_3904, loc_37E8, loc_3904, loc_3904, loc_3904, loc_367E, loc_3904, loc_3818
0x367d  ret
0x367e  ldarg.0
0x367f  ldloc.1
0x3680  ldstr    aArgumentvaluet// "argumentValueText"
0x3685  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x368a  stloc.s  4
0x368c  ldarg.1
0x368d  ldloc.2
0x368e  ldarg.3
0x368f  ldloc.s  5
0x3691  ldloc.3
0x3692  brtrue.s loc_369C
0x3694  ldloc.1
0x3695  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x369a  br.s     loc_36A3
0x369c  ldloc.s  4
0x369e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x36a3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x36a8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x36ad  ldarg.1
0x36ae  ldarg.0
0x36af  ldarg.3
0x36b0  ldarg.1
0x36b1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::get_ValueExpression()
0x36b6  ldsfld   string [mscorlib]System.String::Empty
0x36bb  ldc.i4.s 0xE
0x36bd  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatPrimitiveExpressionForClearOperator(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase valueExpression, object value, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType type)
0x36c2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x36c7  ret
0x36c8  ldarg.0
0x36c9  ldloc.1
0x36ca  ldstr    aArgumentvaluei// "argumentValueInteger"
0x36cf  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x36d4  stloc.s  4
0x36d6  ldarg.1
0x36d7  ldloc.2
0x36d8  ldarg.3
0x36d9  ldloc.s  5
0x36db  ldloc.3
0x36dc  brtrue.s loc_36E6
0x36de  ldloc.1
0x36df  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x36e4  br.s     loc_36ED
0x36e6  ldloc.s  4
0x36e8  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x36ed  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x36f2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x36f7  ret
0x36f8  ldarg.0
0x36f9  ldloc.1
0x36fa  ldstr    aArgumentvaluef// "argumentValueFloat"
0x36ff  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x3704  stloc.s  4
0x3706  ldarg.1
0x3707  ldloc.2
0x3708  ldarg.3
0x3709  ldloc.s  5
0x370b  ldloc.3
0x370c  brtrue.s loc_3716
0x370e  ldloc.1
0x370f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3714  br.s     loc_371D
0x3716  ldloc.s  4
0x3718  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x371d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3722  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3727  ret
0x3728  ldarg.0
0x3729  ldloc.1
0x372a  ldstr    aArgumentvalueb// "argumentValueBoolean"
0x372f  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x3734  stloc.s  4
0x3736  ldarg.1
0x3737  ldloc.2
0x3738  ldarg.3
0x3739  ldloc.s  5
0x373b  ldloc.3
0x373c  brtrue.s loc_3746
0x373e  ldloc.1
0x373f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3744  br.s     loc_374D
0x3746  ldloc.s  4
0x3748  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x374d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3752  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3757  ret
0x3758  ldarg.0
0x3759  ldloc.1
0x375a  ldstr    aArgumentvalued// "argumentValueDecimal"
0x375f  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x3764  stloc.s  4
0x3766  ldarg.1
0x3767  ldloc.2
0x3768  ldarg.3
0x3769  ldloc.s  5
0x376b  ldloc.3
0x376c  brtrue.s loc_3776
0x376e  ldloc.1
0x376f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3774  br.s     loc_377D
0x3776  ldloc.s  4
0x3778  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x377d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3782  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3787  ret
0x3788  ldarg.0
0x3789  ldloc.1
0x378a  ldstr    aArgumentvaluem// "argumentValueMoney"
0x378f  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x3794  stloc.s  4
0x3796  ldarg.1
0x3797  ldloc.2
0x3798  ldarg.3
0x3799  ldloc.s  5
0x379b  ldloc.3
0x379c  brtrue.s loc_37A6
0x379e  ldloc.1
0x379f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x37a4  br.s     loc_37AD
0x37a6  ldloc.s  4
0x37a8  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x37ad  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x37b2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x37b7  ret
0x37b8  ldarg.0
0x37b9  ldloc.1
0x37ba  ldstr    aArgumentvalued_0// "argumentValueDateTime"
0x37bf  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x37c4  stloc.s  4
0x37c6  ldarg.1
0x37c7  ldloc.2
0x37c8  ldarg.3
0x37c9  ldloc.s  5
0x37cb  ldloc.3
0x37cc  brtrue.s loc_37D6
0x37ce  ldloc.1
0x37cf  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x37d4  br.s     loc_37DD
0x37d6  ldloc.s  4
0x37d8  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x37dd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x37e2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x37e7  ret
0x37e8  ldarg.0
0x37e9  ldloc.1
0x37ea  ldstr    aArgumentvaluep// "argumentValuePicklist"
0x37ef  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue(class [System.Xml]System.Xml.XPath.XPathNavigator node, string valueNodeName)
0x37f4  stloc.s  4
0x37f6  ldarg.1
0x37f7  ldloc.2
0x37f8  ldarg.3
0x37f9  ldloc.s  5
0x37fb  ldloc.3
0x37fc  brtrue.s loc_3806
0x37fe  ldloc.1
0x37ff  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3804  br.s     loc_380D
0x3806  ldloc.s  4
0x3808  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x380d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3812  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3817  ret
0x3818  ldloc.1
0x3819  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x381e  ldstr    aSlugbody_0// "<slugbody>"
0x3823  callvirt instance bool [mscorlib]System.String::Contains(string)
0x3828  ldloc.1
0x3829  ldstr    aArgumentvaluel// "argumentValueLookup"
0x382e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x3833  stloc.s  4
0x3835  brfalse.s loc_384D
0x3837  ldarg.1
0x3838  ldloc.2
0x3839  ldarg.3
0x383a  ldc.i4.6
0x383b  ldloc.s  4
0x383d  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_OuterXml()
0x3842  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string)
0x3847  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x384c  ret
0x384d  ldloc.1
0x384e  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3853  ldc.i4.1
0x3854  newarr   [mscorlib]System.Char
0x3859  dup
0x385a  ldc.i4.0
0x385b  ldc.i4.s 0x3B
0x385d  stelem.i2
0x385e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3863  stloc.s  6
0x3865  ldloca.s 7
0x3867  ldloc.s  6
0x3869  ldc.i4.0
0x386a  ldelem.ref
0x386b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3870  ldloc.s  6
0x3872  ldc.i4.1
0x3873  ldelem.ref
0x3874  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3879  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x387e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3883  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3888  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x388d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3892  stloc.s  8
0x3894  ldloc.s  8
0x3896  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x389b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x38a0  stloc.s  9
0x38a2  ldloc.s  8
0x38a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x38a9  ldloc.s  7
0x38ab  ldc.i4.1
0x38ac  newarr   [mscorlib]System.String
0x38b1  dup
0x38b2  ldc.i4.0
0x38b3  ldloc.s  9
0x38b5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x38ba  stelem.ref
0x38bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x38c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38c5  ldsfld   string [mscorlib]System.String::Empty
0x38ca  stloc.s  0xA
0x38cc  ldloc.s  9
0x38ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x38d3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x38d8  castclass [mscorlib]System.String
0x38dd  stloc.s  0xA
0x38df  ldarg.1
0x38e0  ldarg.3
0x38e1  ldarg.3
0x38e2  ldloc.s  7
0x38e4  box      [mscorlib]System.Guid
0x38e9  ldc.i4.s 0xF
0x38eb  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x38f0  ldc.i4.6
0x38f1  ldloc.s  8
0x38f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x38f8  ldloc.s  0xA
0x38fa  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x38ff  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x3904  ret
```
