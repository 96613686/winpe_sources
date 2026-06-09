# Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson

- ea: `0x3d260`
- end: `0x3d2da`
- name: `Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson`
- size: `122`
- prototype: ``
- caller_count: `23`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2b7e0`
- `0x2cd10`
- `0x2d260`
- `0x2d800`
- `0x2f350`
- `0x2ff00`
- `0x31490`
- `0x33930`
- `0x35540`
- `0x379b0`
- `0x386d0`
- `0x3b3f0`
- `0x3b9e0`
- `0x3c500`
- `0x3cc60`
- `0x3d4e0`
- `0x3d7d0`
- `0x3db10`
- `0x3db70`
- `0x3dc00`
- `0x3df80`
- `0x3e4a0`
- `0x3fcb0`

## callees

- `0x28e40`
- `0x3a340`
- `0x3a390`
- `0x3a3e0`

## pseudocode

```c

```

## disassembly

```asm
0x3d260  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3d265  dup
0x3d266  ldstr    aClass// "__class"
0x3d26b  ldarg.0
0x3d26c  ldfld    string Microsoft.Crm.Workflow.Expressions.ExpressionBase::__class
0x3d271  ldc.i4.0
0x3d272  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x3d277  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d27c  pop
0x3d27d  dup
0x3d27e  ldstr    aType_0// "type"
0x3d283  ldarg.0
0x3d284  ldfld    valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.Expressions.ExpressionBase::type
0x3d289  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x3d28e  ldc.i4.1
0x3d28f  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x3d294  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d299  pop
0x3d29a  dup
0x3d29b  ldstr    aTypeset// "typeSet"
0x3d2a0  ldarg.0
0x3d2a1  ldfld    bool Microsoft.Crm.Workflow.Expressions.ExpressionBase::typeSet
0x3d2a6  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x3d2ab  ldc.i4.1
0x3d2ac  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x3d2b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d2b6  pop
0x3d2b7  dup
0x3d2b8  ldstr    aBehavior// "behavior"
0x3d2bd  ldarg.0
0x3d2be  ldfld    valuetype Microsoft.Crm.Workflow.Expressions.AttributeDateTimeBehavior Microsoft.Crm.Workflow.Expressions.ExpressionBase::behavior
0x3d2c3  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x3d2c8  ldc.i4.1
0x3d2c9  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x3d2ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d2d3  pop
0x3d2d4  callvirt instance string [mscorlib]System.Object::ToString()
0x3d2d9  ret
```
