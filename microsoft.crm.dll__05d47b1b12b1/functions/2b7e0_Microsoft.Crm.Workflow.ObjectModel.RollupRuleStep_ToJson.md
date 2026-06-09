# Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::ToJson

- ea: `0x2b7e0`
- end: `0x2b908`
- name: `Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::ToJson`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2b7e0`
- `0x30be0`
- `0x3a340`
- `0x3a390`
- `0x3d260`
- `0x3e800`

## string_xrefs

- `0x2b88f`: `targetLinkedFilter`
- `0x2b8b4`: `targetRelationshipLinked`

## pseudocode

```c

```

## disassembly

```asm
0x2b7e0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2b7e5  stloc.0
0x2b7e6  ldloc.0
0x2b7e7  ldstr    asc_6E6E6// "{"
0x2b7ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b7f1  pop
0x2b7f2  ldloc.0
0x2b7f3  ldarg.0
0x2b7f4  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2b7f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b7fe  pop
0x2b7ff  ldarg.0
0x2b800  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::sourceFilter
0x2b805  brfalse.s loc_2B824
0x2b807  ldloc.0
0x2b808  ldstr    aSourcefilter// "sourceFilter"
0x2b80d  ldarg.0
0x2b80e  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::sourceFilter
0x2b813  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2b818  ldc.i4.1
0x2b819  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b81e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b823  pop
0x2b824  ldloc.0
0x2b825  ldstr    aHierarchicalre// "hierarchicalRelationshipName"
0x2b82a  ldarg.0
0x2b82b  ldfld    string Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::hierarchicalRelationshipName
0x2b830  ldc.i4.1
0x2b831  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2b836  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b83b  pop
0x2b83c  ldarg.0
0x2b83d  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetFilter
0x2b842  brfalse.s loc_2B861
0x2b844  ldloc.0
0x2b845  ldstr    aTargetfilter// "targetFilter"
0x2b84a  ldarg.0
0x2b84b  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetFilter
0x2b850  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2b855  ldc.i4.1
0x2b856  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b85b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b860  pop
0x2b861  ldarg.0
0x2b862  ldfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationship
0x2b867  brfalse.s loc_2B886
0x2b869  ldloc.0
0x2b86a  ldstr    aTargetrelation// "targetRelationship"
0x2b86f  ldarg.0
0x2b870  ldfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationship
0x2b875  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntityBase::ToJson()
0x2b87a  ldc.i4.1
0x2b87b  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b880  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b885  pop
0x2b886  ldarg.0
0x2b887  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetLinkedFilter
0x2b88c  brfalse.s loc_2B8AB
0x2b88e  ldloc.0
0x2b88f  ldstr    aTargetlinkedfi// "targetLinkedFilter"
0x2b894  ldarg.0
0x2b895  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetLinkedFilter
0x2b89a  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2b89f  ldc.i4.1
0x2b8a0  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b8a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b8aa  pop
0x2b8ab  ldarg.0
0x2b8ac  ldfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationshipLinked
0x2b8b1  brfalse.s loc_2B8D0
0x2b8b3  ldloc.0
0x2b8b4  ldstr    aTargetrelation_0// "targetRelationshipLinked"
0x2b8b9  ldarg.0
0x2b8ba  ldfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationshipLinked
0x2b8bf  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntityBase::ToJson()
0x2b8c4  ldc.i4.1
0x2b8c5  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b8ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b8cf  pop
0x2b8d0  ldarg.0
0x2b8d1  ldfld    class Microsoft.Crm.Workflow.Expressions.MethodCallExpression Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::aggregate
0x2b8d6  brfalse.s loc_2B8F5
0x2b8d8  ldloc.0
0x2b8d9  ldstr    aAggregate// "aggregate"
0x2b8de  ldarg.0
0x2b8df  ldfld    class Microsoft.Crm.Workflow.Expressions.MethodCallExpression Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::aggregate
0x2b8e4  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2b8e9  ldc.i4.1
0x2b8ea  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2b8ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b8f4  pop
0x2b8f5  ldloc.0
0x2b8f6  ldstr    asc_6E70E// "}"
0x2b8fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b900  pop
0x2b901  ldloc.0
0x2b902  callvirt instance string [mscorlib]System.Object::ToString()
0x2b907  ret
```
