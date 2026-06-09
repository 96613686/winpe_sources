# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::SetConditionXml

- ea: `0x19fc0`
- end: `0x19fe9`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::SetConditionXml`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x19510`

## callees

- `0x19fa0`
- `0x19fc0`

## string_xrefs

- `0x19fc1`: `conditionxml`
- `0x19fcf`: `conditionxml`

## pseudocode

```c

```

## disassembly

```asm
0x19fc0  ldarg.1
0x19fc1  ldstr    aConditionxml// "conditionxml"
0x19fc6  call     bool Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::ContainsData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string attributeName)
0x19fcb  brfalse.s loc_19FE8
0x19fcd  ldarg.0
0x19fce  ldarg.1
0x19fcf  ldstr    aConditionxml// "conditionxml"
0x19fd4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19fd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19fde  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x19fe3  stfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x19fe8  ret
```
