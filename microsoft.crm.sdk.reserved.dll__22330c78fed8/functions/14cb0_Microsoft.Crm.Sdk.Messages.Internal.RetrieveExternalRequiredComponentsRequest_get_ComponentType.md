# Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::get_ComponentType

- ea: `0x14cb0`
- end: `0x14cda`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::get_ComponentType`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14cb0`

## string_xrefs

- `0x14cb6`: `ComponentType`
- `0x14cc8`: `ComponentType`

## pseudocode

```c

```

## disassembly

```asm
0x14cb0  ldarg.0
0x14cb1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14cb6  ldstr    aComponenttype// "ComponentType"
0x14cbb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14cc0  brfalse.s loc_14CD8
0x14cc2  ldarg.0
0x14cc3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14cc8  ldstr    aComponenttype// "ComponentType"
0x14ccd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14cd2  unbox.any [mscorlib]System.Int32
0x14cd7  ret
0x14cd8  ldc.i4.0
0x14cd9  ret
```
