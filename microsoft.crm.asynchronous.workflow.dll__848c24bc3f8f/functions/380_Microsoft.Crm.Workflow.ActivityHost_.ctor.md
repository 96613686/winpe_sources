# Microsoft.Crm.Workflow.ActivityHost::.ctor

- ea: `0x380`
- end: `0x3b1`
- name: `Microsoft.Crm.Workflow.ActivityHost::.ctor`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa0`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.0
0x381  ldarg.1
0x382  ldarg.2
0x383  ldarg.s  4
0x385  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IWorkflowConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog)
0x38a  ldarg.s  4
0x38c  ldstr    aEventlog// "eventLog"
0x391  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x396  ldarg.0
0x397  ldarg.s  4
0x399  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_eventLog
0x39e  ldarg.0
0x39f  ldarg.3
0x3a0  stfld    int32 Microsoft.Crm.Workflow.ActivityHost::_asyncMaximumRetries
0x3a5  ldarg.0
0x3a6  ldstr    aAsyncoperation// "AsyncOperationId"
0x3ab  stfld    string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_workflowSessionPrimaryKeyName
0x3b0  ret
```
