# Microsoft.Crm.Sdk.Messages.Internal.LogSuccessBulkOperationRequest::get_CreatedObjectId

- ea: `0x162b0`
- end: `0x162da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.LogSuccessBulkOperationRequest::get_CreatedObjectId`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x162b0`

## string_xrefs

- `0x162b6`: `CreatedObjectId`
- `0x162c8`: `CreatedObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x162b0  ldarg.0
0x162b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x162b6  ldstr    aCreatedobjecti// "CreatedObjectId"
0x162bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x162c0  brfalse.s loc_162D8
0x162c2  ldarg.0
0x162c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x162c8  ldstr    aCreatedobjecti// "CreatedObjectId"
0x162cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x162d2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x162d7  ret
0x162d8  ldnull
0x162d9  ret
```
