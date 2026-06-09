# Microsoft.Crm.Transformations.Replace::GetInputString

- ea: `0x2000`
- end: `0x203c`
- name: `Microsoft.Crm.Transformations.Replace::GetInputString`
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

- `0x2006`: `Microsoft.Crm.Transformations.Replace.InputParameter.InputString.Name`
- `0x2016`: `Microsoft.Crm.Transformations.Replace.InputParameter.InputString.Description`

## pseudocode

```c

```

## disassembly

```asm
0x2000  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x2005  dup
0x2006  ldstr    aMicrosoftCrmTr_109// "Microsoft.Crm.Transformations.Replace.I"...
0x200b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2010  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x2015  dup
0x2016  ldstr    aMicrosoftCrmTr_110// "Microsoft.Crm.Transformations.Replace.I"...
0x201b  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x2020  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x2025  dup
0x2026  ldc.i4.s 0x12
0x2028  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x202d  dup
0x202e  ldc.i4.1
0x202f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x2034  dup
0x2035  ldc.i4.0
0x2036  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x203b  ret
```
