# Microsoft.Crm.Sdk.Messages.Internal.TestAzureServiceConnectionRequest::get_AzureServiceConnectionId

- ea: `0x47c0`
- end: `0x47f2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.TestAzureServiceConnectionRequest::get_AzureServiceConnectionId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x47c0`

## string_xrefs

- `0x47c6`: `AzureServiceConnectionId`
- `0x47d8`: `AzureServiceConnectionId`

## pseudocode

```c

```

## disassembly

```asm
0x47c0  ldarg.0
0x47c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x47c6  ldstr    aAzureserviceco// "AzureServiceConnectionId"
0x47cb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x47d0  brfalse.s loc_47E8
0x47d2  ldarg.0
0x47d3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x47d8  ldstr    aAzureserviceco// "AzureServiceConnectionId"
0x47dd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x47e2  unbox.any [mscorlib]System.Guid
0x47e7  ret
0x47e8  ldloca.s 0
0x47ea  initobj  [mscorlib]System.Guid
0x47f0  ldloc.0
0x47f1  ret
```
