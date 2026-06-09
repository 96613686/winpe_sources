# Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveOperationCompleted

- ea: `0x750`
- end: `0x789`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x750`
- `0x35fa0`
- `0x35fe0`

## pseudocode

```c

```

## disassembly

```asm
0x750  ldarg.0
0x751  ldfld    class Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveCompleted
0x756  brfalse.s loc_788
0x758  ldarg.1
0x759  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x75e  stloc.0
0x75f  ldarg.0
0x760  ldfld    class Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveCompleted
0x765  ldarg.0
0x766  ldloc.0
0x767  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x76c  ldloc.0
0x76d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x772  ldloc.0
0x773  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x778  ldloc.0
0x779  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x77e  newobj   instance void Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x783  callvirt instance void Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventArgs e)
0x788  ret
```
