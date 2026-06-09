# Microsoft.Crm.Transformations.Replace::GetReplaceString

- ea: `0x1fc0`
- end: `0x1ffc`
- name: `Microsoft.Crm.Transformations.Replace::GetReplaceString`
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

- `0x1fc6`: `Microsoft.Crm.Transformations.Replace.InputParameter.ReplaceString.Name`
- `0x1fd6`: `Microsoft.Crm.Transformations.Replace.InputParameter.ReplaceString.Description`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::.ctor()
0x1fc5  dup
0x1fc6  ldstr    aMicrosoftCrmTr_107// "Microsoft.Crm.Transformations.Replace.I"...
0x1fcb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1fd0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1fd5  dup
0x1fd6  ldstr    aMicrosoftCrmTr_108// "Microsoft.Crm.Transformations.Replace.I"...
0x1fdb  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1fe0  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1fe5  dup
0x1fe6  ldc.i4.s 0x12
0x1fe8  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1fed  dup
0x1fee  ldc.i4.0
0x1fef  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsMandatory(bool)
0x1ff4  dup
0x1ff5  ldc.i4.0
0x1ff6  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterDescription::set_IsAnArray(bool)
0x1ffb  ret
```
