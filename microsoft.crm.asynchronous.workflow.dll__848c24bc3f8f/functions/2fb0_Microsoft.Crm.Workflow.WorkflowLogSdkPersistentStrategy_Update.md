# Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::Update

- ea: `0x2fb0`
- end: `0x2fc3`
- name: `Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::Update`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  ldfld    class Microsoft.Crm.Workflow.WorkflowContext Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::_context
0x2fb6  ldc.i4.1
0x2fb7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool)
0x2fbc  ldarg.1
0x2fbd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2fc2  ret
```
