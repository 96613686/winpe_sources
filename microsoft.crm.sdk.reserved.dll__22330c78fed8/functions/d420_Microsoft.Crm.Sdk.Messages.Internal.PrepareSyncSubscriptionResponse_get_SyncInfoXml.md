# Microsoft.Crm.Sdk.Messages.Internal.PrepareSyncSubscriptionResponse::get_SyncInfoXml

- ea: `0xd420`
- end: `0xd44a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.PrepareSyncSubscriptionResponse::get_SyncInfoXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd420`

## string_xrefs

- `0xd426`: `SyncInfoXml`
- `0xd438`: `SyncInfoXml`

## pseudocode

```c

```

## disassembly

```asm
0xd420  ldarg.0
0xd421  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xd426  ldstr    aSyncinfoxml// "SyncInfoXml"
0xd42b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xd430  brfalse.s loc_D448
0xd432  ldarg.0
0xd433  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xd438  ldstr    aSyncinfoxml// "SyncInfoXml"
0xd43d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xd442  castclass [mscorlib]System.String
0xd447  ret
0xd448  ldnull
0xd449  ret
```
