# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetDayOffset

- ea: `0x1a80`
- end: `0x1abc`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetDayOffset`
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
0x1a80  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1a85  dup
0x1a86  ldstr    aMicrosoftCrmTr_81// "Microsoft.Crm.Transformations.AdvancedA"...
0x1a8b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1a90  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1a95  dup
0x1a96  ldstr    aMicrosoftCrmTr_82// "Microsoft.Crm.Transformations.AdvancedA"...
0x1a9b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1aa0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1aa5  dup
0x1aa6  ldc.i4.s 9
0x1aa8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1aad  dup
0x1aae  ldc.i4.0
0x1aaf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1ab4  dup
0x1ab5  ldc.i4.0
0x1ab6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1abb  ret
```
