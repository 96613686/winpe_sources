# Microsoft.Crm.Transformations.AddToDate::GetDayOffset

- ea: `0x1160`
- end: `0x119c`
- name: `Microsoft.Crm.Transformations.AddToDate::GetDayOffset`
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
0x1160  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1165  dup
0x1166  ldstr    aMicrosoftCrmTr_63// "Microsoft.Crm.Transformations.AddToDate"...
0x116b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1170  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1175  dup
0x1176  ldstr    aMicrosoftCrmTr_64// "Microsoft.Crm.Transformations.AddToDate"...
0x117b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1180  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1185  dup
0x1186  ldc.i4.s 9
0x1188  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x118d  dup
0x118e  ldc.i4.0
0x118f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1194  dup
0x1195  ldc.i4.0
0x1196  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x119b  ret
```
