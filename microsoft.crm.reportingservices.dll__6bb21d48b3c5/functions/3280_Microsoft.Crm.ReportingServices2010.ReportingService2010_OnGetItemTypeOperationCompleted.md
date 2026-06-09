# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemTypeOperationCompleted

- ea: `0x3280`
- end: `0x32b9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemTypeOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3280`
- `0xcd10`
- `0xcd50`

## pseudocode

```c

```

## disassembly

```asm
0x3280  ldarg.0
0x3281  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemTypeCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemTypeCompleted
0x3286  brfalse.s loc_32B8
0x3288  ldarg.1
0x3289  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x328e  stloc.0
0x328f  ldarg.0
0x3290  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemTypeCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemTypeCompleted
0x3295  ldarg.0
0x3296  ldloc.0
0x3297  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x329c  ldloc.0
0x329d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x32a2  ldloc.0
0x32a3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x32a8  ldloc.0
0x32a9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x32ae  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemTypeCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x32b3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemTypeCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemTypeCompletedEventArgs e)
0x32b8  ret
```
