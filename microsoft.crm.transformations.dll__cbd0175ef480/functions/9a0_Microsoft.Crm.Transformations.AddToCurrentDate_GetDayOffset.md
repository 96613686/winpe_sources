# Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOffset

- ea: `0x9a0`
- end: `0x9dc`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOffset`
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
0x9a0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x9a5  dup
0x9a6  ldstr    aMicrosoftCrmTr_27// "Microsoft.Crm.Transformations.AddToCurr"...
0x9ab  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x9b0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x9b5  dup
0x9b6  ldstr    aMicrosoftCrmTr_28// "Microsoft.Crm.Transformations.AddToCurr"...
0x9bb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x9c0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x9c5  dup
0x9c6  ldc.i4.s 9
0x9c8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x9cd  dup
0x9ce  ldc.i4.0
0x9cf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x9d4  dup
0x9d5  ldc.i4.0
0x9d6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x9db  ret
```
