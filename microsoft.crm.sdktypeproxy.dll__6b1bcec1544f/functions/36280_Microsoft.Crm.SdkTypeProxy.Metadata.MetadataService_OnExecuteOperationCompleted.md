# Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::OnExecuteOperationCompleted

- ea: `0x36280`
- end: `0x362b9`
- name: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::OnExecuteOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x36280`
- `0x37390`
- `0x373d0`

## pseudocode

```c

```

## disassembly

```asm
0x36280  ldarg.0
0x36281  ldfld    class Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteCompleted
0x36286  brfalse.s loc_362B8
0x36288  ldarg.1
0x36289  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x3628e  stloc.0
0x3628f  ldarg.0
0x36290  ldfld    class Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteCompleted
0x36295  ldarg.0
0x36296  ldloc.0
0x36297  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x3629c  ldloc.0
0x3629d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x362a2  ldloc.0
0x362a3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x362a8  ldloc.0
0x362a9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x362ae  newobj   instance void Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x362b3  callvirt instance void Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventArgs e)
0x362b8  ret
```
