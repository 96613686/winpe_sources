# Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_SystemContextService

- ea: `0xb8c0`
- end: `0xb8e1`
- name: `Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_SystemContextService`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb7c0`
- `0xb7d0`

## callees

- `0xb8c0`

## pseudocode

```c

```

## disassembly

```asm
0xb8c0  ldarg.0
0xb8c1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_systemContextService
0xb8c6  brtrue.s loc_B8DA
0xb8c8  ldarg.0
0xb8c9  ldarg.0
0xb8ca  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_asyncEvent
0xb8cf  ldc.i4.1
0xb8d0  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xb8d5  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_systemContextService
0xb8da  ldarg.0
0xb8db  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_systemContextService
0xb8e0  ret
```
