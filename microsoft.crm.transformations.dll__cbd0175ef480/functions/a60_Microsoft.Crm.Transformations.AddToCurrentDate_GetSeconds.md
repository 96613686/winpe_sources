# Microsoft.Crm.Transformations.AddToCurrentDate::GetSeconds

- ea: `0xa60`
- end: `0xa9c`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetSeconds`
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
0xa60  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0xa65  dup
0xa66  ldstr    aMicrosoftCrmTr_33// "Microsoft.Crm.Transformations.AddToCurr"...
0xa6b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xa70  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0xa75  dup
0xa76  ldstr    aMicrosoftCrmTr_34// "Microsoft.Crm.Transformations.AddToCurr"...
0xa7b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xa80  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0xa85  dup
0xa86  ldc.i4.s 9
0xa88  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0xa8d  dup
0xa8e  ldc.i4.0
0xa8f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0xa94  dup
0xa95  ldc.i4.0
0xa96  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0xa9b  ret
```
