# Microsoft.Crm.Transformations.Concatenate::GetPrefix

- ea: `0x200`
- end: `0x23c`
- name: `Microsoft.Crm.Transformations.Concatenate::GetPrefix`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x30`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x200  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x205  dup
0x206  ldstr    aMicrosoftCrmTr_3// "Microsoft.Crm.Transformations.Concatena"...
0x20b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x210  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x215  dup
0x216  ldstr    aMicrosoftCrmTr_4// "Microsoft.Crm.Transformations.Concatena"...
0x21b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x220  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x225  dup
0x226  ldc.i4.s 0x12
0x228  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x22d  dup
0x22e  ldc.i4.0
0x22f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x234  dup
0x235  ldc.i4.0
0x236  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x23b  ret
```
