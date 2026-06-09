# Microsoft.Crm.Transformations.AddToDate::GetDate

- ea: `0x10a0`
- end: `0x10dc`
- name: `Microsoft.Crm.Transformations.AddToDate::GetDate`
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
0x10a0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x10a5  dup
0x10a6  ldstr    aMicrosoftCrmTr_57// "Microsoft.Crm.Transformations.AddToDate"...
0x10ab  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x10b0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x10b5  dup
0x10b6  ldstr    aMicrosoftCrmTr_58// "Microsoft.Crm.Transformations.AddToDate"...
0x10bb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x10c0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x10c5  dup
0x10c6  ldc.i4.s 0x10
0x10c8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x10cd  dup
0x10ce  ldc.i4.1
0x10cf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x10d4  dup
0x10d5  ldc.i4.0
0x10d6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x10db  ret
```
