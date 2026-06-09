# Microsoft.Crm.ObjectModel.Store.AllowedEntityMessages::.cctor

- ea: `0x1f3c80`
- end: `0x1f3d7b`
- name: `Microsoft.Crm.ObjectModel.Store.AllowedEntityMessages::.cctor`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1f3d90`

## string_xrefs

- `0x1f3ca0`: `Create`
- `0x1f3cd6`: `Create`
- `0x1f3d1e`: `Create`
- `0x1f3d44`: `Create`
- `0x1f3cb2`: `Update`
- `0x1f3ce8`: `Update`
- `0x1f3d31`: `Update`
- `0x1f3d57`: `Update`
- `0x1f3cc4`: `Delete`
- `0x1f3cfa`: `Delete`
- `0x1f3d6a`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x1f3c80  ldc.i4.s 0xD
0x1f3c82  newarr   Microsoft.Crm.ObjectModel.Store.EntityMessage
0x1f3c87  dup
0x1f3c88  ldc.i4.0
0x1f3c89  ldstr    aProduct_0// "Product"
0x1f3c8e  ldstr    aRevertproduct// "RevertProduct"
0x1f3c93  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3c98  stelem.ref
0x1f3c99  dup
0x1f3c9a  ldc.i4.1
0x1f3c9b  ldstr    aDynamicpropert// "DynamicProperty"
0x1f3ca0  ldstr    aCreate// "Create"
0x1f3ca5  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3caa  stelem.ref
0x1f3cab  dup
0x1f3cac  ldc.i4.2
0x1f3cad  ldstr    aDynamicpropert// "DynamicProperty"
0x1f3cb2  ldstr    aUpdate// "Update"
0x1f3cb7  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3cbc  stelem.ref
0x1f3cbd  dup
0x1f3cbe  ldc.i4.3
0x1f3cbf  ldstr    aDynamicpropert// "DynamicProperty"
0x1f3cc4  ldstr    aDelete// "Delete"
0x1f3cc9  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3cce  stelem.ref
0x1f3ccf  dup
0x1f3cd0  ldc.i4.4
0x1f3cd1  ldstr    aDynamicpropert_0// "DynamicPropertyAssociation"
0x1f3cd6  ldstr    aCreate// "Create"
0x1f3cdb  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3ce0  stelem.ref
0x1f3ce1  dup
0x1f3ce2  ldc.i4.5
0x1f3ce3  ldstr    aDynamicpropert_0// "DynamicPropertyAssociation"
0x1f3ce8  ldstr    aUpdate// "Update"
0x1f3ced  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3cf2  stelem.ref
0x1f3cf3  dup
0x1f3cf4  ldc.i4.6
0x1f3cf5  ldstr    aDynamicpropert_0// "DynamicPropertyAssociation"
0x1f3cfa  ldstr    aDelete// "Delete"
0x1f3cff  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d04  stelem.ref
0x1f3d05  dup
0x1f3d06  ldc.i4.7
0x1f3d07  ldstr    aProduct_0// "Product"
0x1f3d0c  ldstr    aSetstate// "SetState"
0x1f3d11  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d16  stelem.ref
0x1f3d17  dup
0x1f3d18  ldc.i4.8
0x1f3d19  ldstr    aProductassocia// "ProductAssociation"
0x1f3d1e  ldstr    aCreate// "Create"
0x1f3d23  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d28  stelem.ref
0x1f3d29  dup
0x1f3d2a  ldc.i4.s 9
0x1f3d2c  ldstr    aProductassocia// "ProductAssociation"
0x1f3d31  ldstr    aUpdate// "Update"
0x1f3d36  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d3b  stelem.ref
0x1f3d3c  dup
0x1f3d3d  ldc.i4.s 0xA
0x1f3d3f  ldstr    aProductsubstit// "ProductSubstitute"
0x1f3d44  ldstr    aCreate// "Create"
0x1f3d49  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d4e  stelem.ref
0x1f3d4f  dup
0x1f3d50  ldc.i4.s 0xB
0x1f3d52  ldstr    aProductsubstit// "ProductSubstitute"
0x1f3d57  ldstr    aUpdate// "Update"
0x1f3d5c  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d61  stelem.ref
0x1f3d62  dup
0x1f3d63  ldc.i4.s 0xC
0x1f3d65  ldstr    aProductsubstit// "ProductSubstitute"
0x1f3d6a  ldstr    aDelete// "Delete"
0x1f3d6f  newobj   instance void Microsoft.Crm.ObjectModel.Store.EntityMessage::.ctor(string entityLogicalName, string messageName)
0x1f3d74  stelem.ref
0x1f3d75  stsfld   class Microsoft.Crm.ObjectModel.Store.EntityMessage[] Microsoft.Crm.ObjectModel.Store.AllowedEntityMessages::AllowedMessages
0x1f3d7a  ret
```
