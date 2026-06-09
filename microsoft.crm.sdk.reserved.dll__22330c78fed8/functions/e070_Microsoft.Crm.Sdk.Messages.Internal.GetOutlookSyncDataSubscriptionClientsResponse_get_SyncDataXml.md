# Microsoft.Crm.Sdk.Messages.Internal.GetOutlookSyncDataSubscriptionClientsResponse::get_SyncDataXml

- ea: `0xe070`
- end: `0xe09a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetOutlookSyncDataSubscriptionClientsResponse::get_SyncDataXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe070`

## string_xrefs

- `0xe076`: `SyncDataXml`
- `0xe088`: `SyncDataXml`

## pseudocode

```c

```

## disassembly

```asm
0xe070  ldarg.0
0xe071  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xe076  ldstr    aSyncdataxml// "SyncDataXml"
0xe07b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xe080  brfalse.s loc_E098
0xe082  ldarg.0
0xe083  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xe088  ldstr    aSyncdataxml// "SyncDataXml"
0xe08d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xe092  castclass [mscorlib]System.String
0xe097  ret
0xe098  ldnull
0xe099  ret
```
