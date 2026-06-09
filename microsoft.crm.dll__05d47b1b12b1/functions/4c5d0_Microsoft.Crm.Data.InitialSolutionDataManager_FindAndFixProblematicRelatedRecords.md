# Microsoft.Crm.Data.InitialSolutionDataManager::FindAndFixProblematicRelatedRecords

- ea: `0x4c5d0`
- end: `0x4c8a6`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::FindAndFixProblematicRelatedRecords`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4c990`

## callees

- `0x4c5d0`
- `0x50d40`
- `0x50d60`

## string_xrefs

- `0x4c7d2`: `[Successfully updated related record]`
- `0x4c7ea`: `[Update of related record failed with : `

## pseudocode

```c

```

## disassembly

```asm
0x4c5d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4c5d5  stloc.0
0x4c5d6  ldarg.s  5
0x4c5d8  ldc.i4.0
0x4c5d9  stind.i4
0x4c5da  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::.ctor()
0x4c5df  stloc.1
0x4c5e0  ldloc.1
0x4c5e1  ldarg.2
0x4c5e2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::set_LogicalName(string)
0x4c5e7  ldloc.1
0x4c5e8  ldc.i4.s 0xF
0x4c5ea  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityRequest::set_EntityFilters(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityFilters)
0x4c5ef  ldarg.1
0x4c5f0  ldloc.1
0x4c5f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x4c5f6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityResponse
0x4c5fb  stloc.2
0x4c5fc  leave.s  loc_4C624
0x4c5fe  stloc.3
0x4c5ff  ldloc.0
0x4c600  ldstr    aExceptionGetti// "Exception getting metadata : "
0x4c605  ldloc.3
0x4c606  callvirt instance string [mscorlib]System.Object::ToString()
0x4c60b  call     string [mscorlib]System.String::Concat(string, string)
0x4c610  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c615  pop
0x4c616  ldarg.s  4
0x4c618  ldloc.0
0x4c619  callvirt instance string [mscorlib]System.Object::ToString()
0x4c61e  stind.ref
0x4c61f  leave    loc_4C8A5
0x4c624  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class RelationshipData>::.ctor()
0x4c629  dup
0x4c62a  ldloc.2
0x4c62b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveEntityResponse::get_EntityMetadata()
0x4c630  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata[] [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_OneToManyRelationships()
0x4c635  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, bool> <>c::<>9__10_0
0x4c63a  dup
0x4c63b  brtrue.s loc_4C654
0x4c63d  pop
0x4c63e  ldsfld   class <>c <>c::<>9
0x4c643  ldftn    instance bool <>c::<FindAndFixProblematicRelatedRecords>b__10_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata x)
0x4c649  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, bool>::.ctor(object, native int)
0x4c64e  dup
0x4c64f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, bool> <>c::<>9__10_0
0x4c654  call     T0x2B000069
0x4c659  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, class RelationshipData> <>c::<>9__10_1
0x4c65e  dup
0x4c65f  brtrue.s loc_4C678
0x4c661  pop
0x4c662  ldsfld   class <>c <>c::<>9
0x4c667  ldftn    instance class RelationshipData <>c::<FindAndFixProblematicRelatedRecords>b__10_1(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata x)
0x4c66d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, class RelationshipData>::.ctor(object, native int)
0x4c672  dup
0x4c673  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata, class RelationshipData> <>c::<>9__10_1
0x4c678  call     T0x2B00006A
0x4c67d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RelationshipData>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4c682  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class RelationshipData>::GetEnumerator()
0x4c687  stloc.s  4
0x4c689  br       loc_4C880
0x4c68e  ldloca.s 4
0x4c690  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RelationshipData>::get_Current()
0x4c695  stloc.s  5
0x4c697  ldloc.s  5
0x4c699  callvirt instance string RelationshipData::get_RelatedEntityName()
0x4c69e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4c6a3  stloc.s  6
0x4c6a5  ldloc.s  6
0x4c6a7  ldc.i4.1
0x4c6a8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x4c6ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4c6b2  ldloc.s  5
0x4c6b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata RelationshipData::get_Metadata()
0x4c6b9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x4c6be  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::.ctor(string)
0x4c6c3  stloc.s  7
0x4c6c5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection::.ctor()
0x4c6ca  stloc.s  8
0x4c6cc  ldloc.s  8
0x4c6ce  ldloc.s  7
0x4c6d0  ldloc.s  6
0x4c6d2  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase>::Add(var<u1>, !!T0)
0x4c6d7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x4c6dc  stloc.s  9
0x4c6de  ldloc.s  9
0x4c6e0  ldc.i4.1
0x4c6e1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x4c6e6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4c6eb  ldloc.s  9
0x4c6ed  ldloc.s  8
0x4c6ef  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_RelatedEntitiesQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection)
0x4c6f4  ldloc.s  9
0x4c6f6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor()
0x4c6fb  dup
0x4c6fc  ldarg.3
0x4c6fd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Id(valuetype [mscorlib]System.Guid)
0x4c702  dup
0x4c703  ldarg.2
0x4c704  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_LogicalName(string)
0x4c709  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x4c70e  ldarg.1
0x4c70f  ldloc.s  9
0x4c711  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x4c716  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x4c71b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x4c720  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x4c725  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Values()
0x4c72a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::GetEnumerator()
0x4c72f  stloc.s  0xA
0x4c731  br       loc_4C81D
0x4c736  ldloc.s  0xA
0x4c738  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Current()
0x4c73d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x4c742  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x4c747  stloc.s  0xB
0x4c749  br       loc_4C803
0x4c74e  ldloc.s  0xB
0x4c750  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x4c755  stloc.s  0xC
0x4c757  ldloc.0
0x4c758  ldc.i4.7
0x4c759  newarr   [mscorlib]System.Object
0x4c75e  dup
0x4c75f  ldc.i4.0
0x4c760  ldstr    aRelatedRecord// "[Related record,"
0x4c765  stelem.ref
0x4c766  dup
0x4c767  ldc.i4.1
0x4c768  ldloc.s  5
0x4c76a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata RelationshipData::get_Metadata()
0x4c76f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x4c774  stelem.ref
0x4c775  dup
0x4c776  ldc.i4.2
0x4c777  ldstr    asc_6B1E0// ","
0x4c77c  stelem.ref
0x4c77d  dup
0x4c77e  ldc.i4.3
0x4c77f  ldloc.s  0xC
0x4c781  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x4c786  stelem.ref
0x4c787  dup
0x4c788  ldc.i4.4
0x4c789  ldstr    asc_6B1E0// ","
0x4c78e  stelem.ref
0x4c78f  dup
0x4c790  ldc.i4.5
0x4c791  ldloc.s  0xC
0x4c793  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4c798  box      [mscorlib]System.Guid
0x4c79d  stelem.ref
0x4c79e  dup
0x4c79f  ldc.i4.6
0x4c7a0  ldstr    asc_6E6E2// "]"
0x4c7a5  stelem.ref
0x4c7a6  call     string [mscorlib]System.String::Concat(object[])
0x4c7ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c7b0  pop
0x4c7b1  ldloc.s  5
0x4c7b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata RelationshipData::get_Metadata()
0x4c7b8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingAttribute()
0x4c7bd  stloc.s  0xD
0x4c7bf  ldloc.s  0xC
0x4c7c1  ldloc.s  0xD
0x4c7c3  ldnull
0x4c7c4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x4c7c9  ldarg.1
0x4c7ca  ldloc.s  0xC
0x4c7cc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x4c7d1  ldloc.0
0x4c7d2  ldstr    aSuccessfullyUp// "[Successfully updated related record]"
0x4c7d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c7dc  pop
0x4c7dd  ldarg.s  5
0x4c7df  ldarg.s  5
0x4c7e1  ldind.i4
0x4c7e2  ldc.i4.1
0x4c7e3  add
0x4c7e4  stind.i4
0x4c7e5  leave.s  loc_4C803
0x4c7e7  stloc.s  0xE
0x4c7e9  ldloc.0
0x4c7ea  ldstr    aUpdateOfRelate// "[Update of related record failed with :"...
0x4c7ef  ldloc.s  0xE
0x4c7f1  ldstr    asc_6E6E2// "]"
0x4c7f6  call     string [mscorlib]System.String::Concat(object, object, object)
0x4c7fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c800  pop
0x4c801  leave.s  loc_4C803
0x4c803  ldloc.s  0xB
0x4c805  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c80a  brtrue   loc_4C74E
0x4c80f  leave.s  loc_4C81D
0x4c811  ldloc.s  0xB
0x4c813  brfalse.s loc_4C81C
0x4c815  ldloc.s  0xB
0x4c817  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c81c  endfinally
0x4c81d  ldloc.s  0xA
0x4c81f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c824  brtrue   loc_4C736
0x4c829  leave.s  loc_4C837
0x4c82b  ldloc.s  0xA
0x4c82d  brfalse.s loc_4C836
0x4c82f  ldloc.s  0xA
0x4c831  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c836  endfinally
0x4c837  leave.s  loc_4C880
0x4c839  stloc.s  0xF
0x4c83b  ldloc.0
0x4c83c  ldc.i4.5
0x4c83d  newarr   [mscorlib]System.String
0x4c842  dup
0x4c843  ldc.i4.0
0x4c844  ldstr    aExceptionRetri_0// "[Exception retrieving records for relat"...
0x4c849  stelem.ref
0x4c84a  dup
0x4c84b  ldc.i4.1
0x4c84c  ldloc.s  5
0x4c84e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata RelationshipData::get_Metadata()
0x4c853  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x4c858  stelem.ref
0x4c859  dup
0x4c85a  ldc.i4.2
0x4c85b  ldstr    asc_7BC08// " : "
0x4c860  stelem.ref
0x4c861  dup
0x4c862  ldc.i4.3
0x4c863  ldloc.s  0xF
0x4c865  callvirt instance string [mscorlib]System.Object::ToString()
0x4c86a  stelem.ref
0x4c86b  dup
0x4c86c  ldc.i4.4
0x4c86d  ldstr    asc_6E6E2// "]"
0x4c872  stelem.ref
0x4c873  call     string [mscorlib]System.String::Concat(string[])
0x4c878  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c87d  pop
0x4c87e  leave.s  loc_4C880
0x4c880  ldloca.s 4
0x4c882  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RelationshipData>::MoveNext()
0x4c887  brtrue   loc_4C68E
0x4c88c  leave.s  loc_4C89C
0x4c88e  ldloca.s 4
0x4c890  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RelationshipData>
0x4c896  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c89b  endfinally
0x4c89c  ldarg.s  4
0x4c89e  ldloc.0
0x4c89f  callvirt instance string [mscorlib]System.Object::ToString()
0x4c8a4  stind.ref
0x4c8a5  ret
```
