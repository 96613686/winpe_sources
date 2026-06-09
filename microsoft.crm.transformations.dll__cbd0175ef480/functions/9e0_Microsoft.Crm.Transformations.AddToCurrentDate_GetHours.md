# Microsoft.Crm.Transformations.AddToCurrentDate::GetHours

- ea: `0x9e0`
- end: `0xa1c`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetHours`
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
0x9e0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x9e5  dup
0x9e6  ldstr    aMicrosoftCrmTr_29// "Microsoft.Crm.Transformations.AddToCurr"...
0x9eb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x9f0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x9f5  dup
0x9f6  ldstr    aMicrosoftCrmTr_30// "Microsoft.Crm.Transformations.AddToCurr"...
0x9fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xa00  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0xa05  dup
0xa06  ldc.i4.s 9
0xa08  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0xa0d  dup
0xa0e  ldc.i4.0
0xa0f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0xa14  dup
0xa15  ldc.i4.0
0xa16  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0xa1b  ret
```
