# Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateHandlerInstance

- ea: `0x17900`
- end: `0x17a0e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateHandlerInstance`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8b140`

## callees

- `0x17900`

## string_xrefs

- `0x17908`: `ArticleTemplateHandler`
- `0x17916`: `ContractTemplateHandler`
- `0x17924`: `EmailTemplateHandler`
- `0x17932`: `Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler`
- `0x1793a`: `Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler`
- `0x17942`: `Microsoft.Crm.Tools.Common.ImportExportPublish.EmailTemplateHandler`
- `0x1794f`: `Microsoft.Crm.Tools.Common.ImportExportPublish.EmailTemplateHandler`
- `0x1795b`: `Microsoft.Crm.Tools.Common.ImportExportPublish`
- `0x1796f`: `Microsoft.Crm.Tools.Service.ImportExportPublish`

## pseudocode

```c

```

## disassembly

```asm
0x17900  ldsfld   string [mscorlib]System.String::Empty
0x17905  stloc.0
0x17906  ldarg.s  4
0x17908  ldstr    aArticletemplat// "ArticleTemplateHandler"
0x1790d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17912  brtrue.s loc_17932
0x17914  ldarg.s  4
0x17916  ldstr    aContracttempla_1// "ContractTemplateHandler"
0x1791b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17920  brtrue.s loc_1793A
0x17922  ldarg.s  4
0x17924  ldstr    aEmailtemplateh// "EmailTemplateHandler"
0x17929  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1792e  brtrue.s loc_17942
0x17930  br.s     loc_17948
0x17932  ldstr    aMicrosoftCrmTo// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x17937  stloc.0
0x17938  br.s     loc_17948
0x1793a  ldstr    aMicrosoftCrmTo_0// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x1793f  stloc.0
0x17940  br.s     loc_17948
0x17942  ldstr    aMicrosoftCrmTo_1// "Microsoft.Crm.Tools.Common.ImportExport"...
0x17947  stloc.0
0x17948  ldsfld   string [mscorlib]System.String::Empty
0x1794d  stloc.1
0x1794e  ldloc.0
0x1794f  ldstr    aMicrosoftCrmTo_1// "Microsoft.Crm.Tools.Common.ImportExport"...
0x17954  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17959  brfalse.s loc_1796F
0x1795b  ldstr    aMicrosoftCrmTo_2// "Microsoft.Crm.Tools.Common.ImportExport"...
0x17960  ldloc.0
0x17961  ldc.i4.0
0x17962  newarr   [mscorlib]System.Object
0x17967  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x1796c  stloc.1
0x1796d  br.s     loc_17981
0x1796f  ldstr    aMicrosoftCrmTo_3// "Microsoft.Crm.Tools.Service.ImportExpor"...
0x17974  ldloc.0
0x17975  ldc.i4.0
0x17976  newarr   [mscorlib]System.Object
0x1797b  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x17980  stloc.1
0x17981  ldloc.1
0x17982  ldc.i4.1
0x17983  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x17988  ldc.i4.s 0x24
0x1798a  ldnull
0x1798b  ldc.i4.s 0x20
0x1798d  ldc.i4.4
0x1798e  newarr   [mscorlib]System.Type
0x17993  dup
0x17994  ldc.i4.0
0x17995  ldtoken  Microsoft.Crm.Tools.ImportExportPublish.ExportTracer
0x1799a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1799f  stelem.ref
0x179a0  dup
0x179a1  ldc.i4.1
0x179a2  ldtoken  [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x179a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179ac  stelem.ref
0x179ad  dup
0x179ae  ldc.i4.2
0x179af  ldtoken  class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>
0x179b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179b9  stelem.ref
0x179ba  dup
0x179bb  ldc.i4.3
0x179bc  ldtoken  [mscorlib]System.Boolean
0x179c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179c6  stelem.ref
0x179c7  ldnull
0x179c8  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, valuetype [mscorlib]System.Reflection.CallingConventions, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x179cd  dup
0x179ce  ldnull
0x179cf  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Equality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x179d4  brfalse.s loc_179E8
0x179d6  ldstr    aCouldNotFindCo// "Could not find constructor of type "
0x179db  ldarg.s  4
0x179dd  call     string [mscorlib]System.String::Concat(string, string)
0x179e2  newobj   instance void [mscorlib]System.MissingMethodException::.ctor(string)
0x179e7  throw
0x179e8  ldc.i4.4
0x179e9  newarr   [mscorlib]System.Object
0x179ee  dup
0x179ef  ldc.i4.0
0x179f0  ldarg.0
0x179f1  stelem.ref
0x179f2  dup
0x179f3  ldc.i4.1
0x179f4  ldarg.1
0x179f5  stelem.ref
0x179f6  dup
0x179f7  ldc.i4.2
0x179f8  ldarg.2
0x179f9  stelem.ref
0x179fa  dup
0x179fb  ldc.i4.3
0x179fc  ldarg.3
0x179fd  box      [mscorlib]System.Boolean
0x17a02  stelem.ref
0x17a03  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x17a08  castclass Microsoft.Crm.Tools.ImportExportPublish.ExportHandler
0x17a0d  ret
```
