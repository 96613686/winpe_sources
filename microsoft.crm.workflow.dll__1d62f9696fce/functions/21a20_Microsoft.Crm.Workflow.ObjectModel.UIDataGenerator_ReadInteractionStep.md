# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInteractionStep

- ea: `0x21a20`
- end: `0x21d49`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInteractionStep`
- size: `809`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x21a20`
- `0x223a0`
- `0x22ce0`
- `0x2ddd0`
- `0x2ddf0`
- `0x2de10`
- `0x2de30`
- `0x2de50`
- `0x2deb0`
- `0x2ded0`
- `0x2df10`
- `0x2df30`
- `0x2df50`

## pseudocode

```c

```

## disassembly

```asm
0x21a20  ldc.i4.0
0x21a21  stloc.0
0x21a22  ldarg.0
0x21a23  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21a28  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x21a2d  stloc.1
0x21a2e  ldarg.0
0x21a2f  ldarg.2
0x21a30  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21a35  ldc.i4.0
0x21a36  call     T0x2B000032
0x21a3b  stloc.2
0x21a3c  ldloc.2
0x21a3d  brfalse  loc_21D47
0x21a42  ldloc.2
0x21a43  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.Interaction::get_LogResponse()
0x21a48  brfalse.s loc_21A65
0x21a4a  ldloc.1
0x21a4b  ldloc.2
0x21a4c  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.Interaction::get_LogResponse()
0x21a51  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x21a56  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x21a5b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x21a60  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_LogResponse(bool)
0x21a65  ldloc.2
0x21a66  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseContainerType()
0x21a6b  brfalse.s loc_21A88
0x21a6d  ldloc.1
0x21a6e  ldloc.2
0x21a6f  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseContainerType()
0x21a74  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::get_Expression()
0x21a79  castclass class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x21a7e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x21a83  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseContainerType(int32)
0x21a88  ldloc.2
0x21a89  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseMetadataType()
0x21a8e  brfalse.s loc_21AAB
0x21a90  ldloc.1
0x21a91  ldloc.2
0x21a92  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseMetadataType()
0x21a97  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::get_Expression()
0x21a9c  castclass class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x21aa1  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x21aa6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseMetadataType(int32)
0x21aab  ldloc.2
0x21aac  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.Interaction::get_IsResponseMetadataBound()
0x21ab1  brfalse.s loc_21ACE
0x21ab3  ldloc.1
0x21ab4  ldloc.2
0x21ab5  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.Interaction::get_IsResponseMetadataBound()
0x21aba  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x21abf  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x21ac4  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x21ac9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_IsResponseMetadataBound(bool)
0x21ace  ldc.i4.0
0x21acf  stloc.3
0x21ad0  br       loc_21B9F
0x21ad5  ldarg.2
0x21ad6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21adb  ldloc.3
0x21adc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x21ae1  isinst   [System.Activities]System.Activities.Statements.Sequence
0x21ae6  stloc.s  4
0x21ae8  ldloc.s  4
0x21aea  brfalse  loc_21B9B
0x21aef  ldarg.0
0x21af0  ldloc.s  4
0x21af2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x21af7  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x21afc  ldloc.s  4
0x21afe  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x21b03  stloc.s  5
0x21b05  ldloc.s  5
0x21b07  ldstr    aPromptexpressi// "PromptExpression"
0x21b0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21b11  brtrue.s loc_21B31
0x21b13  ldloc.s  5
0x21b15  ldstr    aHintexpression// "HintExpression"
0x21b1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21b1f  brtrue.s loc_21B55
0x21b21  ldloc.s  5
0x21b23  ldstr    aDefaultvalueex// "DefaultValueExpression"
0x21b28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21b2d  brtrue.s loc_21B79
0x21b2f  br.s     loc_21B9B
0x21b31  ldc.i4.0
0x21b32  stloc.0
0x21b33  ldloc.1
0x21b34  ldarg.0
0x21b35  ldloc.s  4
0x21b37  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21b3c  ldtoken  [System.Activities]System.Activities.Statements.Sequence
0x21b41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21b46  ldc.i4.0
0x21b47  ldloca.s 0
0x21b49  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x21b4e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_PromptText(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21b53  br.s     loc_21B9B
0x21b55  ldc.i4.0
0x21b56  stloc.0
0x21b57  ldloc.1
0x21b58  ldarg.0
0x21b59  ldloc.s  4
0x21b5b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21b60  ldtoken  [System.Activities]System.Activities.Statements.Sequence
0x21b65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21b6a  ldc.i4.0
0x21b6b  ldloca.s 0
0x21b6d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x21b72  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_HintText(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21b77  br.s     loc_21B9B
0x21b79  ldc.i4.0
0x21b7a  stloc.0
0x21b7b  ldloc.1
0x21b7c  ldarg.0
0x21b7d  ldloc.s  4
0x21b7f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21b84  ldtoken  [System.Activities]System.Activities.Statements.Sequence
0x21b89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21b8e  ldc.i4.0
0x21b8f  ldloca.s 0
0x21b91  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x21b96  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_DefaultResponseValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21b9b  ldloc.3
0x21b9c  ldc.i4.1
0x21b9d  add
0x21b9e  stloc.3
0x21b9f  ldloc.3
0x21ba0  ldarg.2
0x21ba1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21ba6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x21bab  blt      loc_21AD5
0x21bb0  ldloc.1
0x21bb1  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseContainerType()
0x21bb6  ldc.i4.2
0x21bb7  beq.s    loc_21BC5
0x21bb9  ldloc.1
0x21bba  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseContainerType()
0x21bbf  ldc.i4.3
0x21bc0  bne.un   loc_21C95
0x21bc5  ldloc.2
0x21bc6  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_StaticResponseValues()
0x21bcb  brfalse.s loc_21BED
0x21bcd  ldloc.1
0x21bce  ldloc.2
0x21bcf  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_StaticResponseValues()
0x21bd4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x21bd9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x21bde  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x21be3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_StaticResponseValues(string)
0x21be8  br       loc_21C95
0x21bed  ldloc.2
0x21bee  callvirt instance string Microsoft.Crm.Workflow.Activities.Interaction::get_QueryVariableName()
0x21bf3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21bf8  brtrue   loc_21C95
0x21bfd  ldloc.1
0x21bfe  ldloc.2
0x21bff  callvirt instance string Microsoft.Crm.Workflow.Activities.Interaction::get_QueryVariableName()
0x21c04  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_QueryVariableName(string)
0x21c09  ldloc.2
0x21c0a  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_DynamicQueryAttributeList()
0x21c0f  brfalse.s loc_21C2C
0x21c11  ldloc.1
0x21c12  ldloc.2
0x21c13  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_DynamicQueryAttributeList()
0x21c18  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x21c1d  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x21c22  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x21c27  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_AttributeList(string)
0x21c2c  ldloc.2
0x21c2d  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_AttributeDelimiter()
0x21c32  brfalse.s loc_21C4F
0x21c34  ldloc.1
0x21c35  ldloc.2
0x21c36  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.Interaction::get_AttributeDelimiter()
0x21c3b  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x21c40  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x21c45  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x21c4a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_AttributeDelimiter(string)
0x21c4f  ldloc.2
0x21c50  callvirt instance string Microsoft.Crm.Workflow.Activities.Interaction::get_QueryVariableName()
0x21c55  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21c5a  brtrue.s loc_21C95
0x21c5c  ldloc.1
0x21c5d  ldloc.2
0x21c5e  callvirt instance string Microsoft.Crm.Workflow.Activities.Interaction::get_QueryEntityName()
0x21c63  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_QueryEntityName(string)
0x21c68  ldarg.0
0x21c69  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21c6e  ldloc.1
0x21c6f  ldloc.1
0x21c70  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_QueryEntityName()
0x21c75  ldarg.1
0x21c76  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep, string, string)
0x21c7b  stloc.s  6
0x21c7d  ldarg.0
0x21c7e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x21c83  ldarg.1
0x21c84  ldstr    aInteractionres_0// "_interactionResponseValue"
0x21c89  call     string [mscorlib]System.String::Concat(string, string)
0x21c8e  ldloc.s  6
0x21c90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x21c95  ldloc.1
0x21c96  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_IsResponseMetadataBound()
0x21c9b  brfalse  loc_21D47
0x21ca0  ldloc.2
0x21ca1  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseMetadataSource()
0x21ca6  brfalse  loc_21D47
0x21cab  ldloc.1
0x21cac  ldloc.2
0x21cad  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource> Microsoft.Crm.Workflow.Activities.Interaction::get_ResponseMetadataSource()
0x21cb2  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource>::get_Expression()
0x21cb7  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource>
0x21cbc  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource>::get_Value()
0x21cc1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::.ctor(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x21cc6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_ResponseMetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x21ccb  ldc.i4.7
0x21ccc  ldloc.1
0x21ccd  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseContainerType()
0x21cd2  bne.un.s loc_21D47
0x21cd4  ldc.i4.5
0x21cd5  ldloc.1
0x21cd6  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataType()
0x21cdb  bne.un.s loc_21D47
0x21cdd  ldarg.0
0x21cde  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_metadataProvider
0x21ce3  ldloc.1
0x21ce4  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataSource()
0x21ce9  stloc.s  9
0x21ceb  ldloca.s 9
0x21ced  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_EntityName()
0x21cf2  ldloc.1
0x21cf3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::get_ResponseMetadataSource()
0x21cf8  stloc.s  9
0x21cfa  ldloca.s 9
0x21cfc  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_AttributeName()
0x21d01  callvirt instance string[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider::GetEntitiesReferencedByLookup(string, string)
0x21d06  stloc.s  7
0x21d08  ldc.i4.0
0x21d09  stloc.s  8
0x21d0b  br.s     loc_21D3F
0x21d0d  ldloc.s  7
0x21d0f  ldloc.s  8
0x21d11  ldelem.ref
0x21d12  stloc.s  0xA
0x21d14  ldarg.0
0x21d15  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21d1a  ldloc.1
0x21d1b  ldloc.s  0xA
0x21d1d  ldarg.1
0x21d1e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep, string, string)
0x21d23  stloc.s  0xB
0x21d25  ldarg.0
0x21d26  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x21d2b  ldloc.s  0xB
0x21d2d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x21d32  ldloc.s  0xB
0x21d34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x21d39  ldloc.s  8
0x21d3b  ldc.i4.1
0x21d3c  add
0x21d3d  stloc.s  8
0x21d3f  ldloc.s  8
0x21d41  ldloc.s  7
0x21d43  ldlen
0x21d44  conv.i4
0x21d45  blt.s    loc_21D0D
0x21d47  ldloc.1
0x21d48  ret
```
