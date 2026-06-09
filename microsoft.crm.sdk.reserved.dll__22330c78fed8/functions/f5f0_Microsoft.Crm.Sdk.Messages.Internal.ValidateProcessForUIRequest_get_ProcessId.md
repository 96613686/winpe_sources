# Microsoft.Crm.Sdk.Messages.Internal.ValidateProcessForUIRequest::get_ProcessId

- ea: `0xf5f0`
- end: `0xf61a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ValidateProcessForUIRequest::get_ProcessId`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xf5f0`

## string_xrefs

- `0xf5f6`: `ProcessId`
- `0xf608`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0xf5f0  ldarg.0
0xf5f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf5f6  ldstr    aProcessid// "ProcessId"
0xf5fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf600  brfalse.s loc_F618
0xf602  ldarg.0
0xf603  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf608  ldstr    aProcessid// "ProcessId"
0xf60d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf612  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xf617  ret
0xf618  ldnull
0xf619  ret
```
