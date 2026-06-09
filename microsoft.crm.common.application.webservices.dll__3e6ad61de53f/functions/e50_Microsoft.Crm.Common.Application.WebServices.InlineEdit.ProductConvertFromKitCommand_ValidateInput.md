# Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::ValidateInput

- ea: `0xe50`
- end: `0xea5`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::ValidateInput`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe00`

## callees

- `0xe50`

## string_xrefs

- `0xe65`: `commandXml is invalid`

## pseudocode

```c

```

## disassembly

```asm
0xe50  ldarg.0
0xe51  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::_convertProductFromKitInputParameter
0xe56  brtrue.s loc_E71
0xe58  ldc.i4   0x80040356
0xe5d  ldc.i4.1
0xe5e  newarr   [mscorlib]System.Object
0xe63  dup
0xe64  ldc.i4.0
0xe65  ldstr    aCommandxmlIsIn// "commandXml is invalid"
0xe6a  stelem.ref
0xe6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe70  throw
0xe71  ldarg.0
0xe72  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::_convertProductFromKitInputParameter
0xe77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xe7c  stloc.0
0xe7d  ldloca.s 0
0xe7f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe84  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xe89  brfalse.s loc_EA4
0xe8b  ldc.i4   0x80040356
0xe90  ldc.i4.1
0xe91  newarr   [mscorlib]System.Object
0xe96  dup
0xe97  ldc.i4.0
0xe98  ldstr    aEntityIdLogica// "Entity Id, logical name or statecode is"...
0xe9d  stelem.ref
0xe9e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xea3  throw
0xea4  ret
```
