# Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x40be0`
- end: `0x40c6b`
- name: `Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x40880`
- `0x40b40`
- `0x6fd60`

## string_xrefs

- `0x40c13`: `privilegeid`
- `0x40bed`: `roletemplateprivilegeid`
- `0x40bfe`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x40be0  ldarg.1
0x40be1  newobj   instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x40be6  dup
0x40be7  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x40bec  dup
0x40bed  ldstr    aRoletemplatepr_4// "roletemplateprivilegeid"
0x40bf2  ldarg.0
0x40bf3  box      [mscorlib]System.Guid
0x40bf8  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40bfd  dup
0x40bfe  ldstr    aRoletemplateid_1// "roletemplateid"
0x40c03  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40c08  box      [mscorlib]System.Guid
0x40c0d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c12  dup
0x40c13  ldstr    aPrivilegeid_1// "privilegeid"
0x40c18  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40c1d  box      [mscorlib]System.Guid
0x40c22  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c27  dup
0x40c28  ldstr    aIsbasic_0// "isbasic"
0x40c2d  ldc.i4.0
0x40c2e  box      [mscorlib]System.Boolean
0x40c33  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c38  dup
0x40c39  ldstr    aIslocal_0// "islocal"
0x40c3e  ldc.i4.0
0x40c3f  box      [mscorlib]System.Boolean
0x40c44  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c49  dup
0x40c4a  ldstr    aIsdeep_0// "isdeep"
0x40c4f  ldc.i4.0
0x40c50  box      [mscorlib]System.Boolean
0x40c55  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c5a  ldstr    aIsglobal_0// "isglobal"
0x40c5f  ldc.i4.0
0x40c60  box      [mscorlib]System.Boolean
0x40c65  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x40c6a  ret
```
