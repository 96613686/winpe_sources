# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCatalogItemOperationCompleted

- ea: `0x2fc0`
- end: `0x2ff9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCatalogItemOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2fc0`
- `0xcb10`
- `0xcb50`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  ldarg.0
0x2fc1  ldfld    class Microsoft.Crm.ReportingServices2010.CreateCatalogItemCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemCompleted
0x2fc6  brfalse.s loc_2FF8
0x2fc8  ldarg.1
0x2fc9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x2fce  stloc.0
0x2fcf  ldarg.0
0x2fd0  ldfld    class Microsoft.Crm.ReportingServices2010.CreateCatalogItemCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemCompleted
0x2fd5  ldarg.0
0x2fd6  ldloc.0
0x2fd7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x2fdc  ldloc.0
0x2fdd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x2fe2  ldloc.0
0x2fe3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x2fe8  ldloc.0
0x2fe9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x2fee  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateCatalogItemCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x2ff3  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateCatalogItemCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateCatalogItemCompletedEventArgs e)
0x2ff8  ret
```
