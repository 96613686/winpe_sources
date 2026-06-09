# Microsoft.Crm.Transformations.Concatenate::GetInputString

- ea: `0x3c0`
- end: `0x3fc`
- name: `Microsoft.Crm.Transformations.Concatenate::GetInputString`
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
0x3c0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x3c5  dup
0x3c6  ldstr    aMicrosoftCrmTr_17// "Microsoft.Crm.Transformations.Concatena"...
0x3cb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x3d0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x3d5  dup
0x3d6  ldstr    aMicrosoftCrmTr_18// "Microsoft.Crm.Transformations.Concatena"...
0x3db  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x3e0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x3e5  dup
0x3e6  ldc.i4.s 0x12
0x3e8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x3ed  dup
0x3ee  ldc.i4.1
0x3ef  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x3f4  dup
0x3f5  ldc.i4.1
0x3f6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x3fb  ret
```
