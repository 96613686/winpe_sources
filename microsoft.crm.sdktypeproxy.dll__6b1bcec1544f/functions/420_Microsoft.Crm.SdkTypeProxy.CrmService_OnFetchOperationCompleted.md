# Microsoft.Crm.SdkTypeProxy.CrmService::OnFetchOperationCompleted

- ea: `0x420`
- end: `0x459`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnFetchOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x420`
- `0x35e10`
- `0x35e50`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.0
0x421  ldfld    class Microsoft.Crm.SdkTypeProxy.FetchCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::FetchCompleted
0x426  brfalse.s loc_458
0x428  ldarg.1
0x429  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x42e  stloc.0
0x42f  ldarg.0
0x430  ldfld    class Microsoft.Crm.SdkTypeProxy.FetchCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::FetchCompleted
0x435  ldarg.0
0x436  ldloc.0
0x437  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x43c  ldloc.0
0x43d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x442  ldloc.0
0x443  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x448  ldloc.0
0x449  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x44e  newobj   instance void Microsoft.Crm.SdkTypeProxy.FetchCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x453  callvirt instance void Microsoft.Crm.SdkTypeProxy.FetchCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.FetchCompletedEventArgs e)
0x458  ret
```
