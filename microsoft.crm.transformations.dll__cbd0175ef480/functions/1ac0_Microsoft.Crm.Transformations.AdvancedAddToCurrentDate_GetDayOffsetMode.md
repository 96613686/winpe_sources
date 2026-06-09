# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetDayOffsetMode

- ea: `0x1ac0`
- end: `0x1b02`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetDayOffsetMode`
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
0x1ac0  ldarg.0
0x1ac1  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetOffsetModeOptions()
0x1ac6  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0x1acb  dup
0x1acc  ldstr    aMicrosoftCrmTr_83// "Microsoft.Crm.Transformations.AdvancedA"...
0x1ad1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1ad6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1adb  dup
0x1adc  ldstr    aMicrosoftCrmTr_84// "Microsoft.Crm.Transformations.AdvancedA"...
0x1ae1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1ae6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1aeb  dup
0x1aec  ldc.i4.s 9
0x1aee  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1af3  dup
0x1af4  ldc.i4.0
0x1af5  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1afa  dup
0x1afb  ldc.i4.0
0x1afc  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1b01  ret
```
