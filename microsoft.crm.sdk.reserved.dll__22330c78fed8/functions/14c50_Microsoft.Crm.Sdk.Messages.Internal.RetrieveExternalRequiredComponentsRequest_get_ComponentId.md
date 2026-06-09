# Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::get_ComponentId

- ea: `0x14c50`
- end: `0x14c82`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::get_ComponentId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14c50`

## string_xrefs

- `0x14c56`: `ComponentId`
- `0x14c68`: `ComponentId`

## pseudocode

```c

```

## disassembly

```asm
0x14c50  ldarg.0
0x14c51  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14c56  ldstr    aComponentid// "ComponentId"
0x14c5b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14c60  brfalse.s loc_14C78
0x14c62  ldarg.0
0x14c63  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14c68  ldstr    aComponentid// "ComponentId"
0x14c6d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14c72  unbox.any [mscorlib]System.Guid
0x14c77  ret
0x14c78  ldloca.s 0
0x14c7a  initobj  [mscorlib]System.Guid
0x14c80  ldloc.0
0x14c81  ret
```
