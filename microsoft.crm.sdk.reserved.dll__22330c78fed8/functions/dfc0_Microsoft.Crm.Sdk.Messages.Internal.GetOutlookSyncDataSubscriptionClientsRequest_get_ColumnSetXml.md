# Microsoft.Crm.Sdk.Messages.Internal.GetOutlookSyncDataSubscriptionClientsRequest::get_ColumnSetXml

- ea: `0xdfc0`
- end: `0xdfea`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetOutlookSyncDataSubscriptionClientsRequest::get_ColumnSetXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdfc0`

## string_xrefs

- `0xdfc6`: `ColumnSetXml`
- `0xdfd8`: `ColumnSetXml`

## pseudocode

```c

```

## disassembly

```asm
0xdfc0  ldarg.0
0xdfc1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xdfc6  ldstr    aColumnsetxml// "ColumnSetXml"
0xdfcb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xdfd0  brfalse.s loc_DFE8
0xdfd2  ldarg.0
0xdfd3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xdfd8  ldstr    aColumnsetxml// "ColumnSetXml"
0xdfdd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xdfe2  castclass [mscorlib]System.String
0xdfe7  ret
0xdfe8  ldnull
0xdfe9  ret
```
