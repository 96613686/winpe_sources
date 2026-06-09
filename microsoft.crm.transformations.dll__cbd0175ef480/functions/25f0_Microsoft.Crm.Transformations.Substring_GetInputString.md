# Microsoft.Crm.Transformations.Substring::GetInputString

- ea: `0x25f0`
- end: `0x262c`
- name: `Microsoft.Crm.Transformations.Substring::GetInputString`
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
0x25f0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x25f5  dup
0x25f6  ldstr    aMicrosoftCrmTr_128// "Microsoft.Crm.Transformations.Substring"...
0x25fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2600  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x2605  dup
0x2606  ldstr    aMicrosoftCrmTr_129// "Microsoft.Crm.Transformations.Substring"...
0x260b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2610  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x2615  dup
0x2616  ldc.i4.s 0x12
0x2618  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x261d  dup
0x261e  ldc.i4.1
0x261f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x2624  dup
0x2625  ldc.i4.0
0x2626  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x262b  ret
```
