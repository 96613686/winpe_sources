# Microsoft.Crm.Transformations.Substring::GetLength

- ea: `0x25b0`
- end: `0x25ec`
- name: `Microsoft.Crm.Transformations.Substring::GetLength`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2370`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x25b5  dup
0x25b6  ldstr    aMicrosoftCrmTr_126// "Microsoft.Crm.Transformations.Substring"...
0x25bb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x25c0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x25c5  dup
0x25c6  ldstr    aMicrosoftCrmTr_127// "Microsoft.Crm.Transformations.Substring"...
0x25cb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x25d0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x25d5  dup
0x25d6  ldc.i4.s 9
0x25d8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x25dd  dup
0x25de  ldc.i4.0
0x25df  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x25e4  dup
0x25e5  ldc.i4.0
0x25e6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x25eb  ret
```
