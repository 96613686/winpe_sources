# Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRootsRequest::get_ComponentId

- ea: `0x14b10`
- end: `0x14b42`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRootsRequest::get_ComponentId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14b10`

## string_xrefs

- `0x14b16`: `ComponentId`
- `0x14b28`: `ComponentId`

## pseudocode

```c

```

## disassembly

```asm
0x14b10  ldarg.0
0x14b11  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14b16  ldstr    aComponentid// "ComponentId"
0x14b1b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14b20  brfalse.s loc_14B38
0x14b22  ldarg.0
0x14b23  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14b28  ldstr    aComponentid// "ComponentId"
0x14b2d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14b32  unbox.any [mscorlib]System.Guid
0x14b37  ret
0x14b38  ldloca.s 0
0x14b3a  initobj  [mscorlib]System.Guid
0x14b40  ldloc.0
0x14b41  ret
```
