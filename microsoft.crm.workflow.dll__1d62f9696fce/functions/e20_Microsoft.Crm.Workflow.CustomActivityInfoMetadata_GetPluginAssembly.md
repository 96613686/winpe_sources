# Microsoft.Crm.Workflow.CustomActivityInfoMetadata::GetPluginAssembly

- ea: `0xe20`
- end: `0xeb7`
- name: `Microsoft.Crm.Workflow.CustomActivityInfoMetadata::GetPluginAssembly`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xe20`
- `0x1250`

## string_xrefs

- `0xe4d`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldarg.1
0xe21  ldarg.0
0xe22  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_pluginAssemblyId
0xe27  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe2c  brtrue.s loc_E36
0xe2e  ldarg.0
0xe2f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_pluginAssembly
0xe34  brtrue.s loc_EB0
0xe36  ldarg.0
0xe37  ldarg.1
0xe38  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_pluginAssemblyId
0xe3d  ldc.i4.8
0xe3e  newarr   [mscorlib]System.String
0xe43  dup
0xe44  ldc.i4.0
0xe45  ldstr    aName// "name"
0xe4a  stelem.ref
0xe4b  dup
0xe4c  ldc.i4.1
0xe4d  ldstr    aPublickeytoken// "publickeytoken"
0xe52  stelem.ref
0xe53  dup
0xe54  ldc.i4.2
0xe55  ldstr    aCulture// "culture"
0xe5a  stelem.ref
0xe5b  dup
0xe5c  ldc.i4.3
0xe5d  ldstr    aVersion// "version"
0xe62  stelem.ref
0xe63  dup
0xe64  ldc.i4.4
0xe65  ldstr    aContent// "content"
0xe6a  stelem.ref
0xe6b  dup
0xe6c  ldc.i4.5
0xe6d  ldstr    aSourcetype// "sourcetype"
0xe72  stelem.ref
0xe73  dup
0xe74  ldc.i4.6
0xe75  ldstr    aPath// "path"
0xe7a  stelem.ref
0xe7b  dup
0xe7c  ldc.i4.7
0xe7d  ldstr    aIsolationmode// "isolationmode"
0xe82  stelem.ref
0xe83  stloc.0
0xe84  ldarg.0
0xe85  ldarg.0
0xe86  ldfld    class Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_sdkCommand
0xe8b  ldc.i4   0xDE
0xe90  stloc.1
0xe91  ldloca.s 1
0xe93  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0xe99  callvirt instance string [mscorlib]System.Object::ToString()
0xe9e  ldarg.1
0xe9f  ldloc.0
0xea0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xea5  ldc.i4.0
0xea6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet, bool useSystemUserContext)
0xeab  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_pluginAssembly
0xeb0  ldarg.0
0xeb1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_pluginAssembly
0xeb6  ret
```
