# Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::ToJson

- ea: `0x2a320`
- end: `0x2a3c4`
- name: `Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::ToJson`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2a320`
- `0x30be0`
- `0x3a340`
- `0x3a390`
- `0x3a3e0`
- `0x3e800`

## string_xrefs

- `0x2a370`: `isReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x2a320  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2a325  stloc.0
0x2a326  ldloc.0
0x2a327  ldstr    asc_6E6E6// "{"
0x2a32c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a331  pop
0x2a332  ldloc.0
0x2a333  ldarg.0
0x2a334  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2a339  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a33e  pop
0x2a33f  ldloc.0
0x2a340  ldstr    aControlid// "controlId"
0x2a345  ldarg.0
0x2a346  ldfld    string Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::controlId
0x2a34b  ldc.i4.1
0x2a34c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2a351  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a356  pop
0x2a357  ldloc.0
0x2a358  ldstr    aControltype// "controlType"
0x2a35d  ldarg.0
0x2a35e  ldfld    string Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::controlType
0x2a363  ldc.i4.1
0x2a364  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2a369  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a36e  pop
0x2a36f  ldloc.0
0x2a370  ldstr    aIsreadonly// "isReadOnly"
0x2a375  ldarg.0
0x2a376  ldfld    bool Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::isReadOnly
0x2a37b  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x2a380  ldc.i4.1
0x2a381  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2a386  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a38b  pop
0x2a38c  ldarg.0
0x2a38d  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::entity
0x2a392  brfalse.s loc_2A3B1
0x2a394  ldloc.0
0x2a395  ldstr    aEntity// "entity"
0x2a39a  ldarg.0
0x2a39b  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::entity
0x2a3a0  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntityBase::ToJson()
0x2a3a5  ldc.i4.1
0x2a3a6  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2a3ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a3b0  pop
0x2a3b1  ldloc.0
0x2a3b2  ldstr    asc_6E70E// "}"
0x2a3b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a3bc  pop
0x2a3bd  ldloc.0
0x2a3be  callvirt instance string [mscorlib]System.Object::ToString()
0x2a3c3  ret
```
