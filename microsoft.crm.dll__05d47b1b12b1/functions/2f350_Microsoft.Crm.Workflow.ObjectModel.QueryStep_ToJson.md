# Microsoft.Crm.Workflow.ObjectModel.QueryStep::ToJson

- ea: `0x2f350`
- end: `0x2f429`
- name: `Microsoft.Crm.Workflow.ObjectModel.QueryStep::ToJson`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2f350`
- `0x30be0`
- `0x3a340`
- `0x3a390`
- `0x3d260`

## string_xrefs

- `0x2f3e7`: `originalFetchXml`
- `0x2f3ff`: `originalLayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x2f350  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2f355  stloc.0
0x2f356  ldloc.0
0x2f357  ldstr    asc_6E6E6// "{"
0x2f35c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f361  pop
0x2f362  ldloc.0
0x2f363  ldarg.0
0x2f364  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2f369  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f36e  pop
0x2f36f  ldarg.0
0x2f370  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchExpression
0x2f375  brfalse.s loc_2F394
0x2f377  ldloc.0
0x2f378  ldstr    aFetchexpressio// "fetchExpression"
0x2f37d  ldarg.0
0x2f37e  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchExpression
0x2f383  callvirt instance string Microsoft.Crm.Workflow.Expressions.ExpressionBase::ToJson()
0x2f388  ldc.i4.1
0x2f389  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2f38e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f393  pop
0x2f394  ldloc.0
0x2f395  ldstr    aFetchcount// "fetchCount"
0x2f39a  ldarg.0
0x2f39b  ldfld    int32 Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchCount
0x2f3a0  box      [mscorlib]System.Int32
0x2f3a5  call     string [mscorlib]System.String::Concat(object)
0x2f3aa  ldc.i4.1
0x2f3ab  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f3b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f3b5  pop
0x2f3b6  ldloc.0
0x2f3b7  ldstr    aAttributelist// "attributeList"
0x2f3bc  ldarg.0
0x2f3bd  ldfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::attributeList
0x2f3c2  ldc.i4.1
0x2f3c3  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f3c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f3cd  pop
0x2f3ce  ldloc.0
0x2f3cf  ldstr    aEntityname// "entityName"
0x2f3d4  ldarg.0
0x2f3d5  ldfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::entityName
0x2f3da  ldc.i4.1
0x2f3db  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f3e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f3e5  pop
0x2f3e6  ldloc.0
0x2f3e7  ldstr    aOriginalfetchx// "originalFetchXml"
0x2f3ec  ldarg.0
0x2f3ed  ldfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::originalFetchXml
0x2f3f2  ldc.i4.1
0x2f3f3  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f3f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f3fd  pop
0x2f3fe  ldloc.0
0x2f3ff  ldstr    aOriginallayout// "originalLayoutXml"
0x2f404  ldarg.0
0x2f405  ldfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::originalLayoutXml
0x2f40a  ldc.i4.1
0x2f40b  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f410  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f415  pop
0x2f416  ldloc.0
0x2f417  ldstr    asc_6E70E// "}"
0x2f41c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f421  pop
0x2f422  ldloc.0
0x2f423  callvirt instance string [mscorlib]System.Object::ToString()
0x2f428  ret
```
