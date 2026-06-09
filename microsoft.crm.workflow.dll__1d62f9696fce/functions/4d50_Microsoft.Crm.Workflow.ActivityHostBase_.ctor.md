# Microsoft.Crm.Workflow.ActivityHostBase::.ctor

- ea: `0x4d50`
- end: `0x4da9`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::.ctor`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10aa0`
- `0x11dd0`

## callees

- `0x3d0`
- `0x4db0`

## string_xrefs

- `0x4d62`: `crmServiceFactory`
- `0x4d6d`: `configuration`

## pseudocode

```c

```

## disassembly

```asm
0x4d50  ldarg.0
0x4d51  newobj   instance void [mscorlib]System.Object::.ctor()
0x4d56  stfld    object Microsoft.Crm.Workflow.ActivityHostBase::_statusChangedLock
0x4d5b  ldarg.0
0x4d5c  call     instance void [mscorlib]System.Object::.ctor()
0x4d61  ldarg.1
0x4d62  ldstr    aCrmservicefact// "crmServiceFactory"
0x4d67  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4d6c  ldarg.2
0x4d6d  ldstr    aConfiguration// "configuration"
0x4d72  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4d77  ldarg.0
0x4d78  ldarg.1
0x4d79  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory Microsoft.Crm.Workflow.ActivityHostBase::_crmServiceFactory
0x4d7e  ldarg.0
0x4d7f  ldarg.2
0x4d80  stfld    class Microsoft.Crm.Asynchronous.IWorkflowConfiguration Microsoft.Crm.Workflow.ActivityHostBase::_configuration
0x4d85  ldarg.0
0x4d86  ldarg.3
0x4d87  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Workflow.ActivityHostBase::_eventLog
0x4d8c  ldarg.0
0x4d8d  call     class Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateWorkflowDefault()
0x4d92  stfld    class Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Workflow.ActivityHostBase::_errorHandler
0x4d97  ldarg.0
0x4d98  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class Microsoft.Crm.Workflow.ICommonWorkflowContext>>::.ctor()
0x4d9d  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class Microsoft.Crm.Workflow.ICommonWorkflowContext>> Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x4da2  ldarg.0
0x4da3  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::LoadStatusMap()
0x4da8  ret
```
