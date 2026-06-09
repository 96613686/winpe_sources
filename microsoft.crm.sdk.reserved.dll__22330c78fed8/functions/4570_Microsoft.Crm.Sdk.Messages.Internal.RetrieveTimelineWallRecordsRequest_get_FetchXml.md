# Microsoft.Crm.Sdk.Messages.Internal.RetrieveTimelineWallRecordsRequest::get_FetchXml

- ea: `0x4570`
- end: `0x459a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveTimelineWallRecordsRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4570`

## string_xrefs

- `0x4576`: `FetchXml`
- `0x4588`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x4570  ldarg.0
0x4571  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4576  ldstr    aFetchxml// "FetchXml"
0x457b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x4580  brfalse.s loc_4598
0x4582  ldarg.0
0x4583  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4588  ldstr    aFetchxml// "FetchXml"
0x458d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x4592  castclass [mscorlib]System.String
0x4597  ret
0x4598  ldnull
0x4599  ret
```
