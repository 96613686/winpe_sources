# Microsoft.Crm.SdkTypeProxy.CrmService::OnUpdateOperationCompleted

- ea: `0x930`
- end: `0x963`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::OnUpdateOperationCompleted`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x930`
- `0x360e0`

## pseudocode

```c

```

## disassembly

```asm
0x930  ldarg.0
0x931  ldfld    class Microsoft.Crm.SdkTypeProxy.UpdateCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::UpdateCompleted
0x936  brfalse.s loc_962
0x938  ldarg.1
0x939  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x93e  stloc.0
0x93f  ldarg.0
0x940  ldfld    class Microsoft.Crm.SdkTypeProxy.UpdateCompletedEventHandler Microsoft.Crm.SdkTypeProxy.CrmService::UpdateCompleted
0x945  ldarg.0
0x946  ldloc.0
0x947  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x94c  ldloc.0
0x94d  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x952  ldloc.0
0x953  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x958  newobj   instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x95d  callvirt instance void Microsoft.Crm.SdkTypeProxy.UpdateCompletedEventHandler::Invoke(object sender, class [System]System.ComponentModel.AsyncCompletedEventArgs e)
0x962  ret
```
