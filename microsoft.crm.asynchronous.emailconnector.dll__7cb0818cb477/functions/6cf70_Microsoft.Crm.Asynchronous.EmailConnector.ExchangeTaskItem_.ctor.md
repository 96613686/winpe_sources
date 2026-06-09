# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::.ctor

- ea: `0x6cf70`
- end: `0x6d0b2`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::.ctor`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cbe0`
- `0x70ce0`

## callees

- `0x69840`
- `0x69850`
- `0x69890`
- `0x6add0`
- `0x6cf70`
- `0x70000`
- `0x70050`
- `0x700c0`
- `0x700d0`
- `0x701b0`
- `0x701c0`

## string_xrefs

- `0x6cfbb`: `settaskstartdate`
- `0x6cfd7`: `settaskduedate`
- `0x6cff3`: `setcompletedate`
- `0x6d00f`: `settaskstatus`
- `0x6d02b`: `taskstartdate`
- `0x6d047`: `taskduedate`
- `0x6cfa2`: `IPM.Task`

## pseudocode

```c

```

## disassembly

```asm
0x6cf70  ldarg.0
0x6cf71  ldarg.2
0x6cf72  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context)
0x6cf77  ldarg.0
0x6cf78  ldarg.1
0x6cf79  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::set_Provider(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider value)
0x6cf7e  ldarg.3
0x6cf7f  brtrue.s loc_6CFAE
0x6cf81  ldarg.0
0x6cf82  ldarg.0
0x6cf83  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Provider()
0x6cf88  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider
0x6cf8d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeService()
0x6cf92  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService)
0x6cf97  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::set_Item(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item value)
0x6cf9c  ldarg.0
0x6cf9d  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6cfa2  ldstr    aIpmTask// "IPM.Task"
0x6cfa7  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::set_ItemClass(string)
0x6cfac  br.s     loc_6CFB5
0x6cfae  ldarg.0
0x6cfaf  ldarg.3
0x6cfb0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::set_Item(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item value)
0x6cfb5  ldarg.0
0x6cfb6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6cfbb  ldstr    aSettaskstartda// "settaskstartdate"
0x6cfc0  ldarg.0
0x6cfc1  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::SetTaskStartDate()
0x6cfc7  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6cfcc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6cfd1  ldarg.0
0x6cfd2  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6cfd7  ldstr    aSettaskduedate// "settaskduedate"
0x6cfdc  ldarg.0
0x6cfdd  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::SetTaskDueDate()
0x6cfe3  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6cfe8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6cfed  ldarg.0
0x6cfee  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6cff3  ldstr    aSetcompletedat// "setcompletedate"
0x6cff8  ldarg.0
0x6cff9  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::SetCompleteDate()
0x6cfff  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d004  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d009  ldarg.0
0x6d00a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6d00f  ldstr    aSettaskstatus// "settaskstatus"
0x6d014  ldarg.0
0x6d015  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::SetTaskStatus()
0x6d01b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d020  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d025  ldarg.0
0x6d026  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6d02b  ldstr    aTaskstartdate// "taskstartdate"
0x6d030  ldarg.0
0x6d031  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::GetTaskStartDate()
0x6d037  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d03c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d041  ldarg.0
0x6d042  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6d047  ldstr    aTaskduedate// "taskduedate"
0x6d04c  ldarg.0
0x6d04d  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::GetTaskDueDate()
0x6d053  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d058  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d05d  ldarg.0
0x6d05e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6d063  ldstr    aActualend// "actualend"
0x6d068  ldarg.0
0x6d069  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::GetActualEnd()
0x6d06f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d074  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d079  ldarg.0
0x6d07a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6d07f  ldstr    aGetstatuscode// "getstatuscode"
0x6d084  ldarg.0
0x6d085  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::GetStatusCode()
0x6d08b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d090  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d095  ldarg.0
0x6d096  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6d09b  ldstr    aBody// "body"
0x6d0a0  ldarg.0
0x6d0a1  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::GetContactTaskDescription()
0x6d0a7  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6d0ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6d0b1  ret
```
