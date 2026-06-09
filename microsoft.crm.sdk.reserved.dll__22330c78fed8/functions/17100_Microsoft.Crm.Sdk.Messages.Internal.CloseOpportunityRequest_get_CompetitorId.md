# Microsoft.Crm.Sdk.Messages.Internal.CloseOpportunityRequest::get_CompetitorId

- ea: `0x17100`
- end: `0x1712a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CloseOpportunityRequest::get_CompetitorId`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x17100`

## string_xrefs

- `0x17106`: `CompetitorId`
- `0x17118`: `CompetitorId`

## pseudocode

```c

```

## disassembly

```asm
0x17100  ldarg.0
0x17101  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x17106  ldstr    aCompetitorid// "CompetitorId"
0x1710b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x17110  brfalse.s loc_17128
0x17112  ldarg.0
0x17113  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x17118  ldstr    aCompetitorid// "CompetitorId"
0x1711d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x17122  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x17127  ret
0x17128  ldnull
0x17129  ret
```
