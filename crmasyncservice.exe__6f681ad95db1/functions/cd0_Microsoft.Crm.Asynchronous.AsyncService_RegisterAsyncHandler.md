# Microsoft.Crm.Asynchronous.AsyncService::RegisterAsyncHandler

- ea: `0xcd0`
- end: `0xd1f`
- name: `Microsoft.Crm.Asynchronous.AsyncService::RegisterAsyncHandler`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18f0`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldloca.s 0
0xcd2  initobj  Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration
0xcd8  ldloca.s 0
0xcda  ldarg.2
0xcdb  stfld    class [mscorlib]System.Type Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration::commandType
0xce0  ldloca.s 0
0xce2  ldarg.3
0xce3  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration::handlerGroup
0xce8  ldarg.0
0xce9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> Microsoft.Crm.Asynchronous.AsyncService::get_OperationCommandTypes()
0xcee  ldarg.1
0xcef  ldloc.0
0xcf0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration>::Add(var<u1>, !!T0)
0xcf5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcfa  ldc.i4.s 0x15
0xcfc  ldstr    aRegisteredAsyn// "Registered Async Handler: {0} for Opera"...
0xd01  ldc.i4.2
0xd02  newarr   [mscorlib]System.Object
0xd07  dup
0xd08  ldc.i4.0
0xd09  ldarg.2
0xd0a  callvirt instance string [mscorlib]System.Type::get_FullName()
0xd0f  stelem.ref
0xd10  dup
0xd11  ldc.i4.1
0xd12  ldarg.1
0xd13  box      [mscorlib]System.Int32
0xd18  stelem.ref
0xd19  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd1e  ret
```
