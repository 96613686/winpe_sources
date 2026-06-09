# Microsoft.Crm.Transformations.Split::GetInputString

- ea: `0x22f0`
- end: `0x232c`
- name: `Microsoft.Crm.Transformations.Split::GetInputString`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2080`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x22f0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x22f5  dup
0x22f6  ldstr    aMicrosoftCrmTr_118// "Microsoft.Crm.Transformations.Split.Inp"...
0x22fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2300  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x2305  dup
0x2306  ldstr    aMicrosoftCrmTr_119// "Microsoft.Crm.Transformations.Split.Inp"...
0x230b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2310  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x2315  dup
0x2316  ldc.i4.s 0x12
0x2318  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x231d  dup
0x231e  ldc.i4.1
0x231f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x2324  dup
0x2325  ldc.i4.0
0x2326  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x232b  ret
```
