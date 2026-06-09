# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMinutes

- ea: `0x1b50`
- end: `0x1b8c`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMinutes`
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
0x1b50  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1b55  dup
0x1b56  ldstr    aMicrosoftCrmTr_87// "Microsoft.Crm.Transformations.AdvancedA"...
0x1b5b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1b60  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1b65  dup
0x1b66  ldstr    aMicrosoftCrmTr_88// "Microsoft.Crm.Transformations.AdvancedA"...
0x1b6b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1b70  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1b75  dup
0x1b76  ldc.i4.s 9
0x1b78  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1b7d  dup
0x1b7e  ldc.i4.0
0x1b7f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1b84  dup
0x1b85  ldc.i4.0
0x1b86  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1b8b  ret
```
