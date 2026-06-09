# Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::GetConditionXml

- ea: `0x16b00`
- end: `0x16b95`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::GetConditionXml`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x161b0`

## callees

- `0x16190`
- `0x16b00`

## string_xrefs

- `0x16b4c`: `applicablewhenxml`
- `0x16b5a`: `applicablewhenxml`
- `0x16b02`: `successconditionsxml`
- `0x16b10`: `successconditionsxml`

## pseudocode

```c

```

## disassembly

```asm
0x16b00  ldarg.0
0x16b01  ldarg.1
0x16b02  ldstr    aSuccessconditi// "successconditionsxml"
0x16b07  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::ContainsData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string attributeName)
0x16b0c  brfalse.s loc_16B29
0x16b0e  ldarg.0
0x16b0f  ldarg.1
0x16b10  ldstr    aSuccessconditi// "successconditionsxml"
0x16b15  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x16b1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16b1f  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x16b24  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16b29  ldarg.0
0x16b2a  ldarg.0
0x16b2b  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16b30  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16b35  brtrue.s loc_16B3F
0x16b37  ldarg.0
0x16b38  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16b3d  br.s     loc_16B45
0x16b3f  ldarg.0
0x16b40  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_defaultSuccessCondition
0x16b45  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16b4a  ldarg.0
0x16b4b  ldarg.1
0x16b4c  ldstr    aApplicablewhen// "applicablewhenxml"
0x16b51  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::ContainsData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string attributeName)
0x16b56  brfalse.s loc_16B73
0x16b58  ldarg.0
0x16b59  ldarg.1
0x16b5a  ldstr    aApplicablewhen// "applicablewhenxml"
0x16b5f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x16b64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16b69  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x16b6e  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16b73  ldarg.0
0x16b74  ldarg.0
0x16b75  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16b7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16b7f  brtrue.s loc_16B89
0x16b81  ldarg.0
0x16b82  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16b87  br.s     loc_16B8F
0x16b89  ldarg.0
0x16b8a  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_defaultApplicableWhenCondition
0x16b8f  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16b94  ret
```
