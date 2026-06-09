# Microsoft.Crm.Transformations.Replace::GetSearchString

- ea: `0x1f80`
- end: `0x1fbc`
- name: `Microsoft.Crm.Transformations.Replace::GetSearchString`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1dd0`

## callees

- `0x2740`

## string_xrefs

- `0x1f86`: `Microsoft.Crm.Transformations.Replace.InputParameter.SearchString.Name`
- `0x1f96`: `Microsoft.Crm.Transformations.Replace.InputParameter.SearchString.Description`

## pseudocode

```c

```

## disassembly

```asm
0x1f80  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1f85  dup
0x1f86  ldstr    aMicrosoftCrmTr_105// "Microsoft.Crm.Transformations.Replace.I"...
0x1f8b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1f90  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1f95  dup
0x1f96  ldstr    aMicrosoftCrmTr_106// "Microsoft.Crm.Transformations.Replace.I"...
0x1f9b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1fa0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1fa5  dup
0x1fa6  ldc.i4.s 0x12
0x1fa8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1fad  dup
0x1fae  ldc.i4.1
0x1faf  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1fb4  dup
0x1fb5  ldc.i4.0
0x1fb6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1fbb  ret
```
