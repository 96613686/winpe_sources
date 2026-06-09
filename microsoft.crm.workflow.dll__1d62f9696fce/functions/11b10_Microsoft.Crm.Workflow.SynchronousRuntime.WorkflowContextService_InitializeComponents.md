# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContextService::InitializeComponents

- ea: `0x11b10`
- end: `0x11b3d`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContextService::InitializeComponents`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11ad0`

## callees

- `0x11b10`

## string_xrefs

- `0x11b26`: `Exception while initializing components: {0} `

## pseudocode

```c

```

## disassembly

```asm
0x11b10  ldarg.0
0x11b11  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::get_Instance()
0x11b16  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContextService::_pluginTypeCache
0x11b1b  leave.s  loc_11B3C
0x11b1d  stloc.0
0x11b1e  ldloc.0
0x11b1f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11b24  ldc.i4.s 0x1E
0x11b26  ldstr    aExceptionWhile// "Exception while initializing components"...
0x11b2b  ldc.i4.1
0x11b2c  newarr   [mscorlib]System.Object
0x11b31  dup
0x11b32  ldc.i4.0
0x11b33  ldloc.0
0x11b34  stelem.ref
0x11b35  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11b3a  rethrow
0x11b3c  ret
```
