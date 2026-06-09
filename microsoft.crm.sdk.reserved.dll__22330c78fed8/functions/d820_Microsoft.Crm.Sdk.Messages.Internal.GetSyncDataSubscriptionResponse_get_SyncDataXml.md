# Microsoft.Crm.Sdk.Messages.Internal.GetSyncDataSubscriptionResponse::get_SyncDataXml

- ea: `0xd820`
- end: `0xd84a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetSyncDataSubscriptionResponse::get_SyncDataXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd820`

## string_xrefs

- `0xd826`: `SyncDataXml`
- `0xd838`: `SyncDataXml`

## pseudocode

```c

```

## disassembly

```asm
0xd820  ldarg.0
0xd821  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xd826  ldstr    aSyncdataxml// "SyncDataXml"
0xd82b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xd830  brfalse.s loc_D848
0xd832  ldarg.0
0xd833  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xd838  ldstr    aSyncdataxml// "SyncDataXml"
0xd83d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xd842  castclass [mscorlib]System.String
0xd847  ret
0xd848  ldnull
0xd849  ret
```
