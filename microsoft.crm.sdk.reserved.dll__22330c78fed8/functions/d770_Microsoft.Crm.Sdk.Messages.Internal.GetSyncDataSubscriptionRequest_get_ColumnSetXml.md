# Microsoft.Crm.Sdk.Messages.Internal.GetSyncDataSubscriptionRequest::get_ColumnSetXml

- ea: `0xd770`
- end: `0xd79a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetSyncDataSubscriptionRequest::get_ColumnSetXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd770`

## string_xrefs

- `0xd776`: `ColumnSetXml`
- `0xd788`: `ColumnSetXml`

## pseudocode

```c

```

## disassembly

```asm
0xd770  ldarg.0
0xd771  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xd776  ldstr    aColumnsetxml// "ColumnSetXml"
0xd77b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xd780  brfalse.s loc_D798
0xd782  ldarg.0
0xd783  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xd788  ldstr    aColumnsetxml// "ColumnSetXml"
0xd78d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xd792  castclass [mscorlib]System.String
0xd797  ret
0xd798  ldnull
0xd799  ret
```
