# Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration

- ea: `0x1a90`
- end: `0x1ab1`
- name: `Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ac0`
- `0x1c70`
- `0x1d60`
- `0x2f30`

## callees

- `0x1a90`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  ldarg.0
0x1a91  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::_orgConfiguration
0x1a96  brtrue.s loc_1AAA
0x1a98  ldarg.0
0x1a99  ldarg.0
0x1a9a  ldarg.0
0x1a9b  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1aa0  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::WorkflowResolveOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x1aa5  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::_orgConfiguration
0x1aaa  ldarg.0
0x1aab  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::_orgConfiguration
0x1ab0  ret
```
