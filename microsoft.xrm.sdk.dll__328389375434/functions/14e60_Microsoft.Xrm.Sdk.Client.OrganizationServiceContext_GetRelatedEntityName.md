# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntityName

- ea: `0x14e60`
- end: `0x14f18`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntityName`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x14dd0`

## callees

- `0x3b90`
- `0x72f0`
- `0x7310`
- `0x10a60`
- `0x10ad0`
- `0x10b20`
- `0x140d0`
- `0x14e60`
- `0x1f4f0`
- `0x1f510`
- `0x1f980`
- `0x1f9c0`

## pseudocode

```c

```

## disassembly

```asm
0x14e60  ldarg.2
0x14e61  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityRole> Microsoft.Xrm.Sdk.Relationship::get_PrimaryEntityRole()
0x14e66  stloc.3
0x14e67  ldloca.s 3
0x14e69  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityRole>::get_HasValue()
0x14e6e  brfalse.s loc_14E77
0x14e70  ldarg.1
0x14e71  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14e76  ret
0x14e77  ldarg.0
0x14e78  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipRequest::.ctor()
0x14e7d  dup
0x14e7e  ldarg.2
0x14e7f  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x14e84  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipRequest::set_Name(string value)
0x14e89  call     instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x14e8e  isinst   Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipResponse
0x14e93  stloc.0
0x14e94  ldloc.0
0x14e95  callvirt instance class Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipResponse::get_RelationshipMetadata()
0x14e9a  isinst   Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x14e9f  stloc.1
0x14ea0  ldloc.1
0x14ea1  brfalse.s loc_14EC4
0x14ea3  ldloc.1
0x14ea4  callvirt instance string Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingEntity()
0x14ea9  ldarg.1
0x14eaa  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14eaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14eb4  brtrue.s loc_14EBD
0x14eb6  ldloc.1
0x14eb7  callvirt instance string Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingEntity()
0x14ebc  ret
0x14ebd  ldloc.1
0x14ebe  callvirt instance string Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedEntity()
0x14ec3  ret
0x14ec4  ldloc.0
0x14ec5  callvirt instance class Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipResponse::get_RelationshipMetadata()
0x14eca  isinst   Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x14ecf  stloc.2
0x14ed0  ldloc.2
0x14ed1  brfalse.s loc_14EF4
0x14ed3  ldloc.2
0x14ed4  callvirt instance string Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1LogicalName()
0x14ed9  ldarg.1
0x14eda  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14edf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14ee4  brtrue.s loc_14EED
0x14ee6  ldloc.2
0x14ee7  callvirt instance string Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1LogicalName()
0x14eec  ret
0x14eed  ldloc.2
0x14eee  callvirt instance string Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2LogicalName()
0x14ef3  ret
0x14ef4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14ef9  ldstr    aUnableToLoadTh// "Unable to load the '{0}' relationship."
0x14efe  ldc.i4.1
0x14eff  newarr   [mscorlib]System.Object
0x14f04  dup
0x14f05  ldc.i4.0
0x14f06  ldarg.2
0x14f07  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x14f0c  stelem.ref
0x14f0d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14f12  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x14f17  throw
```
