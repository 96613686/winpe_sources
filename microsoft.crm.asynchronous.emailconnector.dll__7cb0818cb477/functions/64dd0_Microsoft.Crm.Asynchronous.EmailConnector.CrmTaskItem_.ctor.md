# Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::.ctor

- ea: `0x64dd0`
- end: `0x64e30`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::.ctor`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x60b20`
- `0x624f0`
- `0x62530`
- `0x647a0`

## callees

- `0x60bb0`
- `0x70000`
- `0x700c0`

## string_xrefs

- `0x64de1`: `settaskstartdate`
- `0x64dfd`: `settaskduedate`
- `0x64e19`: `settaskstatus`

## pseudocode

```c

```

## disassembly

```asm
0x64dd0  ldarg.0
0x64dd1  ldarg.1
0x64dd2  ldarg.2
0x64dd3  ldarg.3
0x64dd4  ldarg.s  4
0x64dd6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string entityName)
0x64ddb  ldarg.0
0x64ddc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x64de1  ldstr    aSettaskstartda// "settaskstartdate"
0x64de6  ldarg.0
0x64de7  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskStartDate()
0x64ded  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x64df2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x64df7  ldarg.0
0x64df8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x64dfd  ldstr    aSettaskduedate// "settaskduedate"
0x64e02  ldarg.0
0x64e03  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskDueDate()
0x64e09  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x64e0e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x64e13  ldarg.0
0x64e14  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x64e19  ldstr    aSettaskstatus// "settaskstatus"
0x64e1e  ldarg.0
0x64e1f  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmTaskItem::SetTaskStatus()
0x64e25  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x64e2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x64e2f  ret
```
