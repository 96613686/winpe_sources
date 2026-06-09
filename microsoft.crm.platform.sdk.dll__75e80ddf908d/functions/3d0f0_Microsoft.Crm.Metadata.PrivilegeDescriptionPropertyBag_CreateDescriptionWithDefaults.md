# Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x3d0f0`
- end: `0x3d184`
- name: `Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3cb10`
- `0x3cf00`
- `0x6fd60`

## string_xrefs

- `0x3d0fd`: `privilegeid`
- `0x3d152`: `accessright`

## pseudocode

```c

```

## disassembly

```asm
0x3d0f0  ldarg.1
0x3d0f1  newobj   instance void Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3d0f6  dup
0x3d0f7  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x3d0fc  dup
0x3d0fd  ldstr    aPrivilegeid_1// "privilegeid"
0x3d102  ldarg.0
0x3d103  box      [mscorlib]System.Guid
0x3d108  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d10d  dup
0x3d10e  ldstr    aCanbebasic_0// "canbebasic"
0x3d113  ldc.i4.0
0x3d114  box      [mscorlib]System.Boolean
0x3d119  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d11e  dup
0x3d11f  ldstr    aCanbelocal_0// "canbelocal"
0x3d124  ldc.i4.0
0x3d125  box      [mscorlib]System.Boolean
0x3d12a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d12f  dup
0x3d130  ldstr    aCanbedeep_0// "canbedeep"
0x3d135  ldc.i4.0
0x3d136  box      [mscorlib]System.Boolean
0x3d13b  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d140  dup
0x3d141  ldstr    aCanbeglobal_0// "canbeglobal"
0x3d146  ldc.i4.0
0x3d147  box      [mscorlib]System.Boolean
0x3d14c  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d151  dup
0x3d152  ldstr    aAccessright_0// "accessright"
0x3d157  ldc.i4.0
0x3d158  box      [mscorlib]System.Int32
0x3d15d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d162  dup
0x3d163  ldstr    aCanbeentityref_0// "canbeentityreference"
0x3d168  ldc.i4.0
0x3d169  box      [mscorlib]System.Boolean
0x3d16e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d173  ldstr    aCanbeparentent_0// "canbeparententityreference"
0x3d178  ldc.i4.0
0x3d179  box      [mscorlib]System.Boolean
0x3d17e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3d183  ret
```
