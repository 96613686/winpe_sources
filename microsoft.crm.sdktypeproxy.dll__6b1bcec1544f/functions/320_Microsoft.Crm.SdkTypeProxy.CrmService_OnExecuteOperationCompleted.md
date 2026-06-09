# Microsoft.Crm.SdkTypeProxy.CrmService::OnExecuteOperationCompleted

- ea: `0x320`
- end: `0x359`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnExecuteOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x320`
- `0x35d70`
- `0x35db0`

## pseudocode

```c

```

## disassembly

```asm
0x320  ldarg.0
0x321  ldfld    class Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteCompleted
0x326  brfalse.s loc_358
0x328  ldarg.1
0x329  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x32e  stloc.0
0x32f  ldarg.0
0x330  ldfld    class Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteCompleted
0x335  ldarg.0
0x336  ldloc.0
0x337  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x33c  ldloc.0
0x33d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x342  ldloc.0
0x343  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x348  ldloc.0
0x349  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x34e  newobj   instance void Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x353  callvirt instance void Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventArgs e)
0x358  ret
```
