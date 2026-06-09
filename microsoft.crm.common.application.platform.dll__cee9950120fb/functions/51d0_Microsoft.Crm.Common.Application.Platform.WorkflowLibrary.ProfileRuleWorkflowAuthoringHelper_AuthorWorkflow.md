# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AuthorWorkflow

- ea: `0x51d0`
- end: `0x51e4`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AuthorWorkflow`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5490`

## string_xrefs

- `0x51d3`: `channelaccessprofilerule`
- `0x51d8`: `channelaccessprofileruleitem`

## pseudocode

```c

```

## disassembly

```asm
0x51d0  ldarg.0
0x51d1  ldarg.1
0x51d2  ldarg.2
0x51d3  ldstr    aChannelaccessp// "channelaccessprofilerule"
0x51d8  ldstr    aChannelaccessp_0// "channelaccessprofileruleitem"
0x51dd  ldarg.3
0x51de  call     instance string Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AuthorWorkflow(string entityId, string primaryEntityName, string ruleParentEntityName, string ruleChildEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext)
0x51e3  ret
```
