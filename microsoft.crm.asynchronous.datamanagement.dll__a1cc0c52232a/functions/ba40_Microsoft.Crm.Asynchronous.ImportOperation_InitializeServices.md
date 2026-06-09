# Microsoft.Crm.Asynchronous.ImportOperation::InitializeServices

- ea: `0xba40`
- end: `0xba64`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::InitializeServices`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xab30`

## callees

- `0x3c40`

## pseudocode

```c

```

## disassembly

```asm
0xba40  ldarg.0
0xba41  ldarg.0
0xba42  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xba47  newobj   instance void Microsoft.Crm.Asynchronous.ImportDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0xba4c  stfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xba51  ldarg.0
0xba52  ldarg.0
0xba53  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xba58  ldc.i4.0
0xba59  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xba5e  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xba63  ret
```
