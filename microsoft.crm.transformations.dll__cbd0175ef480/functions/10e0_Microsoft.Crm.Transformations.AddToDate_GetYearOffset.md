# Microsoft.Crm.Transformations.AddToDate::GetYearOffset

- ea: `0x10e0`
- end: `0x111c`
- name: `Microsoft.Crm.Transformations.AddToDate::GetYearOffset`
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
0x10e0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x10e5  dup
0x10e6  ldstr    aMicrosoftCrmTr_59// "Microsoft.Crm.Transformations.AddToDate"...
0x10eb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x10f0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x10f5  dup
0x10f6  ldstr    aMicrosoftCrmTr_60// "Microsoft.Crm.Transformations.AddToDate"...
0x10fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1100  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1105  dup
0x1106  ldc.i4.s 9
0x1108  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x110d  dup
0x110e  ldc.i4.0
0x110f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1114  dup
0x1115  ldc.i4.0
0x1116  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x111b  ret
```
