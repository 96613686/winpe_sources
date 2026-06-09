# Microsoft.Crm.SdkTypeProxy.CrmService::OnDeleteOperationCompleted

- ea: `0x630`
- end: `0x663`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnDeleteOperationCompleted`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x630`
- `0x35f50`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldarg.0
0x631  ldfld    class Microsoft.Crm.SdkTypeProxy.DeleteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::DeleteCompleted
0x636  brfalse.s loc_662
0x638  ldarg.1
0x639  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x63e  stloc.0
0x63f  ldarg.0
0x640  ldfld    class Microsoft.Crm.SdkTypeProxy.DeleteCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::DeleteCompleted
0x645  ldarg.0
0x646  ldloc.0
0x647  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x64c  ldloc.0
0x64d  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x652  ldloc.0
0x653  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x658  newobj   instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x65d  callvirt instance void Microsoft.Crm.SdkTypeProxy.DeleteCompletedEventHandler::Invoke(object sender, class [System]System.ComponentModel.AsyncCompletedEventArgs e)
0x662  ret
```
