# Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::ValidateInput

- ea: `0xf30`
- end: `0xf85`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::ValidateInput`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xee0`

## callees

- `0xf30`

## string_xrefs

- `0xf45`: `commandXml is invalid`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.0
0xf31  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::_convertProductToKitInputParameter
0xf36  brtrue.s loc_F51
0xf38  ldc.i4   0x80040356
0xf3d  ldc.i4.1
0xf3e  newarr   [mscorlib]System.Object
0xf43  dup
0xf44  ldc.i4.0
0xf45  ldstr    aCommandxmlIsIn// "commandXml is invalid"
0xf4a  stelem.ref
0xf4b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xf50  throw
0xf51  ldarg.0
0xf52  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::_convertProductToKitInputParameter
0xf57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xf5c  stloc.0
0xf5d  ldloca.s 0
0xf5f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf64  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xf69  brfalse.s loc_F84
0xf6b  ldc.i4   0x80040356
0xf70  ldc.i4.1
0xf71  newarr   [mscorlib]System.Object
0xf76  dup
0xf77  ldc.i4.0
0xf78  ldstr    aEntityIdLogica// "Entity Id, logical name or statecode is"...
0xf7d  stelem.ref
0xf7e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xf83  throw
0xf84  ret
```
