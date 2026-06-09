# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetYearOffsetMode

- ea: `0x19a0`
- end: `0x19e2`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetYearOffsetMode`
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
0x19a0  ldarg.0
0x19a1  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetOffsetModeOptions()
0x19a6  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0x19ab  dup
0x19ac  ldstr    aMicrosoftCrmTr_75// "Microsoft.Crm.Transformations.AdvancedA"...
0x19b1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x19b6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x19bb  dup
0x19bc  ldstr    aMicrosoftCrmTr_76// "Microsoft.Crm.Transformations.AdvancedA"...
0x19c1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x19c6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x19cb  dup
0x19cc  ldc.i4.s 9
0x19ce  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x19d3  dup
0x19d4  ldc.i4.0
0x19d5  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x19da  dup
0x19db  ldc.i4.0
0x19dc  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x19e1  ret
```
