# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetHours

- ea: `0x1b10`
- end: `0x1b4c`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetHours`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1260`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x1b10  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1b15  dup
0x1b16  ldstr    aMicrosoftCrmTr_85// "Microsoft.Crm.Transformations.AdvancedA"...
0x1b1b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1b20  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1b25  dup
0x1b26  ldstr    aMicrosoftCrmTr_86// "Microsoft.Crm.Transformations.AdvancedA"...
0x1b2b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1b30  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1b35  dup
0x1b36  ldc.i4.s 9
0x1b38  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1b3d  dup
0x1b3e  ldc.i4.0
0x1b3f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1b44  dup
0x1b45  ldc.i4.0
0x1b46  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1b4b  ret
```
