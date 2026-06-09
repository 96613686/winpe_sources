# Microsoft.Crm.Asynchronous.AsyncHandlerHost::ExecuteAsync

- ea: `0x480`
- end: `0x534`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerHost::ExecuteAsync`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x480`
- `0x540`
- `0x620`
- `0x690`
- `0x6a0`
- `0xa240`

## string_xrefs

- `0x4b2`: `Can't find organization configuration with organiationId: {0} `

## pseudocode

```c

```

## disassembly

```asm
0x480  ldarg.1
0x481  ldstr    aOperationreque// "operationRequest"
0x486  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x48b  ldarg.1
0x48c  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x491  ldstr    aAsyncoperation_0// "AsyncOperation"
0x496  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x49b  ldarg.0
0x49c  ldarg.1
0x49d  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x4a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OrganizationId()
0x4a7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncHandlerHost::RetrieveOrganizationConfiguration(valuetype [mscorlib]System.Guid organizationId)
0x4ac  stloc.0
0x4ad  ldnull
0x4ae  stloc.1
0x4af  ldloc.0
0x4b0  brtrue.s loc_508
0x4b2  ldstr    aCanTFindOrgani// "Can't find organization configuration w"...
0x4b7  ldarg.1
0x4b8  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x4bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OrganizationId()
0x4c2  box      [mscorlib]System.Guid
0x4c7  call     string [mscorlib]System.String::Format(string, object)
0x4cc  ldstr    aForGivenOperat// "for given operation (operationType: {0}"...
0x4d1  ldarg.1
0x4d2  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x4d7  callvirt instance int32 [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OperationType()
0x4dc  box      [mscorlib]System.Int32
0x4e1  ldarg.1
0x4e2  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x4e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OperationId()
0x4ec  box      [mscorlib]System.Guid
0x4f1  call     string [mscorlib]System.String::Format(string, object, object)
0x4f6  call     string [mscorlib]System.String::Concat(string, string)
0x4fb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x500  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x505  stloc.1
0x506  br.s     loc_528
0x508  call     class Microsoft.Crm.Asynchronous.AsyncEventFactory Microsoft.Crm.Asynchronous.AsyncEventFactory::get_Instance()
0x50d  ldarg.1
0x50e  callvirt instance class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x513  ldloc.0
0x514  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncEventFactory::CreateFromAsyncOperation(class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation asyncOperation, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x519  stloc.2
0x51a  ldarg.0
0x51b  ldloc.2
0x51c  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand Microsoft.Crm.Asynchronous.AsyncHandlerHost::CreateCommand(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x521  ldloc.2
0x522  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::Execute(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent)
0x527  stloc.1
0x528  ldloc.1
0x529  newobj   instance void Microsoft.Crm.Asynchronous.Bridges.AsyncHandlerResultAdapter::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x52e  call     T0x2B000001
0x533  ret
```
