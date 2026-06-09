# Microsoft.Crm.Metadata.RelationshipService::ValidateParentalRelationship

- ea: `0x53730`
- end: `0x538c4`
- name: `Microsoft.Crm.Metadata.RelationshipService::ValidateParentalRelationship`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x52eb0`
- `0x534f0`

## callees

- `0x53220`
- `0x53730`
- `0x53d80`

## string_xrefs

- `0x5376d`: `Cannot create relationships that result in a cycle, ReferencedEntityId={0},ReferencedEntityIsPublishable={1},referencedEntity.MetadataEntityMetadata={2}`
- `0x5380c`: `Entity: {0} is parented to Entity with id: {1}. Cannot create another parental relation with Entity: {2}`
- `0x53870`: `Cannot create relationships that result in a cycle, referencedEntityId={0},referencingEntityId={1},referencedEntityName={2},referencingEntityName={3}`

## pseudocode

```c

```

## disassembly

```asm
0x53730  ldarg.1
0x53731  ldstr    aEntityid// "entityid"
0x53736  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5373b  unbox.any [mscorlib]System.Guid
0x53740  stloc.0
0x53741  ldarg.2
0x53742  ldstr    aEntityid// "entityid"
0x53747  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5374c  unbox.any [mscorlib]System.Guid
0x53751  stloc.1
0x53752  ldloc.1
0x53753  ldloc.0
0x53754  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x53759  brfalse.s loc_537B2
0x5375b  ldarg.1
0x5375c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x53761  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x53766  brfalse.s loc_537B2
0x53768  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5376d  ldstr    aCannotCreateRe_1// "Cannot create relationships that result"...
0x53772  ldc.i4.3
0x53773  newarr   [mscorlib]System.Object
0x53778  dup
0x53779  ldc.i4.0
0x5377a  ldloc.0
0x5377b  box      [mscorlib]System.Guid
0x53780  stelem.ref
0x53781  dup
0x53782  ldc.i4.1
0x53783  ldarg.1
0x53784  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x53789  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x5378e  box      [mscorlib]System.Boolean
0x53793  stelem.ref
0x53794  dup
0x53795  ldc.i4.2
0x53796  ldarg.1
0x53797  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x5379c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Name()
0x537a1  stelem.ref
0x537a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x537a7  ldc.i4   0x80047004
0x537ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x537b1  throw
0x537b2  ldarg.2
0x537b3  ldstr    aCanbechildincu// "canbechildincustomrelationship"
0x537b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x537bd  unbox.any [mscorlib]System.Boolean
0x537c2  brtrue.s loc_537ED
0x537c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x537c9  ldstr    aEntityWithId0C// "Entity with id {0} cannot be the child "...
0x537ce  ldc.i4.1
0x537cf  newarr   [mscorlib]System.Object
0x537d4  dup
0x537d5  ldc.i4.0
0x537d6  ldloc.0
0x537d7  box      [mscorlib]System.Guid
0x537dc  stelem.ref
0x537dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x537e2  ldc.i4   0x8004432D
0x537e7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x537ec  throw
0x537ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x537f2  stloc.2
0x537f3  ldarg.0
0x537f4  ldloc.1
0x537f5  ldarg.3
0x537f6  ldarg.s  4
0x537f8  ldarg.s  5
0x537fa  ldloca.s 2
0x537fc  ldarg.s  6
0x537fe  ldarg.s  7
0x53800  call     instance bool Microsoft.Crm.Metadata.RelationshipService::TryGetParentalEntityId(valuetype [mscorlib]System.Guid referencingEntityId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingAttribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata referencingAttributeMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] valuetype [mscorlib]System.Guid& parentalEntityId, bool isPartOfPolymorphicRelationships, valuetype [mscorlib]System.Guid relationshipReferencingAttributeId)
0x53805  brfalse.s loc_53856
0x53807  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5380c  ldstr    aEntity0IsParen// "Entity: {0} is parented to Entity with "...
0x53811  ldc.i4.3
0x53812  newarr   [mscorlib]System.Object
0x53817  dup
0x53818  ldc.i4.0
0x53819  ldarg.2
0x5381a  ldstr    aName// "name"
0x5381f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53824  castclass [mscorlib]System.String
0x53829  stelem.ref
0x5382a  dup
0x5382b  ldc.i4.1
0x5382c  ldloc.2
0x5382d  box      [mscorlib]System.Guid
0x53832  stelem.ref
0x53833  dup
0x53834  ldc.i4.2
0x53835  ldarg.1
0x53836  ldstr    aName// "name"
0x5383b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53840  castclass [mscorlib]System.String
0x53845  stelem.ref
0x53846  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5384b  ldc.i4   0x80047007
0x53850  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53855  throw
0x53856  ldloc.0
0x53857  ldloc.1
0x53858  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5385d  brfalse.s loc_538C3
0x5385f  ldarg.0
0x53860  ldloc.0
0x53861  ldloc.1
0x53862  ldarg.s  5
0x53864  call     instance bool Microsoft.Crm.Metadata.RelationshipService::LoopDetected(valuetype [mscorlib]System.Guid sourceEntityId, valuetype [mscorlib]System.Guid destinationEntityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x53869  brfalse.s loc_538C3
0x5386b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53870  ldstr    aCannotCreateRe_2// "Cannot create relationships that result"...
0x53875  ldc.i4.4
0x53876  newarr   [mscorlib]System.Object
0x5387b  dup
0x5387c  ldc.i4.0
0x5387d  ldloc.0
0x5387e  box      [mscorlib]System.Guid
0x53883  stelem.ref
0x53884  dup
0x53885  ldc.i4.1
0x53886  ldloc.1
0x53887  box      [mscorlib]System.Guid
0x5388c  stelem.ref
0x5388d  dup
0x5388e  ldc.i4.2
0x5388f  ldarg.1
0x53890  ldstr    aName// "name"
0x53895  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5389a  castclass [mscorlib]System.String
0x5389f  stelem.ref
0x538a0  dup
0x538a1  ldc.i4.3
0x538a2  ldarg.2
0x538a3  ldstr    aName// "name"
0x538a8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x538ad  castclass [mscorlib]System.String
0x538b2  stelem.ref
0x538b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x538b8  ldc.i4   0x80047004
0x538bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x538c2  throw
0x538c3  ret
```
