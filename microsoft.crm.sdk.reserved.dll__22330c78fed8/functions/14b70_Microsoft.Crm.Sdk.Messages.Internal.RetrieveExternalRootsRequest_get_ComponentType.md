# Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRootsRequest::get_ComponentType

- ea: `0x14b70`
- end: `0x14b9a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRootsRequest::get_ComponentType`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14b70`

## string_xrefs

- `0x14b76`: `ComponentType`
- `0x14b88`: `ComponentType`

## pseudocode

```c

```

## disassembly

```asm
0x14b70  ldarg.0
0x14b71  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14b76  ldstr    aComponenttype// "ComponentType"
0x14b7b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14b80  brfalse.s loc_14B98
0x14b82  ldarg.0
0x14b83  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14b88  ldstr    aComponenttype// "ComponentType"
0x14b8d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14b92  unbox.any [mscorlib]System.Int32
0x14b97  ret
0x14b98  ldc.i4.0
0x14b99  ret
```
