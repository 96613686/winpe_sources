# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetYearOffset

- ea: `0x1960`
- end: `0x199c`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetYearOffset`
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
0x1960  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1965  dup
0x1966  ldstr    aMicrosoftCrmTr_73// "Microsoft.Crm.Transformations.AdvancedA"...
0x196b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1970  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1975  dup
0x1976  ldstr    aMicrosoftCrmTr_74// "Microsoft.Crm.Transformations.AdvancedA"...
0x197b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1980  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1985  dup
0x1986  ldc.i4.s 9
0x1988  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x198d  dup
0x198e  ldc.i4.0
0x198f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1994  dup
0x1995  ldc.i4.0
0x1996  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x199b  ret
```
