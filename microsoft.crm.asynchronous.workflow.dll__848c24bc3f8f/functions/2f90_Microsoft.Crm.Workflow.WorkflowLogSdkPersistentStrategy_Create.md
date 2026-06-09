# Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::Create

- ea: `0x2f90`
- end: `0x2fa4`
- name: `Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::Create`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  ldfld    class Microsoft.Crm.Workflow.WorkflowContext Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::_context
0x2f96  ldc.i4.1
0x2f97  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool)
0x2f9c  ldarg.1
0x2f9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2fa2  pop
0x2fa3  ret
```
