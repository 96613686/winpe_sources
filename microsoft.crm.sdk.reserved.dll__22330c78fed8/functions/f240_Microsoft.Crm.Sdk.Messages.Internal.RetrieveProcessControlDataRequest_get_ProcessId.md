# Microsoft.Crm.Sdk.Messages.Internal.RetrieveProcessControlDataRequest::get_ProcessId

- ea: `0xf240`
- end: `0xf26a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveProcessControlDataRequest::get_ProcessId`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xf240`

## string_xrefs

- `0xf246`: `ProcessId`
- `0xf258`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0xf240  ldarg.0
0xf241  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf246  ldstr    aProcessid// "ProcessId"
0xf24b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf250  brfalse.s loc_F268
0xf252  ldarg.0
0xf253  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf258  ldstr    aProcessid// "ProcessId"
0xf25d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf262  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xf267  ret
0xf268  ldnull
0xf269  ret
```
