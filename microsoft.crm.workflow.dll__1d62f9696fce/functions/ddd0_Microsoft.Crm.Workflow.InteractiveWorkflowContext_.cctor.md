# Microsoft.Crm.Workflow.InteractiveWorkflowContext::.cctor

- ea: `0xddd0`
- end: `0xde17`
- name: `Microsoft.Crm.Workflow.InteractiveWorkflowContext::.cctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xddf8`: `<WorkflowStateXml value="{0}" />`

## pseudocode

```c

```

## disassembly

```asm
0xddd0  ldstr    aInteractivewor// "<InteractiveWorkflowContext>{0}</Intera"...
0xddd5  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_interactiveWorkflowContextTemplate
0xddda  ldstr    aWorkflowactiva_1// "<WorkflowActivationId value=\"{0}\" />"
0xdddf  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowActivationIdTemplate
0xdde4  ldstr    aOriginatingwor_0// "<OriginatingWorkflowInstanceId value=\""...
0xdde9  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_originatingWorkflowInstanceIdTemplate
0xddee  ldstr    aWorkflowinstan_0// "<WorkflowInstanceId value=\"{0}\" />"
0xddf3  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowInstanceIdTemplate
0xddf8  ldstr    aWorkflowstatex_0// "<WorkflowStateXml value=\"{0}\" />"
0xddfd  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowStateXmlTemplate
0xde02  ldstr    aPrimaryentityi_0// "<PrimaryEntityId value=\"{0}\" />"
0xde07  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_primaryEntityIdTemplate
0xde0c  ldstr    aPrimaryentityt_0// "<PrimaryEntityTypeCode value=\"{0}\" />"
0xde11  stsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_primaryEntityTypeCodeTemplate
0xde16  ret
```
