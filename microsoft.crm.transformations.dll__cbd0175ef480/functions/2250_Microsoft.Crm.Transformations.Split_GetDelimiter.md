# Microsoft.Crm.Transformations.Split::GetDelimiter

- ea: `0x2250`
- end: `0x2292`
- name: `Microsoft.Crm.Transformations.Split::GetDelimiter`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2080`

## callees

- `0x22a0`
- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldarg.0
0x2251  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[] Microsoft.Crm.Transformations.Split::GetDelimiterOptions()
0x2256  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor(class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterOption[])
0x225b  dup
0x225c  ldstr    aMicrosoftCrmTr_114// "Microsoft.Crm.Transformations.Split.Inp"...
0x2261  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2266  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x226b  dup
0x226c  ldstr    aMicrosoftCrmTr_115// "Microsoft.Crm.Transformations.Split.Inp"...
0x2271  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2276  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x227b  dup
0x227c  ldc.i4.s 0x12
0x227e  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x2283  dup
0x2284  ldc.i4.1
0x2285  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x228a  dup
0x228b  ldc.i4.0
0x228c  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x2291  ret
```
