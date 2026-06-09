# Microsoft.Crm.Asynchronous.AsyncHandlerHost::CreateCommand

- ea: `0x540`
- end: `0x5f6`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerHost::CreateCommand`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x480`

## callees

- `0x540`
- `0x620`
- `0x18f0`
- `0x5360`

## string_xrefs

- `0x5b9`: `Created AsyncEventHandlerCommand type: {0} for Operation type: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x540  ldnull
0x541  stloc.0
0x542  ldarg.0
0x543  ldarg.1
0x544  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x549  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncHandlerHost::RetrieveOrganizationConfiguration(valuetype [mscorlib]System.Guid organizationId)
0x54e  stloc.1
0x54f  ldloc.1
0x550  brfalse  loc_5F4
0x555  ldarg.0
0x556  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x55b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> Microsoft.Crm.Asynchronous.AsyncService::get_OperationCommandTypes()
0x560  ldarg.1
0x561  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x566  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration>::ContainsKey(var<u1>)
0x56b  brfalse.s loc_5E7
0x56d  ldarg.0
0x56e  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x573  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> Microsoft.Crm.Asynchronous.AsyncService::get_OperationCommandTypes()
0x578  ldarg.1
0x579  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x57e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration>::get_Item(void)
0x583  stloc.2
0x584  ldloc.2
0x585  ldfld    class [mscorlib]System.Type Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration::commandType
0x58a  ldc.i4.3
0x58b  newarr   [mscorlib]System.Object
0x590  dup
0x591  ldc.i4.0
0x592  ldarg.0
0x593  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x598  stelem.ref
0x599  dup
0x59a  ldc.i4.1
0x59b  ldloc.2
0x59c  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration::handlerGroup
0x5a1  stelem.ref
0x5a2  dup
0x5a3  ldc.i4.2
0x5a4  ldloc.1
0x5a5  stelem.ref
0x5a6  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x5ab  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand
0x5b0  stloc.0
0x5b1  ldloc.1
0x5b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5b7  ldc.i4.s 0x15
0x5b9  ldstr    aCreatedAsyncev// "Created AsyncEventHandlerCommand type: "...
0x5be  ldc.i4.2
0x5bf  newarr   [mscorlib]System.Object
0x5c4  dup
0x5c5  ldc.i4.0
0x5c6  ldloc.2
0x5c7  ldfld    class [mscorlib]System.Type Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration::commandType
0x5cc  callvirt instance string [mscorlib]System.Type::get_FullName()
0x5d1  stelem.ref
0x5d2  dup
0x5d3  ldc.i4.1
0x5d4  ldarg.1
0x5d5  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x5da  box      [mscorlib]System.Int32
0x5df  stelem.ref
0x5e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5e5  br.s     loc_5F4
0x5e7  ldarg.0
0x5e8  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x5ed  ldloc.1
0x5ee  newobj   instance void Microsoft.Crm.Asynchronous.UnrecognizedOperationTypeCommand::.ctor(class Microsoft.Crm.Asynchronous.AsyncService asyncService, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x5f3  stloc.0
0x5f4  ldloc.0
0x5f5  ret
```
