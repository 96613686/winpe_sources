# Microsoft.Crm.OperationBehaviors.FaultToleranceBehavior::ApplyBehavior

- ea: `0x80`
- end: `0xa6`
- name: `Microsoft.Crm.OperationBehaviors.FaultToleranceBehavior::ApplyBehavior`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0x8a`: `All service operations running inside a fault tolerant service must implement IMonitoredOperation`

## pseudocode

```c

```

## disassembly

```asm
0x80  ldarg.1
0x81  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IMonitoredOperation
0x86  dup
0x87  ldnull
0x88  cgt.un
0x8a  ldstr    aAllServiceOper// "All service operations running inside a"...
0x8f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x94  ldarg.0
0x95  ldftn    instance void Microsoft.Crm.OperationBehaviors.FaultToleranceBehavior::Execute(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction operation, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operationParameter)
0x9b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.OperationBehavior::.ctor(object, native int)
0xa0  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::ApplyOperationBehavior(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.OperationBehavior)
0xa5  ret
```
