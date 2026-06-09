# Microsoft.Crm.Transformations.AddToCurrentDate::GetYearOffset

- ea: `0x920`
- end: `0x95c`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetYearOffset`
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
0x920  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x925  dup
0x926  ldstr    aMicrosoftCrmTr_23// "Microsoft.Crm.Transformations.AddToCurr"...
0x92b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x930  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x935  dup
0x936  ldstr    aMicrosoftCrmTr_24// "Microsoft.Crm.Transformations.AddToCurr"...
0x93b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x940  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x945  dup
0x946  ldc.i4.s 9
0x948  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x94d  dup
0x94e  ldc.i4.0
0x94f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x954  dup
0x955  ldc.i4.0
0x956  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x95b  ret
```
