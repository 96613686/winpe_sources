# Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::ToJson

- ea: `0x2f930`
- end: `0x2f9ec`
- name: `Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::ToJson`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28e40`
- `0x2f930`
- `0x30be0`
- `0x3a340`
- `0x3a390`
- `0x3cfa0`
- `0x3e800`

## string_xrefs

- `0x2f96d`: `emailTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x2f930  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2f935  stloc.0
0x2f936  ldloc.0
0x2f937  ldstr    asc_6E6E6// "{"
0x2f93c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f941  pop
0x2f942  ldloc.0
0x2f943  ldarg.0
0x2f944  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2f949  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f94e  pop
0x2f94f  ldloc.0
0x2f950  ldstr    aSendemailtype// "sendEmailType"
0x2f955  ldarg.0
0x2f956  ldfld    valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::sendEmailType
0x2f95b  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x2f960  ldc.i4.1
0x2f961  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f966  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f96b  pop
0x2f96c  ldloc.0
0x2f96d  ldstr    aEmailtemplatei// "emailTemplateId"
0x2f972  ldarg.0
0x2f973  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::emailTemplateId
0x2f978  constrained. [mscorlib]System.Guid
0x2f97e  callvirt instance string [mscorlib]System.Object::ToString()
0x2f983  ldc.i4.1
0x2f984  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x2f989  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f98e  pop
0x2f98f  ldarg.0
0x2f990  ldfld    class Microsoft.Crm.Workflow.Expressions.EntitySpecification Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::entity
0x2f995  brfalse.s loc_2F9B4
0x2f997  ldloc.0
0x2f998  ldstr    aEntity// "entity"
0x2f99d  ldarg.0
0x2f99e  ldfld    class Microsoft.Crm.Workflow.Expressions.EntitySpecification Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::entity
0x2f9a3  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntitySpecification::ToJson()
0x2f9a8  ldc.i4.1
0x2f9a9  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2f9ae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f9b3  pop
0x2f9b4  ldarg.0
0x2f9b5  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::regardingEntity
0x2f9ba  brfalse.s loc_2F9D9
0x2f9bc  ldloc.0
0x2f9bd  ldstr    aRegardingentit// "regardingEntity"
0x2f9c2  ldarg.0
0x2f9c3  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::regardingEntity
0x2f9c8  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntityBase::ToJson()
0x2f9cd  ldc.i4.1
0x2f9ce  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2f9d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f9d8  pop
0x2f9d9  ldloc.0
0x2f9da  ldstr    asc_6E70E// "}"
0x2f9df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f9e4  pop
0x2f9e5  ldloc.0
0x2f9e6  callvirt instance string [mscorlib]System.Object::ToString()
0x2f9eb  ret
```
