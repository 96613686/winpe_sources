# Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::.ctor

- ea: `0x16650`
- end: `0x1667f`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16590`
- `0x165e0`
- `0x16630`

## string_xrefs

- `0x16657`: `RemoveMembersByFetchXmlList`

## pseudocode

```c

```

## disassembly

```asm
0x16650  ldarg.0
0x16651  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x16656  ldarg.0
0x16657  ldstr    aRemovemembersb// "RemoveMembersByFetchXmlList"
0x1665c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x16661  ldarg.0
0x16662  ldloca.s 0
0x16664  initobj  [mscorlib]System.Guid
0x1666a  ldloc.0
0x1666b  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_ListId(valuetype [mscorlib]System.Guid value)
0x16670  ldarg.0
0x16671  ldnull
0x16672  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_FetchXml(string value)
0x16677  ldarg.0
0x16678  ldc.i4.0
0x16679  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_KeepReturned(bool value)
0x1667e  ret
```
