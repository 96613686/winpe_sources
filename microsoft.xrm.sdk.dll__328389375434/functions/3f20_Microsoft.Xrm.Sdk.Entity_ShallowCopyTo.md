# Microsoft.Xrm.Sdk.Entity::ShallowCopyTo

- ea: `0x3f20`
- end: `0x3f94`
- name: `Microsoft.Xrm.Sdk.Entity::ShallowCopyTo`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x3e00`
- `0x6fc0`
- `0x7080`

## callees

- `0x3b90`
- `0x3bc0`
- `0x3bd0`
- `0x3c00`
- `0x3c20`
- `0x3c30`
- `0x3c60`
- `0x3c80`
- `0x3c90`
- `0x3ce0`
- `0x3cf0`
- `0x3d00`
- `0x3d20`
- `0x3f20`
- `0x4270`
- `0x4280`
- `0x4290`
- `0x42d0`
- `0x42e0`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldarg.1
0x3f21  brfalse.s loc_3F93
0x3f23  ldarg.1
0x3f24  ldarg.0
0x3f25  beq.s    loc_3F93
0x3f27  ldarg.1
0x3f28  ldarg.0
0x3f29  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x3f2e  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid value)
0x3f33  ldarg.1
0x3f34  ldarg.0
0x3f35  call     instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x3f3a  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetLogicalNameInternal(string logicalName)
0x3f3f  ldarg.1
0x3f40  ldarg.0
0x3f41  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x3f46  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x3f4b  ldarg.1
0x3f4c  ldarg.0
0x3f4d  call     instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x3f52  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetRelatedEntitiesInternal(class Microsoft.Xrm.Sdk.RelatedEntityCollection relatedEntities)
0x3f57  ldarg.1
0x3f58  ldarg.0
0x3f59  call     instance class Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3f5e  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_Attributes(class Microsoft.Xrm.Sdk.AttributeCollection value)
0x3f63  ldarg.1
0x3f64  ldarg.0
0x3f65  call     instance class Microsoft.Xrm.Sdk.FormattedValueCollection Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x3f6a  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_FormattedValues(class Microsoft.Xrm.Sdk.FormattedValueCollection value)
0x3f6f  ldarg.1
0x3f70  ldarg.0
0x3f71  call     instance class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject Microsoft.Xrm.Sdk.Entity::get_ExtensionData()
0x3f76  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_ExtensionData(class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject value)
0x3f7b  ldarg.1
0x3f7c  ldarg.0
0x3f7d  call     instance string Microsoft.Xrm.Sdk.Entity::get_RowVersion()
0x3f82  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_RowVersion(string value)
0x3f87  ldarg.1
0x3f88  ldarg.0
0x3f89  call     instance class Microsoft.Xrm.Sdk.KeyAttributeCollection Microsoft.Xrm.Sdk.Entity::get_KeyAttributes()
0x3f8e  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_KeyAttributes(class Microsoft.Xrm.Sdk.KeyAttributeCollection value)
0x3f93  ret
```
