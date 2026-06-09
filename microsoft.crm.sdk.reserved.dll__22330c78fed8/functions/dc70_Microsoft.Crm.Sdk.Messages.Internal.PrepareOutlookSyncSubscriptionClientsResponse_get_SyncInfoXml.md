# Microsoft.Crm.Sdk.Messages.Internal.PrepareOutlookSyncSubscriptionClientsResponse::get_SyncInfoXml

- ea: `0xdc70`
- end: `0xdc9a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.PrepareOutlookSyncSubscriptionClientsResponse::get_SyncInfoXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdc70`

## string_xrefs

- `0xdc76`: `SyncInfoXml`
- `0xdc88`: `SyncInfoXml`

## pseudocode

```c

```

## disassembly

```asm
0xdc70  ldarg.0
0xdc71  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xdc76  ldstr    aSyncinfoxml// "SyncInfoXml"
0xdc7b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xdc80  brfalse.s loc_DC98
0xdc82  ldarg.0
0xdc83  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xdc88  ldstr    aSyncinfoxml// "SyncInfoXml"
0xdc8d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xdc92  castclass [mscorlib]System.String
0xdc97  ret
0xdc98  ldnull
0xdc99  ret
```
