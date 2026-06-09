# Microsoft.Crm.Asynchronous.AsyncService::OnAsyncOperationStatusChanged

- ea: `0x1620`
- end: `0x164d`
- name: `Microsoft.Crm.Asynchronous.AsyncService::OnAsyncOperationStatusChanged`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1620`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldarg.0
0x1621  ldfld    class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.AsyncService::AsyncOperationStatusChanged
0x1626  stloc.0
0x1627  ldloc.0
0x1628  brfalse.s loc_164C
0x162a  ldloc.0
0x162b  ldarg.0
0x162c  ldarg.2
0x162d  callvirt instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs>::Invoke(object, var<u1>)
0x1632  leave.s  loc_164C
0x1634  stloc.1
0x1635  ldarg.0
0x1636  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Asynchronous.AsyncService::_errorHandler
0x163b  ldloc.1
0x163c  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler::Handle(class [mscorlib]System.Exception)
0x1641  callvirt instance valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x1646  brfalse.s loc_164A
0x1648  leave.s  loc_164C
0x164a  rethrow
0x164c  ret
```
