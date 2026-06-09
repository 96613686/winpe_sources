# Microsoft.Crm.Workflow.CustomActivityInfoMetadata::GetPluginTypeEntity

- ea: `0xdc0`
- end: `0xe16`
- name: `Microsoft.Crm.Workflow.CustomActivityInfoMetadata::GetPluginTypeEntity`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1250`

## string_xrefs

- `0xdd0`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldc.i4.5
0xdc1  newarr   [mscorlib]System.String
0xdc6  dup
0xdc7  ldc.i4.0
0xdc8  ldstr    aTypename// "typename"
0xdcd  stelem.ref
0xdce  dup
0xdcf  ldc.i4.1
0xdd0  ldstr    aPluginassembly// "pluginassemblyid"
0xdd5  stelem.ref
0xdd6  dup
0xdd7  ldc.i4.2
0xdd8  ldstr    aName// "name"
0xddd  stelem.ref
0xdde  dup
0xddf  ldc.i4.3
0xde0  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0xde5  stelem.ref
0xde6  dup
0xde7  ldc.i4.4
0xde8  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0xded  stelem.ref
0xdee  stloc.0
0xdef  ldarg.0
0xdf0  ldfld    class Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Workflow.CustomActivityInfoMetadata::_sdkCommand
0xdf5  ldc.i4   0xE0
0xdfa  stloc.1
0xdfb  ldloca.s 1
0xdfd  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0xe03  callvirt instance string [mscorlib]System.Object::ToString()
0xe08  ldarg.1
0xe09  ldloc.0
0xe0a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xe0f  ldc.i4.0
0xe10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet, bool useSystemUserContext)
0xe15  ret
```
