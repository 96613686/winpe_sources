# Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateImportHandlerInstance

- ea: `0x17a10`
- end: `0x17b50`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateImportHandlerInstance`
- size: `320`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x9840`
- `0x7f600`
- `0x7f810`

## callees

- `0x17a10`

## string_xrefs

- `0x17a18`: `ImportArticleTemplateHandler`
- `0x17a42`: `Microsoft.Crm.Tools.Service.ImportExportPublish`
- `0x17a26`: `ImportContractTemplateHandler`
- `0x17a34`: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler`
- `0x17a3c`: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler`

## pseudocode

```c

```

## disassembly

```asm
0x17a10  ldsfld   string [mscorlib]System.String::Empty
0x17a15  stloc.0
0x17a16  ldarg.s  5
0x17a18  ldstr    aImportarticlet// "ImportArticleTemplateHandler"
0x17a1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17a22  brtrue.s loc_17A34
0x17a24  ldarg.s  5
0x17a26  ldstr    aImportcontract// "ImportContractTemplateHandler"
0x17a2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17a30  brtrue.s loc_17A3C
0x17a32  br.s     loc_17A42
0x17a34  ldstr    aMicrosoftCrmTo_4// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x17a39  stloc.0
0x17a3a  br.s     loc_17A42
0x17a3c  ldstr    aMicrosoftCrmTo_5// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x17a41  stloc.0
0x17a42  ldstr    aMicrosoftCrmTo_3// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x17a47  ldloc.0
0x17a48  ldc.i4.0
0x17a49  newarr   [mscorlib]System.Object
0x17a4e  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x17a53  ldc.i4.1
0x17a54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x17a59  stloc.1
0x17a5a  ldloc.1
0x17a5b  ldc.i4.s 0x24
0x17a5d  ldnull
0x17a5e  ldc.i4.s 0x20
0x17a60  ldc.i4.7
0x17a61  newarr   [mscorlib]System.Type
0x17a66  dup
0x17a67  ldc.i4.0
0x17a68  ldtoken  [System.Xml]System.Xml.XmlDocument
0x17a6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a72  stelem.ref
0x17a73  dup
0x17a74  ldc.i4.1
0x17a75  ldtoken  [mscorlib]System.String
0x17a7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a7f  stelem.ref
0x17a80  dup
0x17a81  ldc.i4.2
0x17a82  ldtoken  [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x17a87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a8c  stelem.ref
0x17a8d  dup
0x17a8e  ldc.i4.3
0x17a8f  ldtoken  Microsoft.Crm.Tools.ImportExportPublish.ImportHelper
0x17a94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a99  stelem.ref
0x17a9a  dup
0x17a9b  ldc.i4.4
0x17a9c  ldtoken  Microsoft.Crm.Tools.ImportExportPublish.ImportTracer
0x17aa1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17aa6  stelem.ref
0x17aa7  dup
0x17aa8  ldc.i4.5
0x17aa9  ldtoken  Microsoft.Crm.Tools.ImportExportPublish.ImportXml
0x17aae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ab3  stelem.ref
0x17ab4  dup
0x17ab5  ldc.i4.6
0x17ab6  ldtoken  [mscorlib]System.String
0x17abb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ac0  stelem.ref
0x17ac1  ldnull
0x17ac2  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, valuetype [mscorlib]System.Reflection.CallingConventions, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x17ac7  dup
0x17ac8  ldnull
0x17ac9  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Equality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x17ace  brfalse.s loc_17AE2
0x17ad0  ldstr    aCouldNotFindCo// "Could not find constructor of type "
0x17ad5  ldarg.s  5
0x17ad7  call     string [mscorlib]System.String::Concat(string, string)
0x17adc  newobj   instance void [mscorlib]System.MissingMethodException::.ctor(string)
0x17ae1  throw
0x17ae2  ldc.i4.7
0x17ae3  newarr   [mscorlib]System.Object
0x17ae8  dup
0x17ae9  ldc.i4.0
0x17aea  ldarg.0
0x17aeb  stelem.ref
0x17aec  dup
0x17aed  ldc.i4.1
0x17aee  ldarg.1
0x17aef  stelem.ref
0x17af0  dup
0x17af1  ldc.i4.2
0x17af2  ldarg.2
0x17af3  stelem.ref
0x17af4  dup
0x17af5  ldc.i4.3
0x17af6  ldarg.3
0x17af7  stelem.ref
0x17af8  dup
0x17af9  ldc.i4.4
0x17afa  ldarg.s  4
0x17afc  stelem.ref
0x17afd  dup
0x17afe  ldc.i4.5
0x17aff  ldarg.s  6
0x17b01  stelem.ref
0x17b02  dup
0x17b03  ldc.i4.6
0x17b04  ldarg.s  8
0x17b06  stelem.ref
0x17b07  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x17b0c  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportHandler
0x17b11  stloc.2
0x17b12  ldarg.s  7
0x17b14  brfalse.s loc_17B4E
0x17b16  ldloc.1
0x17b17  ldstr    aImportitem// "ImportItem"
0x17b1c  ldc.i4.s 0x24
0x17b1e  ldnull
0x17b1f  ldc.i4.1
0x17b20  newarr   [mscorlib]System.Type
0x17b25  dup
0x17b26  ldc.i4.0
0x17b27  ldtoken  [mscorlib]System.Boolean
0x17b2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17b31  stelem.ref
0x17b32  ldnull
0x17b33  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x17b38  ldloc.2
0x17b39  ldc.i4.1
0x17b3a  newarr   [mscorlib]System.Object
0x17b3f  dup
0x17b40  ldc.i4.0
0x17b41  ldc.i4.1
0x17b42  box      [mscorlib]System.Boolean
0x17b47  stelem.ref
0x17b48  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x17b4d  pop
0x17b4e  ldloc.2
0x17b4f  ret
```
