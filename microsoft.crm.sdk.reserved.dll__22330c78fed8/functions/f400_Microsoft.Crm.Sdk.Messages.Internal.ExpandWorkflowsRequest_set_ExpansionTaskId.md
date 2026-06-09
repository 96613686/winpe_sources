# Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::set_ExpansionTaskId

- ea: `0xf400`
- end: `0xf417`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::set_ExpansionTaskId`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xf420`

## string_xrefs

- `0xf406`: `ExpansionTaskId`

## pseudocode

```c

```

## disassembly

```asm
0xf400  ldarg.0
0xf401  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf406  ldstr    aExpansiontaski// "ExpansionTaskId"
0xf40b  ldarg.1
0xf40c  box      [mscorlib]System.Guid
0xf411  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xf416  ret
```
