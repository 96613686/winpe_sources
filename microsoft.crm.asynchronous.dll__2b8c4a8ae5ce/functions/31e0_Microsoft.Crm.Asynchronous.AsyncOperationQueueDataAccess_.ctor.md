# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::.ctor

- ea: `0x31e0`
- end: `0x320b`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::.ctor`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3210`

## callees

- `0x27f0`
- `0xd580`

## pseudocode

```c

```

## disassembly

```asm
0x31e0  ldarg.0
0x31e1  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x31e6  stfld    class [mscorlib]System.Text.Encoding Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::DataEncoding
0x31eb  ldarg.0
0x31ec  ldarg.2
0x31ed  call     instance void Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x31f2  ldarg.0
0x31f3  ldarg.1
0x31f4  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x31f9  ldarg.0
0x31fa  ldarg.0
0x31fb  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3200  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x3205  stfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x320a  ret
```
