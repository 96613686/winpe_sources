# Microsoft.Crm.Transformations.AddToCurrentDate::GetMonthOffset

- ea: `0x960`
- end: `0x99c`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetMonthOffset`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x440`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x960  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x965  dup
0x966  ldstr    aMicrosoftCrmTr_25// "Microsoft.Crm.Transformations.AddToCurr"...
0x96b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x970  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x975  dup
0x976  ldstr    aMicrosoftCrmTr_26// "Microsoft.Crm.Transformations.AddToCurr"...
0x97b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x980  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x985  dup
0x986  ldc.i4.s 9
0x988  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x98d  dup
0x98e  ldc.i4.0
0x98f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x994  dup
0x995  ldc.i4.0
0x996  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x99b  ret
```
