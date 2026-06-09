# Microsoft.Crm.Sdk.Messages.Internal.IntersectRecordsWithQueueAndAggregateRequest::get_InteractionCentricFilterXml

- ea: `0x2db0`
- end: `0x2dda`
- name: `Microsoft.Crm.Sdk.Messages.Internal.IntersectRecordsWithQueueAndAggregateRequest::get_InteractionCentricFilterXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2db0`

## string_xrefs

- `0x2db6`: `InteractionCentricFilterXml`
- `0x2dc8`: `InteractionCentricFilterXml`

## pseudocode

```c

```

## disassembly

```asm
0x2db0  ldarg.0
0x2db1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2db6  ldstr    aInteractioncen// "InteractionCentricFilterXml"
0x2dbb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2dc0  brfalse.s loc_2DD8
0x2dc2  ldarg.0
0x2dc3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2dc8  ldstr    aInteractioncen// "InteractionCentricFilterXml"
0x2dcd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2dd2  castclass [mscorlib]System.String
0x2dd7  ret
0x2dd8  ldnull
0x2dd9  ret
```
