# Microsoft.Crm.Transformations.AddToDate::GetTimeOffset

- ea: `0x11a0`
- end: `0x11dc`
- name: `Microsoft.Crm.Transformations.AddToDate::GetTimeOffset`
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
0x11a0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x11a5  dup
0x11a6  ldstr    aMicrosoftCrmTr_65// "Microsoft.Crm.Transformations.AddToDate"...
0x11ab  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x11b0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x11b5  dup
0x11b6  ldstr    aMicrosoftCrmTr_66// "Microsoft.Crm.Transformations.AddToDate"...
0x11bb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x11c0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x11c5  dup
0x11c6  ldc.i4.s 0x10
0x11c8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x11cd  dup
0x11ce  ldc.i4.0
0x11cf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x11d4  dup
0x11d5  ldc.i4.0
0x11d6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x11db  ret
```
