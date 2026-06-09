# Microsoft.Crm.Metadata.RelationshipService::CreateRelationshipForActivity

- ea: `0x51680`
- end: `0x51ea1`
- name: `Microsoft.Crm.Metadata.RelationshipService::CreateRelationshipForActivity`
- size: `2081`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x28b30`
- `0x514a0`
- `0x51500`
- `0x515f0`
- `0x61d00`

## callees

- `0x51680`
- `0x55090`
- `0x55950`
- `0x55bd0`
- `0x56370`
- `0x563f0`
- `0x59340`
- `0x59360`

## string_xrefs

- `0x51887`: `EntitlementTemplate`
- `0x51a3e`: `entitlementtemplate_{0}`

## pseudocode

```c

```

## disassembly

```asm
0x51680  ldarg.s  5
0x51682  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51687  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5168c  brtrue.s loc_5169A
0x5168e  ldarg.s  4
0x51690  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51695  ldc.i4.0
0x51696  ceq
0x51698  br.s     loc_5169B
0x5169a  ldc.i4.1
0x5169b  ldstr    aExpectedAtleas// "Expected atleast one of the entity name"...
0x516a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x516a5  ldarg.0
0x516a6  ldstr    aName// "name"
0x516ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x516b0  castclass [mscorlib]System.String
0x516b5  stloc.0
0x516b6  ldarg.0
0x516b7  ldstr    aCollectionname// "collectionname"
0x516bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x516c1  castclass [mscorlib]System.String
0x516c6  stloc.1
0x516c7  ldc.i4.1
0x516c8  stloc.2
0x516c9  ldc.i4.1
0x516ca  stloc.3
0x516cb  ldc.i4.1
0x516cc  stloc.s  4
0x516ce  ldc.i4.1
0x516cf  stloc.s  5
0x516d1  ldarg.s  8
0x516d3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x516d8  stloc.s  6
0x516da  ldloc.s  6
0x516dc  ldarg.s  6
0x516de  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipId(valuetype [mscorlib]System.Guid)
0x516e3  ldloc.s  6
0x516e5  ldc.i4.1
0x516e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x516eb  ldloc.s  6
0x516ed  ldc.i4.1
0x516ee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x516f3  ldloc.s  6
0x516f5  ldc.i4.1
0x516f6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x516fb  ldloc.s  6
0x516fd  ldc.i4.0
0x516fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51703  ldloc.s  6
0x51705  ldc.i4.1
0x51706  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5170b  ldloc.s  6
0x5170d  ldc.i4.1
0x5170e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51713  ldloc.s  6
0x51715  ldc.i4.1
0x51716  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5171b  ldarg.2
0x5171c  stloc.s  7
0x5171e  ldarg.3
0x5171f  stloc.s  8
0x51721  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x51726  stloc.s  9
0x51728  ldarg.s  5
0x5172a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5172f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x51734  brfalse.s loc_5178B
0x51736  ldloc.s  9
0x51738  ldarg.s  5
0x5173a  ldstr    aEntity_0// "Entity"
0x5173f  ldarg.s  8
0x51741  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51746  ldstr    aEntity_0// "Entity"
0x5174b  ldc.i4.5
0x5174c  newarr   [mscorlib]System.String
0x51751  dup
0x51752  ldc.i4.0
0x51753  ldstr    aEntityid// "entityid"
0x51758  stelem.ref
0x51759  dup
0x5175a  ldc.i4.1
0x5175b  ldstr    aName// "name"
0x51760  stelem.ref
0x51761  dup
0x51762  ldc.i4.2
0x51763  ldstr    aPhysicalname// "physicalname"
0x51768  stelem.ref
0x51769  dup
0x5176a  ldc.i4.3
0x5176b  ldstr    aObjecttypecode_0// "objecttypecode"
0x51770  stelem.ref
0x51771  dup
0x51772  ldc.i4.4
0x51773  ldstr    aLogicalname// "logicalname"
0x51778  stelem.ref
0x51779  ldarg.s  8
0x5177b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51780  ldarg.s  8
0x51782  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveAsIfPublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x51787  stloc.s  0xA
0x51789  br.s     loc_517D7
0x5178b  ldloc.s  9
0x5178d  ldarg.s  4
0x5178f  ldstr    aEntity_0// "Entity"
0x51794  ldc.i4.5
0x51795  newarr   [mscorlib]System.String
0x5179a  dup
0x5179b  ldc.i4.0
0x5179c  ldstr    aEntityid// "entityid"
0x517a1  stelem.ref
0x517a2  dup
0x517a3  ldc.i4.1
0x517a4  ldstr    aName// "name"
0x517a9  stelem.ref
0x517aa  dup
0x517ab  ldc.i4.2
0x517ac  ldstr    aPhysicalname// "physicalname"
0x517b1  stelem.ref
0x517b2  dup
0x517b3  ldc.i4.3
0x517b4  ldstr    aObjecttypecode_0// "objecttypecode"
0x517b9  stelem.ref
0x517ba  dup
0x517bb  ldc.i4.4
0x517bc  ldstr    aLogicalname// "logicalname"
0x517c1  stelem.ref
0x517c2  ldarg.s  8
0x517c4  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x517c9  ldarg.s  8
0x517cb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x517d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::RetrieveByNameAsIfPublished(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x517d5  stloc.s  0xA
0x517d7  ldloc.s  0xA
0x517d9  ldstr    aName// "name"
0x517de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x517e3  castclass [mscorlib]System.String
0x517e8  starg.s  4
0x517ea  ldloc.s  0xA
0x517ec  ldstr    aPhysicalname// "physicalname"
0x517f1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x517f6  castclass [mscorlib]System.String
0x517fb  stloc.s  0xB
0x517fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51802  ldstr    a01// "{0}_{1}"
0x51807  ldc.i4.2
0x51808  newarr   [mscorlib]System.Object
0x5180d  dup
0x5180e  ldc.i4.0
0x5180f  ldarg.s  4
0x51811  stelem.ref
0x51812  dup
0x51813  ldc.i4.1
0x51814  ldloc.1
0x51815  stelem.ref
0x51816  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5181b  stloc.s  0xC
0x5181d  ldc.i4.2
0x5181e  stloc.s  0xD
0x51820  ldloc.s  0xA
0x51822  ldstr    aObjecttypecode_0// "objecttypecode"
0x51827  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5182c  unbox.any [mscorlib]System.Int32
0x51831  stloc.s  0xE
0x51833  ldloc.s  0xB
0x51835  ldstr    aActivitypointe// "ActivityPointer"
0x5183a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5183f  brtrue.s loc_5189B
0x51841  ldloc.s  0xB
0x51843  ldstr    aActivityparty_0// "ActivityParty"
0x51848  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5184d  brtrue   loc_518F1
0x51852  ldloc.s  0xB
0x51854  ldstr    aCampaignrespon_0// "CampaignResponse"
0x51859  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5185e  brtrue   loc_51943
0x51863  ldloc.s  0xB
0x51865  ldstr    aMailbox// "Mailbox"
0x5186a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5186f  brtrue   loc_5198B
0x51874  ldloc.s  0xB
0x51876  ldstr    aEntitlement// "Entitlement"
0x5187b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51880  brtrue   loc_519E9
0x51885  ldloc.s  0xB
0x51887  ldstr    aEntitlementtem_1// "EntitlementTemplate"
0x5188c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51891  brtrue   loc_51A09
0x51896  br       loc_51A57
0x5189b  ldloc.s  6
0x5189d  ldc.i4.s 0xC
0x5189f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x518a4  ldloc.s  6
0x518a6  ldc.i4.0
0x518a7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518ac  ldloc.s  6
0x518ae  ldc.i4.0
0x518af  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518b4  ldloc.s  6
0x518b6  ldc.i4.0
0x518b7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518bc  ldloc.s  6
0x518be  ldc.i4.0
0x518bf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518c4  ldloc.s  6
0x518c6  ldc.i4.0
0x518c7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518cc  ldloc.s  6
0x518ce  ldc.i4.0
0x518cf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x518d4  ldc.i4.0
0x518d5  stloc.3
0x518d6  ldc.i4.0
0x518d7  stloc.s  5
0x518d9  ldc.i4.0
0x518da  stloc.s  4
0x518dc  ldstr    aActivityPointe// "activity_pointer_"
0x518e1  ldloc.0
0x518e2  call     string [mscorlib]System.String::Concat(string, string)
0x518e7  stloc.s  0xC
0x518e9  ldarg.1
0x518ea  stloc.s  7
0x518ec  br       loc_51A57
0x518f1  ldc.i4.0
0x518f2  stloc.2
0x518f3  ldloc.s  6
0x518f5  ldc.i4.0
0x518f6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x518fb  ldloc.s  6
0x518fd  ldc.i4.0
0x518fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51903  ldloc.s  6
0x51905  ldc.i4.0
0x51906  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5190b  ldloc.s  6
0x5190d  ldc.i4.0
0x5190e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51913  ldloc.s  6
0x51915  ldc.i4.0
0x51916  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5191b  ldloc.s  6
0x5191d  ldc.i4.0
0x5191e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51923  ldloc.s  6
0x51925  ldc.i4.0
0x51926  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5192b  ldloc.0
0x5192c  ldstr    aActivityPartie// "_activity_parties"
0x51931  call     string [mscorlib]System.String::Concat(string, string)
0x51936  stloc.s  0xC
0x51938  ldc.i4.0
0x51939  stloc.s  4
0x5193b  ldarg.1
0x5193c  stloc.s  7
0x5193e  br       loc_51A57
0x51943  ldc.i4.0
0x51944  stloc.2
0x51945  ldloc.s  6
0x51947  ldc.i4.0
0x51948  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x5194d  ldloc.s  6
0x5194f  ldc.i4.1
0x51950  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51955  ldloc.s  6
0x51957  ldc.i4.0
0x51958  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5195d  ldloc.s  6
0x5195f  ldc.i4.0
0x51960  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51965  ldloc.s  6
0x51967  ldc.i4.0
0x51968  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5196d  ldloc.s  6
0x5196f  ldc.i4.0
0x51970  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x51975  ldloc.s  6
0x51977  ldc.i4.0
0x51978  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5197d  ldc.i4.1
0x5197e  stloc.s  4
0x51980  ldc.i4.0
0x51981  stloc.s  5
0x51983  ldarg.1
0x51984  stloc.s  7
0x51986  br       loc_51A57
0x5198b  ldloc.s  6
0x5198d  ldc.i4.0
0x5198e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x51993  ldloc.s  6
0x51995  ldc.i4.0
0x51996  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x5199b  ldloc.s  6
0x5199d  ldc.i4.0
0x5199e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x519a3  ldloc.s  6
0x519a5  ldc.i4.0
0x519a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x519ab  ldloc.s  6
0x519ad  ldc.i4.0
0x519ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x519b3  ldloc.s  6
  ... truncated ...
```
