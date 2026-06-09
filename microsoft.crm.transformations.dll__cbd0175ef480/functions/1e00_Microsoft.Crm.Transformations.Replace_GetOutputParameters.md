# Microsoft.Crm.Transformations.Replace::GetOutputParameters

- ea: `0x1e00`
- end: `0x1e39`
- name: `Microsoft.Crm.Transformations.Replace::GetOutputParameters`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2740`

## string_xrefs

- `0x1e07`: `Microsoft.Crm.Transformations.Replace.OutputParameter.OutputString.Name`
- `0x1e17`: `Microsoft.Crm.Transformations.Replace.OutputParameter.OutputString.Description`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.OutputParameterDescription::.ctor()
0x1e05  stloc.0
0x1e06  ldloc.0
0x1e07  ldstr    aMicrosoftCrmTr_103// "Microsoft.Crm.Transformations.Replace.O"...
0x1e0c  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1e11  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Name(string)
0x1e16  ldloc.0
0x1e17  ldstr    aMicrosoftCrmTr_104// "Microsoft.Crm.Transformations.Replace.O"...
0x1e1c  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1e21  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_Description(string)
0x1e26  ldloc.0
0x1e27  ldc.i4.s 0x12
0x1e29  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ParameterDescription::set_DataType(valuetype [mscorlib]System.TypeCode)
0x1e2e  ldc.i4.1
0x1e2f  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IOutputParameterDescription
0x1e34  dup
0x1e35  ldc.i4.0
0x1e36  ldloc.0
0x1e37  stelem.ref
0x1e38  ret
```
