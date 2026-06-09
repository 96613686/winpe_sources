# Microsoft.Crm.Transformations.AddToDate::GetMonthOffset

- ea: `0x1120`
- end: `0x115c`
- name: `Microsoft.Crm.Transformations.AddToDate::GetMonthOffset`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd10`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x1120  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1125  dup
0x1126  ldstr    aMicrosoftCrmTr_61// "Microsoft.Crm.Transformations.AddToDate"...
0x112b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1130  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1135  dup
0x1136  ldstr    aMicrosoftCrmTr_62// "Microsoft.Crm.Transformations.AddToDate"...
0x113b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1140  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1145  dup
0x1146  ldc.i4.s 9
0x1148  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x114d  dup
0x114e  ldc.i4.0
0x114f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1154  dup
0x1155  ldc.i4.0
0x1156  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x115b  ret
```
