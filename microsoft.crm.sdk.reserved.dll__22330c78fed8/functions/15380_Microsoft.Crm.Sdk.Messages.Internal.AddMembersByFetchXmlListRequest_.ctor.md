# Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::.ctor

- ea: `0x15380`
- end: `0x153a8`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::.ctor`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15310`
- `0x15360`

## string_xrefs

- `0x15387`: `AddMembersByFetchXmlList`

## pseudocode

```c

```

## disassembly

```asm
0x15380  ldarg.0
0x15381  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x15386  ldarg.0
0x15387  ldstr    aAddmembersbyfe// "AddMembersByFetchXmlList"
0x1538c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x15391  ldarg.0
0x15392  ldloca.s 0
0x15394  initobj  [mscorlib]System.Guid
0x1539a  ldloc.0
0x1539b  call     instance void Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_ListId(valuetype [mscorlib]System.Guid value)
0x153a0  ldarg.0
0x153a1  ldnull
0x153a2  call     instance void Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_FetchXml(string value)
0x153a7  ret
```
