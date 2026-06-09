# Microsoft.Crm.Transformations.Substring::GetStartIndex

- ea: `0x2570`
- end: `0x25ac`
- name: `Microsoft.Crm.Transformations.Substring::GetStartIndex`
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
0x2570  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x2575  dup
0x2576  ldstr    aMicrosoftCrmTr_124// "Microsoft.Crm.Transformations.Substring"...
0x257b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2580  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x2585  dup
0x2586  ldstr    aMicrosoftCrmTr_125// "Microsoft.Crm.Transformations.Substring"...
0x258b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2590  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x2595  dup
0x2596  ldc.i4.s 9
0x2598  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x259d  dup
0x259e  ldc.i4.1
0x259f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x25a4  dup
0x25a5  ldc.i4.0
0x25a6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x25ab  ret
```
