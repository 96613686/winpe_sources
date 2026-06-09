# Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::get_FetchXml

- ea: `0x14580`
- end: `0x145aa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14580`

## string_xrefs

- `0x14586`: `FetchXml`
- `0x14598`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x14580  ldarg.0
0x14581  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14586  ldstr    aFetchxml// "FetchXml"
0x1458b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14590  brfalse.s loc_145A8
0x14592  ldarg.0
0x14593  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14598  ldstr    aFetchxml// "FetchXml"
0x1459d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x145a2  castclass [mscorlib]System.String
0x145a7  ret
0x145a8  ldnull
0x145a9  ret
```
