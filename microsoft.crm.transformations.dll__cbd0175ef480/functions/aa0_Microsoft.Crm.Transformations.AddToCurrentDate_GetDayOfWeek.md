# Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOfWeek

- ea: `0xaa0`
- end: `0xae2`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOfWeek`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x440`

## callees

- `0xaf0`
- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOfWeekOptions()
0xaa6  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0xaab  dup
0xaac  ldstr    aMicrosoftCrmTr_35// "Microsoft.Crm.Transformations.AddToCurr"...
0xab1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xab6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0xabb  dup
0xabc  ldstr    aMicrosoftCrmTr_36// "Microsoft.Crm.Transformations.AddToCurr"...
0xac1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xac6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0xacb  dup
0xacc  ldc.i4.s 9
0xace  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0xad3  dup
0xad4  ldc.i4.0
0xad5  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0xada  dup
0xadb  ldc.i4.0
0xadc  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0xae1  ret
```
