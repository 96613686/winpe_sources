# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::.cctor

- ea: `0x2cc00`
- end: `0x2cce1`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::.cctor`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x2cc68`: `CreatedEntities`
- `0x2cc90`: `#Temp`

## pseudocode

```c

```

## disassembly

```asm
0x2cc00  ldsfld   class <>c <>c::<>9
0x2cc05  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type> <>c::<.cctor>b__149_0()
0x2cc0b  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>>::.ctor(object, native int)
0x2cc10  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x2cc15  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_attributeToCrmTypeMapping
0x2cc1a  ldsfld   class <>c <>c::<>9
0x2cc1f  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType> <>c::<.cctor>b__149_1()
0x2cc25  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType>>::.ctor(object, native int)
0x2cc2a  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x2cc2f  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType>> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_crmToXrmWorkflowTypes
0x2cc34  ldsfld   class <>c <>c::<>9
0x2cc39  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator> <>c::<.cctor>b__149_2()
0x2cc3f  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>>::.ctor(object, native int)
0x2cc44  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x2cc49  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_expressionToConditionOperatorMap
0x2cc4e  ldsfld   class <>c <>c::<>9
0x2cc53  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator> <>c::<.cctor>b__149_3()
0x2cc59  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>>::.ctor(object, native int)
0x2cc5e  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x2cc63  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_expressionToLogicalOperatorMap
0x2cc68  ldstr    aCreatedentitie// "CreatedEntities"
0x2cc6d  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x2cc72  ldstr    aInputentities// "InputEntities"
0x2cc77  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InputEntitiesVariableName
0x2cc7c  ldstr    aExecutionpoint// "ExecutionPointers"
0x2cc81  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ExecutionPointersVariableName
0x2cc86  ldstr    aLocalparameter// "_localParameter"
0x2cc8b  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalParameterVariableName
0x2cc90  ldstr    aTemp// "#Temp"
0x2cc95  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x2cc9a  ldstr    aTypename_1// "TypeName"
0x2cc9f  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x2cca4  ldstr    aInteractionste// "InteractionStep"
0x2cca9  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionStepActivityNamePrefix
0x2ccae  ldstr    aInteractionres_1// "InteractionResponses"
0x2ccb3  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionResponsesVariableName
0x2ccb8  ldstr    aQueryresults// "QueryResults"
0x2ccbd  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::QueryResultsVariableName
0x2ccc2  ldstr    aInteractionres_0// "_interactionResponseValue"
0x2ccc7  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionResponseVariableNameSuffix
0x2cccc  ldstr    aIdentifierdefi// "IdentifierDefinition"
0x2ccd1  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x2ccd6  ldstr    aLookupinitiali// "LookupInitialization"
0x2ccdb  stsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LookupInitializationSequenceNamePrefix
0x2cce0  ret
```
