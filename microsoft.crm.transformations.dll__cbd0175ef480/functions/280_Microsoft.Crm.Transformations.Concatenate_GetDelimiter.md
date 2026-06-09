# Microsoft.Crm.Transformations.Concatenate::GetDelimiter

- ea: `0x280`
- end: `0x2c2`
- name: `Microsoft.Crm.Transformations.Concatenate::GetDelimiter`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x30`

## callees

- `0x2d0`
- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x280  ldarg.0
0x281  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.Concatenate::GetDelimiterOptions()
0x286  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0x28b  dup
0x28c  ldstr    aMicrosoftCrmTr_7// "Microsoft.Crm.Transformations.Concatena"...
0x291  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x296  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x29b  dup
0x29c  ldstr    aMicrosoftCrmTr_8// "Microsoft.Crm.Transformations.Concatena"...
0x2a1  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2a6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x2ab  dup
0x2ac  ldc.i4.s 0x12
0x2ae  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x2b3  dup
0x2b4  ldc.i4.0
0x2b5  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x2ba  dup
0x2bb  ldc.i4.0
0x2bc  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x2c1  ret
```
