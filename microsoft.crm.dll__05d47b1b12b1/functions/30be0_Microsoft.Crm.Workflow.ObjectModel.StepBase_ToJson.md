# Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson

- ea: `0x30be0`
- end: `0x30c6d`
- name: `Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson`
- size: `141`
- prototype: ``
- caller_count: `27`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x29260`
- `0x29b40`
- `0x29c80`
- `0x29fc0`
- `0x2a320`
- `0x2a730`
- `0x2ad60`
- `0x2af40`
- `0x2b340`
- `0x2b7e0`
- `0x2cd10`
- `0x2d260`
- `0x2d800`
- `0x2ddd0`
- `0x2e1f0`
- `0x2ec80`
- `0x2f350`
- `0x2f930`
- `0x2ff00`
- `0x31310`
- `0x31490`
- `0x31860`
- `0x34940`
- `0x35170`
- `0x379b0`
- `0x386d0`
- `0x3eea0`

## callees

- `0x311a0`
- `0x3a340`
- `0x3a390`

## pseudocode

```c

```

## disassembly

```asm
0x30be0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x30be5  dup
0x30be6  ldstr    aClass// "__class"
0x30beb  ldarg.0
0x30bec  ldfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::__class
0x30bf1  ldc.i4.0
0x30bf2  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x30bf7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30bfc  pop
0x30bfd  dup
0x30bfe  ldstr    aId_0// "id"
0x30c03  ldarg.0
0x30c04  ldfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::id
0x30c09  callvirt instance string [mscorlib]System.Object::ToString()
0x30c0e  ldc.i4.1
0x30c0f  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x30c14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30c19  pop
0x30c1a  dup
0x30c1b  ldstr    aDescription_0// "description"
0x30c20  ldarg.0
0x30c21  ldfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::description
0x30c26  ldc.i4.1
0x30c27  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x30c2c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30c31  pop
0x30c32  dup
0x30c33  ldstr    aName_0// "name"
0x30c38  ldarg.0
0x30c39  ldfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::name
0x30c3e  ldc.i4.1
0x30c3f  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x30c44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30c49  pop
0x30c4a  dup
0x30c4b  ldstr    aSteplabels// "stepLabels"
0x30c50  ldarg.0
0x30c51  ldfld    class Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection Microsoft.Crm.Workflow.ObjectModel.StepBase::stepLabels
0x30c56  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::ToJson()
0x30c5b  ldc.i4.1
0x30c5c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x30c61  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30c66  pop
0x30c67  callvirt instance string [mscorlib]System.Object::ToString()
0x30c6c  ret
```
