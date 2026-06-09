# Microsoft.Crm.Transformations.Concatenate::GetSuffix

- ea: `0x240`
- end: `0x27c`
- name: `Microsoft.Crm.Transformations.Concatenate::GetSuffix`
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
0x240  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x245  dup
0x246  ldstr    aMicrosoftCrmTr_5// "Microsoft.Crm.Transformations.Concatena"...
0x24b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x250  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x255  dup
0x256  ldstr    aMicrosoftCrmTr_6// "Microsoft.Crm.Transformations.Concatena"...
0x25b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x260  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x265  dup
0x266  ldc.i4.s 0x12
0x268  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x26d  dup
0x26e  ldc.i4.0
0x26f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x274  dup
0x275  ldc.i4.0
0x276  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x27b  ret
```
