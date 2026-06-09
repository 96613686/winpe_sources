# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMonthOffsetMode

- ea: `0x1a30`
- end: `0x1a72`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMonthOffsetMode`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1260`

## callees

- `0x1bd0`
- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x1a30  ldarg.0
0x1a31  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetOffsetModeOptions()
0x1a36  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0x1a3b  dup
0x1a3c  ldstr    aMicrosoftCrmTr_79// "Microsoft.Crm.Transformations.AdvancedA"...
0x1a41  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1a46  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1a4b  dup
0x1a4c  ldstr    aMicrosoftCrmTr_80// "Microsoft.Crm.Transformations.AdvancedA"...
0x1a51  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1a56  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1a5b  dup
0x1a5c  ldc.i4.s 9
0x1a5e  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1a63  dup
0x1a64  ldc.i4.0
0x1a65  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1a6a  dup
0x1a6b  ldc.i4.0
0x1a6c  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1a71  ret
```
