# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddValue_0

- ea: `0x1d4a0`
- end: `0x1d4e3`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddValue_0`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1d4f0`

## callees

- `0x1d460`
- `0x1e8d0`
- `0x1e8f0`
- `0x1e930`
- `0x1e950`
- `0x1e970`
- `0x1e9b0`
- `0x1e9d0`
- `0x1e9e0`

## pseudocode

```c

```

## disassembly

```asm
0x1d4a0  newobj   instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::.ctor()
0x1d4a5  stloc.0
0x1d4a6  ldloc.0
0x1d4a7  ldarg.1
0x1d4a8  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Name(string value)
0x1d4ad  ldloc.0
0x1d4ae  ldarg.2
0x1d4af  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Type(string value)
0x1d4b4  ldloc.0
0x1d4b5  ldarg.s  5
0x1d4b7  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Description(string value)
0x1d4bc  ldloc.0
0x1d4bd  ldarg.s  4
0x1d4bf  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Optional(bool value)
0x1d4c4  ldloc.0
0x1d4c5  ldarg.3
0x1d4c6  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Direction(string value)
0x1d4cb  ldloc.0
0x1d4cc  ldarg.s  7
0x1d4ce  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_Editable(bool value)
0x1d4d3  ldloc.0
0x1d4d4  ldarg.s  6
0x1d4d6  callvirt instance void Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::set_EntityName(string value)
0x1d4db  ldarg.0
0x1d4dc  ldloc.0
0x1d4dd  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddValue(class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue listValue)
0x1d4e2  ret
```
