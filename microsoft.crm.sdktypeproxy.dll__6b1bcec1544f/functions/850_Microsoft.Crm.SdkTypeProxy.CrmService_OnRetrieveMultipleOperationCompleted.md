# Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveMultipleOperationCompleted

- ea: `0x850`
- end: `0x889`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveMultipleOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x850`
- `0x36040`
- `0x36080`

## pseudocode

```c

```

## disassembly

```asm
0x850  ldarg.0
0x851  ldfld    class Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleCompleted
0x856  brfalse.s loc_888
0x858  ldarg.1
0x859  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x85e  stloc.0
0x85f  ldarg.0
0x860  ldfld    class Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleCompleted
0x865  ldarg.0
0x866  ldloc.0
0x867  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x86c  ldloc.0
0x86d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x872  ldloc.0
0x873  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x878  ldloc.0
0x879  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x87e  newobj   instance void Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x883  callvirt instance void Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventArgs e)
0x888  ret
```
