# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetTransactionContextId

- ea: `0x8090`
- end: `0x80d4`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetTransactionContextId`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`

## callees

- `0x8090`

## pseudocode

```c

```

## disassembly

```asm
0x8090  ldarg.1
0x8091  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x8096  stloc.0
0x8097  ldarg.1
0x8098  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext
0x809d  stloc.1
0x809e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x80a3  stloc.2
0x80a4  ldloc.0
0x80a5  brfalse.s loc_80B5
0x80a7  ldloc.0
0x80a8  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_CorrelationToken()
0x80ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_TransactionContextId()
0x80b2  stloc.2
0x80b3  br.s     loc_80BF
0x80b5  ldloc.1
0x80b6  brfalse.s loc_80BF
0x80b8  ldloc.1
0x80b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_TransactionContextId()
0x80be  stloc.2
0x80bf  ldloc.2
0x80c0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x80c5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x80ca  brfalse.s loc_80D2
0x80cc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x80d1  stloc.2
0x80d2  ldloc.2
0x80d3  ret
```
