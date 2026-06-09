# Microsoft.Crm.Workflow.ObjectModel.ActionStep::ToJson

- ea: `0x29260`
- end: `0x293ad`
- name: `Microsoft.Crm.Workflow.ObjectModel.ActionStep::ToJson`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x28e40`
- `0x28ee0`
- `0x29260`
- `0x29930`
- `0x2ddd0`
- `0x30be0`
- `0x3a340`
- `0x3a390`

## string_xrefs

- `0x292b5`: `processId`

## pseudocode

```c

```

## disassembly

```asm
0x29260  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x29265  stloc.0
0x29266  ldloc.0
0x29267  ldstr    asc_6E6E6// "{"
0x2926c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29271  pop
0x29272  ldloc.0
0x29273  ldarg.0
0x29274  call     instance string Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::ToJson()
0x29279  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2927e  pop
0x2927f  ldloc.0
0x29280  ldstr    aActionid// "actionId"
0x29285  ldarg.0
0x29286  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionId
0x2928b  ldc.i4.1
0x2928c  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x29291  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29296  pop
0x29297  ldloc.0
0x29298  ldstr    aActiontype// "actionType"
0x2929d  ldarg.0
0x2929e  ldfld    int32 Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionType
0x292a3  call     string Microsoft.Crm.Workflow.Utils.StringUtility::ToStringInvariant(int32 value)
0x292a8  ldc.i4.1
0x292a9  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x292ae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x292b3  pop
0x292b4  ldloc.0
0x292b5  ldstr    aProcessid// "processId"
0x292ba  ldarg.0
0x292bb  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.ActionStep::processId
0x292c0  constrained. [mscorlib]System.Guid
0x292c6  callvirt instance string [mscorlib]System.Object::ToString()
0x292cb  ldc.i4.1
0x292cc  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x292d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x292d6  pop
0x292d7  ldloc.0
0x292d8  ldstr    aUniquename// "uniqueName"
0x292dd  ldarg.0
0x292de  ldfld    string Microsoft.Crm.Workflow.ObjectModel.ActionStep::uniqueName
0x292e3  ldc.i4.1
0x292e4  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x292e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x292ee  pop
0x292ef  ldarg.0
0x292f0  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x292f5  brfalse.s loc_29370
0x292f7  ldarg.0
0x292f8  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x292fd  ldlen
0x292fe  brfalse.s loc_29370
0x29300  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x29305  stloc.1
0x29306  ldarg.0
0x29307  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x2930c  ldlen
0x2930d  conv.i4
0x2930e  newarr   [mscorlib]System.String
0x29313  stloc.2
0x29314  ldc.i4.0
0x29315  stloc.3
0x29316  br.s     loc_2932C
0x29318  ldloc.2
0x29319  ldloc.3
0x2931a  ldarg.0
0x2931b  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x29320  ldloc.3
0x29321  ldelem.ref
0x29322  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData::ToJson()
0x29327  stelem.ref
0x29328  ldloc.3
0x29329  ldc.i4.1
0x2932a  add
0x2932b  stloc.3
0x2932c  ldloc.3
0x2932d  ldarg.0
0x2932e  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x29333  ldlen
0x29334  conv.i4
0x29335  blt.s    loc_29318
0x29337  ldloc.1
0x29338  ldstr    asc_6E6DE// "["
0x2933d  ldstr    asc_6B1E0// ","
0x29342  ldloc.2
0x29343  call     T0x2B00002B
0x29348  ldstr    asc_6E6E2// "]"
0x2934d  call     string [mscorlib]System.String::Concat(string, string, string)
0x29352  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29357  pop
0x29358  ldloc.0
0x29359  ldstr    aTriggerevents// "triggerEvents"
0x2935e  ldloc.1
0x2935f  callvirt instance string [mscorlib]System.Object::ToString()
0x29364  ldc.i4.1
0x29365  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2936a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2936f  pop
0x29370  ldarg.0
0x29371  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ControlStep Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionControl
0x29376  call     bool Microsoft.Crm.Workflow.Utils.StringUtility::IsNull(object value)
0x2937b  brtrue.s loc_2939A
0x2937d  ldloc.0
0x2937e  ldstr    aActioncontrol// "actionControl"
0x29383  ldarg.0
0x29384  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ControlStep Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionControl
0x29389  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2938e  ldc.i4.1
0x2938f  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x29394  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29399  pop
0x2939a  ldloc.0
0x2939b  ldstr    asc_6E70E// "}"
0x293a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x293a5  pop
0x293a6  ldloc.0
0x293a7  callvirt instance string [mscorlib]System.Object::ToString()
0x293ac  ret
```
