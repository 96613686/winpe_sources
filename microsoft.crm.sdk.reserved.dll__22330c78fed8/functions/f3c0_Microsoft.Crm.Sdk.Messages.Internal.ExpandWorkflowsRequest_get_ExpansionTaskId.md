# Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::get_ExpansionTaskId

- ea: `0xf3c0`
- end: `0xf3f2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::get_ExpansionTaskId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xf3c0`

## string_xrefs

- `0xf3c6`: `ExpansionTaskId`
- `0xf3d8`: `ExpansionTaskId`

## pseudocode

```c

```

## disassembly

```asm
0xf3c0  ldarg.0
0xf3c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf3c6  ldstr    aExpansiontaski// "ExpansionTaskId"
0xf3cb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf3d0  brfalse.s loc_F3E8
0xf3d2  ldarg.0
0xf3d3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf3d8  ldstr    aExpansiontaski// "ExpansionTaskId"
0xf3dd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf3e2  unbox.any [mscorlib]System.Guid
0xf3e7  ret
0xf3e8  ldloca.s 0
0xf3ea  initobj  [mscorlib]System.Guid
0xf3f0  ldloc.0
0xf3f1  ret
```
