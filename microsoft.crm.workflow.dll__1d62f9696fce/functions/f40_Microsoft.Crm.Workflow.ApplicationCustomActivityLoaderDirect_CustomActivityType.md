# Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::CustomActivityType

- ea: `0xf40`
- end: `0xfab`
- name: `Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::CustomActivityType`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xf40`
- `0x1020`
- `0x1250`

## string_xrefs

- `0xf4a`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0xf40  ldnull
0xf41  stloc.0
0xf42  ldc.i4.2
0xf43  newarr   [mscorlib]System.String
0xf48  dup
0xf49  ldc.i4.0
0xf4a  ldstr    aPluginassembly// "pluginassemblyid"
0xf4f  stelem.ref
0xf50  dup
0xf51  ldc.i4.1
0xf52  ldstr    aTypename// "typename"
0xf57  stelem.ref
0xf58  stloc.1
0xf59  ldarg.0
0xf5a  ldfld    class Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::_sdkCommand
0xf5f  ldc.i4   0xE0
0xf64  stloc.s  4
0xf66  ldloca.s 4
0xf68  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0xf6e  callvirt instance string [mscorlib]System.Object::ToString()
0xf73  ldarg.1
0xf74  ldloc.1
0xf75  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xf7a  ldc.i4.0
0xf7b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet, bool useSystemUserContext)
0xf80  stloc.2
0xf81  ldarg.0
0xf82  ldloc.2
0xf83  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Workflow.ApplicationCustomActivityLoaderDirect::CustomActivityAssembly(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity)
0xf88  stloc.3
0xf89  ldloc.3
0xf8a  ldnull
0xf8b  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0xf90  brfalse.s loc_FA9
0xf92  ldloc.3
0xf93  ldloc.2
0xf94  ldstr    aTypename// "typename"
0xf99  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xf9e  castclass [mscorlib]System.String
0xfa3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0xfa8  stloc.0
0xfa9  ldloc.0
0xfaa  ret
```
