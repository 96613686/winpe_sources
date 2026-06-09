# Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::ToJson

- ea: `0x2d260`
- end: `0x2d327`
- name: `Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::ToJson`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28e40`
- `0x2d260`
- `0x2d680`
- `0x30be0`
- `0x3a340`
- `0x3a390`
- `0x3a3e0`
- `0x3d260`

## string_xrefs

- `0x2d298`: `readOnly`

## pseudocode

```c

```

## disassembly

```asm
0x2d260  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2d265  stloc.0
0x2d266  ldloc.0
0x2d267  ldstr    asc_6E6E6// "{"
0x2d26c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d271  pop
0x2d272  ldloc.0
0x2d273  ldarg.0
0x2d274  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2d279  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d27e  pop
0x2d27f  ldloc.0
0x2d280  ldstr    aVariablename// "variableName"
0x2d285  ldarg.0
0x2d286  ldfld    string Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::variableName
0x2d28b  ldc.i4.1
0x2d28c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2d291  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d296  pop
0x2d297  ldloc.0
0x2d298  ldstr    aReadonly// "readOnly"
0x2d29d  ldarg.0
0x2d29e  ldfld    bool Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::readOnly
0x2d2a3  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x2d2a8  ldc.i4.1
0x2d2a9  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2d2ae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d2b3  pop
0x2d2b4  ldloc.0
0x2d2b5  ldstr    aDirection// "direction"
0x2d2ba  ldarg.0
0x2d2bb  ldfld    valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::direction
0x2d2c0  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x2d2c5  ldc.i4.1
0x2d2c6  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2d2cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d2d0  pop
0x2d2d1  ldloc.0
0x2d2d2  ldstr    aDatatype// "dataType"
0x2d2d7  ldarg.0
0x2d2d8  ldarg.0
0x2d2d9  ldfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::dataType
0x2d2de  call     instance string Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::GetDataTypeJson(class [mscorlib]System.Type attributeType)
0x2d2e3  ldc.i4.1
0x2d2e4  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2d2e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d2ee  pop
0x2d2ef  ldarg.0
0x2d2f0  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::valueExpression
0x2d2f5  brfalse.s loc_2D314
0x2d2f7  ldloc.0
0x2d2f8  ldstr    aValueexpressio// "valueExpression"
0x2d2fd  ldarg.0
0x2d2fe  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::valueExpression
0x2d303  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2d308  ldc.i4.1
0x2d309  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2d30e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d313  pop
0x2d314  ldloc.0
0x2d315  ldstr    asc_6E70E// "}"
0x2d31a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d31f  pop
0x2d320  ldloc.0
0x2d321  callvirt instance string [mscorlib]System.Object::ToString()
0x2d326  ret
```
