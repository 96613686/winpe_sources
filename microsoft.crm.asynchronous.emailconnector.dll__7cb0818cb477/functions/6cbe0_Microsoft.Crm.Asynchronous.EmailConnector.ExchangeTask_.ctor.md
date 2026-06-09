# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::.ctor

- ea: `0x6cbe0`
- end: `0x6cc22`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::.ctor`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x70ce0`

## callees

- `0x6cf70`
- `0x70000`
- `0x70050`
- `0x700c0`
- `0x700d0`

## string_xrefs

- `0x6cbef`: `settaskpercentcomplete`
- `0x6cc0b`: `percentcomplete`

## pseudocode

```c

```

## disassembly

```asm
0x6cbe0  ldarg.0
0x6cbe1  ldarg.1
0x6cbe2  ldarg.2
0x6cbe3  ldarg.3
0x6cbe4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x6cbe9  ldarg.0
0x6cbea  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6cbef  ldstr    aSettaskpercent// "settaskpercentcomplete"
0x6cbf4  ldarg.0
0x6cbf5  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::SetTaskPercentComplete()
0x6cbfb  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6cc00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6cc05  ldarg.0
0x6cc06  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6cc0b  ldstr    aPercentcomplet// "percentcomplete"
0x6cc10  ldarg.0
0x6cc11  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::GetPercentComplete()
0x6cc17  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6cc1c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6cc21  ret
```
