# Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeLinkTypes

- ea: `0x538d0`
- end: `0x53be5`
- name: `Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeLinkTypes`
- size: `789`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x52eb0`
- `0x534f0`

## callees

- `0x538d0`
- `0x53bf0`
- `0x53d00`

## string_xrefs

- `0x5392a`: `Cascade User-Owned is not a valid cascade link type for org-owned entity relationships.`
- `0x5397b`: `Cascade ActiveOnly is not a valid cascade link type for relationships where the referencing entity has no statecode attribute.`
- `0x539f7`: `Cascade link type '{0}' is invalid for Delete.`
- `0x53a48`: `Cascade link type '{0}' is invalid for Share.`
- `0x53a99`: `Cascade link type '{0}' is invalid for Unshare.`
- `0x53aea`: `Cascade link type '{0}' is invalid for Reparent.`
- `0x53b44`: `Cascade link type '{0}' is invalid for Assign.`
- `0x53ba2`: `For Relationships referencing Virtual Entites, Cascade link type must be No Cascade`

## pseudocode

```c

```

## disassembly

```asm
0x538d0  ldarg.1
0x538d1  ldstr    aOwnershiptypem// "ownershiptypemask"
0x538d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x538db  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x538e0  ldc.i4.1
0x538e1  and
0x538e2  brtrue.s loc_538E7
0x538e4  ldc.i4.0
0x538e5  br.s     loc_538E8
0x538e7  ldc.i4.1
0x538e8  ldarg.2
0x538e9  ldstr    aOwnershiptypem// "ownershiptypemask"
0x538ee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x538f3  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x538f8  ldc.i4.1
0x538f9  and
0x538fa  brtrue.s loc_538FF
0x538fc  ldc.i4.0
0x538fd  br.s     loc_53900
0x538ff  ldc.i4.1
0x53900  stloc.0
0x53901  brfalse.s loc_53906
0x53903  ldloc.0
0x53904  brtrue.s loc_5393A
0x53906  ldarg.0
0x53907  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x5390c  ldc.i4.5
0x5390d  beq.s    loc_5392A
0x5390f  ldarg.0
0x53910  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53915  ldc.i4.5
0x53916  beq.s    loc_5392A
0x53918  ldarg.0
0x53919  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x5391e  ldc.i4.5
0x5391f  beq.s    loc_5392A
0x53921  ldarg.0
0x53922  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53927  ldc.i4.5
0x53928  bne.un.s loc_5393A
0x5392a  ldstr    aCascadeUserOwn// "Cascade User-Owned is not a valid casca"...
0x5392f  ldc.i4   0x80044156
0x53934  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53939  throw
0x5393a  ldarg.1
0x5393b  ldstr    aEntityid// "entityid"
0x53940  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53945  unbox.any [mscorlib]System.Guid
0x5394a  ldarg.3
0x5394b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x53950  call     bool Microsoft.Crm.Metadata.RelationshipService::DoesReferencingEntityHaveState(valuetype [mscorlib]System.Guid referencingEntityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x53955  brtrue.s loc_5398B
0x53957  ldarg.0
0x53958  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x5395d  ldc.i4.4
0x5395e  beq.s    loc_5397B
0x53960  ldarg.0
0x53961  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53966  ldc.i4.4
0x53967  beq.s    loc_5397B
0x53969  ldarg.0
0x5396a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x5396f  ldc.i4.4
0x53970  beq.s    loc_5397B
0x53972  ldarg.0
0x53973  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53978  ldc.i4.4
0x53979  bne.un.s loc_5398B
0x5397b  ldstr    aCascadeActiveo// "Cascade ActiveOnly is not a valid casca"...
0x53980  ldc.i4   0x80048204
0x53985  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5398a  throw
0x5398b  ldc.i4.0
0x5398c  stloc.1
0x5398d  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x53992  ldarg.0
0x53993  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencingEntityId()
0x53998  ldstr    aEntity_0// "Entity"
0x5399d  ldarg.3
0x5399e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x539a3  ldarga.s 1
0x539a5  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::TryRetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x539aa  brfalse.s loc_539C1
0x539ac  ldarg.1
0x539ad  brfalse.s loc_539BF
0x539af  ldarg.1
0x539b0  ldstr    aDataproviderid// "dataproviderid"
0x539b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x539ba  ldnull
0x539bb  cgt.un
0x539bd  br.s     loc_539C0
0x539bf  ldc.i4.0
0x539c0  stloc.1
0x539c1  ldloc.1
0x539c2  brtrue   loc_53B6D
0x539c7  ldarg.0
0x539c8  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x539cd  ldc.i4.1
0x539ce  beq.s    loc_53A20
0x539d0  ldarg.0
0x539d1  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x539d6  ldc.i4.2
0x539d7  beq.s    loc_53A20
0x539d9  ldarg.0
0x539da  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x539df  ldc.i4.3
0x539e0  beq.s    loc_53A20
0x539e2  ldarg.0
0x539e3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x539e8  brtrue.s loc_539F2
0x539ea  ldarg.0
0x539eb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_IsCustomRelationship()
0x539f0  brfalse.s loc_53A20
0x539f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x539f7  ldstr    aCascadeLinkTyp// "Cascade link type '{0}' is invalid for "...
0x539fc  ldc.i4.1
0x539fd  newarr   [mscorlib]System.Object
0x53a02  dup
0x53a03  ldc.i4.0
0x53a04  ldarg.0
0x53a05  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x53a0a  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53a0f  stelem.ref
0x53a10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53a15  ldc.i4   0x80048204
0x53a1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53a1f  throw
0x53a20  ldarg.0
0x53a21  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53a26  ldc.i4.1
0x53a27  beq.s    loc_53A71
0x53a29  ldarg.0
0x53a2a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53a2f  brfalse.s loc_53A71
0x53a31  ldarg.0
0x53a32  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53a37  ldc.i4.5
0x53a38  beq.s    loc_53A71
0x53a3a  ldarg.0
0x53a3b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53a40  ldc.i4.4
0x53a41  beq.s    loc_53A71
0x53a43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53a48  ldstr    aCascadeLinkTyp_0// "Cascade link type '{0}' is invalid for "...
0x53a4d  ldc.i4.1
0x53a4e  newarr   [mscorlib]System.Object
0x53a53  dup
0x53a54  ldc.i4.0
0x53a55  ldarg.0
0x53a56  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53a5b  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53a60  stelem.ref
0x53a61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53a66  ldc.i4   0x80048204
0x53a6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53a70  throw
0x53a71  ldarg.0
0x53a72  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53a77  ldc.i4.1
0x53a78  beq.s    loc_53AC2
0x53a7a  ldarg.0
0x53a7b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53a80  brfalse.s loc_53AC2
0x53a82  ldarg.0
0x53a83  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53a88  ldc.i4.5
0x53a89  beq.s    loc_53AC2
0x53a8b  ldarg.0
0x53a8c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53a91  ldc.i4.4
0x53a92  beq.s    loc_53AC2
0x53a94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53a99  ldstr    aCascadeLinkTyp_1// "Cascade link type '{0}' is invalid for "...
0x53a9e  ldc.i4.1
0x53a9f  newarr   [mscorlib]System.Object
0x53aa4  dup
0x53aa5  ldc.i4.0
0x53aa6  ldarg.0
0x53aa7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53aac  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53ab1  stelem.ref
0x53ab2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53ab7  ldc.i4   0x80048204
0x53abc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53ac1  throw
0x53ac2  ldarg.0
0x53ac3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53ac8  ldc.i4.1
0x53ac9  beq.s    loc_53B13
0x53acb  ldarg.0
0x53acc  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53ad1  brfalse.s loc_53B13
0x53ad3  ldarg.0
0x53ad4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53ad9  ldc.i4.5
0x53ada  beq.s    loc_53B13
0x53adc  ldarg.0
0x53add  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53ae2  ldc.i4.4
0x53ae3  beq.s    loc_53B13
0x53ae5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53aea  ldstr    aCascadeLinkTyp_2// "Cascade link type '{0}' is invalid for "...
0x53aef  ldc.i4.1
0x53af0  newarr   [mscorlib]System.Object
0x53af5  dup
0x53af6  ldc.i4.0
0x53af7  ldarg.0
0x53af8  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53afd  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53b02  stelem.ref
0x53b03  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53b08  ldc.i4   0x80048204
0x53b0d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53b12  throw
0x53b13  ldarg.0
0x53b14  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b19  ldc.i4.1
0x53b1a  beq      loc_53BBD
0x53b1f  ldarg.0
0x53b20  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b25  brfalse  loc_53BBD
0x53b2a  ldarg.0
0x53b2b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b30  ldc.i4.5
0x53b31  beq      loc_53BBD
0x53b36  ldarg.0
0x53b37  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b3c  ldc.i4.4
0x53b3d  beq.s    loc_53BBD
0x53b3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53b44  ldstr    aCascadeLinkTyp_3// "Cascade link type '{0}' is invalid for "...
0x53b49  ldc.i4.1
0x53b4a  newarr   [mscorlib]System.Object
0x53b4f  dup
0x53b50  ldc.i4.0
0x53b51  ldarg.0
0x53b52  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b57  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53b5c  stelem.ref
0x53b5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53b62  ldc.i4   0x80048204
0x53b67  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53b6c  throw
0x53b6d  ldarg.0
0x53b6e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeAssign()
0x53b73  brtrue.s loc_53B9D
0x53b75  ldarg.0
0x53b76  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeReparent()
0x53b7b  brtrue.s loc_53B9D
0x53b7d  ldarg.0
0x53b7e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeUnshare()
0x53b83  brtrue.s loc_53B9D
0x53b85  ldarg.0
0x53b86  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeShare()
0x53b8b  brtrue.s loc_53B9D
0x53b8d  ldarg.0
0x53b8e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeDelete()
0x53b93  brtrue.s loc_53B9D
0x53b95  ldarg.0
0x53b96  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeMerge()
0x53b9b  brfalse.s loc_53BBD
0x53b9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53ba2  ldstr    aForRelationshi// "For Relationships referencing Virtual E"...
0x53ba7  ldc.i4.0
0x53ba8  newarr   [mscorlib]System.Object
0x53bad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53bb2  ldc.i4   0x80048204
0x53bb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53bbc  throw
0x53bbd  ldarg.0
0x53bbe  ldarg.2
0x53bbf  ldstr    aObjecttypecode_0// "objecttypecode"
0x53bc4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53bc9  unbox.any [mscorlib]System.Int32
0x53bce  ldarg.1
0x53bcf  ldstr    aEntityid// "entityid"
0x53bd4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53bd9  unbox.any [mscorlib]System.Guid
0x53bde  ldarg.3
0x53bdf  call     void Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeRollupView(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, int32 referencedEntityOtc, valuetype [mscorlib]System.Guid referencingEntityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x53be4  ret
```
