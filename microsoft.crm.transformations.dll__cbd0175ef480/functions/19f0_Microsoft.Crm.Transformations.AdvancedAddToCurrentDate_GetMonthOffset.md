# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMonthOffset

- ea: `0x19f0`
- end: `0x1a2c`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetMonthOffset`
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
0x19f0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x19f5  dup
0x19f6  ldstr    aMicrosoftCrmTr_77// "Microsoft.Crm.Transformations.AdvancedA"...
0x19fb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1a00  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1a05  dup
0x1a06  ldstr    aMicrosoftCrmTr_78// "Microsoft.Crm.Transformations.AdvancedA"...
0x1a0b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1a10  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1a15  dup
0x1a16  ldc.i4.s 9
0x1a18  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1a1d  dup
0x1a1e  ldc.i4.0
0x1a1f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1a24  dup
0x1a25  ldc.i4.0
0x1a26  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1a2b  ret
```
