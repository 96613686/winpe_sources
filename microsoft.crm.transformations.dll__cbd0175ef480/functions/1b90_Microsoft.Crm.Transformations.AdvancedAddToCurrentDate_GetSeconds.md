# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetSeconds

- ea: `0x1b90`
- end: `0x1bcc`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetSeconds`
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
0x1b90  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1b95  dup
0x1b96  ldstr    aMicrosoftCrmTr_89// "Microsoft.Crm.Transformations.AdvancedA"...
0x1b9b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1ba0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1ba5  dup
0x1ba6  ldstr    aMicrosoftCrmTr_90// "Microsoft.Crm.Transformations.AdvancedA"...
0x1bab  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1bb0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1bb5  dup
0x1bb6  ldc.i4.s 9
0x1bb8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1bbd  dup
0x1bbe  ldc.i4.0
0x1bbf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1bc4  dup
0x1bc5  ldc.i4.0
0x1bc6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1bcb  ret
```
