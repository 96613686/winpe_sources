# Microsoft.Crm.Workflow.ActivityHost::GetXamlWorkflowsResource

- ea: `0x6d0`
- end: `0x6e0`
- name: `Microsoft.Crm.Workflow.ActivityHost::GetXamlWorkflowsResource`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x6d0`: `Workflow.NotEnoughPrivilegesForXamlWorkflows`

## pseudocode

```c

```

## disassembly

```asm
0x6d0  ldstr    aWorkflowNoteno// "Workflow.NotEnoughPrivilegesForXamlWork"...
0x6d5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x6da  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x6df  ret
```
