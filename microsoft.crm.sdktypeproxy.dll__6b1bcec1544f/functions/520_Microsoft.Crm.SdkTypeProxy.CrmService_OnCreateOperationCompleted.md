# Microsoft.Crm.SdkTypeProxy.CrmService::OnCreateOperationCompleted

- ea: `0x520`
- end: `0x559`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnCreateOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x520`
- `0x35eb0`
- `0x35ef0`

## pseudocode

```c

```

## disassembly

```asm
0x520  ldarg.0
0x521  ldfld    class Microsoft.Crm.SdkTypeProxy.CreateCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::CreateCompleted
0x526  brfalse.s loc_558
0x528  ldarg.1
0x529  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x52e  stloc.0
0x52f  ldarg.0
0x530  ldfld    class Microsoft.Crm.SdkTypeProxy.CreateCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::CreateCompleted
0x535  ldarg.0
0x536  ldloc.0
0x537  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x53c  ldloc.0
0x53d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x542  ldloc.0
0x543  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x548  ldloc.0
0x549  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x54e  newobj   instance void Microsoft.Crm.SdkTypeProxy.CreateCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x553  callvirt instance void Microsoft.Crm.SdkTypeProxy.CreateCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.CreateCompletedEventArgs e)
0x558  ret
```
