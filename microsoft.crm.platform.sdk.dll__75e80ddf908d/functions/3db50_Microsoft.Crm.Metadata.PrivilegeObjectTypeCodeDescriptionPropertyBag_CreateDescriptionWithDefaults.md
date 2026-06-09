# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x3db50`
- end: `0x3db93`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3d770`
- `0x3d980`
- `0x6fd60`

## string_xrefs

- `0x3db6e`: `privilegeid`
- `0x3db5d`: `privilegeobjecttypecodeid`

## pseudocode

```c

```

## disassembly

```asm
0x3db50  ldarg.1
0x3db51  newobj   instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3db56  dup
0x3db57  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::get_InnerEntityData()
0x3db5c  dup
0x3db5d  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodeid"
0x3db62  ldarg.0
0x3db63  box      [mscorlib]System.Guid
0x3db68  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3db6d  dup
0x3db6e  ldstr    aPrivilegeid_1// "privilegeid"
0x3db73  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3db78  box      [mscorlib]System.Guid
0x3db7d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3db82  ldstr    aObjecttypecode_0// "objecttypecode"
0x3db87  ldc.i4.0
0x3db88  box      [mscorlib]System.Int32
0x3db8d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3db92  ret
```
