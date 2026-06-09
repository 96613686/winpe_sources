# Microsoft.Crm.Transformations.AddToCurrentDate::GetMinutes

- ea: `0xa20`
- end: `0xa5c`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetMinutes`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x440`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0xa20  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0xa25  dup
0xa26  ldstr    aMicrosoftCrmTr_31// "Microsoft.Crm.Transformations.AddToCurr"...
0xa2b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xa30  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0xa35  dup
0xa36  ldstr    aMicrosoftCrmTr_32// "Microsoft.Crm.Transformations.AddToCurr"...
0xa3b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xa40  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0xa45  dup
0xa46  ldc.i4.s 9
0xa48  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0xa4d  dup
0xa4e  ldc.i4.0
0xa4f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0xa54  dup
0xa55  ldc.i4.0
0xa56  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0xa5b  ret
```
