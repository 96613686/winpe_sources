# Microsoft.Crm.Workflow.ObjectModel.ControlStep::ToJson

- ea: `0x34940`
- end: `0x34a8e`
- name: `Microsoft.Crm.Workflow.ObjectModel.ControlStep::ToJson`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x28e40`
- `0x28ee0`
- `0x30be0`
- `0x34940`
- `0x3a340`
- `0x3a390`
- `0x3a3e0`
- `0x3e800`

## string_xrefs

- `0x34978`: `classId`

## pseudocode

```c

```

## disassembly

```asm
0x34940  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x34945  stloc.0
0x34946  ldloc.0
0x34947  ldstr    asc_6E6E6// "{"
0x3494c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34951  pop
0x34952  ldloc.0
0x34953  ldarg.0
0x34954  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x34959  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3495e  pop
0x3495f  ldloc.0
0x34960  ldstr    aControlid// "controlId"
0x34965  ldarg.0
0x34966  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlId
0x3496b  ldc.i4.1
0x3496c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x34971  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34976  pop
0x34977  ldloc.0
0x34978  ldstr    aClassid// "classId"
0x3497d  ldarg.0
0x3497e  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::classId
0x34983  ldc.i4.1
0x34984  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x34989  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3498e  pop
0x3498f  ldloc.0
0x34990  ldstr    aDatafieldname// "dataFieldName"
0x34995  ldarg.0
0x34996  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::dataFieldName
0x3499b  ldc.i4.1
0x3499c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x349a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x349a6  pop
0x349a7  ldloc.0
0x349a8  ldstr    aSystemsteptype// "systemStepType"
0x349ad  ldarg.0
0x349ae  ldflda   valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep Microsoft.Crm.Workflow.ObjectModel.ControlStep::systemStepType
0x349b3  constrained. Microsoft.Crm.Workflow.ObjectModel.SystemStep
0x349b9  callvirt instance string [mscorlib]System.Object::ToString()
0x349be  ldc.i4.1
0x349bf  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x349c4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x349c9  pop
0x349ca  ldloc.0
0x349cb  ldstr    aIssystemcontro// "isSystemControl"
0x349d0  ldarg.0
0x349d1  ldfld    bool Microsoft.Crm.Workflow.ObjectModel.ControlStep::isSystemControl
0x349d6  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x349db  ldc.i4.1
0x349dc  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x349e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x349e6  pop
0x349e7  ldloc.0
0x349e8  ldstr    aParameters// "parameters"
0x349ed  ldarg.0
0x349ee  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::parameters
0x349f3  ldc.i4.1
0x349f4  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x349f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x349fe  pop
0x349ff  ldloc.0
0x34a00  ldstr    aControldisplay// "controlDisplayName"
0x34a05  ldarg.0
0x34a06  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlDisplayName
0x34a0b  ldc.i4.1
0x34a0c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x34a11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a16  pop
0x34a17  ldloc.0
0x34a18  ldstr    aIsunbound// "isUnbound"
0x34a1d  ldarg.0
0x34a1e  ldfld    bool Microsoft.Crm.Workflow.ObjectModel.ControlStep::isUnbound
0x34a23  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x34a28  ldc.i4.1
0x34a29  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x34a2e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a33  pop
0x34a34  ldloc.0
0x34a35  ldstr    aControltype// "controlType"
0x34a3a  ldarg.0
0x34a3b  ldfld    int32 Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlType
0x34a40  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x34a45  ldc.i4.1
0x34a46  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x34a4b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a50  pop
0x34a51  ldarg.0
0x34a52  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.ControlStep::entity
0x34a57  call     bool Microsoft.Crm.Workflow.Utils.StringUtility::IsNull(object value)
0x34a5c  brtrue.s loc_34A7B
0x34a5e  ldloc.0
0x34a5f  ldstr    aEntity// "entity"
0x34a64  ldarg.0
0x34a65  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.ControlStep::entity
0x34a6a  callvirt instance string Microsoft.Crm.Workflow.Expressions.EntityBase::ToJson()
0x34a6f  ldc.i4.1
0x34a70  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x34a75  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a7a  pop
0x34a7b  ldloc.0
0x34a7c  ldstr    asc_6E70E// "}"
0x34a81  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a86  pop
0x34a87  ldloc.0
0x34a88  callvirt instance string [mscorlib]System.Object::ToString()
0x34a8d  ret
```
